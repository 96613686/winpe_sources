# CFilteredItemFactory::RemoveFilterForProperty(IShellItem *,_tagpropertykey const &,_GUID const &,void * *)

- ea: `0x1800238c0`
- end: `0x180023a15`
- name: `?RemoveFilterForProperty@CFilteredItemFactory@@UEAAJPEAUIShellItem@@AEBU_tagpropertykey@@AEBU_GUID@@PEAPEAX@Z`
- size: `341`
- prototype: `int(CFilteredItemFactory *__hidden this, struct IShellItem *, const struct _tagpropertykey *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800113b4`
- `0x18001d494`
- `0x1800238c0`
- `0x180023fb0`
- `0x18003ec4c`
- `0x18003eee4`
- `0x180051010`

## import_xrefs

- `SHELL32!SHGetIDListFromObject` at `0x1800238f3`
- `SHELL32!SHGetIDListFromObject` at `0x1800238f3`
- `SHELL32!SHCreateItemFromIDList` at `0x1800239ea`
- `SHELL32!SHCreateItemFromIDList` at `0x1800239ea`
- `SHELL32!__imp_ILFindLastID` at `0x18002399a`
- `SHELL32!__imp_ILFindLastID` at `0x18002399a`
- `SHELL32!__imp_ILRemoveLastID` at `0x1800239b9`
- `SHELL32!__imp_ILRemoveLastID` at `0x1800239b9`
- `SHELL32!__imp_ILFree` at `0x1800239d6`
- `SHELL32!__imp_ILFree` at `0x1800239f6`
- `SHELL32!__imp_ILFree` at `0x180023a00`
- `SHELL32!__imp_ILFree` at `0x1800239d6`
- `SHELL32!__imp_ILFree` at `0x1800239f6`
- `SHELL32!__imp_ILFree` at `0x180023a00`

## pseudocode

