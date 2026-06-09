# Windows::Compat::Inventory::AepicInvCache::GetNextItem(Windows::Compat::Inventory::InventoryCacheItem * &,ushort *,ulong)

- ea: `0x180021d80`
- end: `0x180021e41`
- name: `?GetNextItem@AepicInvCache@Inventory@Compat@Windows@@UEAAJAEAPEAVInventoryCacheItem@234@PEAGK@Z`
- size: `193`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::AepicInvCache *__hidden this, struct Windows::Compat::Inventory::InventoryCacheItem **, unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800197d4`
- `0x180021d80`
- `0x180059db4`

## import_xrefs

- `AEPIC!__imp_InvCacheCloseHandle` at `0x180021e0e`
- `AEPIC!__imp_InvCacheCloseHandle` at `0x180021e0e`
- `AEPIC!__imp_InvCacheEnumerateItems` at `0x180021db2`
- `AEPIC!__imp_InvCacheEnumerateItems` at `0x180021db2`

## string_xrefs

- `0x180021e1d`: `InvCacheEnumerateItems failed. [%#x]`
- `0x180021e2e`: `Windows::Compat::Inventory::AepicInvCache::GetNextItem`

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
  if ( v6 < 0 )
  {
    if ( v6 != -2147024637 )
      AslLogCallPrintf(
        1,
        (unsigned int)"Windows::Compat::Inventory::AepicInvCache::GetNextItem",
        301,
        (unsigned int)"InvCacheEnumerateItems failed. [%#x]");
  }
  else
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
  if ( v11 )
    InvCacheCloseHandle(v11);
  return v7;
}

```

## disassembly

```asm
0x180021d80  mov     [rsp+arg_8], rbx
0x180021d85  mov     [rsp+arg_18], r9d
0x180021d8a  push    rdi
0x180021d8b  sub     rsp, 40h
0x180021d8f  mov     rax, [rcx+8]
0x180021d93  lea     r9, [rsp+48h+arg_18]
0x180021d98  mov     rdi, rdx
0x180021d9b  mov     [rsp+48h+arg_0], 0
0x180021da4  lea     rdx, [rcx+10h]
0x180021da8  mov     [rsp+48h+var_28], rax
0x180021dad  lea     rcx, [rsp+48h+arg_0]
0x180021db2  call    cs:__imp_InvCacheEnumerateItems
0x180021db8  mov     ebx, eax
0x180021dba  test    eax, eax
0x180021dbc  js      short loc_180021DFC
0x180021dbe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180021dc5  mov     ecx, 10h; unsigned __int64
0x180021dca  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180021dcf  mov     [rsp+48h+var_18], rax
0x180021dd4  test    rax, rax
0x180021dd7  jz      short loc_180021E16
0x180021dd9  mov     rcx, [rsp+48h+arg_0]
0x180021dde  lea     rdx, ??_7AepicInvCacheItem@Inventory@Compat@Windows@@6B@; const Windows::Compat::Inventory::AepicInvCacheItem::`vftable'
0x180021de5  mov     [rax], rdx
0x180021de8  mov     [rax+8], rcx
0x180021dec  mov     [rdi], rax
0x180021def  mov     eax, ebx
0x180021df1  mov     rbx, [rsp+48h+arg_8]
0x180021df6  add     rsp, 40h
0x180021dfa  pop     rdi
0x180021dfb  retn
0x180021dfc  cmp     ebx, 80070103h
0x180021e02  jnz     short loc_180021E1D
0x180021e04  mov     rcx, [rsp+48h+arg_0]
0x180021e09  test    rcx, rcx
0x180021e0c  jz      short loc_180021DEF
0x180021e0e  call    cs:__imp_InvCacheCloseHandle
0x180021e14  jmp     short loc_180021DEF
0x180021e16  mov     ebx, 8007000Eh
0x180021e1b  jmp     short loc_180021E04
0x180021e1d  lea     r9, aInvcacheenumer; "InvCacheEnumerateItems failed. [%#x]"
0x180021e24  mov     dword ptr [rsp+48h+var_28], ebx
0x180021e28  mov     r8d, 12Dh
0x180021e2e  lea     rdx, aWindowsCompatI_8; "Windows::Compat::Inventory::AepicInvCac"...
0x180021e35  mov     ecx, 1
0x180021e3a  call    AslLogCallPrintf
0x180021e3f  jmp     short loc_180021E04
```
