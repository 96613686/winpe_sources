# Windows::Compat::Inventory::AepicInvCache::OpenItem(ushort const *,Windows::Compat::Inventory::InventoryCacheItem * &)

- ea: `0x180020cb0`
- end: `0x180020d64`
- name: `?OpenItem@AepicInvCache@Inventory@Compat@Windows@@UEBAJPEBGAEAPEAVInventoryCacheItem@234@@Z`
- size: `180`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, const unsigned __int16 *, struct Windows::Compat::Inventory::InventoryCacheItem **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006d30`
- `0x180020cb0`
- `0x18004c020`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x180020d51`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x180020d51`
- `AEPIC!__imp_InvCacheOpenItem` at `0x180020cd8`
- `AEPIC!__imp_InvCacheOpenItem` at `0x180020cd8`

## string_xrefs

- `0x180020cfc`: `Windows::Compat::Inventory::AepicInvCache::OpenItem`
- `0x180020ceb`: `InvCacheOpenItem failed [%#x]`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::AepicInvCache::OpenItem(
        Windows::Compat::Inventory::AepicInvCache *this,
        const unsigned __int16 *a2,
        struct Windows::Compat::Inventory::InventoryCacheItem **a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  struct Windows::Compat::Inventory::InventoryCacheItem *v6; // rax
  __int64 v7; // rcx
  __int64 v9; // [rsp+40h] [rbp+8h] BYREF
  struct Windows::Compat::Inventory::InventoryCacheItem *v10; // [rsp+58h] [rbp+20h]

  v9 = 0;
  v4 = InvCacheOpenItem(&v9, *((_QWORD *)this + 1), a2, 1);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v6 = (struct Windows::Compat::Inventory::InventoryCacheItem *)operator new(
                                                                    0x10u,
                                                                    (const struct std::nothrow_t *)&std::nothrow);
    v10 = v6;
    if ( v6 )
    {
      v7 = v9;
      *(_QWORD *)v6 = &Windows::Compat::Inventory::AepicInvCacheItem::`vftable';
      *((_QWORD *)v6 + 1) = v7;
      *a3 = v6;
      return v5;
    }
    v5 = -2147024882;
  }
  else if ( v4 != -2147024894 )
  {
    AslLogCallPrintf(1, "Windows::Compat::Inventory::AepicInvCache::OpenItem", 196, "InvCacheOpenItem failed [%#x]", v4);
  }
  if ( v9 )
    InvCacheCloseHandle(0);
  return v5;
}

```

## disassembly

```asm
0x180020cb0  mov     [rsp+arg_8], rbx
0x180020cb5  push    rdi
0x180020cb6  sub     rsp, 30h
0x180020cba  mov     rdi, r8
0x180020cbd  mov     [rsp+38h+arg_0], 0
0x180020cc6  mov     r8, rdx
0x180020cc9  mov     r9d, 1
0x180020ccf  mov     rdx, [rcx+8]
0x180020cd3  lea     rcx, [rsp+38h+arg_0]
0x180020cd8  call    cs:__imp_InvCacheOpenItem
0x180020cde  mov     ebx, eax
0x180020ce0  test    eax, eax
0x180020ce2  jns     short loc_180020D0F
0x180020ce4  cmp     eax, 80070002h
0x180020ce9  jz      short loc_180020D47
0x180020ceb  lea     r9, aInvcacheopenit; "InvCacheOpenItem failed [%#x]"
0x180020cf2  mov     [rsp+38h+var_18], eax
0x180020cf6  mov     r8d, 0C4h
0x180020cfc  lea     rdx, aWindowsCompatI_15; "Windows::Compat::Inventory::AepicInvCac"...
0x180020d03  mov     ecx, 1
0x180020d08  call    AslLogCallPrintf
0x180020d0d  jmp     short loc_180020D47
0x180020d0f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020d16  mov     ecx, 10h; unsigned __int64
0x180020d1b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180020d20  mov     [rsp+38h+arg_18], rax
0x180020d25  test    rax, rax
0x180020d28  jz      short loc_180020D42
0x180020d2a  mov     rcx, [rsp+38h+arg_0]
0x180020d2f  lea     rdx, ??_7AepicInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCacheItem::`vftable'
0x180020d36  mov     [rax], rdx
0x180020d39  mov     [rax+8], rcx
0x180020d3d  mov     [rdi], rax
0x180020d40  jmp     short loc_180020D57
0x180020d42  mov     ebx, 8007000Eh
0x180020d47  cmp     [rsp+38h+arg_0], 0
0x180020d4d  jz      short loc_180020D57
0x180020d4f  xor     ecx, ecx
0x180020d51  call    cs:__imp_InvCacheCloseHandle
0x180020d57  mov     eax, ebx
0x180020d59  mov     rbx, [rsp+38h+arg_8]
0x180020d5e  add     rsp, 30h
0x180020d62  pop     rdi
0x180020d63  retn
```
