# CConflictFolder::GetUIObjectOf(HWND__ *,uint,_ITEMID_CHILD const * const *,_GUID const &,uint *,void * *)

- ea: `0x180033860`
- end: `0x180033a79`
- name: `?GetUIObjectOf@CConflictFolder@@UEAAJPEAUHWND__@@IPEBQEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAIPEAPEAX@Z`
- size: `537`
- prototype: `int(CConflictFolder *__hidden this, HWND, unsigned int, const struct _ITEMID_CHILD *const *, const struct _GUID *, unsigned int *, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180033860`
- `0x18003506c`
- `0x180035134`
- `0x180036f30`
- `0x1800380b4`
- `0x1800475a0`

## import_xrefs

- `SHELL32!__imp_CIDLData_CreateFromIDArray` at `0x1800338ed`
- `SHELL32!__imp_CIDLData_CreateFromIDArray` at `0x1800338ed`
- `SHELL32!__imp_ILFree` at `0x1800338f9`
- `SHELL32!__imp_ILFree` at `0x1800338f9`
- `SHELL32!__imp_CreateInfoTipFromItem2` at `0x1800339af`
- `SHELL32!__imp_CreateInfoTipFromItem2` at `0x1800339af`

## pseudocode

```c
__int64 __fastcall CConflictFolder::GetUIObjectOf(
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
  __int64 v19; // rax
  char *v20; // rcx
  struct DEFCONTEXTMENU v22; // [rsp+30h] [rbp-50h] BYREF

  v7 = (void **)ppdtobj;
  *(_QWORD *)&ppdtobj->mkid.cb = 0;
  v11 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IContextMenu.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IContextMenu.Data1 )
    v11 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IContextMenu.Data4;
  if ( !v11 )
  {
    v22.hwnd = (HWND)a2;
    v20 = (char *)(this - 16);
    if ( v20 )
      v22.pcmcb = (IContextMenuCB *)(this + 88);
    else
      v22.pcmcb = 0;
    v22.pidlFolder = *(LPCITEMIDLIST *)(this + 64);
    v22.cidl = a3;
    v22.apidl = a4;
    v22.psf = (IShellFolder *)(this & -(__int64)(v20 != 0));
    *(&v22.cidl + 1) = 0;
    memset(&v22.punkAssociationInfo, 0, 24);
    return (unsigned int)CRenameCanonicalMenuWrapper_CreateInstance(&v22, a2, (unsigned int)a5, a5, v7);
  }
  v12 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&IID_IDataObject.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&IID_IDataObject.Data1 )
    v12 = *(_QWORD *)a5->Data4 - *(_QWORD *)IID_IDataObject.Data4;
  if ( !v12 )
  {
    ppdtobj = 0;
    UnfilteredSelfIDList = CConflictFolder::_GetUnfilteredSelfIDList(
                             (CConflictFolder *)(this - 16),
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
    return (unsigned int)CConflictFolder::_AssocCreate(
                           (CConflictFolder *)this,
                           (const struct _ITEMID_CHILD *)*a4,
                           a5,
                           v7);
  UnfilteredSelfIDList = -2147467262;
  if ( a3 != 1 )
    return UnfilteredSelfIDList;
  v16 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_9c204249_c443_4ba4_85ed_c972681db137.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_9c204249_c443_4ba4_85ed_c972681db137.Data1 )
    v16 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_9c204249_c443_4ba4_85ed_c972681db137.Data4;
  if ( !v16 )
    return (unsigned int)CConflictFolder::_BindToConflict(
                           (CConflictFolder *)(this - 16),
                           (const struct _ITEMIDLIST_RELATIVE *)*a4,
                           a5,
                           v7);
  v17 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_00021500_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_00021500_0000_0000_c000_000000000046.Data1 )
    v17 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_00021500_0000_0000_c000_000000000046.Data4;
  if ( !v17 )
    return (unsigned int)CreateInfoTipFromItem2(this & -(__int64)(this != 16), *a4, &PKEY_PropList_InfoTip, 0, a5, v7);
  v18 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_000214eb_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_000214eb_0000_0000_c000_000000000046.Data1 )
    v18 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_000214eb_0000_0000_c000_000000000046.Data4;
  if ( !v18 )
    return (unsigned int)CConflictExtractIcon::s_CreateInstance(
                           (struct IShellFolder *)(this & -(__int64)(this != 16)),
                           (const struct _ITEMID_CHILD *)*a4,
                           a5,
                           v7);
  v19 = *(_QWORD *)&a5->Data1 - *(_QWORD *)&GUID_000214fa_0000_0000_c000_000000000046.Data1;
  if ( *(_QWORD *)&a5->Data1 == *(_QWORD *)&GUID_000214fa_0000_0000_c000_000000000046.Data1 )
    v19 = *(_QWORD *)a5->Data4 - *(_QWORD *)GUID_000214fa_0000_0000_c000_000000000046.Data4;
  if ( !v19 )
    return (unsigned int)CConflictExtractIcon::s_CreateInstance(
                           (struct IShellFolder *)(this & -(__int64)(this != 16)),
                           (const struct _ITEMID_CHILD *)*a4,
                           a5,
                           v7);
  return UnfilteredSelfIDList;
}

```

