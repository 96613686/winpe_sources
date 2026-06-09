# CtapCborClientPinHMACToken

- ea: `0x1800c93e8`
- end: `0x1800c94c1`
- name: `CtapCborClientPinHMACToken`
- size: `217`
- prototype: `__int64 __fastcall(ULONG cbSecret, PUCHAR pbSecret, ULONG cbInput, PUCHAR pbInput, PUCHAR pbOutput)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800cafd4`
- `0x1800cb534`
- `0x1800e0144`

## callees

- `0x1800c93e8`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c94ae`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c94ae`
- `bcrypt!BCryptDestroyHash` at `0x1800c949c`
- `bcrypt!BCryptDestroyHash` at `0x1800c949c`
- `bcrypt!BCryptFinishHash` at `0x1800c948a`
- `bcrypt!BCryptFinishHash` at `0x1800c948a`
- `bcrypt!BCryptHashData` at `0x1800c946a`
- `bcrypt!BCryptHashData` at `0x1800c946a`
- `bcrypt!BCryptCreateHash` at `0x1800c9450`
- `bcrypt!BCryptCreateHash` at `0x1800c9450`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c9426`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c9426`

## pseudocode

```c
__int64 __fastcall CtapCborClientPinHMACToken(
        ULONG cbSecret,
        PUCHAR pbSecret,
        ULONG cbInput,
        PUCHAR pbInput,
        PUCHAR pbOutput)
{
  unsigned int v9; // ebx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-38h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-30h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  v9 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 8u);
  if ( !v9 )
  {
    v9 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, pbSecret, cbSecret, 0);
    if ( !v9 )
    {
      v9 = BCryptHashData(phHash, pbInput, cbInput, 0);
      if ( !v9 )
        v9 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
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
0x1800c93e8  push    rbx
0x1800c93ea  push    rbp
0x1800c93eb  push    rsi
0x1800c93ec  push    rdi
0x1800c93ed  push    r14
0x1800c93ef  sub     rsp, 50h
0x1800c93f3  mov     rdi, r9
0x1800c93f6  mov     [rsp+78h+phAlgorithm], 0
0x1800c93ff  mov     esi, r8d
0x1800c9402  mov     [rsp+78h+phHash], 0
0x1800c940b  mov     rbp, rdx
0x1800c940e  mov     r14d, ecx
0x1800c9411  mov     r9d, 8; dwFlags
0x1800c9417  lea     rdx, pwszCNGHashAlgid; "SHA256"
0x1800c941e  xor     r8d, r8d; pszImplementation
0x1800c9421  lea     rcx, [rsp+78h+phAlgorithm]; phAlgorithm
0x1800c9426  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c942c  mov     ebx, eax
0x1800c942e  test    eax, eax
0x1800c9430  jnz     short loc_1800C9492
0x1800c9432  mov     rcx, [rsp+78h+phAlgorithm]; hAlgorithm
0x1800c9437  lea     rdx, [rsp+78h+phHash]; phHash
0x1800c943c  mov     [rsp+78h+dwFlags], eax; dwFlags
0x1800c9440  xor     r9d, r9d; cbHashObject
0x1800c9443  mov     [rsp+78h+cbSecret], r14d; cbSecret
0x1800c9448  xor     r8d, r8d; pbHashObject
0x1800c944b  mov     [rsp+78h+pbSecret], rbp; pbSecret
0x1800c9450  call    cs:__imp_BCryptCreateHash
0x1800c9456  mov     ebx, eax
0x1800c9458  test    eax, eax
0x1800c945a  jnz     short loc_1800C9492
0x1800c945c  mov     rcx, [rsp+78h+phHash]; hHash
0x1800c9461  xor     r9d, r9d; dwFlags
0x1800c9464  mov     r8d, esi; cbInput
0x1800c9467  mov     rdx, rdi; pbInput
0x1800c946a  call    cs:__imp_BCryptHashData
0x1800c9470  mov     ebx, eax
0x1800c9472  test    eax, eax
0x1800c9474  jnz     short loc_1800C9492
0x1800c9476  mov     rdx, [rsp+78h+pbOutput]; pbOutput
0x1800c947e  lea     r8d, [rax+20h]; cbOutput
0x1800c9482  mov     rcx, [rsp+78h+phHash]; hHash
0x1800c9487  xor     r9d, r9d; dwFlags
0x1800c948a  call    cs:__imp_BCryptFinishHash
0x1800c9490  mov     ebx, eax
0x1800c9492  mov     rcx, [rsp+78h+phHash]; hHash
0x1800c9497  test    rcx, rcx
0x1800c949a  jz      short loc_1800C94A2
0x1800c949c  call    cs:__imp_BCryptDestroyHash
0x1800c94a2  mov     rcx, [rsp+78h+phAlgorithm]; hAlgorithm
0x1800c94a7  test    rcx, rcx
0x1800c94aa  jz      short loc_1800C94B4
0x1800c94ac  xor     edx, edx; dwFlags
0x1800c94ae  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800c94b4  mov     eax, ebx
0x1800c94b6  add     rsp, 50h
0x1800c94ba  pop     r14
0x1800c94bc  pop     rdi
0x1800c94bd  pop     rsi
0x1800c94be  pop     rbp
0x1800c94bf  pop     rbx
0x1800c94c0  retn
```
