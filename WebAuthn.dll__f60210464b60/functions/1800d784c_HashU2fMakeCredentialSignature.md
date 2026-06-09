# _HashU2fMakeCredentialSignature

- ea: `0x1800d784c`
- end: `0x1800d7995`
- name: `_HashU2fMakeCredentialSignature`
- size: `329`
- prototype: `__int64 __fastcall(ULONG cbInput, PUCHAR pbInput, ULONG, PUCHAR, ULONG, PUCHAR, ULONG, PUCHAR, PUCHAR pbOutput)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800d862c`

## callees

- `0x1800d784c`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800d7980`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800d7980`
- `bcrypt!BCryptDestroyHash` at `0x1800d796f`
- `bcrypt!BCryptDestroyHash` at `0x1800d796f`
- `bcrypt!BCryptFinishHash` at `0x1800d795e`
- `bcrypt!BCryptFinishHash` at `0x1800d795e`
- `bcrypt!BCryptHashData` at `0x1800d78db`
- `bcrypt!BCryptHashData` at `0x1800d78f4`
- `bcrypt!BCryptHashData` at `0x1800d790d`
- `bcrypt!BCryptHashData` at `0x1800d7928`
- `bcrypt!BCryptHashData` at `0x1800d7943`
- `bcrypt!BCryptHashData` at `0x1800d78db`
- `bcrypt!BCryptHashData` at `0x1800d78f4`
- `bcrypt!BCryptHashData` at `0x1800d790d`
- `bcrypt!BCryptHashData` at `0x1800d7928`
- `bcrypt!BCryptHashData` at `0x1800d7943`
- `bcrypt!BCryptCreateHash` at `0x1800d78bc`
- `bcrypt!BCryptCreateHash` at `0x1800d78bc`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800d788d`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800d788d`

## pseudocode

```c
__int64 __fastcall HashU2fMakeCredentialSignature(
        ULONG cbInput,
        PUCHAR pbInput,
        ULONG a3,
        PUCHAR a4,
        ULONG cbInputa,
        PUCHAR a6,
        ULONG a7,
        PUCHAR a8,
        PUCHAR pbOutput)
{
  unsigned int v13; // ebx
  UCHAR pbInputa[8]; // [rsp+40h] [rbp-28h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-18h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  pbInputa[0] = 0;
  v13 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( !v13 )
  {
    v13 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
    if ( !v13 )
    {
      v13 = BCryptHashData(phHash, pbInputa, 1u, 0);
      if ( !v13 )
      {
        v13 = BCryptHashData(phHash, pbInput, cbInput, 0);
        if ( !v13 )
        {
          v13 = BCryptHashData(phHash, a4, a3, 0);
          if ( !v13 )
          {
            v13 = BCryptHashData(phHash, a6, cbInputa, 0);
            if ( !v13 )
            {
              v13 = BCryptHashData(phHash, a8, a7, 0);
              if ( !v13 )
                v13 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
            }
          }
        }
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v13;
}

```

## disassembly

