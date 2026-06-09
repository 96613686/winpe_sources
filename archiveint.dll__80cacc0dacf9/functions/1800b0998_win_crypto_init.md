# win_crypto_init

- ea: `0x1800b0998`
- end: `0x1800b0a19`
- name: `win_crypto_init`
- size: `129`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800e38b4`
- `0x1801098ec`

## callees

- `0x1800b0998`

## import_xrefs

- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b09b8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x1800b09b8`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b09fe`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800b09fe`
- `bcrypt!BCryptCreateHash` at `0x1800b09ef`
- `bcrypt!BCryptCreateHash` at `0x1800b09ef`

## pseudocode

```c
__int64 __fastcall win_crypto_init(__int64 a1, const WCHAR *a2)
{
  BCRYPT_ALG_HANDLE *v2; // rdi

  v2 = (BCRYPT_ALG_HANDLE *)(a1 + 8);
  *(_DWORD *)a1 = 0;
  if ( BCryptOpenAlgorithmProvider((BCRYPT_ALG_HANDLE *)(a1 + 8), a2, 0, 0) < 0 )
    return 4294967271LL;
  if ( BCryptCreateHash(*v2, (BCRYPT_HASH_HANDLE *)(a1 + 16), 0, 0, 0, 0, 0) < 0 )
  {
    BCryptCloseAlgorithmProvider(*v2, 0);
    return 4294967271LL;
  }
  *(_DWORD *)a1 = 1;
  return 0;
}

```

## disassembly

```asm
0x1800b0998  mov     [rsp+arg_0], rbx
0x1800b099d  push    rdi
0x1800b099e  sub     rsp, 40h
0x1800b09a2  lea     rdi, [rcx+8]
0x1800b09a6  mov     dword ptr [rcx], 0
0x1800b09ac  mov     rbx, rcx
0x1800b09af  xor     r9d, r9d; dwFlags
0x1800b09b2  mov     rcx, rdi; phAlgorithm
0x1800b09b5  xor     r8d, r8d; pszImplementation
0x1800b09b8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x1800b09be  test    eax, eax
0x1800b09c0  jns     short loc_1800B09C9
0x1800b09c2  mov     eax, 0FFFFFFE7h
0x1800b09c7  jmp     short loc_1800B0A0E
0x1800b09c9  mov     rcx, [rdi]; hAlgorithm
0x1800b09cc  lea     rdx, [rbx+10h]; phHash
0x1800b09d0  mov     [rsp+48h+dwFlags], 0; dwFlags
0x1800b09d8  xor     r9d, r9d; cbHashObject
0x1800b09db  mov     [rsp+48h+cbSecret], 0; cbSecret
0x1800b09e3  xor     r8d, r8d; pbHashObject
0x1800b09e6  mov     [rsp+48h+pbSecret], 0; pbSecret
0x1800b09ef  call    cs:__imp_BCryptCreateHash
0x1800b09f5  test    eax, eax
0x1800b09f7  jns     short loc_1800B0A06
0x1800b09f9  mov     rcx, [rdi]; hAlgorithm
0x1800b09fc  xor     edx, edx; dwFlags
0x1800b09fe  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800b0a04  jmp     short loc_1800B09C2
0x1800b0a06  mov     dword ptr [rbx], 1
0x1800b0a0c  xor     eax, eax
0x1800b0a0e  mov     rbx, [rsp+48h+arg_0]
0x1800b0a13  add     rsp, 40h
0x1800b0a17  pop     rdi
0x1800b0a18  retn
```
