# _HashU2fGetAssertionSignature

- ea: `0x1800d7718`
- end: `0x1800d7844`
- name: `_HashU2fGetAssertionSignature`
- size: `300`
- prototype: `__int64 __usercall@<rax>(ULONG cbInput@<ecx>, PUCHAR pbInput@<rdx>, ULONG, PUCHAR, PUCHAR pbOutput)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800d857c`

## callees

- `0x1800d7718`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800d7833`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800d7833`
- `bcrypt!BCryptDestroyHash` at `0x1800d7822`
- `bcrypt!BCryptDestroyHash` at `0x1800d7822`
- `bcrypt!BCryptFinishHash` at `0x1800d7811`
- `bcrypt!BCryptFinishHash` at `0x1800d7811`
- `bcrypt!BCryptHashData` at `0x1800d77a5`
- `bcrypt!BCryptHashData` at `0x1800d77c0`
- `bcrypt!BCryptHashData` at `0x1800d77db`
- `bcrypt!BCryptHashData` at `0x1800d77f6`
- `bcrypt!BCryptHashData` at `0x1800d77a5`
- `bcrypt!BCryptHashData` at `0x1800d77c0`
- `bcrypt!BCryptHashData` at `0x1800d77db`
- `bcrypt!BCryptHashData` at `0x1800d77f6`
- `bcrypt!BCryptCreateHash` at `0x1800d7788`
- `bcrypt!BCryptCreateHash` at `0x1800d7788`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800d7759`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800d7759`

## pseudocode

```c
__int64 __fastcall HashU2fGetAssertionSignature(
        ULONG cbInput,
        PUCHAR pbInput,
        __int64 a3,
        unsigned int a4,
        ULONG cbInputa,
        PUCHAR a6,
        PUCHAR pbOutput)
{
  unsigned int v9; // ebx
  UCHAR pbInputa[8]; // [rsp+40h] [rbp-28h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-18h] BYREF
  unsigned __int32 v14; // [rsp+A0h] [rbp+38h] BYREF

  v14 = _byteswap_ulong(a4);
  pbInputa[0] = 0;
  phAlgorithm = 0;
  phHash = 0;
  v9 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 0);
  if ( !v9 )
  {
    v9 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
    if ( !v9 )
    {
      v9 = BCryptHashData(phHash, pbInput, cbInput, 0);
      if ( !v9 )
      {
        v9 = BCryptHashData(phHash, pbInputa, 1u, 0);
        if ( !v9 )
        {
          v9 = BCryptHashData(phHash, (PUCHAR)&v14, 4u, 0);
          if ( !v9 )
          {
            v9 = BCryptHashData(phHash, a6, cbInputa, 0);
            if ( !v9 )
              v9 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
          }
        }
      }
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v9;
}

```

## disassembly

```asm
0x1800d7718  mov     byte ptr [rsp-20h+arg_10], r8b
0x1800d771d  push    rbp
0x1800d771e  push    rbx
0x1800d771f  push    rsi
0x1800d7720  push    rdi
0x1800d7721  mov     rbp, rsp
0x1800d7724  sub     rsp, 68h
0x1800d7728  bswap   r9d
0x1800d772b  mov     [rbp+arg_10], r9d
0x1800d772f  mov     rdi, rdx
0x1800d7732  mov     esi, ecx
0x1800d7734  mov     [rbp+pbInput], 0
0x1800d7738  xor     r9d, r9d; dwFlags
0x1800d773b  mov     [rbp+phAlgorithm], 0
0x1800d7743  xor     r8d, r8d; pszImplementation
0x1800d7746  mov     [rbp+phHash], 0
0x1800d774e  lea     rdx, pwszCNGHashAlgid; "SHA256"
0x1800d7755  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x1800d7759  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800d775f  mov     ebx, eax
0x1800d7761  test    eax, eax
0x1800d7763  jnz     loc_1800D7819
0x1800d7769  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800d776d  lea     rdx, [rbp+phHash]; phHash
0x1800d7771  mov     [rsp+68h+dwFlags], eax; dwFlags
0x1800d7775  xor     r9d, r9d; cbHashObject
0x1800d7778  mov     [rsp+68h+cbSecret], eax; cbSecret
0x1800d777c  xor     r8d, r8d; pbHashObject
0x1800d777f  mov     [rsp+68h+pbSecret], 0; pbSecret
0x1800d7788  call    cs:__imp_BCryptCreateHash
0x1800d778e  mov     ebx, eax
0x1800d7790  test    eax, eax
0x1800d7792  jnz     loc_1800D7819
0x1800d7798  mov     rcx, [rbp+phHash]; hHash
0x1800d779c  xor     r9d, r9d; dwFlags
0x1800d779f  mov     r8d, esi; cbInput
0x1800d77a2  mov     rdx, rdi; pbInput
0x1800d77a5  call    cs:__imp_BCryptHashData
0x1800d77ab  mov     ebx, eax
0x1800d77ad  test    eax, eax
0x1800d77af  jnz     short loc_1800D7819
0x1800d77b1  mov     rcx, [rbp+phHash]; hHash
0x1800d77b5  lea     r8d, [rax+1]; cbInput
0x1800d77b9  xor     r9d, r9d; dwFlags
0x1800d77bc  lea     rdx, [rbp+pbInput]; pbInput
0x1800d77c0  call    cs:__imp_BCryptHashData
0x1800d77c6  mov     ebx, eax
0x1800d77c8  test    eax, eax
0x1800d77ca  jnz     short loc_1800D7819
0x1800d77cc  mov     rcx, [rbp+phHash]; hHash
0x1800d77d0  lea     r8d, [rax+4]; cbInput
0x1800d77d4  xor     r9d, r9d; dwFlags
0x1800d77d7  lea     rdx, [rbp+arg_10]; pbInput
0x1800d77db  call    cs:__imp_BCryptHashData
0x1800d77e1  mov     ebx, eax
0x1800d77e3  test    eax, eax
0x1800d77e5  jnz     short loc_1800D7819
0x1800d77e7  mov     r8d, [rbp+cbInput]; cbInput
0x1800d77eb  xor     r9d, r9d; dwFlags
0x1800d77ee  mov     rdx, [rbp+arg_28]; pbInput
0x1800d77f2  mov     rcx, [rbp+phHash]; hHash
0x1800d77f6  call    cs:__imp_BCryptHashData
0x1800d77fc  mov     ebx, eax
0x1800d77fe  test    eax, eax
0x1800d7800  jnz     short loc_1800D7819
0x1800d7802  mov     rdx, [rbp+pbOutput]; pbOutput
0x1800d7806  lea     r8d, [rax+20h]; cbOutput
0x1800d780a  mov     rcx, [rbp+phHash]; hHash
0x1800d780e  xor     r9d, r9d; dwFlags
0x1800d7811  call    cs:__imp_BCryptFinishHash
0x1800d7817  mov     ebx, eax
0x1800d7819  mov     rcx, [rbp+phHash]; hHash
0x1800d781d  test    rcx, rcx
0x1800d7820  jz      short loc_1800D7828
0x1800d7822  call    cs:__imp_BCryptDestroyHash
0x1800d7828  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800d782c  test    rcx, rcx
0x1800d782f  jz      short loc_1800D7839
0x1800d7831  xor     edx, edx; dwFlags
0x1800d7833  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800d7839  mov     eax, ebx
0x1800d783b  add     rsp, 68h
0x1800d783f  pop     rdi
0x1800d7840  pop     rsi
0x1800d7841  pop     rbx
0x1800d7842  pop     rbp
0x1800d7843  retn
```
