# CDBFolder::Initialize(_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x18000ac10`
- end: `0x18000b647`
- name: `?Initialize@CDBFolder@@UEAAJPEBU_ITEMIDLIST_ABSOLUTE@@@Z`
- size: `2615`
- prototype: `int(CDBFolder *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000c560`

## callees

- `0x18000ac10`
- `0x18000b650`
- `0x18000b6d0`
- `0x18000ccdc`
- `0x18000e450`
- `0x180035860`
- `0x180071dc0`
- `0x180072cd0`
- `0x180072cdc`
- `0x180072cf4`
- `0x1800ea010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x18000b4b8`
- `SHCORE!IUnknown_Set` at `0x18000b4b8`
- `Windows.Storage!ILFindLastID` at `0x18000ace3`
- `Windows.Storage!ILFindLastID` at `0x18000ad27`
- `Windows.Storage!ILFindLastID` at `0x18000ad65`
- `Windows.Storage!ILFindLastID` at `0x18000adc8`
- `Windows.Storage!ILFindLastID` at `0x18000ae08`
- `Windows.Storage!ILFindLastID` at `0x18000ae94`
- `Windows.Storage!ILFindLastID` at `0x18000af34`
- `Windows.Storage!ILFindLastID` at `0x18000af74`
- `Windows.Storage!ILFindLastID` at `0x18000b057`
- `Windows.Storage!ILFindLastID` at `0x18000b063`
- `Windows.Storage!ILFindLastID` at `0x18000b0a9`
- `Windows.Storage!ILFindLastID` at `0x18000ace3`
- `Windows.Storage!ILFindLastID` at `0x18000ad27`
- `Windows.Storage!ILFindLastID` at `0x18000ad65`
- `Windows.Storage!ILFindLastID` at `0x18000adc8`
- `Windows.Storage!ILFindLastID` at `0x18000ae08`
- `Windows.Storage!ILFindLastID` at `0x18000ae94`
- `Windows.Storage!ILFindLastID` at `0x18000af34`
- `Windows.Storage!ILFindLastID` at `0x18000af74`
- `Windows.Storage!ILFindLastID` at `0x18000b057`
- `Windows.Storage!ILFindLastID` at `0x18000b063`
- `Windows.Storage!ILFindLastID` at `0x18000b0a9`
- `Windows.Storage!ILFree` at `0x18000af1f`
- `Windows.Storage!ILFree` at `0x18000b039`
- `Windows.Storage!ILFree` at `0x18000b14b`
- `Windows.Storage!ILFree` at `0x18000b15d`
- `Windows.Storage!ILFree` at `0x18000af1f`
- `Windows.Storage!ILFree` at `0x18000b039`
- `Windows.Storage!ILFree` at `0x18000b14b`
- `Windows.Storage!ILFree` at `0x18000b15d`
- `Windows.Storage!ILClone` at `0x18000ad9f`
- `Windows.Storage!ILClone` at `0x18000b1d8`
- `Windows.Storage!ILClone` at `0x18000ad9f`
- `Windows.Storage!ILClone` at `0x18000b1d8`
- `Windows.Storage!ILGetSize` at `0x18000ae4f`
- `Windows.Storage!ILGetSize` at `0x18000ae4f`
- `Windows.Storage!__imp_SHGetTopViewDescription` at `0x18000b427`
- `Windows.Storage!__imp_SHGetTopViewDescription` at `0x18000b427`
- `Windows.Storage!__imp_?UpdateAutoListInitFromTopViewDesc@@YAJPEAUITopViewDescription@@PEAUIShellItem@@PEAUAUTOLISTINIT@@@Z` at `0x18000b46f`
- `Windows.Storage!__imp_?UpdateAutoListInitFromTopViewDesc@@YAJPEAUITopViewDescription@@PEAUIShellItem@@PEAUAUTOLISTINIT@@@Z` at `0x18000b46f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ae5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ae5c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b4dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b4e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000af03`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b4dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000b4e7`

## pseudocode

```c
__int64 __fastcall CDBFolder::Initialize(CDBFolder *this, const ITEMIDLIST *a2)
{
  CDBFolder *v2; // r14
  __int64 v3; // rcx
  __int64 (__fastcall ***v5)(_QWORD, GUID *, __int64 *); // rcx
  BOOL v6; // r12d
  int v7; // eax
  int AUTOLISTINITFromAutoListDescription; // esi
  const struct _ITEMIDLIST_RELATIVE *ID; // rbx
  const struct _HIDDENITEMID *HiddenID; // rcx
  unsigned __int64 v11; // rbx
  LPITEMIDLIST v12; // rax
  LPITEMIDLIST v13; // rdx
  unsigned __int64 cb; // rax
  const struct _ITEMIDLIST_RELATIVE *v15; // rbx
  const struct _HIDDENITEMID *v16; // rcx
  unsigned __int64 v17; // rbx
  ITEMIDLIST *v18; // rsi
  const ITEMIDLIST *v19; // rax
  ITEMIDLIST *v20; // r14
  int v21; // edi
  LPITEMIDLIST v22; // rax
  LPITEMIDLIST v23; // r13
  unsigned __int64 v24; // rax
  const struct _ITEMIDLIST_RELATIVE *v25; // rdi
  const struct _HIDDENITEMID *v26; // rcx
  unsigned __int64 v27; // rdi
  ITEMIDLIST *v28; // r15
  UINT v29; // r13d
  ITEMIDLIST *v30; // rax
  size_t v31; // rax
  const struct _ITEMIDLIST_RELATIVE *v32; // r12
  const struct _ITEMIDLIST_RELATIVE *v33; // rcx
  unsigned __int16 v34; // r8
  int v35; // eax
  unsigned __int16 *v36; // rdx
  LPITEMIDLIST v37; // rax
  LPITEMIDLIST v38; // r13
  unsigned __int64 v39; // rax
  BYTE *v40; // r13
  const struct _ITEMIDLIST_RELATIVE *v41; // r15
  const struct _HIDDENITEMID *v42; // rcx
  unsigned __int64 v43; // r15
  unsigned __int16 *v44; // rdx
  __int128 v45; // xmm0
  DWORD pid; // esi
  unsigned int v47; // ecx
  const ITEMIDLIST *v48; // rdi
  LPITEMIDLIST v49; // rax
  LPITEMIDLIST v50; // rdx
  unsigned __int64 v51; // rax
  const struct _ITEMIDLIST_RELATIVE *v52; // rdi
  const struct _HIDDENITEMID *v53; // rcx
  unsigned __int64 v54; // rdi
  BYTE *v55; // rdx
  const struct _HIDDENITEMID *v56; // r8
  unsigned __int16 *v57; // r9
  unsigned __int16 *abID; // rdx
  LPITEMIDLIST v60; // rax
  const struct _HIDDENITEMID *v61; // r8
  unsigned __int16 *v62; // r9
  const struct _HIDDENITEMID *v63; // r8
  unsigned __int16 *v64; // rdx
  const struct _HIDDENITEMID *v65; // rdx
  unsigned __int16 *v66; // r9
  __int128 v67; // xmm0
  int v68; // ebx
  unsigned __int16 *v69; // r8
  __int64 v70; // rcx
  const struct _HIDDENITEMID *v71; // r9
  unsigned __int16 *v72; // r8
  unsigned int v73; // ebx
  __int64 v74; // [rsp+28h] [rbp-E0h] BYREF
  IUnknown *punk; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v76; // [rsp+38h] [rbp-D0h]
  struct ITopViewDescription *v77; // [rsp+40h] [rbp-C8h] BYREF
  CDBFolder *v78; // [rsp+48h] [rbp-C0h]
  _BYTE v79[84]; // [rsp+58h] [rbp-B0h] BYREF
  int v80; // [rsp+ACh] [rbp-5Ch]
  LPVOID pv; // [rsp+B0h] [rbp-58h]
  LPVOID v82; // [rsp+C0h] [rbp-48h]
  PROPERTYKEY Buf2; // [rsp+108h] [rbp+0h] BYREF
  __int128 Buf1; // [rsp+120h] [rbp+18h] BYREF
  int v85; // [rsp+130h] [rbp+28h]
  __int128 v86; // [rsp+138h] [rbp+30h] BYREF
  __int128 v87; // [rsp+148h] [rbp+40h] BYREF
  __int128 v88; // [rsp+158h] [rbp+50h] BYREF
  __int128 v89; // [rsp+168h] [rbp+60h] BYREF

  v2 = this;
  v78 = this;
  v3 = *((_QWORD *)this + 32);
  if ( !v3 )
    return 2147549183LL;
  Buf2 = PKEY_Null;
  (*(void (__fastcall **)(__int64, _QWORD, PROPERTYKEY *))(*(_QWORD *)v3 + 40LL))(v3, 0, &Buf2);
  v5 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)v2 + 32);
  v6 = 0;
  v74 = 0;
  v7 = (**v5)(v5, &GUID_607c87f7_0696_4558_a368_de5e59cfe456, &v74);
  LODWORD(v76) = 1;
  if ( v7 < 0 )
    goto LABEL_7;
  v86 = 0;
  v87 = 0;
  if ( !a2 || !a2->mkid.cb )
  {
LABEL_122:
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
    goto LABEL_7;
  }
  AUTOLISTINITFromAutoListDescription = 0;
  ID = (const struct _ITEMIDLIST_RELATIVE *)ILFindLastID(a2);
  HiddenID = ILFindFirstHiddenID(ID);
  v11 = (unsigned __int64)ID + *(unsigned __int16 *)ID;
  if ( !HiddenID )
    goto LABEL_6;
  while ( 1 )
  {
    v66 = (unsigned __int16 *)((char *)HiddenID + 8);
    if ( *((_DWORD *)HiddenID + 1) == -1091633127 )
      break;
    v65 = 0;
    if ( (unsigned __int64)v66 <= v11 )
    {
      v69 = (unsigned __int16 *)((char *)HiddenID + *(unsigned __int16 *)HiddenID);
      if ( v69 == (unsigned __int16 *)v11 )
        goto LABEL_122;
      if ( (unsigned __int64)v69 <= v11 )
      {
        if ( (unsigned __int64)(v69 + 4) > v11
          || HIWORD(*((_DWORD *)v69 + 1)) != 0xBEEF
          || (unsigned __int64)v69 + *v69 > v11
          || v69 < v66 )
        {
          goto LABEL_122;
        }
        v65 = (const struct _HIDDENITEMID *)((char *)HiddenID + *(unsigned __int16 *)HiddenID);
      }
    }
    HiddenID = v65;
    if ( !v65 )
      goto LABEL_122;
  }
  v67 = *(_OWORD *)v66;
  punk = 0;
  v86 = v67;
  v87 = *(_OWORD *)((char *)HiddenID + 24);
  v88 = 0;
  v89 = 0;
  if ( (**(int (__fastcall ***)(__int64, GUID *, IUnknown **))v74)(
         v74,
         &GUID_8279feb8_5ca4_45c4_be27_770dcdea1deb,
         &punk) >= 0 )
  {
    v68 = ((__int64 (__fastcall *)(IUnknown *, __int128 *))punk->lpVtbl[1].QueryInterface)(punk, &v88);
    ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
    if ( v68 >= 0 && !memcmp_0(&v88, &v86, 0x10u) && !memcmp_0(&v89, &v87, 0x10u) )
    {
      v70 = *((_QWORD *)v2 + 32);
      v85 = 0;
      Buf1 = 0;
      v6 = (*(int (__fastcall **)(__int64, _QWORD, __int128 *))(*(_QWORD *)v70 + 40LL))(v70, 0, &Buf1) >= 0;
      goto LABEL_122;
    }
  }
  v77 = 0;
  AUTOLISTINITFromAutoListDescription = SHGetTopViewDescription(&v86, &GUID_fe812157_522c_46cb_8d53_6efe3dce2c46, &v77);
  if ( AUTOLISTINITFromAutoListDescription >= 0 )
  {
    memset_0(v79, 0, 0xB0u);
    AUTOLISTINITFromAutoListDescription = GetAUTOLISTINITFromAutoListDescription(v74, 3, v79);
    if ( AUTOLISTINITFromAutoListDescription >= 0 )
    {
      AUTOLISTINITFromAutoListDescription = UpdateAutoListInitFromTopViewDesc(v77, 0, (struct AUTOLISTINIT *)v79);
      if ( AUTOLISTINITFromAutoListDescription >= 0 )
      {
        if ( v80 )
          v6 = 1;
        punk = 0;
        AUTOLISTINITFromAutoListDescription = CAutoList::s_CreateInstance(
                                                (const struct AUTOLISTINIT *)v79,
                                                0,
                                                &GUID_077386d3_344c_4e33_aa67_31408b2ee7a8,
                                                (void **)&punk);
        if ( AUTOLISTINITFromAutoListDescription >= 0 )
        {
          IUnknown_Set((IUnknown **)v2 + 32, punk);
          ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
        }
      }
    }
    ClearAutoListInit((struct AUTOLISTINIT *)v79);
    CoTaskMemFree(pv);
    CoTaskMemFree(v82);
    (*(void (__fastcall **)(struct ITopViewDescription *))(*(_QWORD *)v77 + 16LL))(v77);
  }
