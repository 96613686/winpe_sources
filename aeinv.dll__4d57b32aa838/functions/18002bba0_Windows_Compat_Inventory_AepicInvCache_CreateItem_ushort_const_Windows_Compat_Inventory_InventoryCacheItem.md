# Windows::Compat::Inventory::AepicInvCache::CreateItem(ushort const *,Windows::Compat::Inventory::InventoryCacheItem * &)

- ea: `0x18002bba0`
- end: `0x18002bc4a`
- name: `?CreateItem@AepicInvCache@Inventory@Compat@Windows@@UEAAJPEBGAEAPEAVInventoryCacheItem@234@@Z`
- size: `170`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, const unsigned __int16 *, struct Windows::Compat::Inventory::InventoryCacheItem **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800197d4`
- `0x18002bba0`
- `0x180059db4`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x18002bc42`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x18002bc42`
- `AEPIC!__imp_InvCacheOpenItem` at `0x18002bbc5`
- `AEPIC!__imp_InvCacheOpenItem` at `0x18002bbc5`

## string_xrefs

- `0x18002bc0f`: `InvCacheOpenItem failed [%#x]`
- `0x18002bc20`: `Windows::Compat::Inventory::AepicInvCache::CreateItem`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::AepicInvCache::CreateItem(
        Windows::Compat::Inventory::AepicInvCache *this,
        const unsigned __int16 *a2,
        struct Windows::Compat::Inventory::InventoryCacheItem **a3)
{
  int v4; // ebx
  struct Windows::Compat::Inventory::InventoryCacheItem *v5; // rax
  __int64 v6; // rcx
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  struct Windows::Compat::Inventory::InventoryCacheItem *v9; // [rsp+58h] [rbp+20h]

  v8 = 0;
  v4 = InvCacheOpenItem(&v8, *((_QWORD *)this + 1), a2, 0);
  if ( v4 < 0 )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"Windows::Compat::Inventory::AepicInvCache::CreateItem",
      235,
      (unsigned int)"InvCacheOpenItem failed [%#x]");
  }
  else
  {
    v5 = (struct Windows::Compat::Inventory::InventoryCacheItem *)operator new(
                                                                    0x10u,
                                                                    (const struct std::nothrow_t *)&std::nothrow);
    v9 = v5;
    if ( v5 )
    {
      v6 = v8;
      *(_QWORD *)v5 = &Windows::Compat::Inventory::AepicInvCacheItem::`vftable';
      *((_QWORD *)v5 + 1) = v6;
      *a3 = v5;
      return (unsigned int)v4;
    }
    v4 = -2147024882;
  }
  if ( v8 )
    InvCacheCloseHandle(v8);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18002bba0  mov     [rsp+arg_8], rbx
0x18002bba5  push    rdi
0x18002bba6  sub     rsp, 30h
0x18002bbaa  mov     rdi, r8
0x18002bbad  mov     [rsp+38h+arg_0], 0
0x18002bbb6  mov     r8, rdx
0x18002bbb9  xor     r9d, r9d
0x18002bbbc  mov     rdx, [rcx+8]
0x18002bbc0  lea     rcx, [rsp+38h+arg_0]
0x18002bbc5  call    cs:__imp_InvCacheOpenItem
0x18002bbcb  mov     ebx, eax
0x18002bbcd  test    eax, eax
0x18002bbcf  js      short loc_18002BC0F
0x18002bbd1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002bbd8  mov     ecx, 10h; unsigned __int64
0x18002bbdd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002bbe2  mov     [rsp+38h+arg_18], rax
0x18002bbe7  test    rax, rax
0x18002bbea  jz      short loc_18002BC33
0x18002bbec  mov     rcx, [rsp+38h+arg_0]
0x18002bbf1  lea     rdx, ??_7AepicInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCacheItem::`vftable'
0x18002bbf8  mov     [rax], rdx
0x18002bbfb  mov     [rax+8], rcx
0x18002bbff  mov     [rdi], rax
0x18002bc02  mov     eax, ebx
0x18002bc04  mov     rbx, [rsp+38h+arg_8]
0x18002bc09  add     rsp, 30h
0x18002bc0d  pop     rdi
0x18002bc0e  retn
0x18002bc0f  lea     r9, aInvcacheopenit; "InvCacheOpenItem failed [%#x]"
0x18002bc16  mov     [rsp+38h+var_18], eax
0x18002bc1a  mov     r8d, 0EBh
0x18002bc20  lea     rdx, aWindowsCompatI_20; "Windows::Compat::Inventory::AepicInvCac"...
0x18002bc27  mov     ecx, 1
0x18002bc2c  call    AslLogCallPrintf
0x18002bc31  jmp     short loc_18002BC38
0x18002bc33  mov     ebx, 8007000Eh
0x18002bc38  mov     rcx, [rsp+38h+arg_0]
0x18002bc3d  test    rcx, rcx
0x18002bc40  jz      short loc_18002BC02
0x18002bc42  call    cs:__imp_InvCacheCloseHandle
0x18002bc48  jmp     short loc_18002BC02
```
