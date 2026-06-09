# CtapCborClientPinHMACPin

- ea: `0x1800c92dc`
- end: `0x1800c93df`
- name: `CtapCborClientPinHMACPin`
- size: `259`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbInput, PUCHAR pbInput, ULONG, PUCHAR, PUCHAR pbOutput)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800c9e98`
- `0x1800caac4`

## callees

- `0x1800c92dc`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c93cc`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800c93cc`
- `bcrypt!BCryptDestroyHash` at `0x1800c93ba`
- `bcrypt!BCryptDestroyHash` at `0x1800c93ba`
- `bcrypt!BCryptFinishHash` at `0x1800c93a8`
- `bcrypt!BCryptFinishHash` at `0x1800c93a8`
- `bcrypt!BCryptHashData` at `0x1800c9365`
- `bcrypt!BCryptHashData` at `0x1800c9388`
- `bcrypt!BCryptHashData` at `0x1800c9365`
- `bcrypt!BCryptHashData` at `0x1800c9388`
- `bcrypt!BCryptCreateHash` at `0x1800c934b`
- `bcrypt!BCryptCreateHash` at `0x1800c934b`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c931a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800c931a`

## pseudocode

```c
__int64 __fastcall CtapCborClientPinHMACPin(
        PUCHAR pbSecret,
        ULONG cbInput,
        PUCHAR pbInput,
        ULONG a4,
        PUCHAR pbInputa,
        PUCHAR pbOutput)
{
  unsigned int v10; // ebx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-38h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-30h] BYREF

  phAlgorithm = 0;
  phHash = 0;
  v10 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 8u);
  if ( !v10 )
  {
    v10 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, pbSecret, 0x20u, 0);
    if ( !v10 )
    {
      v10 = BCryptHashData(phHash, pbInput, cbInput, 0);
      if ( !v10 && (!a4 || (v10 = BCryptHashData(phHash, pbInputa, a4, 0)) == 0) )
        v10 = BCryptFinishHash(phHash, pbOutput, 0x20u, 0);
    }
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return v10;
}

```

## disassembly

```asm
0x1800c92dc  push    rbx
0x1800c92de  push    rbp
0x1800c92df  push    rsi
0x1800c92e0  push    rdi
0x1800c92e1  push    r14
0x1800c92e3  sub     rsp, 50h
0x1800c92e7  mov     edi, r9d
0x1800c92ea  mov     [rsp+78h+phAlgorithm], 0
0x1800c92f3  mov     rbp, r8
0x1800c92f6  mov     [rsp+78h+phHash], 0
0x1800c92ff  mov     r14d, edx
0x1800c9302  mov     rsi, rcx
0x1800c9305  mov     r9d, 8; dwFlags
0x1800c930b  lea     rdx, pwszCNGHashAlgid; "SHA256"
0x1800c9312  xor     r8d, r8d; pszImplementation
0x1800c9315  lea     rcx, [rsp+78h+phAlgorithm]; phAlgorithm
0x1800c931a  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800c9320  mov     ebx, eax
0x1800c9322  test    eax, eax
0x1800c9324  jnz     loc_1800C93B0
0x1800c932a  mov     rcx, [rsp+78h+phAlgorithm]; hAlgorithm
0x1800c932f  lea     rdx, [rsp+78h+phHash]; phHash
0x1800c9334  mov     [rsp+78h+dwFlags], eax; dwFlags
0x1800c9338  xor     r9d, r9d; cbHashObject
0x1800c933b  mov     [rsp+78h+cbSecret], 20h ; ' '; cbSecret
0x1800c9343  xor     r8d, r8d; pbHashObject
0x1800c9346  mov     [rsp+78h+pbSecret], rsi; pbSecret
0x1800c934b  call    cs:__imp_BCryptCreateHash
0x1800c9351  mov     ebx, eax
0x1800c9353  test    eax, eax
0x1800c9355  jnz     short loc_1800C93B0
0x1800c9357  mov     rcx, [rsp+78h+phHash]; hHash
0x1800c935c  xor     r9d, r9d; dwFlags
0x1800c935f  mov     r8d, r14d; cbInput
0x1800c9362  mov     rdx, rbp; pbInput
0x1800c9365  call    cs:__imp_BCryptHashData
0x1800c936b  mov     ebx, eax
0x1800c936d  test    eax, eax
0x1800c936f  jnz     short loc_1800C93B0
0x1800c9371  test    edi, edi
0x1800c9373  jz      short loc_1800C9394
0x1800c9375  mov     rdx, [rsp+78h+pbInput]; pbInput
0x1800c937d  xor     r9d, r9d; dwFlags
0x1800c9380  mov     rcx, [rsp+78h+phHash]; hHash
0x1800c9385  mov     r8d, edi; cbInput
0x1800c9388  call    cs:__imp_BCryptHashData
0x1800c938e  mov     ebx, eax
0x1800c9390  test    eax, eax
0x1800c9392  jnz     short loc_1800C93B0
0x1800c9394  mov     rdx, [rsp+78h+pbOutput]; pbOutput
0x1800c939c  xor     r9d, r9d; dwFlags
0x1800c939f  mov     rcx, [rsp+78h+phHash]; hHash
0x1800c93a4  lea     r8d, [r9+20h]; cbOutput
0x1800c93a8  call    cs:__imp_BCryptFinishHash
0x1800c93ae  mov     ebx, eax
0x1800c93b0  mov     rcx, [rsp+78h+phHash]; hHash
0x1800c93b5  test    rcx, rcx
0x1800c93b8  jz      short loc_1800C93C0
0x1800c93ba  call    cs:__imp_BCryptDestroyHash
0x1800c93c0  mov     rcx, [rsp+78h+phAlgorithm]; hAlgorithm
0x1800c93c5  test    rcx, rcx
0x1800c93c8  jz      short loc_1800C93D2
0x1800c93ca  xor     edx, edx; dwFlags
0x1800c93cc  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800c93d2  mov     eax, ebx
0x1800c93d4  add     rsp, 50h
0x1800c93d8  pop     r14
0x1800c93da  pop     rdi
0x1800c93db  pop     rsi
0x1800c93dc  pop     rbp
0x1800c93dd  pop     rbx
0x1800c93de  retn
```