LABEL_6:
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74);
  if ( AUTOLISTINITFromAutoListDescription < 0 )
    return (unsigned int)AUTOLISTINITFromAutoListDescription;
LABEL_7:
  v12 = ILFindLastID(a2);
  v13 = v12;
  if ( !v12
    || (cb = v12->mkid.cb, (unsigned int)cb < 0x2E)
    || *(_DWORD *)&v13[2].mkid.cb != 269752705
    || cb < (unsigned __int64)*(unsigned __int16 *)((char *)&v13[3].mkid.cb + 1) + 46
    || (abID = (unsigned __int16 *)v13[4].mkid.abID) == 0 )
  {
    if ( !a2
      || !a2->mkid.cb
      || (v15 = (const struct _ITEMIDLIST_RELATIVE *)ILFindLastID(a2),
          v16 = ILFindFirstHiddenID(v15),
          v17 = (unsigned __int64)v15 + *(unsigned __int16 *)v15,
          !v16) )
    {
LABEL_14:
      if ( !v6 )
        goto LABEL_15;
      goto LABEL_95;
    }
    while ( 1 )
    {
      abID = (unsigned __int16 *)((char *)v16 + 8);
      if ( *((_DWORD *)v16 + 1) == -1091633133 )
        break;
      v61 = 0;
      if ( (unsigned __int64)abID <= v17 )
      {
        v62 = (unsigned __int16 *)((char *)v16 + *(unsigned __int16 *)v16);
        if ( v62 == (unsigned __int16 *)v17 )
          goto LABEL_14;
        if ( (unsigned __int64)v62 <= v17 )
        {
          if ( (unsigned __int64)(v62 + 4) > v17
            || HIWORD(*((_DWORD *)v62 + 1)) != 0xBEEF
            || (unsigned __int64)v62 + *v62 > v17
            || v62 < abID )
          {
            goto LABEL_14;
          }
          v61 = (const struct _HIDDENITEMID *)((char *)v16 + *(unsigned __int16 *)v16);
        }
      }
      v16 = v61;
      if ( !v61 )
        goto LABEL_14;
    }
  }
  if ( !v6 || (*((_DWORD *)abID + 7) & 0x2000) != 0 )
  {
    v73 = -2147024809;
    if ( a2 )
    {
      v60 = ILClone(a2);
      v21 = 0;
      v18 = v60;
      if ( !v60 )
        v21 = -2147024882;
      goto LABEL_54;
    }
    v18 = 0;
    goto LABEL_156;
  }
