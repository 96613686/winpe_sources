# Windows::Compat::Inventory::AepicInvCache::OpenItem(ushort const *,Windows::Compat::Inventory::InventoryCacheItem * &)

- ea: `0x180026ed0`
- end: `0x180026f86`
- name: `?OpenItem@AepicInvCache@Inventory@Compat@Windows@@UEBAJPEBGAEAPEAVInventoryCacheItem@234@@Z`
- size: `182`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, const unsigned __int16 *, struct Windows::Compat::Inventory::InventoryCacheItem **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800197d4`
- `0x180026ed0`
- `0x180059db4`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x180026f53`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x180026f53`
- `AEPIC!__imp_InvCacheOpenItem` at `0x180026ef8`
- `AEPIC!__imp_InvCacheOpenItem` at `0x180026ef8`

## string_xrefs

- `0x180026f73`: `Windows::Compat::Inventory::AepicInvCache::OpenItem`
- `0x180026f62`: `InvCacheOpenItem failed [%#x]`

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
  if ( v4 < 0 )
  {
    if ( v4 != -2147024894 )
      AslLogCallPrintf(
        1,
        (unsigned int)"Windows::Compat::Inventory::AepicInvCache::OpenItem",
        196,
        (unsigned int)"InvCacheOpenItem failed [%#x]");
  }
  else
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
  if ( v9 )
    InvCacheCloseHandle(0);
  return v5;
}

```

## disassembly

```asm
0x180026ed0  mov     [rsp+arg_8], rbx
0x180026ed5  push    rdi
0x180026ed6  sub     rsp, 30h
0x180026eda  mov     rdi, r8
0x180026edd  mov     [rsp+38h+arg_0], 0
0x180026ee6  mov     r8, rdx
0x180026ee9  mov     r9d, 1
0x180026eef  mov     rdx, [rcx+8]
0x180026ef3  lea     rcx, [rsp+38h+arg_0]
0x180026ef8  call    cs:__imp_InvCacheOpenItem
0x180026efe  mov     ebx, eax
0x180026f00  test    eax, eax
0x180026f02  js      short loc_180026F42
0x180026f04  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180026f0b  mov     ecx, 10h; unsigned __int64
0x180026f10  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180026f15  mov     [rsp+38h+arg_18], rax
0x180026f1a  test    rax, rax
0x180026f1d  jz      short loc_180026F5B
0x180026f1f  mov     rcx, [rsp+38h+arg_0]
0x180026f24  lea     rdx, ??_7AepicInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCacheItem::`vftable'
0x180026f2b  mov     [rax], rdx
0x180026f2e  mov     [rax+8], rcx
0x180026f32  mov     [rdi], rax
0x180026f35  mov     eax, ebx
0x180026f37  mov     rbx, [rsp+38h+arg_8]
0x180026f3c  add     rsp, 30h
0x180026f40  pop     rdi
0x180026f41  retn
0x180026f42  cmp     eax, 80070002h
0x180026f47  jnz     short loc_180026F62
0x180026f49  cmp     [rsp+38h+arg_0], 0
0x180026f4f  jz      short loc_180026F35
0x180026f51  xor     ecx, ecx
0x180026f53  call    cs:__imp_InvCacheCloseHandle
0x180026f59  jmp     short loc_180026F35
0x180026f5b  mov     ebx, 8007000Eh
0x180026f60  jmp     short loc_180026F49
0x180026f62  lea     r9, aInvcacheopenit; "InvCacheOpenItem failed [%#x]"
0x180026f69  mov     [rsp+38h+var_18], eax
0x180026f6d  mov     r8d, 0C4h
0x180026f73  lea     rdx, aWindowsCompatI_9; "Windows::Compat::Inventory::AepicInvCac"...
0x180026f7a  mov     ecx, 1
0x180026f7f  call    AslLogCallPrintf
0x180026f84  jmp     short loc_180026F49
```
