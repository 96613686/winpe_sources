# Windows::Compat::Inventory::AepicInvCache::GetFirstItem(Windows::Compat::Inventory::InventoryCacheItem * &,ushort *,ulong)

- ea: `0x18001b400`
- end: `0x18001b44d`
- name: `?GetFirstItem@AepicInvCache@Inventory@Compat@Windows@@UEAAJAEAPEAVInventoryCacheItem@234@PEAGK@Z`
- size: `77`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, struct Windows::Compat::Inventory::InventoryCacheItem **, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18001b400`
- `0x1800ec010`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x18001b41e`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x18001b41e`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::AepicInvCache::GetFirstItem(
        Windows::Compat::Inventory::AepicInvCache *this,
        struct Windows::Compat::Inventory::InventoryCacheItem **a2,
        unsigned __int16 *a3,
        unsigned int a4)
{
  __int64 v6; // rcx

  v6 = *((_QWORD *)this + 2);
  if ( v6 )
  {
    InvCacheCloseHandle(v6);
    *((_QWORD *)this + 2) = 0;
  }
  return (*(__int64 (__fastcall **)(Windows::Compat::Inventory::AepicInvCache *, struct Windows::Compat::Inventory::InventoryCacheItem **, unsigned __int16 *, _QWORD))(*(_QWORD *)this + 48LL))(
           this,
           a2,
           a3,
           a4);
}

```

## disassembly

```asm
0x18001b400  push    rbx
0x18001b402  push    rbp
0x18001b403  push    rsi
0x18001b404  push    rdi
0x18001b405  sub     rsp, 38h
0x18001b409  mov     rbx, rcx
0x18001b40c  mov     edi, r9d
0x18001b40f  mov     rcx, [rcx+10h]
0x18001b413  mov     rsi, r8
0x18001b416  mov     rbp, rdx
0x18001b419  test    rcx, rcx
0x18001b41c  jz      short loc_18001B42C
0x18001b41e  call    cs:__imp_InvCacheCloseHandle
0x18001b424  mov     qword ptr [rbx+10h], 0
0x18001b42c  mov     rax, [rbx]
0x18001b42f  mov     r9d, edi
0x18001b432  mov     r8, rsi
0x18001b435  mov     rdx, rbp
0x18001b438  mov     rcx, rbx
0x18001b43b  mov     rax, [rax+30h]
0x18001b43f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b444  add     rsp, 38h
0x18001b448  pop     rdi
0x18001b449  pop     rsi
0x18001b44a  pop     rbp
0x18001b44b  pop     rbx
0x18001b44c  retn
```