LABEL_95:
  (*(void (__fastcall **)(_QWORD, _QWORD, PROPERTYKEY *))(**((_QWORD **)v2 + 32) + 40LL))(
    *((_QWORD *)v2 + 32),
    0,
    &Buf2);
LABEL_15:
  v18 = 0;
  if ( !a2 )
  {
    v73 = -2147024809;
LABEL_156:
    v21 = -2147024809;
    goto LABEL_54;
  }
  v19 = ILClone(a2);
  v20 = (ITEMIDLIST *)v19;
  if ( v19 )
  {
    v22 = ILFindLastID(v19);
    v23 = v22;
    v73 = -2147024809;
    if ( !v22
      || (v24 = v22->mkid.cb, (unsigned int)v24 < 0x2E)
      || *(_DWORD *)&v23[2].mkid.cb != 269752705
      || v24 < (unsigned __int64)*(unsigned __int16 *)((char *)&v23[3].mkid.cb + 1) + 46
      || (v40 = v23[4].mkid.abID) == 0 )
    {
      if ( !v20->mkid.cb
        || (v25 = (const struct _ITEMIDLIST_RELATIVE *)ILFindLastID(v20),
            v26 = ILFindFirstHiddenID(v25),
            v27 = (unsigned __int64)v25 + *(unsigned __int16 *)v25,
            !v26) )
      {
LABEL_24:
        v21 = -2147024882;
        v28 = v20;
        LODWORD(v74) = PKEY_Null.pid;
        if ( v20->mkid.cb )
        {
          v29 = ILGetSize(v20);
          v30 = (ITEMIDLIST *)CoTaskMemAlloc(v29 + 42);
          v28 = v30;
          if ( v30 )
          {
            v31 = CTCoAllocPolicy::_CoTaskMemSize(v30);
            memset_0(v28, 0, v31);
            memcpy_0(v28, v20, v29);
            v32 = (const struct _ITEMIDLIST_RELATIVE *)ILFindLastID(v28);
            if ( ILFindFirstHiddenID(v32) )
              v33 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v32 + *(unsigned __int16 *)v32 - 2);
            else
              v33 = v32;
            v34 = *(_WORD *)v33;
            v35 = v74;
            v36 = (unsigned __int16 *)((char *)v28 + v29 - 2);
            *(_DWORD *)v36 = 40;
            *((_DWORD *)v36 + 1) = -1091633133;
            *((_DWORD *)v36 + 2) = 0x20000000;
            *(GUID *)(v36 + 6) = PKEY_Null.fmtid;
            *((_DWORD *)v36 + 7) = v35;
            *((_DWORD *)v36 + 8) = 0;
            *((_DWORD *)v36 + 9) = 1;
            *v36 = 42;
            if ( (unsigned __int16)(*(_WORD *)v32 + 42) >= *(_WORD *)v32 )
            {
              *(_WORD *)v32 += 42;
              *(unsigned __int16 *)((char *)v36 + *v36 - 2) = v34;
            }
            else
            {
              CoTaskMemFree(v28);
              v28 = 0;
            }
          }
          ILFree(v20);
        }
        v20 = v28;
        if ( !v28 )
          goto LABEL_53;
        v37 = ILFindLastID(v28);
        v38 = v37;
        if ( v37
          && (v39 = v37->mkid.cb, (unsigned int)v39 >= 0x2E)
          && *(_DWORD *)&v38[2].mkid.cb == 269752705
          && v39 >= (unsigned __int64)*(unsigned __int16 *)((char *)&v38[3].mkid.cb + 1) + 46 )
        {
          v40 = v38[4].mkid.abID;
          if ( v40 )
            goto LABEL_42;
        }
        else
        {
          v40 = 0;
        }
        v21 = -2147024809;
        if ( !v28->mkid.cb
          || (v41 = (const struct _ITEMIDLIST_RELATIVE *)ILFindLastID(v28),
              v42 = ILFindFirstHiddenID(v41),
              v43 = (unsigned __int64)v41 + *(unsigned __int16 *)v41,
              !v42) )
        {
LABEL_43:
          if ( v21 < 0 )
          {
LABEL_53:
            ILFree(v20);
            v2 = v78;
            goto LABEL_54;
          }
LABEL_44:
          v45 = *(_OWORD *)(v40 + 4);
          pid = Buf2.pid;
          v85 = *((_DWORD *)v40 + 5);
          Buf1 = v45;
          if ( v85 != Buf2.pid || memcmp_0(&Buf1, &Buf2, 0x10u) )
          {
            if ( pid || memcmp_0(&Buf2, &PKEY_Null, 0x10u) )
              LODWORD(v76) = 0;
            v47 = *((_DWORD *)v40 + 7) & 0xFFFFEFFF;
            if ( !(_DWORD)v76 )
              v47 = *((_DWORD *)v40 + 7) | 0x1000;
            *((_DWORD *)v40 + 7) = v47 & 0xFFFFDFFF;
            *(GUID *)(v40 + 4) = Buf2.fmtid;
            *(_QWORD *)(v40 + 20) = Buf2.pid;
          }
          v18 = v20;
          v20 = 0;
          goto LABEL_53;
        }
        while ( 1 )
        {
          v44 = (unsigned __int16 *)((char *)v42 + 8);
          if ( *((_DWORD *)v42 + 1) == -1091633133 )
            break;
          v71 = 0;
          if ( (unsigned __int64)v44 <= v43 )
          {
            v72 = (unsigned __int16 *)((char *)v42 + *(unsigned __int16 *)v42);
            if ( v72 == (unsigned __int16 *)v43 )
              goto LABEL_43;
            if ( (unsigned __int64)v72 <= v43 )
            {
              if ( (unsigned __int64)(v72 + 4) > v43
                || HIWORD(*((_DWORD *)v72 + 1)) != 0xBEEF
                || (unsigned __int64)v72 + *v72 > v43
                || v72 < v44 )
              {
                goto LABEL_43;
              }
              v71 = (const struct _HIDDENITEMID *)((char *)v42 + *(unsigned __int16 *)v42);
            }
          }
          v42 = v71;
          if ( !v71 )
            goto LABEL_43;
        }
        v40 = (BYTE *)v42 + 8;
LABEL_42:
        v21 = 0;
        goto LABEL_43;
      }
      while ( 1 )
      {
        v40 = (BYTE *)v26 + 8;
        if ( *((_DWORD *)v26 + 1) == -1091633133 )
          break;
        v63 = 0;
        if ( (unsigned __int64)v40 <= v27 )
        {
          v64 = (unsigned __int16 *)((char *)v26 + *(unsigned __int16 *)v26);
          if ( v64 == (unsigned __int16 *)v27 )
            goto LABEL_24;
          if ( (unsigned __int64)v64 <= v27 )
          {
            if ( (unsigned __int64)(v64 + 4) > v27
              || HIWORD(*((_DWORD *)v64 + 1)) != 0xBEEF
              || (unsigned __int64)v64 + *v64 > v27
              || v64 < (unsigned __int16 *)v40 )
            {
              goto LABEL_24;
            }
            v63 = (const struct _HIDDENITEMID *)((char *)v26 + *(unsigned __int16 *)v26);
          }
        }
        v26 = v63;
        if ( !v63 )
          goto LABEL_24;
      }
    }
    v21 = 0;
    goto LABEL_44;
  }
  v21 = -2147024882;
  v2 = v78;
  v73 = -2147024809;
