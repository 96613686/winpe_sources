# CtapCborHashAuthenticatorDataAndClientDataHashSignature

- ea: `0x18001d8f4`
- end: `0x18001da25`
- name: `CtapCborHashAuthenticatorDataAndClientDataHashSignature`
- size: `305`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d6d8`
- `0x18001f2c4`
- `0x18002a584`
- `0x1800cb9f4`

## callees

- `0x18001d8f4`
- `0x1800c7c2c`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001da0e`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18001da0e`
- `bcrypt!BCryptDestroyHash` at `0x18001d9fc`
- `bcrypt!BCryptDestroyHash` at `0x18001d9fc`
- `bcrypt!BCryptFinishHash` at `0x18001d9ea`
- `bcrypt!BCryptFinishHash` at `0x18001d9ea`
- `bcrypt!BCryptHashData` at `0x18001d9b1`
- `bcrypt!BCryptHashData` at `0x18001d9d0`
- `bcrypt!BCryptHashData` at `0x18001d9b1`
- `bcrypt!BCryptHashData` at `0x18001d9d0`
- `bcrypt!BCryptCreateHash` at `0x18001d997`
- `bcrypt!BCryptCreateHash` at `0x18001d997`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001d95b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18001d95b`

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
0x18001d8f4  push    rbx
0x18001d8f6  push    rbp
0x18001d8f7  push    rsi
0x18001d8f8  push    rdi
0x18001d8f9  push    r12
0x18001d8fb  push    r14
0x18001d8fd  push    r15
0x18001d8ff  sub     rsp, 50h
0x18001d903  mov     rbx, [rdx+18h]
0x18001d907  mov     edi, 40h ; '@'
0x18001d90c  cmp     [rdx+30h], edi
0x18001d90f  mov     r12, r9
0x18001d912  mov     rbp, [rsp+88h+pbInput]
0x18001d91a  mov     r15d, r8d
0x18001d91d  cmovb   edi, [rdx+30h]
0x18001d921  mov     rsi, rdx
0x18001d924  mov     r14, [rsp+88h+pbOutput]
0x18001d92c  mov     [rsp+88h+phAlgorithm], 0
0x18001d935  mov     [rsp+88h+phHash], 0
0x18001d93e  test    rbx, rbx
0x18001d941  jz      short loc_18001D94C
0x18001d943  call    CtapCborIsPseudoHandleSupported
0x18001d948  test    eax, eax
0x18001d94a  jnz     short loc_18001D970
0x18001d94c  mov     rdx, [rsi+10h]; pszAlgId
0x18001d950  lea     rcx, [rsp+88h+phAlgorithm]; phAlgorithm
0x18001d955  xor     r9d, r9d; dwFlags
0x18001d958  xor     r8d, r8d; pszImplementation
0x18001d95b  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18001d961  mov     ebx, eax
0x18001d963  test    eax, eax
0x18001d965  jnz     loc_18001D9F2
0x18001d96b  mov     rbx, [rsp+88h+phAlgorithm]
0x18001d970  mov     [rsp+88h+dwFlags], 0; dwFlags
0x18001d978  lea     rdx, [rsp+88h+phHash]; phHash
0x18001d97d  mov     [rsp+88h+cbSecret], 0; cbSecret
0x18001d985  xor     r9d, r9d; cbHashObject
0x18001d988  xor     r8d, r8d; pbHashObject
0x18001d98b  mov     [rsp+88h+pbSecret], 0; pbSecret
0x18001d994  mov     rcx, rbx; hAlgorithm
0x18001d997  call    cs:__imp_BCryptCreateHash
0x18001d99d  mov     ebx, eax
0x18001d99f  test    eax, eax
0x18001d9a1  jnz     short loc_18001D9F2
0x18001d9a3  mov     rcx, [rsp+88h+phHash]; hHash
0x18001d9a8  xor     r9d, r9d; dwFlags
0x18001d9ab  mov     r8d, r15d; cbInput
0x18001d9ae  mov     rdx, r12; pbInput
0x18001d9b1  call    cs:__imp_BCryptHashData
0x18001d9b7  mov     ebx, eax
0x18001d9b9  test    eax, eax
0x18001d9bb  jnz     short loc_18001D9F2
0x18001d9bd  mov     r8d, [rsp+88h+cbInput]; cbInput
0x18001d9c5  xor     r9d, r9d; dwFlags
0x18001d9c8  mov     rcx, [rsp+88h+phHash]; hHash
0x18001d9cd  mov     rdx, rbp; pbInput
0x18001d9d0  call    cs:__imp_BCryptHashData
0x18001d9d6  mov     ebx, eax
0x18001d9d8  test    eax, eax
0x18001d9da  jnz     short loc_18001D9F2
0x18001d9dc  mov     rcx, [rsp+88h+phHash]; hHash
0x18001d9e1  xor     r9d, r9d; dwFlags
0x18001d9e4  mov     r8d, edi; cbOutput
0x18001d9e7  mov     rdx, r14; pbOutput
0x18001d9ea  call    cs:__imp_BCryptFinishHash
0x18001d9f0  mov     ebx, eax
0x18001d9f2  mov     rcx, [rsp+88h+phHash]; hHash
0x18001d9f7  test    rcx, rcx
0x18001d9fa  jz      short loc_18001DA02
0x18001d9fc  call    cs:__imp_BCryptDestroyHash
0x18001da02  mov     rcx, [rsp+88h+phAlgorithm]; hAlgorithm
0x18001da07  test    rcx, rcx
0x18001da0a  jz      short loc_18001DA14
0x18001da0c  xor     edx, edx; dwFlags
0x18001da0e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18001da14  mov     eax, ebx
0x18001da16  add     rsp, 50h
0x18001da1a  pop     r15
0x18001da1c  pop     r14
0x18001da1e  pop     r12
0x18001da20  pop     rdi
0x18001da21  pop     rsi
0x18001da22  pop     rbp
0x18001da23  pop     rbx
0x18001da24  retn
```
