# Windows::Compat::Inventory::AepicInvCache::~AepicInvCache(void)

- ea: `0x18002a71c`
- end: `0x18002a76f`
- name: `??1AepicInvCache@Inventory@Compat@Windows@@UEAA@XZ`
- size: `83`
- prototype: `void __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002a6e0`

## callees

- `0x18002a71c`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x18002a738`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x18002a75f`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x18002a738`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x18002a75f`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::AepicInvCache::~AepicInvCache(
        Windows::Compat::Inventory::AepicInvCache *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx

  *(_QWORD *)this = &Windows::Compat::Inventory::AepicInvCache::`vftable';
  v2 = *((_QWORD *)this + 1);
  if ( v2 )
  {
    InvCacheCloseHandle(v2);
    *((_QWORD *)this + 1) = 0;
  }
  v3 = *((_QWORD *)this + 2);
  if ( v3 )
  {
    InvCacheCloseHandle(v3);
    *((_QWORD *)this + 2) = 0;
  }
  *(_QWORD *)this = &Windows::Compat::Inventory::InventoryCache::`vftable';
}

```

## disassembly

```asm
0x18002a71c  push    rbx
0x18002a71e  sub     rsp, 20h
0x18002a722  lea     rax, ??_7AepicInvCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCache::`vftable'
0x18002a729  mov     rbx, rcx
0x18002a72c  mov     [rcx], rax
0x18002a72f  mov     rcx, [rcx+8]
0x18002a733  test    rcx, rcx
0x18002a736  jz      short loc_18002A746
0x18002a738  call    cs:__imp_InvCacheCloseHandle
0x18002a73e  mov     qword ptr [rbx+8], 0
0x18002a746  mov     rcx, [rbx+10h]
0x18002a74a  test    rcx, rcx
0x18002a74d  jnz     short loc_18002A75F
0x18002a74f  lea     rax, ??_7InventoryCache@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::InventoryCache::`vftable'
0x18002a756  mov     [rbx], rax
0x18002a759  add     rsp, 20h
0x18002a75d  pop     rbx
0x18002a75e  retn
0x18002a75f  call    cs:__imp_InvCacheCloseHandle
0x18002a765  mov     qword ptr [rbx+10h], 0
0x18002a76d  jmp     short loc_18002A74F
```