## disassembly

```asm
0x180033860  push    rbp
0x180033862  push    rbx
0x180033863  push    rsi
0x180033864  push    rdi
0x180033865  push    r14
0x180033867  mov     rbp, rsp
0x18003386a  sub     rsp, 80h
0x180033871  mov     rdi, [rbp+ppdtobj]
0x180033875  mov     r14d, r8d
0x180033878  mov     r8, [rbp+arg_20]; unsigned int
0x18003387c  mov     rsi, r9
0x18003387f  mov     r10, rcx
0x180033882  mov     qword ptr [rdi], 0
0x180033889  mov     rax, [r8]
0x18003388c  sub     rax, qword ptr cs:IID_IContextMenu.Data1
0x180033893  jnz     short loc_1800338A0
0x180033895  mov     rax, [r8+8]
0x180033899  sub     rax, qword ptr cs:IID_IContextMenu.Data4
0x1800338a0  test    rax, rax
0x1800338a3  jz      loc_180033A0C
0x1800338a9  mov     rax, [r8]
0x1800338ac  sub     rax, qword ptr cs:IID_IDataObject.Data1
0x1800338b3  jnz     short loc_1800338C0
0x1800338b5  mov     rax, [r8+8]
0x1800338b9  sub     rax, qword ptr cs:IID_IDataObject.Data4
0x1800338c0  test    rax, rax
0x1800338c3  jnz     short loc_180033904
0x1800338c5  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x1800338c9  mov     [rbp+ppdtobj], rax
0x1800338cd  lea     rdx, [rbp+ppdtobj]; struct _ITEMIDLIST_ABSOLUTE **
0x1800338d1  call    ?_GetUnfilteredSelfIDList@CConflictFolder@@AEAAJPEAPEAU_ITEMIDLIST_ABSOLUTE@@@Z; CConflictFolder::_GetUnfilteredSelfIDList(_ITEMIDLIST_ABSOLUTE * *)
0x1800338d6  mov     ebx, eax
0x1800338d8  test    eax, eax
0x1800338da  js      loc_180033A69
0x1800338e0  mov     rcx, [rbp+ppdtobj]; pidlFolder
0x1800338e4  mov     r9, rdi; ppdtobj
0x1800338e7  mov     r8, rsi; apidl
0x1800338ea  mov     edx, r14d; cidl
0x1800338ed  call    cs:__imp_CIDLData_CreateFromIDArray
0x1800338f3  mov     rcx, [rbp+ppdtobj]; pidl
0x1800338f7  mov     ebx, eax
0x1800338f9  call    cs:__imp_ILFree
0x1800338ff  jmp     loc_180033A69
0x180033904  mov     rax, [r8]
0x180033907  sub     rax, qword ptr cs:_GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data1
0x18003390e  jnz     short loc_18003391B
0x180033910  mov     rax, [r8+8]
0x180033914  sub     rax, qword ptr cs:_GUID_c46ca590_3c3f_11d2_bee6_0000f805ca57.Data4
0x18003391b  test    rax, rax
0x18003391e  jnz     short loc_180033930
0x180033920  mov     rdx, [rsi]; struct _ITEMID_CHILD *
0x180033923  mov     r9, rdi; void **
0x180033926  call    ?_AssocCreate@CConflictFolder@@AEAAJPEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z; CConflictFolder::_AssocCreate(_ITEMID_CHILD const *,_GUID const &,void * *)
0x18003392b  jmp     loc_180033A67
0x180033930  mov     ebx, 80004002h
0x180033935  cmp     r14d, 1
0x180033939  jnz     loc_180033A69
0x18003393f  mov     rax, [r8]
0x180033942  sub     rax, qword ptr cs:_GUID_9c204249_c443_4ba4_85ed_c972681db137.Data1
0x180033949  jnz     short loc_180033956
0x18003394b  mov     rax, [r8+8]
0x18003394f  sub     rax, qword ptr cs:_GUID_9c204249_c443_4ba4_85ed_c972681db137.Data4
0x180033956  test    rax, rax
0x180033959  jnz     short loc_18003396F
0x18003395b  mov     rdx, [rsi]; struct _ITEMIDLIST_RELATIVE *
0x18003395e  add     rcx, 0FFFFFFFFFFFFFFF0h; this
0x180033962  mov     r9, rdi; void **
0x180033965  call    ?_BindToConflict@CConflictFolder@@AEAAJPEFBU_ITEMIDLIST_RELATIVE@@AEBU_GUID@@PEAPEAX@Z; CConflictFolder::_BindToConflict(_ITEMIDLIST_RELATIVE const *,_GUID const &,void * *)
0x18003396a  jmp     loc_180033A67
0x18003396f  mov     rax, [r8]
0x180033972  sub     rax, qword ptr cs:_GUID_00021500_0000_0000_c000_000000000046.Data1
0x180033979  jnz     short loc_180033986
0x18003397b  mov     rax, [r8+8]
0x18003397f  sub     rax, qword ptr cs:_GUID_00021500_0000_0000_c000_000000000046.Data4
0x180033986  test    rax, rax
0x180033989  jnz     short loc_1800339BA
0x18003398b  mov     rdx, [rsi]
0x18003398e  lea     rax, [rcx-10h]
0x180033992  neg     rax
0x180033995  mov     [rsp+80h+var_58], rdi
0x18003399a  mov     [rsp+80h+var_60], r8
0x18003399f  lea     r8, PKEY_PropList_InfoTip
0x1800339a6  sbb     rcx, rcx
0x1800339a9  xor     r9d, r9d
0x1800339ac  and     rcx, r10
0x1800339af  call    cs:__imp_CreateInfoTipFromItem2
0x1800339b5  jmp     loc_180033A67
0x1800339ba  mov     rax, [r8]
0x1800339bd  sub     rax, qword ptr cs:_GUID_000214eb_0000_0000_c000_000000000046.Data1
0x1800339c4  jnz     short loc_1800339D1
0x1800339c6  mov     rax, [r8+8]
0x1800339ca  sub     rax, qword ptr cs:_GUID_000214eb_0000_0000_c000_000000000046.Data4
0x1800339d1  test    rax, rax
0x1800339d4  jz      short loc_1800339F2
0x1800339d6  mov     rax, [r8]
0x1800339d9  sub     rax, qword ptr cs:_GUID_000214fa_0000_0000_c000_000000000046.Data1
0x1800339e0  jnz     short loc_1800339ED
0x1800339e2  mov     rax, [r8+8]
0x1800339e6  sub     rax, qword ptr cs:_GUID_000214fa_0000_0000_c000_000000000046.Data4
0x1800339ed  test    rax, rax
0x1800339f0  jnz     short loc_180033A69
0x1800339f2  mov     rdx, [rsi]; struct _ITEMID_CHILD *
0x1800339f5  lea     rax, [rcx-10h]
0x1800339f9  neg     rax
0x1800339fc  mov     r9, rdi; void **
0x1800339ff  sbb     rcx, rcx
0x180033a02  and     rcx, r10; struct IShellFolder *
0x180033a05  call    ?s_CreateInstance@CConflictExtractIcon@@SAJPEAUIShellFolder@@PEFBU_ITEMID_CHILD@@AEBU_GUID@@PEAPEAX@Z; CConflictExtractIcon::s_CreateInstance(IShellFolder *,_ITEMID_CHILD const *,_GUID const &,void * *)
0x180033a0a  jmp     short loc_180033A67
0x180033a0c  mov     [rbp+var_50.hwnd], rdx
0x180033a10  add     rcx, 0FFFFFFFFFFFFFFF0h
0x180033a14  jz      short loc_180033A20
0x180033a16  lea     rax, [r10+58h]
0x180033a1a  mov     [rbp+var_50.pcmcb], rax
0x180033a1e  jmp     short loc_180033A28
0x180033a20  mov     [rbp+var_50.pcmcb], 0
0x180033a28  mov     rax, [r10+40h]
0x180033a2c  neg     rcx
0x180033a2f  mov     [rbp+var_50.pidlFolder], rax
0x180033a33  lea     rcx, [rbp+var_50]; struct DEFCONTEXTMENU *
0x180033a37  sbb     rax, rax
0x180033a3a  mov     [rbp+var_50.cidl], r14d
0x180033a3e  and     rax, r10
0x180033a41  mov     [rbp+var_50.apidl], rsi
0x180033a45  mov     [rbp+var_50.psf], rax
0x180033a49  mov     r9, r8; struct _GUID *
0x180033a4c  xor     eax, eax
0x180033a4e  mov     [rsp+80h+var_60], rdi; void **
0x180033a53  mov     dword ptr [rbp+var_50+24h], eax
0x180033a56  mov     [rbp+var_50.punkAssociationInfo], rax
0x180033a5a  mov     qword ptr [rbp+var_50.cKeys], rax
0x180033a5e  mov     [rbp+var_50.aKeys], rax
0x180033a62  call    ?CRenameCanonicalMenuWrapper_CreateInstance@@YAJPEBUDEFCONTEXTMENU@@PEBGIAEBU_GUID@@PEAPEAX@Z; CRenameCanonicalMenuWrapper_CreateInstance(DEFCONTEXTMENU const *,ushort const *,uint,_GUID const &,void * *)
0x180033a67  mov     ebx, eax
0x180033a69  mov     eax, ebx
0x180033a6b  add     rsp, 80h
0x180033a72  pop     r14
0x180033a74  pop     rdi
0x180033a75  pop     rsi
0x180033a76  pop     rbx
0x180033a77  pop     rbp
0x180033a78  retn
```