```asm
0x1800d784c  push    rbp
0x1800d784e  push    rbx
0x1800d784f  push    rsi
0x1800d7850  push    rdi
0x1800d7851  push    r14
0x1800d7853  push    r15
0x1800d7855  mov     rbp, rsp
0x1800d7858  sub     rsp, 68h
0x1800d785c  mov     rdi, r9
0x1800d785f  mov     [rbp+phAlgorithm], 0
0x1800d7867  mov     esi, r8d
0x1800d786a  mov     [rbp+phHash], 0
0x1800d7872  mov     r14, rdx
0x1800d7875  mov     [rbp+pbInput], 0
0x1800d7879  mov     r15d, ecx
0x1800d787c  lea     rdx, pwszCNGHashAlgid; "SHA256"
0x1800d7883  xor     r9d, r9d; dwFlags
0x1800d7886  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800d788a  xor     r8d, r8d; pszImplementation
0x1800d788d  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800d7893  mov     ebx, eax
0x1800d7895  test    eax, eax
0x1800d7897  jnz     loc_1800D7966
0x1800d789d  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800d78a1  lea     rdx, [rbp+phHash]; phHash
0x1800d78a5  mov     [rsp+68h+dwFlags], eax; dwFlags
0x1800d78a9  xor     r9d, r9d; cbHashObject
0x1800d78ac  mov     [rsp+68h+cbSecret], eax; cbSecret
0x1800d78b0  xor     r8d, r8d; pbHashObject
0x1800d78b3  mov     [rsp+68h+pbSecret], 0; pbSecret
0x1800d78bc  call    cs:__imp_BCryptCreateHash
0x1800d78c2  mov     ebx, eax
0x1800d78c4  test    eax, eax
0x1800d78c6  jnz     loc_1800D7966
0x1800d78cc  mov     rcx, [rbp+phHash]; hHash
0x1800d78d0  lea     r8d, [rax+1]; cbInput
0x1800d78d4  xor     r9d, r9d; dwFlags
0x1800d78d7  lea     rdx, [rbp+pbInput]; pbInput
0x1800d78db  call    cs:__imp_BCryptHashData
0x1800d78e1  mov     ebx, eax
0x1800d78e3  test    eax, eax
0x1800d78e5  jnz     short loc_1800D7966
0x1800d78e7  mov     rcx, [rbp+phHash]; hHash
0x1800d78eb  xor     r9d, r9d; dwFlags
0x1800d78ee  mov     r8d, r15d; cbInput
0x1800d78f1  mov     rdx, r14; pbInput
0x1800d78f4  call    cs:__imp_BCryptHashData
0x1800d78fa  mov     ebx, eax
0x1800d78fc  test    eax, eax
0x1800d78fe  jnz     short loc_1800D7966
0x1800d7900  mov     rcx, [rbp+phHash]; hHash
0x1800d7904  xor     r9d, r9d; dwFlags
0x1800d7907  mov     r8d, esi; cbInput
0x1800d790a  mov     rdx, rdi; pbInput
0x1800d790d  call    cs:__imp_BCryptHashData
0x1800d7913  mov     ebx, eax
0x1800d7915  test    eax, eax
0x1800d7917  jnz     short loc_1800D7966
0x1800d7919  mov     r8d, [rbp+cbInput]; cbInput
0x1800d791d  xor     r9d, r9d; dwFlags
0x1800d7920  mov     rdx, [rbp+arg_28]; pbInput
0x1800d7924  mov     rcx, [rbp+phHash]; hHash
0x1800d7928  call    cs:__imp_BCryptHashData
0x1800d792e  mov     ebx, eax
0x1800d7930  test    eax, eax
0x1800d7932  jnz     short loc_1800D7966
0x1800d7934  mov     r8d, [rbp+arg_30]; cbInput
0x1800d7938  xor     r9d, r9d; dwFlags
0x1800d793b  mov     rdx, [rbp+arg_38]; pbInput
0x1800d793f  mov     rcx, [rbp+phHash]; hHash
0x1800d7943  call    cs:__imp_BCryptHashData
0x1800d7949  mov     ebx, eax
0x1800d794b  test    eax, eax
0x1800d794d  jnz     short loc_1800D7966
0x1800d794f  mov     rdx, [rbp+pbOutput]; pbOutput
0x1800d7953  lea     r8d, [rax+20h]; cbOutput
0x1800d7957  mov     rcx, [rbp+phHash]; hHash
0x1800d795b  xor     r9d, r9d; dwFlags
0x1800d795e  call    cs:__imp_BCryptFinishHash
0x1800d7964  mov     ebx, eax
0x1800d7966  mov     rcx, [rbp+phHash]; hHash
0x1800d796a  test    rcx, rcx
0x1800d796d  jz      short loc_1800D7975
0x1800d796f  call    cs:__imp_BCryptDestroyHash
0x1800d7975  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800d7979  test    rcx, rcx
0x1800d797c  jz      short loc_1800D7986
0x1800d797e  xor     edx, edx; dwFlags
0x1800d7980  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800d7986  mov     eax, ebx
0x1800d7988  add     rsp, 68h
0x1800d798c  pop     r15
0x1800d798e  pop     r14
0x1800d7990  pop     rdi
0x1800d7991  pop     rsi
0x1800d7992  pop     rbx
0x1800d7993  pop     rbp
0x1800d7994  retn
```
