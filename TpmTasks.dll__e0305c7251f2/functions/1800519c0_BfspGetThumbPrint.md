# BfspGetThumbPrint

- ea: `0x1800519c0`
- end: `0x180051a94`
- name: `BfspGetThumbPrint`
- size: `212`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180051a9c`

## callees

- `0x1800519c0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180051a85`
- `ntdll!RtlNtStatusToDosError` at `0x180051a85`
- `bcrypt!BCryptCreateHash` at `0x180051a24`
- `bcrypt!BCryptCreateHash` at `0x180051a24`
- `bcrypt!BCryptHashData` at `0x180051a3e`
- `bcrypt!BCryptHashData` at `0x180051a3e`
- `bcrypt!BCryptDestroyHash` at `0x180051a6b`
- `bcrypt!BCryptDestroyHash` at `0x180051a6b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180051a7d`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180051a7d`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800519f5`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800519f5`
- `bcrypt!BCryptFinishHash` at `0x180051a59`
- `bcrypt!BCryptFinishHash` at `0x180051a59`

## pseudocode

```c
ULONG __fastcall BfspGetThumbPrint(PUCHAR pbInput, ULONG cbInput, PUCHAR pbOutput)
{
  int v6; // ebx
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-38h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+48h] [rbp-30h] BYREF

  phHash = 0;
  phAlgorithm = 0;
  BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA1", 0, 0);
  v6 = BCryptCreateHash(phAlgorithm, &phHash, 0, 0, 0, 0, 0);
  if ( v6 >= 0 )
  {
    v6 = BCryptHashData(phHash, pbInput, cbInput, 0);
    if ( v6 >= 0 )
      v6 = BCryptFinishHash(phHash, pbOutput, 0x14u, 0);
  }
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return RtlNtStatusToDosError(v6);
}

```

## disassembly

```asm
0x1800519c0  push    rbx
0x1800519c2  push    rbp
0x1800519c3  push    rsi
0x1800519c4  push    rdi
0x1800519c5  sub     rsp, 58h
0x1800519c9  mov     rdi, r8
0x1800519cc  mov     [rsp+78h+phHash], 0
0x1800519d5  mov     esi, edx
0x1800519d7  mov     [rsp+78h+phAlgorithm], 0
0x1800519e0  mov     rbp, rcx
0x1800519e3  lea     rdx, aSha1; "SHA1"
0x1800519ea  xor     r8d, r8d; pszImplementation
0x1800519ed  lea     rcx, [rsp+78h+phAlgorithm]; phAlgorithm
0x1800519f2  xor     r9d, r9d; dwFlags
0x1800519f5  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800519fb  mov     rcx, [rsp+78h+phAlgorithm]; hAlgorithm
0x180051a00  lea     rdx, [rsp+78h+phHash]; phHash
0x180051a05  mov     [rsp+78h+dwFlags], 0; dwFlags
0x180051a0d  xor     r9d, r9d; cbHashObject
0x180051a10  mov     [rsp+78h+cbSecret], 0; cbSecret
0x180051a18  xor     r8d, r8d; pbHashObject
0x180051a1b  mov     [rsp+78h+pbSecret], 0; pbSecret
0x180051a24  call    cs:__imp_BCryptCreateHash
0x180051a2a  mov     ebx, eax
0x180051a2c  test    eax, eax
0x180051a2e  js      short loc_180051A61
0x180051a30  mov     rcx, [rsp+78h+phHash]; hHash
0x180051a35  xor     r9d, r9d; dwFlags
0x180051a38  mov     r8d, esi; cbInput
0x180051a3b  mov     rdx, rbp; pbInput
0x180051a3e  call    cs:__imp_BCryptHashData
0x180051a44  mov     ebx, eax
0x180051a46  test    eax, eax
0x180051a48  js      short loc_180051A61
0x180051a4a  mov     rcx, [rsp+78h+phHash]; hHash
0x180051a4f  xor     r9d, r9d; dwFlags
0x180051a52  mov     rdx, rdi; pbOutput
0x180051a55  lea     r8d, [r9+14h]; cbOutput
0x180051a59  call    cs:__imp_BCryptFinishHash
0x180051a5f  mov     ebx, eax
0x180051a61  mov     rcx, [rsp+78h+phHash]; hHash
0x180051a66  test    rcx, rcx
0x180051a69  jz      short loc_180051A71
0x180051a6b  call    cs:__imp_BCryptDestroyHash
0x180051a71  mov     rcx, [rsp+78h+phAlgorithm]; hAlgorithm
0x180051a76  test    rcx, rcx
0x180051a79  jz      short loc_180051A83
0x180051a7b  xor     edx, edx; dwFlags
0x180051a7d  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180051a83  mov     ecx, ebx; Status
0x180051a85  call    cs:__imp_RtlNtStatusToDosError
0x180051a8b  add     rsp, 58h
0x180051a8f  pop     rdi
0x180051a90  pop     rsi
0x180051a91  pop     rbp
0x180051a92  pop     rbx
0x180051a93  retn
```