```c
__int64 __fastcall CFilteredItemFactory::RemoveFilterForProperty(
        CFilteredItemFactory *this,
        IUnknown *a2,
        const struct _tagpropertykey *a3,
        const struct _GUID *a4,
        void **pidl)
{
  void **v5; // r14
  HRESULT v9; // ebx
  struct IShellItemVtbl *lpVtbl; // rax
  struct IFilterCondition **v11; // r9
  const struct _ITEMIDLIST_RELATIVE *v12; // rbx
  HRESULT v13; // eax
  const struct _ITEMID_CHILD *ID; // rax
  struct IFilterCondition *v15; // r8
  LPITEMIDLIST ppidl; // [rsp+30h] [rbp-28h] BYREF
  LPCITEMIDLIST v18; // [rsp+38h] [rbp-20h] BYREF
  _QWORD v19[3]; // [rsp+40h] [rbp-18h] BYREF

  v5 = pidl;
  ppidl = 0;
  *pidl = 0;
  v9 = SHGetIDListFromObject(a2, &ppidl);
  if ( v9 >= 0 )
  {
    lpVtbl = (struct IShellItemVtbl *)a2->lpVtbl;
    v18 = 0;
    v19[0] = 0;
    if ( ((int (__fastcall *)(IUnknown *, _QWORD, const GUID *, GUID *, _QWORD *))lpVtbl->BindToHandler)(
           a2,
           0,
           &BHID_SFObject,
           &GUID_711b2cfd_93d1_422b_bdf4_69be923f2449,
           v19) < 0 )
    {
      pidl = 0;
      ID = (const struct _ITEMID_CHILD *)ILFindLastID(ppidl);
      v9 = SHSetFilterToIDList(ID, a3, v15, (struct _ITEMID_CHILD **)&pidl);
      if ( v9 < 0 )
      {
LABEL_11:
        ILFree(ppidl);
        return (unsigned int)v9;
      }
      ILRemoveLastID(ppidl);
      v9 = SHILCombine(
             (const struct _ITEMIDLIST_ABSOLUTE *)ppidl,
             (const struct _ITEMIDLIST_RELATIVE *)pidl,
             (struct _ITEMIDLIST_ABSOLUTE **)&v18);
      ILFree((LPITEMIDLIST)pidl);
    }
    else
    {
      v12 = (const struct _ITEMIDLIST_RELATIVE *)ppidl;
      LODWORD(pidl) = 0;
      if ( (int)_GetPropertyFilterFromIDList((const struct _ITEMIDLIST_ABSOLUTE *)ppidl, a3, (unsigned int *)&pidl, v11) < 0 )
        v13 = SHILClone(v12, (struct _ITEMIDLIST_RELATIVE **)&v18);
      else
        v13 = ModifyOrRemoveFilterByIndex(v12, (unsigned int)pidl, 0, &v18);
      v9 = v13;
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v19[0] + 16LL))(v19[0]);
    }
    if ( v9 >= 0 )
    {
      v9 = SHCreateItemFromIDList(v18, a4, v5);
      ILFree((LPITEMIDLIST)v18);
    }
    goto LABEL_11;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800238c0  push    rbp
0x1800238c2  push    rbx
0x1800238c3  push    rsi
0x1800238c4  push    rdi
0x1800238c5  push    r14
0x1800238c7  push    r15
0x1800238c9  mov     rbp, rsp
0x1800238cc  sub     rsp, 58h
0x1800238d0  mov     r14, [rbp+pidl]
0x1800238d4  mov     rsi, rdx
0x1800238d7  lea     rdx, [rbp+ppidl]; ppidl
0x1800238db  mov     [rbp+ppidl], 0
0x1800238e3  mov     rcx, rsi; punk
0x1800238e6  mov     r15, r9
0x1800238e9  mov     rdi, r8
0x1800238ec  mov     qword ptr [r14], 0
0x1800238f3  call    cs:__imp_SHGetIDListFromObject
0x1800238f9  mov     ebx, eax
0x1800238fb  test    eax, eax
0x1800238fd  js      loc_180023A06
0x180023903  mov     rax, [rsi]
0x180023906  lea     rcx, [rbp+var_18]
0x18002390a  mov     [rsp+58h+var_38], rcx
0x18002390f  lea     r9, _GUID_711b2cfd_93d1_422b_bdf4_69be923f2449
0x180023916  lea     r8, BHID_SFObject
0x18002391d  mov     [rbp+var_20], 0
0x180023925  xor     edx, edx
0x180023927  mov     [rbp+var_18], 0
0x18002392f  mov     rax, [rax+18h]
0x180023933  mov     rcx, rsi
0x180023936  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002393b  test    eax, eax
0x18002393d  js      short loc_18002398E
0x18002393f  mov     rbx, [rbp+ppidl]
0x180023943  lea     r8, [rbp+pidl]; unsigned int *
0x180023947  mov     rcx, rbx; struct _ITEMIDLIST_ABSOLUTE *
0x18002394a  mov     dword ptr [rbp+pidl], 0
0x180023951  mov     rdx, rdi; struct _tagpropertykey *
0x180023954  call    ?_GetPropertyFilterFromIDList@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@AEBU_tagpropertykey@@PEAIPEAPEAUIFilterCondition@@@Z; _GetPropertyFilterFromIDList(_ITEMIDLIST_ABSOLUTE const *,_tagpropertykey const &,uint *,IFilterCondition * *)
0x180023959  mov     rcx, rbx; struct _ITEMIDLIST_RELATIVE *
0x18002395c  test    eax, eax
0x18002395e  js      short loc_180023971
0x180023960  mov     edx, dword ptr [rbp+pidl]
0x180023963  lea     r9, [rbp+var_20]
0x180023967  xor     r8d, r8d
0x18002396a  call    ModifyOrRemoveFilterByIndex
0x18002396f  jmp     short loc_18002397A
0x180023971  lea     rdx, [rbp+var_20]; struct _ITEMIDLIST_RELATIVE **
0x180023975  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x18002397a  mov     rcx, [rbp+var_18]
0x18002397e  mov     ebx, eax
0x180023980  mov     rax, [rcx]
0x180023983  mov     rax, [rax+10h]
0x180023987  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002398c  jmp     short loc_1800239DC
0x18002398e  mov     rcx, [rbp+ppidl]; pidl
0x180023992  mov     [rbp+pidl], 0
0x18002399a  call    cs:__imp_ILFindLastID
0x1800239a0  lea     r9, [rbp+pidl]; struct _ITEMID_CHILD **
0x1800239a4  mov     rdx, rdi; struct _tagpropertykey *
0x1800239a7  mov     rcx, rax; struct _ITEMID_CHILD *
0x1800239aa  call    ?SHSetFilterToIDList@@YAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAUIFilterCondition@@PEAPEAU1@@Z; SHSetFilterToIDList(_ITEMID_CHILD const *,_tagpropertykey const &,IFilterCondition *,_ITEMID_CHILD * *)
0x1800239af  mov     ebx, eax
0x1800239b1  test    eax, eax
0x1800239b3  js      short loc_1800239FC
0x1800239b5  mov     rcx, [rbp+ppidl]; pidl
0x1800239b9  call    cs:__imp_ILRemoveLastID
0x1800239bf  mov     rdx, [rbp+pidl]; struct _ITEMIDLIST_RELATIVE *
0x1800239c3  lea     r8, [rbp+var_20]; struct _ITEMIDLIST_ABSOLUTE **
0x1800239c7  mov     rcx, [rbp+ppidl]; struct _ITEMIDLIST_ABSOLUTE *
0x1800239cb  call    ?SHILCombine@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILCombine(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_ABSOLUTE * *)
0x1800239d0  mov     rcx, [rbp+pidl]; pidl
0x1800239d4  mov     ebx, eax
0x1800239d6  call    cs:__imp_ILFree
0x1800239dc  test    ebx, ebx
0x1800239de  js      short loc_1800239FC
0x1800239e0  mov     rcx, [rbp+var_20]; pidl
0x1800239e4  mov     r8, r14; ppv
0x1800239e7  mov     rdx, r15; riid
0x1800239ea  call    cs:__imp_SHCreateItemFromIDList
0x1800239f0  mov     rcx, [rbp+var_20]; pidl
0x1800239f4  mov     ebx, eax
0x1800239f6  call    cs:__imp_ILFree
0x1800239fc  mov     rcx, [rbp+ppidl]; pidl
0x180023a00  call    cs:__imp_ILFree
0x180023a06  mov     eax, ebx
0x180023a08  add     rsp, 58h
0x180023a0c  pop     r15
0x180023a0e  pop     r14
0x180023a10  pop     rdi
0x180023a11  pop     rsi
0x180023a12  pop     rbx
0x180023a13  pop     rbp
0x180023a14  retn
```
