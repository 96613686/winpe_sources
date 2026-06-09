# CSyncResultsFolder::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x180039d90`
- end: `0x180039f74`
- name: `?GetUIObjectOf@CSyncResultsFolder@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `484`
- prototype: `int(CSyncResultsFolder *__hidden this, HWND, unsigned int, const struct _ITEMID_CHILD *const *, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180039d90`
- `0x18003a590`
- `0x18003aae8`
- `0x18003ac0c`
- `0x18003b394`
- `0x1800475a0`

## import_xrefs

- `SHELL32!__imp_CIDLData_CreateFromIDArray` at `0x180039e1d`
- `SHELL32!__imp_CIDLData_CreateFromIDArray` at `0x180039e1d`
- `SHELL32!__imp_ILFree` at `0x180039e29`
- `SHELL32!__imp_ILFree` at `0x180039e29`
- `SHELL32!__imp_CreateInfoTipFromItem2` at `0x180039eaf`
- `SHELL32!__imp_CreateInfoTipFromItem2` at `0x180039eaf`

## pseudocode

```c
__int64 __fastcall CSyncResultsFolder::GetUIObjectOf(
        unsigned __int64 this,
        unsigned __int16 *a2,
        UINT a3,
        LPCITEMIDLIST *a4,
        const struct _GUID *a5,
        unsigned int *a6,
        ITEMIDLIST *ppdtobj)
{
  void **v7; // rdi
  __int64 v11; // rax
  __int64 v12; // rax
  unsigned int UnfilteredSelfIDList; // ebx
  __int64 v14; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  const struct CSyncResultsFolder::IDEVENT *ValidIDEVENT; // rax
  CSyncResultsFolder *v20; // rcx
  const struct _GUID *v21; // r8
  char *v22; // rcx
  struct DEFCONTEXTMENU v24; // [rsp+30h] [rbp-50h] BYREF

  v7 = (void **)ppdtobj;
  *(_QWORD *)&ppdtobj->mkid.cb = 0;
  v11 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
    v11 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
  if ( !v11 )
  {
    v24.hwnd = (HWND)a2;
    v22 = (char *)(this - 16);
    if ( v22 )
      v24.pcmcb = (IContextMenuCB *)(this + 88);
    else
      v24.pcmcb = 0;
    v24.pidlFolder = *(LPCITEMIDLIST *)(this + 64);
    v24.cidl = a3;
    v24.apidl = a4;
    v24.psf = (IShellFolder *)(this & -(__int64)(v22 != 0));
    *(&v24.cidl + 1) = 0;
    memset(&v24.punkAssociationInfo, 0, 24);
    return (unsigned int)CRenameCanonicalMenuWrapper_CreateInstance(&v24, a2, (unsigned int)a5, a5, v7);
  }
  v12 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IDataObject.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IDataObject.Data1 )
    v12 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IDataObject.Data4;
  if ( !v12 )
  {
    ppdtobj = 0;
    UnfilteredSelfIDList = CSyncResultsFolder::_GetUnfilteredSelfIDList(
                             (CSyncResultsFolder *)(this - 16),
                             (struct _ITEMIDLIST_ABSOLUTE **)&ppdtobj);
    if ( (UnfilteredSelfIDList & 0x80000000) == 0 )
    {
      UnfilteredSelfIDList = CIDLData_CreateFromIDArray(ppdtobj, a3, a4, (IDataObject **)v7);
      ILFree(ppdtobj);
    }
    return UnfilteredSelfIDList;
  }
  v14 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data1 )
    v14 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data4;
  if ( !v14 )
    return (unsigned int)CSyncResultsFolder::_AssocCreate(
                           (CSyncResultsFolder *)this,
                           (const struct _ITEMID_CHILD *)*a4,
                           a5,
                           v7);
  UnfilteredSelfIDList = -2147467262;
  if ( a3 != 1 )
    return UnfilteredSelfIDList;
  v16 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_00021500_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_00021500_0000_0000_c000_000000000046.Data1 )
    v16 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_00021500_0000_0000_c000_000000000046.Data4;
  if ( !v16 )
    return (unsigned int)CreateInfoTipFromItem2(this & -(__int64)(this != 16), *a4, &PKEY_PropList_InfoTip, 0, a5, v7);
  v17 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_000214eb_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_000214eb_0000_0000_c000_000000000046.Data1 )
    v17 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_000214eb_0000_0000_c000_000000000046.Data4;
  if ( !v17 )
    goto LABEL_24;
  v18 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_000214fa_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_000214fa_0000_0000_c000_000000000046.Data1 )
    v18 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_000214fa_0000_0000_c000_000000000046.Data4;
  if ( !v18 )
  {
LABEL_24:
    ValidIDEVENT = CSyncResultsFolder::s_GetValidIDEVENT((const struct _ITEMIDLIST_RELATIVE *)*a4);
    return (unsigned int)CSyncResultsFolder::_GetIconExtractor(v20, ValidIDEVENT, v21, v7);
  }
  return UnfilteredSelfIDList;
}

