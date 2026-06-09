# RDP_MD5Init

- ea: `0x180042f70`
- end: `0x180043014`
- name: `RDP_MD5Init`
- size: `164`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180042d18`
- `0x18014c4a0`
- `0x18014c5f4`
- `0x18014c698`
- `0x18014c7e0`

## callees

- `0x180042f70`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180042fbf`
- `bcrypt!BCryptCreateHash` at `0x180042fbf`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180043009`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180043009`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180042fe6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180042fe6`

## pseudocode

```c
void __fastcall RDP_MD5Init(BCRYPT_HASH_HANDLE *phHash)
{
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+58h] [rbp+10h] BYREF

  if ( !g_hMD5Alg )
  {
    phAlgorithm = 0;
    if ( BCryptOpenAlgorithmProvider(&phAlgorithm, (LPCWSTR)"M\x00D\x005", 0, 0) < 0 )
      return;
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&g_hMD5Alg, (signed __int64)phAlgorithm, 0) )
      BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  }
  if ( phHash )
  {
    *phHash = 0;
    *(_OWORD *)(phHash + 1) = 0;
    BCryptCreateHash(g_hMD5Alg, phHash, 0, 0, 0, 0, 0);
  }
}

```

## disassembly

```asm
0x180042f70  push    rbx
0x180042f72  sub     rsp, 40h
0x180042f76  cmp     cs:?g_hMD5Alg@@3PEAXEA, 0; void * g_hMD5Alg
0x180042f7e  mov     rbx, rcx
0x180042f81  jz      short loc_180042FCB
0x180042f83  test    rbx, rbx
0x180042f86  jz      short loc_180042FC5
0x180042f88  mov     qword ptr [rbx], 0
0x180042f8f  xorps   xmm0, xmm0
0x180042f92  movups  xmmword ptr [rbx+8], xmm0
0x180042f96  mov     rcx, cs:?g_hMD5Alg@@3PEAXEA; hAlgorithm
0x180042f9d  xor     r9d, r9d; cbHashObject
0x180042fa0  mov     [rsp+48h+dwFlags], 0; dwFlags
0x180042fa8  xor     r8d, r8d; pbHashObject
0x180042fab  mov     [rsp+48h+cbSecret], 0; cbSecret
0x180042fb3  mov     rdx, rbx; phHash
0x180042fb6  mov     [rsp+48h+pbSecret], 0; pbSecret
0x180042fbf  call    cs:__imp_BCryptCreateHash
0x180042fc5  add     rsp, 40h
0x180042fc9  pop     rbx
0x180042fca  retn
0x180042fcb  xor     r9d, r9d; dwFlags
0x180042fce  mov     [rsp+48h+phAlgorithm], 0
0x180042fd7  xor     r8d, r8d; pszImplementation
0x180042fda  lea     rdx, ?g_abPad1@@3QBEB+28h; pszAlgId
0x180042fe1  lea     rcx, [rsp+48h+phAlgorithm]; phAlgorithm
0x180042fe6  call    cs:__imp_BCryptOpenAlgorithmProvider
0x180042fec  test    eax, eax
0x180042fee  js      short loc_180042FC5
0x180042ff0  mov     rcx, [rsp+48h+phAlgorithm]
0x180042ff5  xor     eax, eax
0x180042ff7  lock cmpxchg cs:?g_hMD5Alg@@3PEAXEA, rcx; void * g_hMD5Alg
0x180043000  jz      short loc_180042F83
0x180043002  mov     rcx, [rsp+48h+phAlgorithm]; hAlgorithm
0x180043007  xor     edx, edx; dwFlags
0x180043009  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18004300f  jmp     loc_180042F83
```
