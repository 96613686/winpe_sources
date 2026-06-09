# Windows::Compat::Inventory::AepicInvCache::OpenItem(ushort const *,Windows::Compat::Inventory::InventoryCacheItem * &)

- ea: `0x180029000`
- end: `0x1800290b4`
- name: `?OpenItem@AepicInvCache@Inventory@Compat@Windows@@UEBAJPEBGAEAPEAVInventoryCacheItem@234@@Z`
- size: `180`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, const unsigned __int16 *, struct Windows::Compat::Inventory::InventoryCacheItem **)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000514c`
- `0x1800152d0`
- `0x180029000`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x1800290a1`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x1800290a1`
- `AEPIC!__imp_InvCacheOpenItem` at `0x180029028`
- `AEPIC!__imp_InvCacheOpenItem` at `0x180029028`

## string_xrefs

- `0x18002904c`: `Windows::Compat::Inventory::AepicInvCache::OpenItem`
- `0x18002903b`: `InvCacheOpenItem failed [%#x]`

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
0x180029000  mov     [rsp+arg_8], rbx
0x180029005  push    rdi
0x180029006  sub     rsp, 30h
0x18002900a  mov     rdi, r8
0x18002900d  mov     [rsp+38h+arg_0], 0
0x180029016  mov     r8, rdx
0x180029019  mov     r9d, 1
0x18002901f  mov     rdx, [rcx+8]
0x180029023  lea     rcx, [rsp+38h+arg_0]
0x180029028  call    cs:__imp_InvCacheOpenItem
0x18002902e  mov     ebx, eax
0x180029030  test    eax, eax
0x180029032  jns     short loc_18002905F
0x180029034  cmp     eax, 80070002h
0x180029039  jz      short loc_180029097
0x18002903b  lea     r9, aInvcacheopenit; "InvCacheOpenItem failed [%#x]"
0x180029042  mov     [rsp+38h+var_18], eax
0x180029046  mov     r8d, 0C4h
0x18002904c  lea     rdx, aWindowsCompatI_31; "Windows::Compat::Inventory::AepicInvCac"...
0x180029053  mov     ecx, 1
0x180029058  call    AslLogCallPrintf
0x18002905d  jmp     short loc_180029097
0x18002905f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180029066  mov     ecx, 10h; unsigned __int64
0x18002906b  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180029070  mov     [rsp+38h+arg_18], rax
0x180029075  test    rax, rax
0x180029078  jz      short loc_180029092
0x18002907a  mov     rcx, [rsp+38h+arg_0]
0x18002907f  lea     rdx, ??_7AepicInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCacheItem::`vftable'
0x180029086  mov     [rax], rdx
0x180029089  mov     [rax+8], rcx
0x18002908d  mov     [rdi], rax
0x180029090  jmp     short loc_1800290A7
0x180029092  mov     ebx, 8007000Eh
0x180029097  cmp     [rsp+38h+arg_0], 0
0x18002909d  jz      short loc_1800290A7
0x18002909f  xor     ecx, ecx
0x1800290a1  call    cs:__imp_InvCacheCloseHandle
0x1800290a7  mov     eax, ebx
0x1800290a9  mov     rbx, [rsp+38h+arg_8]
0x1800290ae  add     rsp, 30h
0x1800290b2  pop     rdi
0x1800290b3  retn
```