```

## disassembly

```asm
0x180039d90  push    rbp
0x180039d92  push    rbx
0x180039d93  push    rsi
0x180039d94  push    rdi
0x180039d95  push    r14
0x180039d97  mov     rbp, rsp
0x180039d9a  sub     rsp, 80h
0x180039da1  mov     rdi, [rbp+ppdtobj]
0x180039da5  mov     r14d, r8d
0x180039da8  mov     r8, [rbp+arg_20]; unsigned int
0x180039dac  mov     rsi, r9
0x180039daf  mov     r10, rcx
0x180039db2  mov     qword ptr [rdi], 0
0x180039db9  mov     rax, [r8]
0x180039dbc  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x180039dc3  jnz     short loc_180039DD0
0x180039dc5  mov     rax, [r8+8]
0x180039dc9  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x180039dd0  test    rax, rax
0x180039dd3  jz      loc_180039F07
0x180039dd9  mov     rax, [r8]
0x180039ddc  sub     rax, qword ptr cs:IID_IDataObject.Data1
0x180039de3  jnz     short loc_180039DF0
0x180039de5  mov     rax, [r8+8]
0x180039de9  sub     rax, qword ptr cs:IID_IDataObject.Data4
0x180039df0  test    rax, rax
0x180039df3  jnz     short loc_180039E34
0x180039df5  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x180039df9  mov     [rbp+ppdtobj], rax
0x180039dfd  lea     rdx, [rbp+ppdtobj]; struct _ITEMIDLIST_ABSOLUTE **
0x180039e01  call    ?_GetUnfilteredSelfIDList@CSyncResultsFolder@@AEAAJPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CSyncResultsFolder::_GetUnfilteredSelfIDList(_ITEMIDLIST_ABSOLUTE * *)
0x180039e06  mov     ebx, eax
0x180039e08  test    eax, eax
0x180039e0a  js      loc_180039F64
0x180039e10  mov     rcx, [rbp+ppdtobj]; pidlFolder
0x180039e14  mov     r9, rdi; ppdtobj
0x180039e17  mov     r8, rsi; apidl
0x180039e1a  mov     edx, r14d; cidl
0x180039e1d  call    cs:__imp_CIDLData_CreateFromIDArray
0x180039e23  mov     rcx, [rbp+ppdtobj]; pidl
0x180039e27  mov     ebx, eax
0x180039e29  call    cs:__imp_ILFree
0x180039e2f  jmp     loc_180039F64
0x180039e34  mov     rax, [r8]
0x180039e37  sub     rax, qword ptr cs:_GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data1
0x180039e3e  jnz     short loc_180039E4B
0x180039e40  mov     rax, [r8+8]
0x180039e44  sub     rax, qword ptr cs:_GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data4
0x180039e4b  test    rax, rax
0x180039e4e  jnz     short loc_180039E60
0x180039e50  mov     rdx, [rsi]; struct _ITEMID_CHILD *
0x180039e53  mov     r9, rdi; void **
0x180039e56  call    ?_AssocCreate@CSyncResultsFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z; CSyncResultsFolder::_AssocCreate(_ITEMID_CHILD const *,_GUID const &,void * *)
0x180039e5b  jmp     loc_180039F62
0x180039e60  mov     ebx, 80004002h
0x180039e65  cmp     r14d, 1
0x180039e69  jnz     loc_180039F64
0x180039e6f  mov     rax, [r8]
0x180039e72  sub     rax, qword ptr cs:_GUID_00021500_0000_0000_c000_000000000046.Data1
0x180039e79  jnz     short loc_180039E86
0x180039e7b  mov     rax, [r8+8]
0x180039e7f  sub     rax, qword ptr cs:_GUID_00021500_0000_0000_c000_000000000046.Data4
0x180039e86  test    rax, rax
0x180039e89  jnz     short loc_180039EBA
0x180039e8b  mov     rdx, [rsi]
0x180039e8e  lea     rax, [rcx-10h]
0x180039e92  neg     rax
0x180039e95  mov     [rsp+80h+var_58], rdi
0x180039e9a  mov     [rsp+80h+var_60], r8
0x180039e9f  lea     r8, PKEY_PropList_InfoTip
0x180039ea6  sbb     rcx, rcx
0x180039ea9  xor     r9d, r9d
0x180039eac  and     rcx, r10
0x180039eaf  call    cs:__imp_CreateInfoTipFromItem2
0x180039eb5  jmp     loc_180039F62
0x180039eba  mov     rax, [r8]
0x180039ebd  sub     rax, qword ptr cs:_GUID_000214eb_0000_0000_c000_000000000046.Data1
0x180039ec4  jnz     short loc_180039ED1
0x180039ec6  mov     rax, [r8+8]
0x180039eca  sub     rax, qword ptr cs:_GUID_000214eb_0000_0000_c000_000000000046.Data4
0x180039ed1  test    rax, rax
0x180039ed4  jz      short loc_180039EF2
0x180039ed6  mov     rax, [r8]
0x180039ed9  sub     rax, qword ptr cs:_GUID_000214fa_0000_0000_c000_000000000046.Data1
0x180039ee0  jnz     short loc_180039EED
0x180039ee2  mov     rax, [r8+8]
0x180039ee6  sub     rax, qword ptr cs:_GUID_000214fa_0000_0000_c000_000000000046.Data4
0x180039eed  test    rax, rax
0x180039ef0  jnz     short loc_180039F64
0x180039ef2  mov     rcx, [r9]; struct _ITEMIDLIST_RELATIVE *
0x180039ef5  call    ?s_GetValidIDEVENT@CSyncResultsFolder@@CAPEFBUIDEVENT@1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CSyncResultsFolder::s_GetValidIDEVENT(_ITEMIDLIST_RELATIVE const *)
0x180039efa  mov     rdx, rax; struct CSyncResultsFolder::IDEVENT *
0x180039efd  mov     r9, rdi; void **
0x180039f00  call    ?_GetIconExtractor@CSyncResultsFolder@@AEAAJPEFBUIDEVENT@1@AEBU_GUID@@PEAPEAX@Z; CSyncResultsFolder::_GetIconExtractor(CSyncResultsFolder::IDEVENT const *,_GUID const &,void * *)
0x180039f05  jmp     short loc_180039F62
0x180039f07  mov     [rbp+var_50.hwnd], rdx
0x180039f0b  add     rcx, 0FFFFFFFFFFFFFFF0h
0x180039f0f  jz      short loc_180039F1B
0x180039f11  lea     rax, [r10+58h]
0x180039f15  mov     [rbp+var_50.pcmcb], rax
0x180039f19  jmp     short loc_180039F23
0x180039f1b  mov     [rbp+var_50.pcmcb], 0
0x180039f23  mov     rax, [r10+40h]
0x180039f27  neg     rcx
0x180039f2a  mov     [rbp+var_50.pidlFolder], rax
0x180039f2e  lea     rcx, [rbp+var_50]; struct DEFCONTEXTMENU *
0x180039f32  sbb     rax, rax
0x180039f35  mov     [rbp+var_50.cidl], r14d
0x180039f39  and     rax, r10
0x180039f3c  mov     [rbp+var_50.apidl], rsi
0x180039f40  mov     [rbp+var_50.psf], rax
0x180039f44  mov     r9, r8; struct _GUID *
0x180039f47  xor     eax, eax
0x180039f49  mov     [rsp+80h+var_60], rdi; void **
0x180039f4e  mov     dword ptr [rbp+var_50+24h], eax
0x180039f51  mov     [rbp+var_50.punkAssociationInfo], rax
0x180039f55  mov     qword ptr [rbp+var_50.cKeys], rax
0x180039f59  mov     [rbp+var_50.aKeys], rax
0x180039f5d  call    ?CRenameCanonicalMenuWrapper_CreateInstance@@YAJPEBUDEFCONTEXTMENU@@PEBGIAEBU_GUID@@PEAPEAX@Z; CRenameCanonicalMenuWrapper_CreateInstance(DEFCONTEXTMENU const *,ushort const *,uint,_GUID const &,void * *)
0x180039f62  mov     ebx, eax
0x180039f64  mov     eax, ebx
0x180039f66  add     rsp, 80h
0x180039f6d  pop     r14
0x180039f6f  pop     rdi
0x180039f70  pop     rsi
0x180039f71  pop     rbx
0x180039f72  pop     rbp
0x180039f73  retn
```
