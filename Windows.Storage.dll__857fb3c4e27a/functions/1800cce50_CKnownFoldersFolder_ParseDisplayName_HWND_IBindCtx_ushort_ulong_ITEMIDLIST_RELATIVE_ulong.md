# CKnownFoldersFolder::ParseDisplayName(HWND__ *,IBindCtx *,ushort *,ulong *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x1800cce50`
- end: `0x1800cd785`
- name: `?ParseDisplayName@CKnownFoldersFolder@@UEAAJPEAUHWND__@@PEAUIBindCtx@@PEAGPEAKPEAPEAU_ITEMIDLIST_RELATIVE@@3@Z`
- size: `2357`
- prototype: `int(CKnownFoldersFolder *__hidden this, HWND, struct IBindCtx *, unsigned __int16 *, unsigned int *, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `1`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x180300e60`

## callees

- `0x18001e350`
- `0x180046930`
- `0x18004e540`
- `0x180052490`
- `0x18009c6c0`
- `0x18009c960`
- `0x1800cce50`
- `0x1800ce040`
- `0x1800ce0f8`
- `0x1800ce130`
- `0x1800ce160`
- `0x1800ce2b0`
- `0x1800d3d10`
- `0x18016cb6c`
- `0x18016cd40`
- `0x18019c0f0`
- `0x180209ac8`
- `0x180271860`
- `0x1802d7510`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800cd418`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800cd418`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800cced6`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x1800cced6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd42b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd49c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd4b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd5fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd6b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd6f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd42b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd49c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd4b5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd5fd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd6b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cd6f9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800cd764`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800cd764`
- `SHCORE!__imp_StrRetToBufW` at `0x1800cd3e3`
- `SHCORE!__imp_StrRetToBufW` at `0x1800cd3e3`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x1800cd758`
- `PROPSYS!PropVariantToUInt32WithDefault` at `0x1800cd758`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x1800cd739`
- `PROPSYS!PSGetPropertyFromPropertyStorage` at `0x1800cd739`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall CKnownFoldersFolder::ParseDisplayName(
        CKnownFoldersFolder *this,
        HWND a2,
        struct IBindCtx *a3,
        unsigned __int16 *a4,
        unsigned int *a5,
        struct _ITEMIDLIST_RELATIVE **a6,
        unsigned int *a7)
{
  unsigned __int16 *v7; // rbx
  struct IBindCtx *v8; // r15
  CKnownFoldersFolder *v9; // r12
  struct _ITEMIDLIST_RELATIVE **v10; // r14
  unsigned int *v11; // r13
  int AttributesOf; // edi
  ULONG v13; // edi
  PWSTR v14; // rax
  PWSTR v15; // r9
  unsigned __int64 v16; // rcx
  __int64 v17; // rdx
  WCHAR *v18; // rax
  unsigned __int16 v19; // r8
  WCHAR *v20; // rcx
  struct _ITEMIDLIST_RELATIVE *v21; // rbx
  CKnownFoldersFolder *v22; // rsi
  int ParsingFolderID; // eax
  unsigned int v24; // ecx
  enum FOLDER_ENUM_MODE v25; // eax
  unsigned int v26; // r8d
  int v27; // eax
  HDPA v28; // r13
  struct _DPA *v29; // rbx
  int v30; // ecx
  int v31; // eax
  unsigned __int16 *v32; // r12
  int v33; // eax
  unsigned __int64 v34; // rax
  __int64 IsValid; // rax
  DWORD v36; // edx
  int *v37; // rsi
  int v38; // r15d
  int v39; // r14d
  int v40; // r15d
  int v41; // eax
  int v42; // edi
  const struct CKnownFoldersFolder::CACHEITEMINFO *v43; // rdx
  int v44; // eax
  const struct CKnownFoldersFolder::CACHEITEMINFO *v45; // rdx
  int v46; // eax
  __int64 v47; // r14
  __int64 v48; // rsi
  BOOL v49; // edx
  int v50; // edi
  unsigned __int64 v51; // rax
  HRESULT v52; // edi
  int v53; // eax
  void *v54; // rcx
  int v55; // edi
  const ITEMIDLIST *v56; // rsi
  __int64 v57; // rdi
  ITEMIDLIST *v58; // rcx
  __int64 v59; // rcx
  ITEMIDLIST *v60; // rcx
  __int64 v61; // rcx
  __int64 v63; // rax
  __int64 v64; // rdx
  WCHAR *v65; // r8
  unsigned __int16 v66; // cx
  unsigned int v67; // ebx
  WCHAR *v68; // rcx
  const unsigned __int16 *Ptr; // rax
  struct _ITEMIDLIST_RELATIVE *v70; // rbx
  enum FOLDER_ENUM_MODE FolderEnumMode; // eax
  ITEMIDLIST *v72; // rcx
  __int64 v73; // rcx
  int v74; // eax
  int v75; // [rsp+40h] [rbp-C0h]
  int v76; // [rsp+40h] [rbp-C0h]
  int v77; // [rsp+44h] [rbp-BCh]
  int v78; // [rsp+48h] [rbp-B8h] BYREF
  HDPA hdpa; // [rsp+50h] [rbp-B0h] BYREF
  CKnownFoldersFolder *v80; // [rsp+58h] [rbp-A8h]
  struct IBindCtx *v81; // [rsp+60h] [rbp-A0h]
  struct _ITEMID_CHILD **v82; // [rsp+68h] [rbp-98h]
  CKnownFoldersFolder *v83; // [rsp+70h] [rbp-90h]
  INT_PTR i; // [rsp+78h] [rbp-88h]
  unsigned int *v85; // [rsp+80h] [rbp-80h]
  HWND v86; // [rsp+88h] [rbp-78h]
  void *v87; // [rsp+90h] [rbp-70h] BYREF
  void *ppv; // [rsp+98h] [rbp-68h] BYREF
  HDPA v89; // [rsp+A0h] [rbp-60h] BYREF
  struct _ITEMIDLIST_RELATIVE *v90; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v91; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v92; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v93; // [rsp+C8h] [rbp-38h]
  ULONG v94; // [rsp+D0h] [rbp-30h]
  int v95; // [rsp+D4h] [rbp-2Ch]
  __int128 v96; // [rsp+D8h] [rbp-28h]
  LPCITEMIDLIST pidl; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v98; // [rsp+F0h] [rbp-10h] BYREF
  KNOWNFOLDERID rfid; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v100; // [rsp+108h] [rbp+8h]
  struct _GUID v101; // [rsp+110h] [rbp+10h] BYREF
  STRRET pstr; // [rsp+120h] [rbp+20h] BYREF
  WCHAR String1[264]; // [rsp+230h] [rbp+130h] BYREF
  WCHAR pszBuf[264]; // [rsp+440h] [rbp+340h] BYREF

  v7 = a4;
  v8 = a3;
  v81 = a3;
  v86 = a2;
  v9 = this;
  v83 = this;
  v10 = a6;
  v82 = a6;
  v11 = a7;
  v85 = a7;
  AttributesOf = -2147024809;
  if ( a6 && a4 )
  {
    v13 = 0;
    *a6 = 0;
    String1[0] = 0;
    v14 = StrChrW(a4, 0x5Cu);
    v15 = v14;
    if ( v14 )
    {
      if ( v14 <= v7 )
        return (unsigned int)-2147024809;
      v16 = (int)(v14 - v7);
      if ( v16 > 0x7FFFFFFE )
      {
        String1[0] = 0;
      }
      else
      {
        v17 = 260;
        v18 = String1;
        do
        {
          if ( !v16 )
            break;
          v19 = *v7;
          if ( !*v7 )
            break;
          ++v7;
          *v18++ = v19;
          --v16;
          --v17;
        }
        while ( v17 );
        v20 = v18 - 1;
        if ( v17 )
          v20 = v18;
        *v20 = 0;
      }
      v21 = 0;
      if ( v15[1] )
        v21 = (struct _ITEMIDLIST_RELATIVE *)(v15 + 1);
      v90 = v21;
    }
    else
    {
      v63 = 2147483646;
      v64 = 260;
      v65 = String1;
      do
      {
        if ( !v63 )
          break;
        v66 = *v7;
        if ( !*v7 )
          break;
        ++v7;
        *v65++ = v66;
        --v63;
        --v64;
      }
      while ( v64 );
      v67 = -2147024774;
      if ( v64 )
        v67 = 0;
      v68 = v65 - 1;
      if ( v64 )
        v68 = v65;
      *v68 = 0;
      v90 = 0;
      if ( !v64 )
        return v67;
    }
    v101 = 0;
    v78 = 0;
    v22 = (CKnownFoldersFolder *)((char *)v9 - 48);
    v80 = (CKnownFoldersFolder *)((char *)v9 - 48);
    ParsingFolderID = CKnownFoldersFolder::_GetParsingFolderID(
                        (CKnownFoldersFolder *)((char *)v9 - 48),
                        v8,
                        String1,
                        &v101,
                        &v78);
    v75 = ParsingFolderID;
    if ( ParsingFolderID >= 0 )
    {
      FolderEnumMode = BindCtx_GetFolderEnumMode(v8);
      AttributesOf = CKnownFoldersFolder::_CreateItemID(
                       (CKnownFoldersFolder *)((char *)v9 - 48),
                       &v101,
                       FolderEnumMode,
                       a6);
    }
    else
    {
      if ( (unsigned int)FailForceReturn(ParsingFolderID) )
        return v24;
      v25 = BindCtx_GetFolderEnumMode(v8);
      v26 = 12448;
      if ( v25 != FEM_NAVIGATION )
        v26 = 8352;
      hdpa = 0;
      v89 = 0;
      v27 = CKnownFoldersFolder::_EnumFolders((void **)v9 - 6, 0, v26, &hdpa, &v89);
      v28 = hdpa;
      v29 = v89;
      if ( v27 >= 0 )
      {
        v30 = 0;
        while ( 1 )
        {
          v77 = v30;
          if ( v28 )
            v31 = *(_DWORD *)v28;
          else
            v31 = 0;
          if ( v30 >= v31 )
          {
LABEL_101:
            if ( v28 )
            {
              DPA_DestroyCallback(v28, DPA_ILFreeCB<_ITEMIDLIST_ABSOLUTE>, 0);
              v28 = 0;
              hdpa = 0;
            }
            if ( v29 )
            {
              DPA_DestroyCallback(v29, DPA_ILFreeCB<_ITEMIDLIST_ABSOLUTE>, 0);
              v29 = 0;
            }
            v9 = v83;
            break;
          }
          i = v30;
          if ( v28 && v30 >= 0LL && v30 < (__int64)*(int *)v28 )
          {
            _mm_lfence();
            v32 = *(unsigned __int16 **)(*((_QWORD *)v28 + 1) + 8LL * v30);
          }
          else
          {
            v32 = 0;
          }
          v98 = 0;
          pidl = 0;
          v91 = 0;
          v87 = 0;
          v33 = CKnownFoldersFolder::_ValidateCache(v22);
          if ( v33 >= 0 )
          {
            if ( v32 )
            {
              v34 = *v32;
              if ( (unsigned int)v34 >= 0x1E
                && *(_DWORD *)(v32 + 3) == 603896814
                && v34 >= (unsigned __int64)v32[5] + 30
                && v32 != (unsigned __int16 *)-14LL )
              {
                v92 = *(_OWORD *)(v32 + 7);
                v93 = 0;
                rfid = 0;
                v100 = 0;
                IsValid = CItemIDFactory<KNOWNFOLDERSITEM,603896814>::_IsValid(v32);
                if ( IsValid )
                {
                  v36 = *(unsigned __int16 *)(IsValid + 10);
                  if ( (_WORD)v36 )
                  {
                    if ( IsValid != -30
                      && PSGetPropertyFromPropertyStorage(
                           (PCUSERIALIZEDPROPSTORAGE)(IsValid + 30),
                           v36,
                           &rpkey,
                           (PROPVARIANT *)&rfid) >= 0
                      && LOWORD(rfid.Data1) )
                    {
                      v13 = PropVariantToUInt32WithDefault((const PROPVARIANT *const)&rfid, 0);
                      PropVariantClear((PROPVARIANT *)&rfid);
                    }
                  }
                }
                v94 = v13;
                v95 = 0;
                v96 = 0;
                v37 = (int *)*((_QWORD *)v22 + 24);
                if ( v37 )
                  v38 = *v37;
                else
                  v38 = 0;
                v39 = 0;
                v40 = v38 - 1;
                while ( 1 )
                {
                  while ( 1 )
                  {
                    if ( v39 > v40 )
                      goto LABEL_42;
                    v41 = (v40 + v39) / 2;
                    v42 = v41;
                    v43 = 0;
                    if ( v37 && v41 >= 0 && v41 < *v37 )
                      v43 = (const struct CKnownFoldersFolder::CACHEITEMINFO *)(*((_QWORD *)v37 + 1)
                                                                              + (unsigned int)(v37[5] * v41));
                    v44 = CKnownFoldersFolder::s_CompareCacheItems(
                            (const struct CKnownFoldersFolder::CACHEITEMINFO *)&v92,
                            v43,
                            0);
                    if ( v44 >= 0 )
                      break;
                    v40 = v42 - 1;
                  }
                  if ( v44 <= 0 )
                    break;
                  v39 = v42 + 1;
                }
                for ( ; v42 > 0; --v42 )
                {
                  v45 = 0;
                  if ( v37 )
                  {
                    v46 = v42 - 1;
                    if ( v42 - 1 >= 0 && v46 < *v37 )
                      v45 = (const struct CKnownFoldersFolder::CACHEITEMINFO *)(*((_QWORD *)v37 + 1)
                                                                              + (unsigned int)(v37[5] * v46));
                  }
                  if ( (unsigned int)CKnownFoldersFolder::s_CompareCacheItems(
                                       (const struct CKnownFoldersFolder::CACHEITEMINFO *)&v92,
                                       v45,
                                       0) )
                    break;
                }
                if ( v42 == -1 )
                {
LABEL_42:
                  v33 = -2147467259;
                  goto LABEL_72;
                }
                v47 = 0;
                if ( v37 && v42 >= 0 && v42 < *v37 )
                  v47 = *((_QWORD *)v37 + 1) + (unsigned int)(v37[5] * v42);
                v48 = *(_QWORD *)(v47 + 16);
                if ( v48 )
                {
                  v49 = 1;
                  v50 = 0;
                  while ( v49 )
                  {
                    if ( *((_DWORD *)&unk_180676E50 + 6 * v50 + 4) )
                      v49 = ((__int64 (__fastcall *)(__int64, unsigned __int16 *, _QWORD))*(&funcs_180051BCD + 3 * v50))(
                              v48,
                              v32,
                              *((unsigned int *)&unk_180676E50 + 6 * v50)) == 0;
                    if ( (unsigned int)++v50 >= 9 )
                    {
                      if ( !v49 )
                        goto LABEL_74;
                      v33 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(v47 + 32))(
                              *(_QWORD *)(v47 + 32),
                              &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                              &v87);
                      goto LABEL_72;
                    }
                  }
                }
                goto LABEL_74;
              }
            }
            v33 = -2147024809;
          }
LABEL_72:
          if ( v33 >= 0 )
          {
            v53 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))v87)(
                    v87,
                    &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                    &v91);
            v54 = v87;
            goto LABEL_81;
          }
          if ( !v32 )
            goto LABEL_78;
LABEL_74:
          v51 = *v32;
          if ( (unsigned int)v51 < 0x1E
            || *(_DWORD *)(v32 + 3) != 603896814
            || v51 < (unsigned __int64)v32[5] + 30
            || v32 == (unsigned __int16 *)-14LL )
          {
LABEL_78:
            v52 = -2147024809;
            goto LABEL_89;
          }
          rfid = *(KNOWNFOLDERID *)(v32 + 7);
          ppv = 0;
          v52 = SHGetKnownFolderItem(
                  &rfid,
                  KF_FLAG_SIMPLE_IDLIST|KF_FLAG_NO_ALIAS|KF_FLAG_DONT_VERIFY,
                  0,
                  &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                  &ppv);
          if ( v52 < 0 )
            goto LABEL_89;
          v53 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv)(
                  ppv,
                  &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                  &v91);
          v54 = ppv;
LABEL_81:
          v55 = v53;
          (*(void (__fastcall **)(void *))(*(_QWORD *)v54 + 16LL))(v54);
          if ( v55 < 0 )
            goto LABEL_93;
          pidl = 0;
          v98 = 0;
          v87 = 0;
          v52 = (**(__int64 (__fastcall ***)(__int64, GUID *, void **))v91)(
                  v91,
                  &GUID_b3a4b685_b685_4805_99d9_5dead2873236,
                  &v87);
          if ( v52 >= 0 )
          {
            ppv = 0;
            v52 = (*(__int64 (__fastcall **)(void *, _QWORD, void **, LPCITEMIDLIST *))(*(_QWORD *)v87 + 32LL))(
                    v87,
                    0,
                    &ppv,
                    &pidl);
            if ( v52 >= 0 )
            {
              v52 = (**(__int64 (__fastcall ***)(void *, GUID *, __int64 *))ppv)(
                      ppv,
                      &GUID_000214e6_0000_0000_c000_000000000046,
                      &v98);
              if ( v52 < 0 )
              {
                CoTaskMemFree((LPVOID)pidl);
                pidl = 0;
              }
              (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
            }
            (*(void (__fastcall **)(void *))(*(_QWORD *)v87 + 16LL))(v87);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v91 + 16LL))(v91);
LABEL_89:
          if ( v52 >= 0 )
          {
            v56 = pidl;
            v57 = v98;
            pszBuf[0] = 0;
            memset_0(&pstr, 0, sizeof(pstr));
            if ( (*(int (__fastcall **)(__int64, const ITEMIDLIST *, __int64, STRRET *))(*(_QWORD *)v57 + 88LL))(
                   v57,
                   v56,
                   32769,
                   &pstr) >= 0
              && StrRetToBufW(&pstr, v56, pszBuf, 0x104u) >= 0
              && CompareStringW(0x7Fu, 1u, String1, -1, pszBuf, -1) == 2 )
            {
              v10 = v82;
              if ( *v82 )
              {
                CoTaskMemFree(*v82);
                *v10 = 0;
                v75 = -2147467259;
                v60 = (ITEMIDLIST *)pidl;
                pidl = 0;
                CoTaskMemFree(v60);
                v61 = v98;
                if ( v98 )
                {
                  v98 = 0;
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v61 + 16LL))(v61);
                }
                v22 = v80;
                v8 = v81;
                goto LABEL_101;
              }
              v8 = v81;
              if ( (unsigned int)BindCtx_ContainsObject(v81, L"File System Bind Data") )
              {
                Ptr = (const unsigned __int16 *)DPA_GetPtr(v29, i);
                v22 = v80;
                if ( !CKnownFoldersFolder::_PathIsChildOfOurParent(v80, Ptr) )
                {
                  v75 = -2147467259;
                  v72 = (ITEMIDLIST *)pidl;
                  pidl = 0;
                  CoTaskMemFree(v72);
                  v73 = v98;
                  if ( v98 )
                  {
                    v98 = 0;
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v73 + 16LL))(v73);
                  }
                  goto LABEL_101;
                }
              }
              v75 = SHILCloneFirst((const struct _ITEMIDLIST_RELATIVE *)v32, v10);
            }
          }
LABEL_93:
          v58 = (ITEMIDLIST *)pidl;
          pidl = 0;
          CoTaskMemFree(v58);
          v59 = v98;
          if ( v98 )
          {
            v98 = 0;
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 16LL))(v59);
          }
          v30 = v77 + 1;
          v22 = v80;
          v10 = v82;
          v8 = v81;
          v13 = 0;
        }
      }
      if ( v29 )
      {
        DPA_DestroyCallback(v29, CQueueItem::AppliesTo, 0);
        DPA_Destroy(0);
      }
      if ( v28 )
      {
        DPA_DestroyCallback(v28, CQueueItem::AppliesTo, 0);
        DPA_Destroy(0);
      }
      AttributesOf = v75;
      v11 = v85;
    }
    if ( AttributesOf >= 0 )
    {
      v70 = v90;
      if ( !v90 || v78 )
      {
        if ( !v11 || !*v11 )
          return (unsigned int)AttributesOf;
        AttributesOf = CKnownFoldersFolder::_GetAttributesOf(v22, *v10, *v11, v11);
      }
      else
      {
        v89 = 0;
        v74 = (*(__int64 (__fastcall **)(CKnownFoldersFolder *, struct _ITEMIDLIST_RELATIVE *, struct IBindCtx *, GUID *, HDPA *))(*(_QWORD *)v9 + 40LL))(
                v9,
                *v10,
                v8,
                &GUID_000214e6_0000_0000_c000_000000000046,
                &v89);
        if ( v74 < 0 )
        {
          AttributesOf = v74;
          goto LABEL_135;
        }
        v90 = 0;
        v76 = (*(__int64 (__fastcall **)(HDPA, HWND, struct IBindCtx *, struct _ITEMIDLIST_RELATIVE *, _QWORD, struct _ITEMIDLIST_RELATIVE **, unsigned int *))(*(_QWORD *)v89 + 24LL))(
                v89,
                v86,
                v8,
                v70,
                0,
                &v90,
                v11);
        if ( v76 >= 0 )
          v76 = _ILCombineAndFree(*v10, v90, v10);
        (*(void (__fastcall **)(HDPA))(*(_QWORD *)v89 + 16LL))(v89);
        AttributesOf = v76;
      }
      if ( AttributesOf >= 0 )
        return (unsigned int)AttributesOf;
LABEL_135:
      CoTaskMemFree(*v10);
      *v10 = 0;
    }
  }
  return (unsigned int)AttributesOf;
}

```

