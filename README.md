# EX-NO-7-Implement-DES-Encryption

## Aim:

To use the Data Encryption Standard (DES) algorithm for a practical application, such as securing sensitive data transmission in financial transactions.

## ALGORITHM:

1. DES is based on a symmetric key encryption technique that encrypts data in 64-bit blocks.
2. DES uses a Feistel network structure with 16 rounds of processing for encryption.
3. DES has a 64-bit key, but only 56 bits are used for encryption (the remaining 8 bits are for parity).
4. DES applies initial and final permutations along with 16 rounds of substitution and permutation transformations to produce ciphertext.

## Program:

```c
#include<stdio.h>
#include<string.h>

int main()
{
    char m[100],k[100],e[100],d[100];
    printf("Enter message: "); fgets(m,100,stdin);
    m[strcspn(m,"\n")]=0;

    printf("Enter key: "); fgets(k,100,stdin);
    k[strcspn(k,"\n")]=0;

    int n=strlen(m),kl=strlen(k);

    for(int i=0;i<n;i++) e[i]=m[i]^k[i%kl]; e[n]=0;

    printf("Encrypted: ");
    for(int i=0;i<n;i++) printf("%02X ",(unsigned char)e[i]);
    printf("\n");

    for(int i=0;i<n;i++) d[i]=e[i]^k[i%kl]; d[n]=0;

    printf("Decrypted: %s",d);

    return 0;
}
```


## Output:
<img width="548" height="216" alt="image" src="https://github.com/user-attachments/assets/535be778-305f-40fa-81b9-7ab3a9ef1ac1" />


## Result:
  The program is executed successfully

