# CFilteredItemFactory::RemoveFilterForProperty(IShellItem *,_tagpropertykey const &,_GUID const &,void * *)

- ea: `0x1800be7d0`
- end: `0x1800be925`
- name: `?RemoveFilterForProperty@CFilteredItemFactory@@UEAAJPEAUIShellItem@@AEBU_tagpropertykey@@AEBU_GUID@@PEAPEAX@Z`
- size: `341`
- prototype: `int(CFilteredItemFactory *__hidden this, struct IShellItem *, const struct _tagpropertykey *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1800435e0`
- `0x1800515ac`
- `0x1800be7d0`
- `0x1800be9c4`
- `0x1800bfa94`
- `0x1800bfe98`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFindLastID` at `0x1800be8aa`
- `Windows.Storage!ILFindLastID` at `0x1800be8aa`
- `Windows.Storage!ILFree` at `0x1800be8e6`
- `Windows.Storage!ILFree` at `0x1800be906`
- `Windows.Storage!ILFree` at `0x1800be910`
- `Windows.Storage!ILFree` at `0x1800be8e6`
- `Windows.Storage!ILFree` at `0x1800be906`
- `Windows.Storage!ILFree` at `0x1800be910`
- `Windows.Storage!SHGetIDListFromObject` at `0x1800be803`
- `Windows.Storage!SHGetIDListFromObject` at `0x1800be803`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1800be8fa`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1800be8fa`
- `Windows.Storage!ILRemoveLastID` at `0x1800be8c9`
- `Windows.Storage!ILRemoveLastID` at `0x1800be8c9`

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
0x1800be7d0  push    rbp
0x1800be7d2  push    rbx
0x1800be7d3  push    rsi
0x1800be7d4  push    rdi
0x1800be7d5  push    r14
0x1800be7d7  push    r15
0x1800be7d9  mov     rbp, rsp
0x1800be7dc  sub     rsp, 58h
0x1800be7e0  mov     r14, [rbp+pidl]
0x1800be7e4  mov     rsi, rdx
0x1800be7e7  lea     rdx, [rbp+ppidl]; ppidl
0x1800be7eb  mov     [rbp+ppidl], 0
0x1800be7f3  mov     rcx, rsi; punk
0x1800be7f6  mov     r15, r9
0x1800be7f9  mov     rdi, r8
0x1800be7fc  mov     qword ptr [r14], 0
0x1800be803  call    cs:__imp_SHGetIDListFromObject
0x1800be809  mov     ebx, eax
0x1800be80b  test    eax, eax
0x1800be80d  js      loc_1800BE916
0x1800be813  mov     rax, [rsi]
0x1800be816  lea     rcx, [rbp+var_18]
0x1800be81a  mov     [rsp+58h+var_38], rcx
0x1800be81f  lea     r9, _GUID_711b2cfd_93d1_422b_bdf4_69be923f2449
0x1800be826  lea     r8, BHID_SFObject
0x1800be82d  mov     [rbp+var_20], 0
0x1800be835  xor     edx, edx
0x1800be837  mov     [rbp+var_18], 0
0x1800be83f  mov     rax, [rax+18h]
0x1800be843  mov     rcx, rsi
0x1800be846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be84b  test    eax, eax
0x1800be84d  js      short loc_1800BE89E
0x1800be84f  mov     rbx, [rbp+ppidl]
0x1800be853  lea     r8, [rbp+pidl]; unsigned int *
0x1800be857  mov     rcx, rbx; struct _ITEMIDLIST_ABSOLUTE *
0x1800be85a  mov     dword ptr [rbp+pidl], 0
0x1800be861  mov     rdx, rdi; struct _tagpropertykey *
0x1800be864  call    ?_GetPropertyFilterFromIDList@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@AEBU_tagpropertykey@@PEAIPEAPEAUIFilterCondition@@@Z; _GetPropertyFilterFromIDList(_ITEMIDLIST_ABSOLUTE const *,_tagpropertykey const &,uint *,IFilterCondition * *)
0x1800be869  mov     rcx, rbx; struct _ITEMIDLIST_RELATIVE *
0x1800be86c  test    eax, eax
0x1800be86e  js      short loc_1800BE881
0x1800be870  mov     edx, dword ptr [rbp+pidl]
0x1800be873  lea     r9, [rbp+var_20]
0x1800be877  xor     r8d, r8d
0x1800be87a  call    ModifyOrRemoveFilterByIndex
0x1800be87f  jmp     short loc_1800BE88A
0x1800be881  lea     rdx, [rbp+var_20]; struct _ITEMIDLIST_RELATIVE **
0x1800be885  call    ?SHILClone@@YAJPEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILClone(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE * *)
0x1800be88a  mov     rcx, [rbp+var_18]
0x1800be88e  mov     ebx, eax
0x1800be890  mov     rax, [rcx]
0x1800be893  mov     rax, [rax+10h]
0x1800be897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be89c  jmp     short loc_1800BE8EC
0x1800be89e  mov     rcx, [rbp+ppidl]; pidl
0x1800be8a2  mov     [rbp+pidl], 0
0x1800be8aa  call    cs:__imp_ILFindLastID
0x1800be8b0  lea     r9, [rbp+pidl]; struct _ITEMID_CHILD **
0x1800be8b4  mov     rdx, rdi; struct _tagpropertykey *
0x1800be8b7  mov     rcx, rax; struct _ITEMID_CHILD *
0x1800be8ba  call    ?SHSetFilterToIDList@@YAJPEFBU_ITEMID_CHILD@@AEBU_tagpropertykey@@PEAUIFilterCondition@@PEAPEAU1@@Z; SHSetFilterToIDList(_ITEMID_CHILD const *,_tagpropertykey const &,IFilterCondition *,_ITEMID_CHILD * *)
0x1800be8bf  mov     ebx, eax
0x1800be8c1  test    eax, eax
0x1800be8c3  js      short loc_1800BE90C
0x1800be8c5  mov     rcx, [rbp+ppidl]; pidl
0x1800be8c9  call    cs:__imp_ILRemoveLastID
0x1800be8cf  mov     rdx, [rbp+pidl]; struct _ITEMIDLIST_RELATIVE *
0x1800be8d3  lea     r8, [rbp+var_20]; struct _ITEMIDLIST_ABSOLUTE **
0x1800be8d7  mov     rcx, [rbp+ppidl]; struct _ITEMIDLIST_ABSOLUTE *
0x1800be8db  call    ?SHILCombine@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMIDLIST_RELATIVE@@PEAPEAU1@@Z; SHILCombine(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_ABSOLUTE * *)
0x1800be8e0  mov     rcx, [rbp+pidl]; pidl
0x1800be8e4  mov     ebx, eax
0x1800be8e6  call    cs:__imp_ILFree
0x1800be8ec  test    ebx, ebx
0x1800be8ee  js      short loc_1800BE90C
0x1800be8f0  mov     rcx, [rbp+var_20]; pidl
0x1800be8f4  mov     r8, r14; ppv
0x1800be8f7  mov     rdx, r15; riid
0x1800be8fa  call    cs:__imp_SHCreateItemFromIDList
0x1800be900  mov     rcx, [rbp+var_20]; pidl
0x1800be904  mov     ebx, eax
0x1800be906  call    cs:__imp_ILFree
0x1800be90c  mov     rcx, [rbp+ppidl]; pidl
0x1800be910  call    cs:__imp_ILFree
0x1800be916  mov     eax, ebx
0x1800be918  add     rsp, 58h
0x1800be91c  pop     r15
0x1800be91e  pop     r14
0x1800be920  pop     rdi
0x1800be921  pop     rsi
0x1800be922  pop     rbx
0x1800be923  pop     rbp
0x1800be924  retn
```
