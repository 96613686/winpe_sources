# CngRsa32Compat_MD5Init

- ea: `0x1800829e4`
- end: `0x180082a24`
- name: `CngRsa32Compat_MD5Init`
- size: `64`
- prototype: `__int64 __fastcall(BCRYPT_HASH_HANDLE *phHash)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18008251c`
- `0x180083990`

## callees

- `0x1800829e4`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x180082a0e`
- `bcrypt!BCryptCreateHash` at `0x180082a0e`

## pseudocode

```c
NTSTATUS __fastcall CngRsa32Compat_MD5Init(BCRYPT_HASH_HANDLE *phHash)
{
  NTSTATUS result; // eax

  result = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x21, phHash, 0, 0, 0, 0, 0);
  if ( result < 0 )
    __fastfail(7u);
  return result;
}

```

## disassembly

```asm
0x1800829e4  sub     rsp, 48h
0x1800829e8  xor     r9d, r9d; cbHashObject
0x1800829eb  mov     [rsp+48h+dwFlags], 0; dwFlags
0x1800829f3  mov     rdx, rcx; phHash
0x1800829f6  mov     [rsp+48h+cbSecret], 0; cbSecret
0x1800829fe  xor     r8d, r8d; pbHashObject
0x180082a01  mov     [rsp+48h+pbSecret], 0; pbSecret
0x180082a0a  lea     ecx, [r9+21h]; hAlgorithm
0x180082a0e  call    cs:__imp_BCryptCreateHash
0x180082a14  test    eax, eax
0x180082a16  jns     short loc_180082A1F
0x180082a18  mov     ecx, 7
0x180082a1d  int     29h; Win8: RtlFailFast(ecx)
0x180082a1f  add     rsp, 48h
0x180082a23  retn
```
