# Windows::Compat::Inventory::AepicInvCache::GetNextItem(Windows::Compat::Inventory::InventoryCacheItem * &,ushort *,ulong)

- ea: `0x18001d580`
- end: `0x18001d63b`
- name: `?GetNextItem@AepicInvCache@Inventory@Compat@Windows@@UEAAJAEAPEAVInventoryCacheItem@234@PEAGK@Z`
- size: `187`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, struct Windows::Compat::Inventory::InventoryCacheItem **, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180006d30`
- `0x18001d580`
- `0x18004c020`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x18001d628`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x18001d628`
- `AEPIC!__imp_InvCacheEnumerateItems` at `0x18001d5af`
- `AEPIC!__imp_InvCacheEnumerateItems` at `0x18001d5af`

## string_xrefs

- `0x18001d5c2`: `InvCacheEnumerateItems failed. [%#x]`
- `0x18001d5d3`: `Windows::Compat::Inventory::AepicInvCache::GetNextItem`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Inventory::AepicInvCache::GetNextItem(
        Windows::Compat::Inventory::AepicInvCache *this,
        struct Windows::Compat::Inventory::InventoryCacheItem **a2,
        unsigned __int16 *a3,
        int a4)
{
  __int64 v4; // rax
  int v6; // eax
  unsigned int v7; // ebx
  struct Windows::Compat::Inventory::InventoryCacheItem *v8; // rax
  __int64 v9; // rcx
  __int64 v11; // [rsp+50h] [rbp+8h] BYREF
  int v12; // [rsp+68h] [rbp+20h] BYREF

  v12 = a4;
  v4 = *((_QWORD *)this + 1);
  v11 = 0;
  v6 = InvCacheEnumerateItems(&v11, (char *)this + 16, a3, &v12, v4);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v8 = (struct Windows::Compat::Inventory::InventoryCacheItem *)operator new(
                                                                    0x10u,
                                                                    (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
    {
      v9 = v11;
      *(_QWORD *)v8 = &Windows::Compat::Inventory::AepicInvCacheItem::`vftable';
      *((_QWORD *)v8 + 1) = v9;
      *a2 = v8;
      return v7;
    }
    v7 = -2147024882;
  }
  else if ( v6 != -2147024637 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::AepicInvCache::GetNextItem",
      301,
      "InvCacheEnumerateItems failed. [%#x]",
      v6);
  }
  if ( v11 )
    InvCacheCloseHandle();
  return v7;
}

```

## disassembly

```asm
0x18001d580  mov     r11, rsp
0x18001d583  mov     [r11+10h], rbx
0x18001d587  mov     [r11+20h], r9d
0x18001d58b  push    rdi
0x18001d58c  sub     rsp, 40h
0x18001d590  mov     rax, [rcx+8]
0x18001d594  lea     r9, [r11+20h]
0x18001d598  mov     rdi, rdx
0x18001d59b  mov     qword ptr [r11+8], 0
0x18001d5a3  lea     rdx, [rcx+10h]
0x18001d5a7  mov     [r11-28h], rax
0x18001d5ab  lea     rcx, [r11+8]
0x18001d5af  call    cs:__imp_InvCacheEnumerateItems
0x18001d5b5  mov     ebx, eax
0x18001d5b7  test    eax, eax
0x18001d5b9  jns     short loc_18001D5E6
0x18001d5bb  cmp     eax, 80070103h
0x18001d5c0  jz      short loc_18001D61E
0x18001d5c2  lea     r9, aInvcacheenumer; "InvCacheEnumerateItems failed. [%#x]"
0x18001d5c9  mov     [rsp+48h+var_28], eax
0x18001d5cd  mov     r8d, 12Dh
0x18001d5d3  lea     rdx, aWindowsCompatI_14; "Windows::Compat::Inventory::AepicInvCac"...
0x18001d5da  mov     ecx, 1
0x18001d5df  call    AslLogCallPrintf
0x18001d5e4  jmp     short loc_18001D61E
0x18001d5e6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001d5ed  mov     ecx, 10h; unsigned __int64
0x18001d5f2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001d5f7  mov     [rsp+48h+var_18], rax
0x18001d5fc  test    rax, rax
0x18001d5ff  jz      short loc_18001D619
0x18001d601  mov     rcx, [rsp+48h+arg_0]
0x18001d606  lea     rdx, ??_7AepicInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCacheItem::`vftable'
0x18001d60d  mov     [rax], rdx
0x18001d610  mov     [rax+8], rcx
0x18001d614  mov     [rdi], rax
0x18001d617  jmp     short loc_18001D62E
0x18001d619  mov     ebx, 8007000Eh
0x18001d61e  mov     rcx, [rsp+48h+arg_0]
0x18001d623  test    rcx, rcx
0x18001d626  jz      short loc_18001D62E
0x18001d628  call    cs:__imp_InvCacheCloseHandle
0x18001d62e  mov     eax, ebx
0x18001d630  mov     rbx, [rsp+48h+arg_8]
0x18001d635  add     rsp, 40h
0x18001d639  pop     rdi
0x18001d63a  retn
```