LABEL_54:
  if ( v21 >= 0 )
  {
    v48 = ILFindLastID(v18);
    v49 = ILFindLastID(v48);
    v50 = v49;
    if ( !v49
      || (v51 = v49->mkid.cb, (unsigned int)v51 < 0x2E)
      || *(_DWORD *)&v50[2].mkid.cb != 269752705
      || v51 < (unsigned __int64)*(unsigned __int16 *)((char *)&v50[3].mkid.cb + 1) + 46
      || (v55 = v50[4].mkid.abID) == 0 )
    {
      if ( !v48 )
        goto LABEL_74;
      if ( !v48->mkid.cb )
        goto LABEL_74;
      v52 = (const struct _ITEMIDLIST_RELATIVE *)ILFindLastID(v48);
      v53 = ILFindFirstHiddenID(v52);
      v54 = (unsigned __int64)v52 + *(unsigned __int16 *)v52;
      if ( !v53 )
        goto LABEL_74;
      while ( 1 )
      {
        v55 = (BYTE *)v53 + 8;
        if ( *((_DWORD *)v53 + 1) == -1091633133 )
          break;
        v56 = 0;
        if ( (unsigned __int64)v55 <= v54 )
        {
          v57 = (unsigned __int16 *)((char *)v53 + *(unsigned __int16 *)v53);
          if ( v57 == (unsigned __int16 *)v54 )
            goto LABEL_74;
          if ( (unsigned __int64)v57 <= v54 )
          {
            if ( (unsigned __int64)(v57 + 4) > v54
              || HIWORD(*((_DWORD *)v57 + 1)) != 0xBEEF
              || (unsigned __int64)v57 + *v57 > v54
              || v57 < (unsigned __int16 *)v55 )
            {
              goto LABEL_74;
            }
            v56 = (const struct _HIDDENITEMID *)((char *)v53 + *(unsigned __int16 *)v53);
          }
        }
        v53 = v56;
        if ( !v56 )
          goto LABEL_74;
      }
    }
    v73 = 0;
    *((_OWORD *)v2 + 14) = *(_OWORD *)(v55 + 4);
    *((_DWORD *)v2 + 60) = *((_DWORD *)v55 + 5);
    ILFree(*((LPITEMIDLIST *)v2 + 27));
    *((_QWORD *)v2 + 27) = v18;
    v18 = 0;
LABEL_74:
    ILFree(v18);
    return v73;
  }
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18000ac10  mov     r11, rsp
0x18000ac13  push    rbp
0x18000ac14  push    rdi
0x18000ac15  push    r14
0x18000ac17  push    r15
0x18000ac19  lea     rbp, [r11-0C8h]
0x18000ac20  sub     rsp, 1A8h
0x18000ac27  mov     rax, cs:__security_cookie
0x18000ac2e  xor     rax, rsp
0x18000ac31  mov     [rbp+0C0h+var_50], rax
0x18000ac35  mov     r14, rcx
0x18000ac38  mov     [rsp+1C0h+var_180], rcx
0x18000ac3d  mov     rcx, [rcx+100h]
0x18000ac44  mov     rdi, rdx
0x18000ac47  test    rcx, rcx
0x18000ac4a  jz      loc_18000B19F
0x18000ac50  mov     eax, cs:PKEY_Null.pid
0x18000ac56  lea     r8, [rbp+0C0h+Buf2]
0x18000ac5a  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x18000ac61  mov     [r11-28h], rsi
0x18000ac65  xor     edx, edx
0x18000ac67  mov     [rbp+0C0h+var_B0], eax
0x18000ac6a  mov     [r11-30h], r12
0x18000ac6e  movups  [rbp+0C0h+Buf2], xmm0
0x18000ac72  mov     rax, [rcx]
0x18000ac75  mov     [r11-38h], r13
0x18000ac79  mov     [r11+18h], rbx
0x18000ac7d  mov     rax, [rax+28h]
0x18000ac81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac86  mov     rcx, [r14+100h]
0x18000ac8d  lea     r8, [rsp+1C0h+var_1A0]
0x18000ac92  xor     r12d, r12d
0x18000ac95  lea     rdx, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x18000ac9c  mov     [rsp+1C0h+var_1A0], r12
0x18000aca1  mov     rax, [rcx]
0x18000aca4  mov     rax, [rax]
0x18000aca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acac  mov     r13d, 1
0x18000acb2  mov     esi, 0BEEFh
0x18000acb7  mov     dword ptr [rsp+1C0h+var_190], r13d
0x18000acbc  test    eax, eax
0x18000acbe  js      short loc_18000AD24
0x18000acc0  xorps   xmm0, xmm0
0x18000acc3  movups  [rbp+0C0h+var_90], xmm0
0x18000acc7  movups  [rbp+0C0h+var_80], xmm0
0x18000accb  test    rdi, rdi
0x18000acce  jz      loc_18000B378
0x18000acd4  cmp     [rdi], r12w
0x18000acd8  jz      loc_18000B378
0x18000acde  mov     rcx, rdi; pidl
0x18000ace1  xor     esi, esi
0x18000ace3  call    cs:__imp_ILFindLastID
0x18000ace9  mov     rcx, rax; struct _ITEMIDLIST_RELATIVE *
0x18000acec  mov     rbx, rax
0x18000acef  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ILFindFirstHiddenID(_ITEMIDLIST_RELATIVE const *)
0x18000acf4  mov     rcx, rax
0x18000acf7  movzx   eax, word ptr [rbx]
0x18000acfa  add     rbx, rax
0x18000acfd  test    rcx, rcx
0x18000ad00  jnz     loc_18000B5FD
0x18000ad06  mov     rcx, [rsp+1C0h+var_1A0]
0x18000ad0b  mov     rax, [rcx]
0x18000ad0e  mov     rax, [rax+10h]
0x18000ad12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad17  test    esi, esi
0x18000ad19  js      loc_18000B60F
0x18000ad1f  mov     esi, 0BEEFh
0x18000ad24  mov     rcx, rdi; pidl
0x18000ad27  call    cs:__imp_ILFindLastID
0x18000ad2d  mov     rdx, rax
0x18000ad30  test    rax, rax
0x18000ad33  jz      short loc_18000AD57
0x18000ad35  movzx   eax, word ptr [rax]
0x18000ad38  cmp     eax, 2Eh ; '.'
0x18000ad3b  jb      short loc_18000AD57
0x18000ad3d  cmp     dword ptr [rdx+6], 10141981h
0x18000ad44  jnz     short loc_18000AD57
0x18000ad46  movzx   ecx, word ptr [rdx+0Ah]
0x18000ad4a  add     rcx, 2Eh ; '.'
0x18000ad4e  cmp     rax, rcx
0x18000ad51  jnb     loc_18000B1A6
0x18000ad57  test    rdi, rdi
0x18000ad5a  jz      short loc_18000AD88
0x18000ad5c  cmp     word ptr [rdi], 0
0x18000ad60  jz      short loc_18000AD88
0x18000ad62  mov     rcx, rdi; pidl
0x18000ad65  call    cs:__imp_ILFindLastID
0x18000ad6b  mov     rcx, rax; struct _ITEMIDLIST_RELATIVE *
0x18000ad6e  mov     rbx, rax
0x18000ad71  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ILFindFirstHiddenID(_ITEMIDLIST_RELATIVE const *)
0x18000ad76  mov     rcx, rax
0x18000ad79  movzx   eax, word ptr [rbx]
0x18000ad7c  add     rbx, rax
0x18000ad7f  test    rcx, rcx
0x18000ad82  jnz     loc_18000B1B1
0x18000ad88  test    r12d, r12d
0x18000ad8b  jnz     loc_18000B267
0x18000ad91  xor     esi, esi
0x18000ad93  test    rdi, rdi
0x18000ad96  jz      loc_18000B634
0x18000ad9c  mov     rcx, rdi; pidl
0x18000ad9f  call    cs:__imp_ILClone
0x18000ada5  xor     edi, edi
0x18000ada7  mov     r15d, 8007000Eh
0x18000adad  test    rax, rax
0x18000adb0  mov     r14, rax
0x18000adb3  cmovz   edi, r15d
0x18000adb7  jz      loc_18000B625
0x18000adbd  mov     rcx, rax; pidl
0x18000adc0  movaps  [rsp+1C0h+var_48+8], xmm6
0x18000adc8  call    cs:__imp_ILFindLastID
0x18000adce  mov     r13, rax
0x18000add1  mov     ebx, 80070057h
0x18000add6  test    rax, rax
0x18000add9  jz      short loc_18000ADFF
0x18000addb  movzx   eax, word ptr [rax]
0x18000adde  cmp     eax, 2Eh ; '.'
0x18000ade1  jb      short loc_18000ADFF
0x18000ade3  cmp     dword ptr [r13+6], 10141981h
0x18000adeb  jnz     short loc_18000ADFF
0x18000aded  movzx   ecx, word ptr [r13+0Ah]
0x18000adf2  add     rcx, 2Eh ; '.'
0x18000adf6  cmp     rax, rcx
0x18000adf9  jnb     loc_18000B294
0x18000adff  cmp     [r14], si
0x18000ae03  jz      short loc_18000AE2B
0x18000ae05  mov     rcx, r14; pidl
0x18000ae08  call    cs:__imp_ILFindLastID
0x18000ae0e  mov     rcx, rax; struct _ITEMIDLIST_RELATIVE *
0x18000ae11  mov     rdi, rax
0x18000ae14  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ILFindFirstHiddenID(_ITEMIDLIST_RELATIVE const *)
0x18000ae19  mov     rcx, rax
0x18000ae1c  movzx   eax, word ptr [rdi]
0x18000ae1f  add     rdi, rax
0x18000ae22  test    rcx, rcx
0x18000ae25  jnz     loc_18000B61A
0x18000ae2b  mov     edi, r15d
0x18000ae2e  mov     eax, cs:PKEY_Null.pid
0x18000ae34  mov     r15, r14
0x18000ae37  mov     dword ptr [rsp+1C0h+var_1A0], eax
0x18000ae3b  movups  xmm6, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x18000ae42  cmp     [r14], si
0x18000ae46  jz      loc_18000AF25
0x18000ae4c  mov     rcx, r14; pidl
0x18000ae4f  call    cs:__imp_ILGetSize
0x18000ae55  mov     r13d, eax
0x18000ae58  lea     ecx, [r13+2Ah]; cb
0x18000ae5c  call    cs:__imp_CoTaskMemAlloc
0x18000ae62  mov     r15, rax
0x18000ae65  test    rax, rax
0x18000ae68  jz      loc_18000AF1C
0x18000ae6e  mov     rcx, rax; void *
0x18000ae71  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18000ae76  mov     r8, rax; Size
0x18000ae79  xor     edx, edx; Val
0x18000ae7b  mov     rcx, r15; void *
0x18000ae7e  call    memset_0
0x18000ae83  mov     r8d, r13d; Size
0x18000ae86  mov     rdx, r14; Src
0x18000ae89  mov     rcx, r15; void *
0x18000ae8c  call    memcpy_0
0x18000ae91  mov     rcx, r15; pidl
0x18000ae94  call    cs:__imp_ILFindLastID
0x18000ae9a  mov     rcx, rax; struct _ITEMIDLIST_RELATIVE *
0x18000ae9d  mov     r12, rax
0x18000aea0  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ILFindFirstHiddenID(_ITEMIDLIST_RELATIVE const *)
0x18000aea5  test    rax, rax
0x18000aea8  jz      loc_18000B011
0x18000aeae  movzx   ecx, word ptr [r12]
0x18000aeb3  add     rcx, 0FFFFFFFFFFFFFFFEh
0x18000aeb7  add     rcx, r12
0x18000aeba  movzx   r8d, word ptr [rcx]
0x18000aebe  lea     edx, [r13-2]
0x18000aec2  mov     eax, dword ptr [rsp+1C0h+var_1A0]
0x18000aec6  add     rdx, r15
0x18000aec9  mov     dword ptr [rdx], 28h ; '('
0x18000aecf  mov     dword ptr [rdx+4], 0BEEF0013h
0x18000aed6  mov     dword ptr [rdx+8], 20000000h
0x18000aedd  movups  xmmword ptr [rdx+0Ch], xmm6
0x18000aee1  mov     [rdx+1Ch], eax
0x18000aee4  mov     [rdx+20h], esi
0x18000aee7  mov     dword ptr [rdx+24h], 1
0x18000aeee  mov     word ptr [rdx], 2Ah ; '*'
0x18000aef3  movzx   eax, word ptr [r12]
0x18000aef8  lea     ecx, [rax+2Ah]
0x18000aefb  cmp     cx, ax
0x18000aefe  jnb     short loc_18000AF0E
0x18000af00  mov     rcx, r15; pv
0x18000af03  call    cs:__imp_CoTaskMemFree
0x18000af09  xor     r15d, r15d
0x18000af0c  jmp     short loc_18000AF1C
0x18000af0e  mov     [r12], cx
0x18000af13  movzx   eax, word ptr [rdx]
0x18000af16  mov     [rax+rdx-2], r8w
0x18000af1c  mov     rcx, r14; pidl
0x18000af1f  call    cs:__imp_ILFree
0x18000af25  mov     r14, r15
0x18000af28  test    r15, r15
0x18000af2b  jz      loc_18000B036
0x18000af31  mov     rcx, r15; pidl
0x18000af34  call    cs:__imp_ILFindLastID
0x18000af3a  mov     r13, rax
0x18000af3d  test    rax, rax
0x18000af40  jz      short loc_18000AF66
0x18000af42  movzx   eax, word ptr [rax]
0x18000af45  cmp     eax, 2Eh ; '.'
0x18000af48  jb      short loc_18000AF66
0x18000af4a  cmp     dword ptr [r13+6], 10141981h
0x18000af52  jnz     short loc_18000AF66
0x18000af54  movzx   ecx, word ptr [r13+0Ah]
0x18000af59  add     rcx, 2Eh ; '.'
0x18000af5d  cmp     rax, rcx
0x18000af60  jnb     loc_18000B314
0x18000af66  xor     r13d, r13d
0x18000af69  mov     edi, ebx
0x18000af6b  cmp     [r15], si
0x18000af6f  jz      short loc_18000AFAA
0x18000af71  mov     rcx, r15; pidl
0x18000af74  call    cs:__imp_ILFindLastID
0x18000af7a  mov     rcx, rax; struct _ITEMIDLIST_RELATIVE *
0x18000af7d  mov     r15, rax
0x18000af80  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ILFindFirstHiddenID(_ITEMIDLIST_RELATIVE const *)
0x18000af85  mov     rcx, rax
0x18000af88  movzx   eax, word ptr [r15]
0x18000af8c  add     r15, rax
0x18000af8f  test    rcx, rcx
0x18000af92  jz      short loc_18000AFAA
0x18000af94  cmp     dword ptr [rcx+4], 0BEEF0013h
0x18000af9b  lea     rdx, [rcx+8]
0x18000af9f  jnz     loc_18000B593
0x18000afa5  mov     r13, rdx
0x18000afa8  xor     edi, edi
0x18000afaa  test    edi, edi
0x18000afac  js      loc_18000B036
0x18000afb2  mov     eax, [r13+14h]
0x18000afb6  movups  xmm0, xmmword ptr [r13+4]
0x18000afbb  mov     esi, [rbp+0C0h+var_B0]
0x18000afbe  mov     [rbp+0C0h+var_98], eax
0x18000afc1  movups  [rbp+0C0h+Buf1], xmm0
0x18000afc5  cmp     eax, esi
0x18000afc7  jz      short loc_18000B019
0x18000afc9  test    esi, esi
0x18000afcb  jz      loc_18000B323
0x18000afd1  mov     dword ptr [rsp+1C0h+var_190], 0
0x18000afd9  mov     ecx, [r13+1Ch]
0x18000afdd  mov     eax, ecx
0x18000afdf  bts     eax, 0Ch
0x18000afe3  btr     ecx, 0Ch
0x18000afe7  cmp     dword ptr [rsp+1C0h+var_190], 0
0x18000afec  cmovz   ecx, eax
0x18000afef  btr     ecx, 0Dh
0x18000aff3  mov     [r13+1Ch], ecx
0x18000aff7  movups  xmm0, [rbp+0C0h+Buf2]
0x18000affb  movups  xmmword ptr [r13+4], xmm0
0x18000b000  mov     eax, [rbp+0C0h+var_B0]
0x18000b003  mov     [r13+14h], eax
0x18000b007  mov     dword ptr [r13+18h], 0
0x18000b00f  jmp     short loc_18000B030
0x18000b011  mov     rcx, r12
0x18000b014  jmp     loc_18000AEBA
0x18000b019  mov     r8d, 10h; Size
0x18000b01f  lea     rdx, [rbp+0C0h+Buf2]; Buf2
0x18000b023  lea     rcx, [rbp+0C0h+Buf1]; Buf1
0x18000b027  call    memcmp_0
0x18000b02c  test    eax, eax
0x18000b02e  jnz     short loc_18000AFC9
0x18000b030  mov     rsi, r14
0x18000b033  xor     r14d, r14d
0x18000b036  mov     rcx, r14; pidl
0x18000b039  call    cs:__imp_ILFree
0x18000b03f  mov     r14, [rsp+1C0h+var_180]
0x18000b044  movaps  xmm6, [rsp+1C0h+var_48+8]
0x18000b04c  test    edi, edi
0x18000b04e  js      loc_18000B640
0x18000b054  mov     rcx, rsi; pidl
0x18000b057  call    cs:__imp_ILFindLastID
0x18000b05d  mov     rcx, rax; pidl
0x18000b060  mov     rdi, rax
0x18000b063  call    cs:__imp_ILFindLastID
0x18000b069  mov     rdx, rax
0x18000b06c  test    rax, rax
0x18000b06f  jz      short loc_18000B093
0x18000b071  movzx   eax, word ptr [rax]
0x18000b074  cmp     eax, 2Eh ; '.'
0x18000b077  jb      short loc_18000B093
0x18000b079  cmp     dword ptr [rdx+6], 10141981h
0x18000b080  jnz     short loc_18000B093
0x18000b082  movzx   ecx, word ptr [rdx+0Ah]
0x18000b086  add     rcx, 2Eh ; '.'
0x18000b08a  cmp     rax, rcx
0x18000b08d  jnb     loc_18000B285
0x18000b093  test    rdi, rdi
0x18000b096  jz      loc_18000B15A
0x18000b09c  cmp     word ptr [rdi], 0
0x18000b0a0  jz      loc_18000B15A
0x18000b0a6  mov     rcx, rdi; pidl
0x18000b0a9  call    cs:__imp_ILFindLastID
0x18000b0af  mov     rcx, rax; struct _ITEMIDLIST_RELATIVE *
0x18000b0b2  mov     rdi, rax
0x18000b0b5  call    ?ILFindFirstHiddenID@@YAPEFBU_HIDDENITEMID@@PEFBU_ITEMIDLIST_RELATIVE@@@Z; ILFindFirstHiddenID(_ITEMIDLIST_RELATIVE const *)
  ... truncated ...
```
