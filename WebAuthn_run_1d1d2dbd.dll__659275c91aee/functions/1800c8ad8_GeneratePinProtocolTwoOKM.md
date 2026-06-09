# _GeneratePinProtocolTwoOKM

- ea: `0x1800c8ad8`
- end: `0x1800c8be3`
- name: `_GeneratePinProtocolTwoOKM`
- size: `267`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, PUCHAR pbInput, PUCHAR pbOutput)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800c89d4`

## callees

- `0x1800c8ad8`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c8bc8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c8bc8`
- `bcrypt!BCryptDestroyHash` at `0x1800c8bb7`
- `bcrypt!BCryptDestroyHash` at `0x1800c8bb7`
- `bcrypt!BCryptFinishHash` at `0x1800c8ba6`
- `bcrypt!BCryptFinishHash` at `0x1800c8ba6`
- `bcrypt!BCryptHashData` at `0x1800c8b71`
- `bcrypt!BCryptHashData` at `0x1800c8b8c`
- `bcrypt!BCryptHashData` at `0x1800c8b71`
- `bcrypt!BCryptHashData` at `0x1800c8b8c`
- `bcrypt!BCryptCreateHash` at `0x1800c8b4d`
- `bcrypt!BCryptCreateHash` at `0x1800c8b4d`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c8b1e`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c8b1e`

## pseudocode

```c
__int64 __fastcall GeneratePinProtocolTwoOKM(PUCHAR pbSecret, PUCHAR pbInput, PUCHAR pbOutput)
{
  unsigned int v6; // ebx
  __int64 v7; // r8
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-10h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-8h] BYREF
  UCHAR pbInputa; // [rsp+88h] [rbp+38h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  pbInputa = 1;
  v6 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 8u);
  if ( !v6 )
  {
    v6 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, pbSecret, 0x20u, 0);
    if ( !v6 )
    {
      v7 = -1;
      do
        ++v7;
      while ( pbInput[v7] );
      v6 = BCryptHashData(phHash, pbInput, v7, 0);
      if ( !v6 )
      {
        v6 = BCryptHashData(phHash, &pbInputa, 1u, 0);
        if ( !v6 )
          v6 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v6;
}

```

## disassembly

```asm
0x1800c8ad8  mov     [rsp-18h+arg_0], rbx
0x1800c8add  mov     [rsp-18h+arg_8], rsi
0x1800c8ae2  push    rbp
0x1800c8ae3  push    rdi
0x1800c8ae4  push    r14
0x1800c8ae6  mov     rbp, rsp
0x1800c8ae9  sub     rsp, 50h
0x1800c8aed  mov     r14, r8
0x1800c8af0  mov     [rbp+phAlgorithm], 0
0x1800c8af8  mov     rdi, rdx
0x1800c8afb  mov     [rbp+phHash], 0
0x1800c8b03  mov     rsi, rcx
0x1800c8b06  mov     [rbp+pbInput], 1
0x1800c8b0a  xor     r8d, r8d; pszImplementation
0x1800c8b0d  lea     rdx, pwszCNGHashAlgid; "SHA256"
0x1800c8b14  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800c8b18  mov     r9d, 8; dwFlags
0x1800c8b1e  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c8b24  mov     ebx, eax
0x1800c8b26  test    eax, eax
0x1800c8b28  jnz     loc_1800C8BAE
0x1800c8b2e  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800c8b32  lea     rdx, [rbp+phHash]; phHash
0x1800c8b36  mov     [rsp+50h+dwFlags], eax; dwFlags
0x1800c8b3a  xor     r9d, r9d; cbHashObject
0x1800c8b3d  mov     [rsp+50h+cbSecret], 20h ; ' '; cbSecret
0x1800c8b45  xor     r8d, r8d; pbHashObject
0x1800c8b48  mov     [rsp+50h+pbSecret], rsi; pbSecret
0x1800c8b4d  call    cs:__imp_BCryptCreateHash
0x1800c8b53  mov     ebx, eax
0x1800c8b55  test    eax, eax
0x1800c8b57  jnz     short loc_1800C8BAE
0x1800c8b59  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800c8b5d  inc     r8; cbInput
0x1800c8b60  cmp     byte ptr [rdi+r8], 0
0x1800c8b65  jnz     short loc_1800C8B5D
0x1800c8b67  mov     rcx, [rbp+phHash]; hHash
0x1800c8b6b  xor     r9d, r9d; dwFlags
0x1800c8b6e  mov     rdx, rdi; pbInput
0x1800c8b71  call    cs:__imp_BCryptHashData
0x1800c8b77  mov     ebx, eax
0x1800c8b79  test    eax, eax
0x1800c8b7b  jnz     short loc_1800C8BAE
0x1800c8b7d  mov     rcx, [rbp+phHash]; hHash
0x1800c8b81  lea     r8d, [rax+1]; cbInput
0x1800c8b85  xor     r9d, r9d; dwFlags
0x1800c8b88  lea     rdx, [rbp+pbInput]; pbInput
0x1800c8b8c  call    cs:__imp_BCryptHashData
0x1800c8b92  mov     ebx, eax
0x1800c8b94  test    eax, eax
0x1800c8b96  jnz     short loc_1800C8BAE
0x1800c8b98  mov     rcx, [rbp+phHash]; hHash
0x1800c8b9c  lea     r8d, [rax+20h]; cbOutput
0x1800c8ba0  xor     r9d, r9d; dwFlags
0x1800c8ba3  mov     rdx, r14; pbOutput
0x1800c8ba6  call    cs:__imp_BCryptFinishHash
0x1800c8bac  mov     ebx, eax
0x1800c8bae  mov     rcx, [rbp+phHash]; hHash
0x1800c8bb2  test    rcx, rcx
0x1800c8bb5  jz      short loc_1800C8BBD
0x1800c8bb7  call    cs:__imp_BCryptDestroyHash
0x1800c8bbd  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800c8bc1  test    rcx, rcx
0x1800c8bc4  jz      short loc_1800C8BCE
0x1800c8bc6  xor     edx, edx; dwFlags
0x1800c8bc8  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800c8bce  mov     rsi, [rsp+50h+arg_8]
0x1800c8bd3  mov     eax, ebx
0x1800c8bd5  mov     rbx, [rsp+50h+arg_0]
0x1800c8bda  add     rsp, 50h
0x1800c8bde  pop     r14
0x1800c8be0  pop     rdi
0x1800c8be1  pop     rbp
0x1800c8be2  retn
```
