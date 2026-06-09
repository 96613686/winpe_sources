# CFilteredItemFactory::RemoveAllFilters(IShellItem *,_GUID const &,void * *)

- ea: `0x1800237b0`
- end: `0x1800238b6`
- name: `?RemoveAllFilters@CFilteredItemFactory@@UEAAJPEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z`
- size: `262`
- prototype: `int(CFilteredItemFactory *__hidden this, struct IShellItem *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x1800106b0`
- `0x180010728`
- `0x180022da0`
- `0x1800237b0`
- `0x180051010`

## import_xrefs

- `SHELL32!SHGetIDListFromObject` at `0x1800237e4`
- `SHELL32!SHGetIDListFromObject` at `0x1800237e4`
- `SHELL32!SHCreateItemFromIDList` at `0x18002384f`
- `SHELL32!SHCreateItemFromIDList` at `0x18002388f`
- `SHELL32!SHCreateItemFromIDList` at `0x18002384f`
- `SHELL32!SHCreateItemFromIDList` at `0x18002388f`
- `SHELL32!__imp_ILFree` at `0x18002385b`
- `SHELL32!__imp_ILFree` at `0x18002389b`
- `SHELL32!__imp_ILFree` at `0x18002385b`
- `SHELL32!__imp_ILFree` at `0x18002389b`

## pseudocode

```c
__int64 __fastcall CFilteredItemFactory::RemoveAllFilters(
        CFilteredItemFactory *this,
        IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT NonFilteredRoot; // ebx
  struct IShellItemVtbl *lpVtbl; // rax
  LPCITEMIDLIST pidl; // [rsp+30h] [rbp-10h] BYREF
  __int64 v11; // [rsp+38h] [rbp-8h] BYREF
  LPITEMIDLIST ppidl; // [rsp+78h] [rbp+38h] BYREF

  *a4 = 0;
  ppidl = 0;
  NonFilteredRoot = SHGetIDListFromObject(a2, &ppidl);
  if ( NonFilteredRoot >= 0 )
  {
    lpVtbl = (struct IShellItemVtbl *)a2->lpVtbl;
    v11 = 0;
    if ( ((int (__fastcall *)(IUnknown *, _QWORD, const GUID *, GUID *, __int64 *))lpVtbl->BindToHandler)(
           a2,
           0,
           &BHID_SFObject,
           &GUID_711b2cfd_93d1_422b_bdf4_69be923f2449,
           &v11) < 0 )
    {
      if ( (unsigned int)ILRemoveHiddenID(ppidl) )
        ILExpungeRemovedHiddenIDs(ppidl);
      NonFilteredRoot = SHCreateItemFromIDList(ppidl, a3, a4);
    }
    else
    {
      pidl = 0;
      NonFilteredRoot = GetNonFilteredRoot(
                          (const struct _ITEMIDLIST_ABSOLUTE *)ppidl,
                          0,
                          (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
      if ( NonFilteredRoot >= 0 )
      {
        NonFilteredRoot = SHCreateItemFromIDList(pidl, a3, a4);
        ILFree((LPITEMIDLIST)pidl);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    ILFree(ppidl);
  }
  return (unsigned int)NonFilteredRoot;
}

```

## disassembly

```asm
0x1800237b0  mov     [rsp-18h+arg_0], rbx
0x1800237b5  mov     [rsp-18h+arg_8], rsi
0x1800237ba  push    rbp
0x1800237bb  push    rdi
0x1800237bc  push    r14
0x1800237be  mov     rbp, rsp
0x1800237c1  sub     rsp, 40h
0x1800237c5  mov     r14, rdx
0x1800237c8  mov     qword ptr [r9], 0
0x1800237cf  mov     rcx, r14; punk
0x1800237d2  mov     [rbp+ppidl], 0
0x1800237da  lea     rdx, [rbp+ppidl]; ppidl
0x1800237de  mov     rdi, r9
0x1800237e1  mov     rsi, r8
0x1800237e4  call    cs:__imp_SHGetIDListFromObject
0x1800237ea  mov     ebx, eax
0x1800237ec  test    eax, eax
0x1800237ee  js      loc_1800238A1
0x1800237f4  mov     rax, [r14]
0x1800237f7  lea     rcx, [rbp+var_8]
0x1800237fb  mov     [rsp+40h+var_20], rcx
0x180023800  lea     r9, _GUID_711b2cfd_93d1_422b_bdf4_69be923f2449
0x180023807  lea     r8, BHID_SFObject
0x18002380e  mov     [rbp+var_8], 0
0x180023816  xor     edx, edx
0x180023818  mov     rcx, r14
0x18002381b  mov     rax, [rax+18h]
0x18002381f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023824  mov     rcx, [rbp+ppidl]; struct _ITEMIDLIST_ABSOLUTE *
0x180023828  test    eax, eax
0x18002382a  js      short loc_180023873
0x18002382c  lea     r8, [rbp+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x180023830  mov     [rbp+pidl], 0
0x180023838  xor     edx, edx; int
0x18002383a  call    ?GetNonFilteredRoot@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@HPEAPEAU1@@Z; GetNonFilteredRoot(_ITEMIDLIST_ABSOLUTE const *,int,_ITEMIDLIST_ABSOLUTE * *)
0x18002383f  mov     ebx, eax
0x180023841  test    eax, eax
0x180023843  js      short loc_180023861
0x180023845  mov     rcx, [rbp+pidl]; pidl
0x180023849  mov     r8, rdi; ppv
0x18002384c  mov     rdx, rsi; riid
0x18002384f  call    cs:__imp_SHCreateItemFromIDList
0x180023855  mov     rcx, [rbp+pidl]; pidl
0x180023859  mov     ebx, eax
0x18002385b  call    cs:__imp_ILFree
0x180023861  mov     rcx, [rbp+var_8]
0x180023865  mov     rax, [rcx]
0x180023868  mov     rax, [rax+10h]
0x18002386c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023871  jmp     short loc_180023897
0x180023873  call    ILRemoveHiddenID
0x180023878  test    eax, eax
0x18002387a  jz      short loc_180023885
0x18002387c  mov     rcx, [rbp+ppidl]
0x180023880  call    ILExpungeRemovedHiddenIDs
0x180023885  mov     rcx, [rbp+ppidl]; pidl
0x180023889  mov     r8, rdi; ppv
0x18002388c  mov     rdx, rsi; riid
0x18002388f  call    cs:__imp_SHCreateItemFromIDList
0x180023895  mov     ebx, eax
0x180023897  mov     rcx, [rbp+ppidl]; pidl
0x18002389b  call    cs:__imp_ILFree
0x1800238a1  mov     rsi, [rsp+40h+arg_8]
0x1800238a6  mov     eax, ebx
0x1800238a8  mov     rbx, [rsp+40h+arg_0]
0x1800238ad  add     rsp, 40h
0x1800238b1  pop     r14
0x1800238b3  pop     rdi
0x1800238b4  pop     rbp
0x1800238b5  retn
```