## disassembly

```asm
0x1800cce50  push    rbp
0x1800cce52  push    rbx
0x1800cce53  push    rsi
0x1800cce54  push    rdi
0x1800cce55  push    r12
0x1800cce57  push    r13
0x1800cce59  push    r14
0x1800cce5b  push    r15
0x1800cce5d  lea     rbp, [rsp-568h]
0x1800cce65  sub     rsp, 668h
0x1800cce6c  mov     rax, cs:__security_cookie
0x1800cce73  xor     rax, rsp
0x1800cce76  mov     [rbp+5A0h+var_50], rax
0x1800cce7d  mov     rbx, r9
0x1800cce80  mov     r15, r8
0x1800cce83  mov     [rsp+6A0h+var_640], r8
0x1800cce88  mov     [rbp+5A0h+var_618], rdx
0x1800cce8c  mov     r12, rcx
0x1800cce8f  mov     [rsp+6A0h+var_630], rcx
0x1800cce94  mov     r14, [rbp+5A0h+arg_28]
0x1800cce9b  mov     [rsp+6A0h+var_638], r14
0x1800ccea0  mov     r13, [rbp+5A0h+arg_30]
0x1800ccea7  mov     [rbp+5A0h+var_620], r13
0x1800cceab  mov     edi, 80070057h
0x1800cceb0  test    r14, r14
0x1800cceb3  jz      loc_1800CD56E
0x1800cceb9  test    rbx, rbx
0x1800ccebc  jz      loc_1800CD56E
0x1800ccec2  xor     edi, edi
0x1800ccec4  mov     [r14], rdi
0x1800ccec7  mov     [rbp+5A0h+String1], di
0x1800ccece  mov     edx, 5Ch ; '\'; wMatch
0x1800cced3  mov     rcx, rbx; pszStart
0x1800cced6  call    cs:__imp_StrChrW
0x1800ccedc  mov     r9, rax
0x1800ccedf  test    rax, rax
0x1800ccee2  jz      loc_1800CD59B
0x1800ccee8  cmp     rax, rbx
0x1800cceeb  jbe     loc_1800CD77B
0x1800ccef1  sub     rax, rbx
0x1800ccef4  sar     rax, 1
0x1800ccef7  movsxd  rcx, eax
0x1800ccefa  mov     eax, 7FFFFFFEh
0x1800cceff  cmp     rcx, rax
0x1800ccf02  ja      loc_1800CD76F
0x1800ccf08  mov     edx, 104h
0x1800ccf0d  lea     rax, [rbp+5A0h+String1]
0x1800ccf14  test    rcx, rcx
0x1800ccf17  jz      short loc_1800CCF38
0x1800ccf19  movzx   r8d, word ptr [rbx]
0x1800ccf1d  test    r8w, r8w
0x1800ccf21  jz      short loc_1800CCF38
0x1800ccf23  add     rbx, 2
0x1800ccf27  mov     [rax], r8w
0x1800ccf2b  add     rax, 2
0x1800ccf2f  dec     rcx
0x1800ccf32  sub     rdx, 1
0x1800ccf36  jnz     short loc_1800CCF14
0x1800ccf38  lea     rcx, [rax-2]
0x1800ccf3c  test    rdx, rdx
0x1800ccf3f  cmovnz  rcx, rax
0x1800ccf43  mov     [rcx], di
0x1800ccf46  lea     rax, [r9+2]
0x1800ccf4a  mov     rbx, rdi
0x1800ccf4d  cmp     [rax], bx
0x1800ccf50  cmovnz  rbx, rax
0x1800ccf54  mov     [rbp+5A0h+var_5F8], rbx
0x1800ccf58  xorps   xmm0, xmm0
0x1800ccf5b  movups  xmmword ptr [rbp+5A0h+var_590.Data1], xmm0
0x1800ccf5f  mov     [rsp+6A0h+var_658], edi
0x1800ccf63  lea     rsi, [r12-30h]
0x1800ccf68  mov     [rsp+6A0h+var_648], rsi
0x1800ccf6d  lea     rax, [rsp+6A0h+var_658]
0x1800ccf72  mov     [rsp+6A0h+ppv], rax; int *
0x1800ccf77  lea     r9, [rbp+5A0h+var_590]; struct _GUID *
0x1800ccf7b  lea     r8, [rbp+5A0h+String1]; unsigned __int16 *
0x1800ccf82  mov     rdx, r15; struct IBindCtx *
0x1800ccf85  mov     rcx, rsi; this
0x1800ccf88  call    ?_GetParsingFolderID@CKnownFoldersFolder@@IEAAJPEAUIBindCtx@@PEBGPEAU_GUID@@PEAH@Z; CKnownFoldersFolder::_GetParsingFolderID(IBindCtx *,ushort const *,_GUID *,int *)
0x1800ccf8d  mov     [rsp+6A0h+var_660], eax
0x1800ccf91  test    eax, eax
0x1800ccf93  jns     loc_1800CD6C6
0x1800ccf99  mov     ecx, eax; int
0x1800ccf9b  call    ?FailForceReturn@@YAHJ@Z; FailForceReturn(long)
0x1800ccfa0  test    eax, eax
0x1800ccfa2  jnz     loc_1800CD61B
0x1800ccfa8  mov     rcx, r15; struct IBindCtx *
0x1800ccfab  call    ?BindCtx_GetFolderEnumMode@@YA?AW4FOLDER_ENUM_MODE@@PEAUIBindCtx@@@Z; BindCtx_GetFolderEnumMode(IBindCtx *)
0x1800ccfb0  mov     ecx, 20A0h
0x1800ccfb5  mov     r8d, 30A0h
0x1800ccfbb  cmp     eax, 1
0x1800ccfbe  cmovnz  r8d, ecx
0x1800ccfc2  mov     [rsp+6A0h+hdpa], rdi
0x1800ccfc7  mov     [rbp+5A0h+var_600], rdi
0x1800ccfcb  lea     rax, [rbp+5A0h+var_600]
0x1800ccfcf  mov     [rsp+6A0h+ppv], rax
0x1800ccfd4  lea     r9, [rsp+6A0h+hdpa]
0x1800ccfd9  xor     edx, edx
0x1800ccfdb  mov     rcx, rsi
0x1800ccfde  call    ?_EnumFolders@CKnownFoldersFolder@@IEAAJHKPEAV?$CDPA@U_ITEMID_CHILD@@V?$CTContainer_PolicyUnOwned@U_ITEMID_CHILD@@@@@@PEAV?$CDPA@GV?$CTContainer_PolicyUnOwned@G@@@@@Z; CKnownFoldersFolder::_EnumFolders(int,ulong,CDPA<_ITEMID_CHILD,CTContainer_PolicyUnOwned<_ITEMID_CHILD>> *,CDPA<ushort,CTContainer_PolicyUnOwned<ushort>> *)
0x1800ccfe3  mov     r13, [rsp+6A0h+hdpa]
0x1800ccfe8  mov     rbx, [rbp+5A0h+var_600]
0x1800ccfec  test    eax, eax
0x1800ccfee  js      loc_1800CD520
0x1800ccff4  mov     ecx, edi
0x1800ccff6  mov     [rsp+6A0h+var_65C], ecx
0x1800ccffa  test    r13, r13
0x1800ccffd  jz      loc_1800CD614
0x1800cd003  mov     eax, [r13+0]
0x1800cd007  cmp     ecx, eax
0x1800cd009  jge     loc_1800CD4E2
0x1800cd00f  movsxd  rcx, ecx
0x1800cd012  mov     [rsp+6A0h+i], rcx
0x1800cd017  test    r13, r13
0x1800cd01a  jz      loc_1800CD60C
0x1800cd020  test    rcx, rcx
0x1800cd023  js      loc_1800CD60C
0x1800cd029  movsxd  rax, dword ptr [r13+0]
0x1800cd02d  cmp     rcx, rax
0x1800cd030  jge     loc_1800CD60C
0x1800cd036  lfence
0x1800cd039  mov     rax, [r13+8]
0x1800cd03d  mov     r12, [rax+rcx*8]
0x1800cd041  mov     [rbp+5A0h+var_5B0], rdi
0x1800cd045  mov     [rbp+5A0h+pidl], rdi
0x1800cd049  mov     [rbp+5A0h+var_5F0], rdi
0x1800cd04d  mov     [rbp+5A0h+var_610], rdi
0x1800cd051  mov     rcx, rsi; this
0x1800cd054  call    ?_ValidateCache@CKnownFoldersFolder@@IEAAJXZ; CKnownFoldersFolder::_ValidateCache(void)
0x1800cd059  test    eax, eax
0x1800cd05b  js      loc_1800CD112
0x1800cd061  test    r12, r12
0x1800cd064  jz      loc_1800CD11A
0x1800cd06a  movzx   eax, word ptr [r12]
0x1800cd06f  cmp     eax, 1Eh
0x1800cd072  jb      loc_1800CD11A
0x1800cd078  cmp     dword ptr [r12+6], 23FEBBEEh
0x1800cd081  jnz     loc_1800CD11A
0x1800cd087  movzx   ecx, word ptr [r12+0Ah]
0x1800cd08d  add     rcx, 1Eh
0x1800cd091  cmp     rax, rcx
0x1800cd094  jb      loc_1800CD11A
0x1800cd09a  lea     rax, [r12+0Eh]
0x1800cd09f  test    rax, rax
0x1800cd0a2  jz      short loc_1800CD11A
0x1800cd0a4  movups  xmm0, xmmword ptr [rax]
0x1800cd0a7  movups  [rbp+5A0h+var_5E8], xmm0
0x1800cd0ab  mov     [rbp+5A0h+var_5D8], rdi
0x1800cd0af  xorps   xmm0, xmm0
0x1800cd0b2  xor     eax, eax
0x1800cd0b4  movups  xmmword ptr [rbp+5A0h+rfid.Data1], xmm0
0x1800cd0b8  mov     [rbp+5A0h+var_598], rax
0x1800cd0bc  mov     rcx, r12
0x1800cd0bf  call    ?_IsValid@?$CItemIDFactory@UKNOWNFOLDERSITEM@@$0CDPOLLOO@@@CAPEFBUCHILDITEMID@1@PEFBU_ITEMIDLIST_RELATIVE@@@Z; CItemIDFactory<KNOWNFOLDERSITEM,603896814>::_IsValid(_ITEMIDLIST_RELATIVE const *)
0x1800cd0c4  test    rax, rax
0x1800cd0c7  jz      short loc_1800CD0DF
0x1800cd0c9  movzx   edx, word ptr [rax+0Ah]; cb
0x1800cd0cd  test    dx, dx
0x1800cd0d0  jz      short loc_1800CD0DF
0x1800cd0d2  lea     rcx, [rax+1Eh]; psps
0x1800cd0d6  test    rcx, rcx
0x1800cd0d9  jnz     loc_1800CD72E
0x1800cd0df  mov     [rbp+5A0h+var_5D0], edi
0x1800cd0e2  xor     eax, eax
0x1800cd0e4  mov     [rbp+5A0h+var_5CC], eax
0x1800cd0e7  xorps   xmm0, xmm0
0x1800cd0ea  movdqu  [rbp+5A0h+var_5C8], xmm0
0x1800cd0ef  mov     rsi, [rsi+0C0h]
0x1800cd0f6  test    rsi, rsi
0x1800cd0f9  jz      loc_1800CD593
0x1800cd0ff  mov     r15d, [rsi]
0x1800cd102  xor     r14d, r14d
0x1800cd105  dec     r15d
0x1800cd108  cmp     r14d, r15d
0x1800cd10b  jle     short loc_1800CD121
0x1800cd10d  mov     eax, 80004005h
0x1800cd112  xor     r15d, r15d
0x1800cd115  jmp     loc_1800CD233
0x1800cd11a  mov     eax, 80070057h
0x1800cd11f  jmp     short loc_1800CD112
0x1800cd121  lea     eax, [r15+r14]
0x1800cd125  cdq
0x1800cd126  sub     eax, edx
0x1800cd128  sar     eax, 1
0x1800cd12a  mov     edi, eax
0x1800cd12c  xor     edx, edx
0x1800cd12e  test    rsi, rsi
0x1800cd131  jz      short loc_1800CD145
0x1800cd133  test    eax, eax
0x1800cd135  js      short loc_1800CD145
0x1800cd137  cmp     eax, [rsi]
0x1800cd139  jge     short loc_1800CD145
0x1800cd13b  mov     edx, eax
0x1800cd13d  imul    edx, [rsi+14h]
0x1800cd141  add     rdx, [rsi+8]; struct CKnownFoldersFolder::CACHEITEMINFO *
0x1800cd145  xor     r8d, r8d; __int64
0x1800cd148  lea     rcx, [rbp+5A0h+var_5E8]; struct CKnownFoldersFolder::CACHEITEMINFO *
0x1800cd14c  call    ?s_CompareCacheItems@CKnownFoldersFolder@@KAHPEBUCACHEITEMINFO@1@0_J@Z; CKnownFoldersFolder::s_CompareCacheItems(CKnownFoldersFolder::CACHEITEMINFO const *,CKnownFoldersFolder::CACHEITEMINFO const *,__int64)
0x1800cd151  test    eax, eax
0x1800cd153  js      short loc_1800CD15D
0x1800cd155  jle     short loc_1800CD163
0x1800cd157  lea     r14d, [rdi+1]
0x1800cd15b  jmp     short loc_1800CD108
0x1800cd15d  lea     r15d, [rdi-1]
0x1800cd161  jmp     short loc_1800CD108
0x1800cd163  xor     r15d, r15d
0x1800cd166  test    edi, edi
0x1800cd168  jle     short loc_1800CD19B
0x1800cd16a  mov     rdx, r15
0x1800cd16d  test    rsi, rsi
0x1800cd170  jz      short loc_1800CD187
0x1800cd172  lea     eax, [rdi-1]
0x1800cd175  test    eax, eax
0x1800cd177  js      short loc_1800CD187
0x1800cd179  cmp     eax, [rsi]
0x1800cd17b  jge     short loc_1800CD187
0x1800cd17d  imul    eax, [rsi+14h]
0x1800cd181  mov     edx, eax
0x1800cd183  add     rdx, [rsi+8]; struct CKnownFoldersFolder::CACHEITEMINFO *
0x1800cd187  xor     r8d, r8d; __int64
0x1800cd18a  lea     rcx, [rbp+5A0h+var_5E8]; struct CKnownFoldersFolder::CACHEITEMINFO *
0x1800cd18e  call    ?s_CompareCacheItems@CKnownFoldersFolder@@KAHPEBUCACHEITEMINFO@1@0_J@Z; CKnownFoldersFolder::s_CompareCacheItems(CKnownFoldersFolder::CACHEITEMINFO const *,CKnownFoldersFolder::CACHEITEMINFO const *,__int64)
0x1800cd193  test    eax, eax
0x1800cd195  jz      loc_1800CD71F
0x1800cd19b  cmp     edi, 0FFFFFFFFh
0x1800cd19e  jz      loc_1800CD10D
0x1800cd1a4  mov     r14, r15
0x1800cd1a7  test    rsi, rsi
0x1800cd1aa  jz      short loc_1800CD1BF
0x1800cd1ac  test    edi, edi
0x1800cd1ae  js      short loc_1800CD1BF
0x1800cd1b0  cmp     edi, [rsi]
0x1800cd1b2  jge     short loc_1800CD1BF
0x1800cd1b4  imul    edi, [rsi+14h]
0x1800cd1b8  mov     r14d, edi
0x1800cd1bb  add     r14, [rsi+8]
0x1800cd1bf  mov     rsi, [r14+10h]
0x1800cd1c3  test    rsi, rsi
0x1800cd1c6  jz      short loc_1800CD240
0x1800cd1c8  mov     edx, 1
0x1800cd1cd  mov     edi, r15d
0x1800cd1d0  test    edx, edx
0x1800cd1d2  jz      short loc_1800CD240
0x1800cd1d4  movsxd  rax, edi
0x1800cd1d7  lea     rcx, [rax+rax*2]
0x1800cd1db  lea     rax, ds:0[rcx*8]
0x1800cd1e3  lea     r9, unk_180676E50
0x1800cd1ea  cmp     dword ptr [rax+r9+10h], 0
0x1800cd1f0  jz      short loc_1800CD20E
0x1800cd1f2  mov     r8d, [rax+r9]
0x1800cd1f6  mov     rdx, r12
0x1800cd1f9  mov     rcx, rsi
0x1800cd1fc  mov     rax, ds:(funcs_180051BCD - 180676E50h)[rax+r9]
0x1800cd201  call    _guard_dispatch_icall$thunk$10345483385596137414; ILCompareHiddenString(_ITEMIDLIST_RELATIVE const *,_ITEMIDLIST_RELATIVE const *,IDLHID) ...
0x1800cd206  mov     edx, r15d
0x1800cd209  test    eax, eax
0x1800cd20b  setz    dl
0x1800cd20e  inc     edi
0x1800cd210  cmp     edi, 9
0x1800cd213  jb      short loc_1800CD1D0
0x1800cd215  test    edx, edx
0x1800cd217  jz      short loc_1800CD240
0x1800cd219  mov     rcx, [r14+20h]
0x1800cd21d  mov     rax, [rcx]
0x1800cd220  lea     r8, [rbp+5A0h+var_610]
0x1800cd224  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x1800cd22b  mov     rax, [rax]
0x1800cd22e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800cd233  test    eax, eax
0x1800cd235  jns     loc_1800CD468
0x1800cd23b  test    r12, r12
0x1800cd23e  jz      short loc_1800CD26E
0x1800cd240  movzx   eax, word ptr [r12]
0x1800cd245  cmp     eax, 1Eh
0x1800cd248  jb      short loc_1800CD26E
0x1800cd24a  cmp     dword ptr [r12+6], 23FEBBEEh
0x1800cd253  jnz     short loc_1800CD26E
0x1800cd255  movzx   ecx, word ptr [r12+0Ah]
0x1800cd25b  add     rcx, 1Eh
0x1800cd25f  cmp     rax, rcx
0x1800cd262  jb      short loc_1800CD26E
0x1800cd264  lea     rax, [r12+0Eh]
0x1800cd269  test    rax, rax
0x1800cd26c  jnz     short loc_1800CD278
0x1800cd26e  mov     edi, 80070057h
0x1800cd273  jmp     loc_1800CD386
0x1800cd278  movups  xmm0, xmmword ptr [rax]
0x1800cd27b  movups  xmmword ptr [rbp+5A0h+rfid.Data1], xmm0
0x1800cd27f  mov     [rbp+5A0h+var_608], r15
0x1800cd283  lea     rax, [rbp+5A0h+var_608]
0x1800cd287  mov     [rsp+6A0h+ppv], rax; ppv
0x1800cd28c  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800cd293  xor     r8d, r8d; hToken
0x1800cd296  mov     edx, 5100h; flags
0x1800cd29b  lea     rcx, [rbp+5A0h+rfid]; rfid
0x1800cd29f  call    SHGetKnownFolderItem
0x1800cd2a4  mov     edi, eax
0x1800cd2a6  test    eax, eax
0x1800cd2a8  js      loc_1800CD386
0x1800cd2ae  mov     rcx, [rbp+5A0h+var_608]
  ... truncated ...
```
