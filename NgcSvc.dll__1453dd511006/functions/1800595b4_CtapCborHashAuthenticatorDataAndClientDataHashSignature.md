# CtapCborHashAuthenticatorDataAndClientDataHashSignature

- ea: `0x1800595b4`
- end: `0x1800596e5`
- name: `CtapCborHashAuthenticatorDataAndClientDataHashSignature`
- size: `305`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180059404`

## callees

- `0x1800595b4`
- `0x1800a94f8`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800596ce`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800596ce`
- `bcrypt!BCryptDestroyHash` at `0x1800596bc`
- `bcrypt!BCryptDestroyHash` at `0x1800596bc`
- `bcrypt!BCryptFinishHash` at `0x1800596aa`
- `bcrypt!BCryptFinishHash` at `0x1800596aa`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18005961b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18005961b`
- `bcrypt!BCryptHashData` at `0x180059671`
- `bcrypt!BCryptHashData` at `0x180059690`
- `bcrypt!BCryptHashData` at `0x180059671`
- `bcrypt!BCryptHashData` at `0x180059690`
- `bcrypt!BCryptCreateHash` at `0x180059657`
- `bcrypt!BCryptCreateHash` at `0x180059657`

## pseudocode

```c
__int64 __fastcall CtapCborHashAuthenticatorDataAndClientDataHashSignature(
        __int64 a1,
        __int64 a2,
        ULONG a3,
        UCHAR *a4,
        ULONG cbInput,
        UCHAR *pbInput,
        UCHAR *pbOutput)
{
  BCRYPT_ALG_HANDLE v7; // rbx
  ULONG v8; // edi
  unsigned int v12; // ebx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-48h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-40h] BYREF

  v7 = *(BCRYPT_ALG_HANDLE *)(a2 + 24);
  v8 = 64;
  if ( *(_DWORD *)(a2 + 48) < 0x40u )
    v8 = *(_DWORD *)(a2 + 48);
  phAlgorithm = 0;
  phHash = 0;
  if ( !v7 || !(unsigned int)CtapCborIsPseudoHandleSupported() )
  {
    v12 = BCryptOpenAlgorithmProvider(&phAlgorithm, *(LPCWSTR *)(a2 + 16), 0, 0);
    if ( v12 )
      goto LABEL_11;
    v7 = phAlgorithm;
  }
  v12 = BCryptCreateHash(v7, &phHash, 0, 0, 0, 0, 0);
  if ( !v12 )
  {
    v12 = BCryptHashData(phHash, a4, a3, 0);
    if ( !v12 )
    {
      v12 = BCryptHashData(phHash, pbInput, cbInput, 0);
      if ( !v12 )
        v12 = BCryptFinishHash(phHash, pbOutput, v8, 0);
    }
  }
LABEL_11:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v12;
}

```

## disassembly

```asm
0x1800595b4  push    rbx
0x1800595b6  push    rbp
0x1800595b7  push    rsi
0x1800595b8  push    rdi
0x1800595b9  push    r12
0x1800595bb  push    r14
0x1800595bd  push    r15
0x1800595bf  sub     rsp, 50h
0x1800595c3  mov     rbx, [rdx+18h]
0x1800595c7  mov     edi, 40h ; '@'
0x1800595cc  cmp     [rdx+30h], edi
0x1800595cf  mov     r12, r9
0x1800595d2  mov     rbp, [rsp+88h+pbInput]
0x1800595da  mov     r15d, r8d
0x1800595dd  cmovb   edi, [rdx+30h]
0x1800595e1  mov     rsi, rdx
0x1800595e4  mov     r14, [rsp+88h+pbOutput]
0x1800595ec  mov     [rsp+88h+phAlgorithm], 0
0x1800595f5  mov     [rsp+88h+phHash], 0
0x1800595fe  test    rbx, rbx
0x180059601  jz      short loc_18005960C
0x180059603  call    CtapCborIsPseudoHandleSupported
0x180059608  test    eax, eax
0x18005960a  jnz     short loc_180059630
0x18005960c  mov     rdx, [rsi+10h]; pszAlgId
0x180059610  lea     rcx, [rsp+88h+phAlgorithm]; phAlgorithm
0x180059615  xor     r9d, r9d; dwFlags
0x180059618  xor     r8d, r8d; pszImplementation
0x18005961b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180059621  mov     ebx, eax
0x180059623  test    eax, eax
0x180059625  jnz     loc_1800596B2
0x18005962b  mov     rbx, [rsp+88h+phAlgorithm]
0x180059630  mov     [rsp+88h+dwFlags], 0; dwFlags
0x180059638  lea     rdx, [rsp+88h+phHash]; phHash
0x18005963d  mov     [rsp+88h+cbSecret], 0; cbSecret
0x180059645  xor     r9d, r9d; cbHashObject
0x180059648  xor     r8d, r8d; pbHashObject
0x18005964b  mov     [rsp+88h+pbSecret], 0; pbSecret
0x180059654  mov     rcx, rbx; hAlgorithm
0x180059657  call    cs:__imp_BCryptCreateHash
0x18005965d  mov     ebx, eax
0x18005965f  test    eax, eax
0x180059661  jnz     short loc_1800596B2
0x180059663  mov     rcx, [rsp+88h+phHash]; hHash
0x180059668  xor     r9d, r9d; dwFlags
0x18005966b  mov     r8d, r15d; cbInput
0x18005966e  mov     rdx, r12; pbInput
0x180059671  call    cs:__imp_BCryptHashData
0x180059677  mov     ebx, eax
0x180059679  test    eax, eax
0x18005967b  jnz     short loc_1800596B2
0x18005967d  mov     r8d, [rsp+88h+cbInput]; cbInput
0x180059685  xor     r9d, r9d; dwFlags
0x180059688  mov     rcx, [rsp+88h+phHash]; hHash
0x18005968d  mov     rdx, rbp; pbInput
0x180059690  call    cs:__imp_BCryptHashData
0x180059696  mov     ebx, eax
0x180059698  test    eax, eax
0x18005969a  jnz     short loc_1800596B2
0x18005969c  mov     rcx, [rsp+88h+phHash]; hHash
0x1800596a1  xor     r9d, r9d; dwFlags
0x1800596a4  mov     r8d, edi; cbOutput
0x1800596a7  mov     rdx, r14; pbOutput
0x1800596aa  call    cs:__imp_BCryptFinishHash
0x1800596b0  mov     ebx, eax
0x1800596b2  mov     rcx, [rsp+88h+phHash]; hHash
0x1800596b7  test    rcx, rcx
0x1800596ba  jz      short loc_1800596C2
0x1800596bc  call    cs:__imp_BCryptDestroyHash
0x1800596c2  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x1800596c7  test    rcx, rcx
0x1800596ca  jz      short loc_1800596D4
0x1800596cc  xor     edx, edx; dwFlags
0x1800596ce  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800596d4  mov     eax, ebx
0x1800596d6  add     rsp, 50h
0x1800596da  pop     r15
0x1800596dc  pop     r14
0x1800596de  pop     r12
0x1800596e0  pop     rdi
0x1800596e1  pop     rsi
0x1800596e2  pop     rbp
0x1800596e3  pop     rbx
0x1800596e4  retn
```
