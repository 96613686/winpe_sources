# Windows::Compat::Inventory::AepicInvCache::CreateItem(ushort const *,Windows::Compat::Inventory::InventoryCacheItem * &)

- ea: `0x180017990`
- end: `0x180017a3a`
- name: `?CreateItem@AepicInvCache@Inventory@Compat@Windows@@UEAAJPEBGAEAPEAVInventoryCacheItem@234@@Z`
- size: `170`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, const unsigned __int16 *, struct Windows::Compat::Inventory::InventoryCacheItem **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006d30`
- `0x180017990`
- `0x18004c020`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x180017a27`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x180017a27`
- `AEPIC!__imp_InvCacheOpenItem` at `0x1800179b5`
- `AEPIC!__imp_InvCacheOpenItem` at `0x1800179b5`

## string_xrefs

- `0x1800179c1`: `InvCacheOpenItem failed [%#x]`
- `0x1800179d2`: `Windows::Compat::Inventory::AepicInvCache::CreateItem`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::AepicInvCache::CreateItem(
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
  v4 = InvCacheOpenItem(&v9, *((_QWORD *)this + 1), a2, 0);
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
  else
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::AepicInvCache::CreateItem",
      235,
      "InvCacheOpenItem failed [%#x]",
      v4);
  }
  if ( v9 )
    InvCacheCloseHandle();
  return v5;
}

```

## disassembly

```asm
0x180017990  mov     [rsp+arg_8], rbx
0x180017995  push    rdi
0x180017996  sub     rsp, 30h
0x18001799a  mov     rdi, r8
0x18001799d  mov     [rsp+38h+arg_0], 0
0x1800179a6  mov     r8, rdx
0x1800179a9  xor     r9d, r9d
0x1800179ac  mov     rdx, [rcx+8]
0x1800179b0  lea     rcx, [rsp+38h+arg_0]
0x1800179b5  call    cs:__imp_InvCacheOpenItem
0x1800179bb  mov     ebx, eax
0x1800179bd  test    eax, eax
0x1800179bf  jns     short loc_1800179E5
0x1800179c1  lea     r9, aInvcacheopenit; "InvCacheOpenItem failed [%#x]"
0x1800179c8  mov     [rsp+38h+var_18], eax
0x1800179cc  mov     r8d, 0EBh
0x1800179d2  lea     rdx, aWindowsCompatI_30; "Windows::Compat::Inventory::AepicInvCac"...
0x1800179d9  mov     ecx, 1
0x1800179de  call    AslLogCallPrintf
0x1800179e3  jmp     short loc_180017A1D
0x1800179e5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800179ec  mov     ecx, 10h; unsigned __int64
0x1800179f1  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800179f6  mov     [rsp+38h+arg_18], rax
0x1800179fb  test    rax, rax
0x1800179fe  jz      short loc_180017A18
0x180017a00  mov     rcx, [rsp+38h+arg_0]
0x180017a05  lea     rdx, ??_7AepicInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCacheItem::`vftable'
0x180017a0c  mov     [rax], rdx
0x180017a0f  mov     [rax+8], rcx
0x180017a13  mov     [rdi], rax
0x180017a16  jmp     short loc_180017A2D
0x180017a18  mov     ebx, 8007000Eh
0x180017a1d  mov     rcx, [rsp+38h+arg_0]
0x180017a22  test    rcx, rcx
0x180017a25  jz      short loc_180017A2D
0x180017a27  call    cs:__imp_InvCacheCloseHandle
0x180017a2d  mov     eax, ebx
0x180017a2f  mov     rbx, [rsp+38h+arg_8]
0x180017a34  add     rsp, 30h
0x180017a38  pop     rdi
0x180017a39  retn
```
