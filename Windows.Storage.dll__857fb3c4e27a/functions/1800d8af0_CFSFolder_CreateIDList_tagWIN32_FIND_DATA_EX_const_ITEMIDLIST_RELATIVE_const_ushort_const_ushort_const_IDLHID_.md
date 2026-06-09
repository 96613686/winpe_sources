# CFSFolder::_CreateIDList(tagWIN32_FIND_DATA_EX const *,_ITEMIDLIST_RELATIVE const *,ushort const *,ushort const *,IDLHID,CREATE_IDLIST_FLAGS,FOLDER_ENUM_MODE,_ITEMID_CHILD * *)

- ea: `0x1800d8af0`
- end: `0x1800d98c8`
- name: `?_CreateIDList@CFSFolder@@IEAAJPEBUtagWIN32_FIND_DATA_EX@@PEFBU_ITEMIDLIST_RELATIVE@@PEBG2W4IDLHID@@W4CREATE_IDLIST_FLAGS@@W4FOLDER_ENUM_MODE@@PEAPEAU_ITEMID_CHILD@@@Z`
- size: `3544`
- prototype: ``
- caller_count: `5`
- callee_count: `22`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001cc70`
- `0x18001d330`
- `0x1800d7780`
- `0x1800d7800`
- `0x1800da5f0`

## callees

- `0x180043320`
- `0x180093c20`
- `0x1800979d0`
- `0x1800d7650`
- `0x1800d8af0`
- `0x1800d98d0`
- `0x1800d998c`
- `0x1800d9b80`
- `0x1800d9c10`
- `0x1800e1c90`
- `0x1801b1350`
- `0x1801b56b0`
- `0x1801ca1a0`
- `0x1801cd254`
- `0x1801de0c0`
- `0x1803528f4`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a5bc5`
- `0x1803a96d9`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d94c9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d94c9`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800d92e2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x1800d92e2`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800d8ea3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!DosDateTimeToFileTime` at `0x1800d8ea3`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x1800d8d14`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x1800d8dc7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x1800d8df0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x1800d8e88`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x1800d9189`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x1800d8d14`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x1800d8dc7`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x1800d8df0`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x1800d8e88`
- `api-ms-win-core-kernel32-legacy-l1-1-0!FileTimeToDosDateTime` at `0x1800d9189`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d8c73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d93f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d9529`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d8c73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d93f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d9529`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800d8c94`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800d8c94`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8ffd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d900c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d901b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d90b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d924b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d939d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d959d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d974f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9817`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d983a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d989a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d8ffd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d900c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d901b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d90b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d924b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d939d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d959d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d974f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d9817`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d983a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d989a`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1800d94b7`
- `SHCORE!__imp_SHRegGetCLSIDKey` at `0x1800d94b7`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800d9038`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800d9038`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800d97f2`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800d97f2`
- `SHCORE!__imp_ualstrcpynW` at `0x1800d8e3d`
- `SHCORE!__imp_ualstrcpynW` at `0x1800d8e64`
- `SHCORE!__imp_ualstrcpynW` at `0x1800d9783`
- `SHCORE!__imp_ualstrcpynW` at `0x1800d98bd`
- `SHCORE!__imp_ualstrcpynW` at `0x1800d8e3d`
- `SHCORE!__imp_ualstrcpynW` at `0x1800d8e64`
- `SHCORE!__imp_ualstrcpynW` at `0x1800d9783`
- `SHCORE!__imp_ualstrcpynW` at `0x1800d98bd`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_DoesStringRoundTripW` at `0x1800d8b7f`
- `api-ms-win-shlwapi-winrt-storage-l1-1-1!__imp_DoesStringRoundTripW` at `0x1800d8b7f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CFSFolder::_CreateIDList(
        CFSFolder *a1,
        __int64 a2,
        void *a3,
        unsigned __int16 *a4,
        __int64 a5,
        unsigned int a6,
        char a7,
        enum FOLDER_ENUM_MODE a8,
        _QWORD *a9)
{
  unsigned __int16 *v9; // r13
  const WCHAR *v11; // rbx
  _BYTE *v12; // r12
  _BYTE *v13; // rdi
  __int64 v14; // rsi
  bool v15; // zf
  __int64 v16; // rax
  int v17; // r15d
  __int64 v18; // rax
  int v19; // edi
  int v20; // edi
  __int64 v21; // r15
  unsigned int v22; // r14d
  unsigned __int16 *p_cb; // rdi
  __int64 v24; // rcx
  unsigned int v25; // r13d
  int v26; // ecx
  ITEMIDLIST *v27; // rsi
  size_t v28; // rdi
  __int64 v29; // rax
  const FILETIME *v30; // r14
  BYTE v31; // al
  CFSFolder *v32; // rcx
  char *v33; // rdi
  unsigned __int16 *v34; // rax
  int v35; // r14d
  ITEMIDLIST *v36; // r14
  int FolderValue; // r15d
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  const struct _ITEMIDLIST_RELATIVE *v42; // rcx
  unsigned __int16 v43; // r8
  unsigned __int16 *v44; // rdx
  __int64 result; // rax
  unsigned __int16 *v46; // rax
  __int64 v47; // rax
  unsigned __int16 *v48; // r14
  char v49; // al
  CFSFolder *v50; // rcx
  char *v51; // r12
  char *abID; // r12
  char v53; // al
  int v54; // r14d
  LPWSTR ExtensionW; // rax
  __int64 v56; // rdx
  __int64 v57; // rcx
  const struct _ITEMIDLIST_RELATIVE *v58; // r14
  unsigned __int16 v59; // r14
  unsigned __int16 *v60; // rsi
  unsigned __int16 v61; // cx
  unsigned __int16 v62; // cx
  unsigned __int16 v63; // si
  unsigned __int16 *v64; // rdx
  __int64 v65; // rcx
  _WORD *v66; // rax
  _WORD *v67; // r14
  size_t v68; // rax
  unsigned __int16 v69; // ax
  const struct _ITEMIDLIST_RELATIVE *v70; // rcx
  const struct _ITEMIDLIST_RELATIVE *v71; // rbx
  void *v72; // r15
  unsigned int v73; // esi
  __int64 v74; // rcx
  unsigned __int16 *v75; // rax
  size_t v76; // rax
  unsigned __int16 v77; // ax
  const struct _ITEMIDLIST_RELATIVE *v78; // rcx
  const struct _ITEMIDLIST_RELATIVE *v79; // rbx
  unsigned __int16 *v80; // rdx
  int v81; // r8d
  __int64 v82; // rcx
  __int64 v83; // r15
  ITEMIDLIST *v84; // rdx
  unsigned int v85; // r14d
  __int64 cb; // rcx
  ITEMIDLIST *v87; // rax
  LPITEMIDLIST v88; // r12
  LPMALLOC v89; // r14
  int v90; // r15d
  unsigned int v91; // ebx
  unsigned __int16 *v92; // rax
  unsigned __int16 *v93; // rax
  GUID v94; // xmm0
  unsigned int v95; // [rsp+20h] [rbp-E0h]
  unsigned int v96; // [rsp+40h] [rbp-C0h]
  unsigned int v97; // [rsp+44h] [rbp-BCh]
  ITEMIDLIST *v98; // [rsp+48h] [rbp-B8h]
  WORD FatTime[2]; // [rsp+78h] [rbp-88h] BYREF
  WORD v102[2]; // [rsp+7Ch] [rbp-84h] BYREF
  size_t Size[2]; // [rsp+80h] [rbp-80h] BYREF
  WORD FatDate[8]; // [rsp+90h] [rbp-70h] BYREF
  LPMALLOC ppMalloc[4]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 *v106[2]; // [rsp+C0h] [rbp-40h] BYREF
  void *Buf1[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v108[2]; // [rsp+E0h] [rbp-20h] BYREF
  LPVOID v109; // [rsp+F0h] [rbp-10h]
  LPVOID v110; // [rsp+F8h] [rbp-8h]
  LPVOID pv; // [rsp+110h] [rbp+10h]
  __int64 v112; // [rsp+118h] [rbp+18h]
  __int64 v113; // [rsp+120h] [rbp+20h]
  __int64 v114; // [rsp+128h] [rbp+28h]
  _BYTE Src[272]; // [rsp+390h] [rbp+290h] BYREF
  unsigned __int16 v116[264]; // [rsp+4A0h] [rbp+3A0h] BYREF

  v9 = a4;
  v106[0] = a4;
  Buf1[0] = a3;
  v11 = (const WCHAR *)(a2 + 44);
  v12 = (_BYTE *)(a2 + 44);
  v13 = (_BYTE *)(a2 + 564);
  if ( *(_WORD *)(a2 + 564) && !(unsigned int)IsAppCompatModeEnabled(19) )
    v12 = v13;
  v14 = -1;
  v15 = (unsigned int)DoesStringRoundTripW(v12, Src, 260) == 0;
  v16 = -1;
  if ( v15 )
  {
    do
      ++v16;
    while ( *(_WORD *)&v12[2 * v16] );
    v17 = 2 * v16 + 2;
    *(_DWORD *)v102 = 1;
  }
  else
  {
    do
      ++v16;
    while ( Src[v16] );
    v17 = v16 + 1;
    v12 = Src;
    *(_DWORD *)v102 = 0;
  }
  LODWORD(Size[0]) = v17;
  v18 = -1;
  do
    ++v18;
  while ( v11[v18] );
  v97 = 2 * v18 + 2;
  v19 = 42;
  if ( (a7 & 8) == 0 )
    v19 = 46;
  v20 = 2 * v18 + 2 + v19;
  v96 = 0;
  if ( (a7 & 1) != 0 )
  {
    if ( !v9 )
    {
      if ( (int)CFSFolder::_DiscoverLocalizedName(
                  a1,
                  (const struct _ITEMIDLIST_RELATIVE *)Buf1[0],
                  (const struct tagWIN32_FIND_DATA_EX *)a2,
                  v116,
                  v95) < 0 )
        goto LABEL_11;
      v9 = v116;
      v106[0] = v116;
    }
    do
      ++v14;
    while ( v9[v14] );
    v96 = v14 + 1;
    v20 += 2 * (v14 + 1);
  }
  else
  {
    v106[0] = 0;
  }
LABEL_11:
  v21 = (v17 + 15) & 0xFFFFFFFE;
  v22 = (v20 + 1) & 0xFFFFFFFE;
  p_cb = 0;
  v24 = *((_QWORD *)a1 + 77);
  v25 = 2;
  if ( !v24 || Buf1[0] )
  {
    if ( (unsigned int)v21 > 0xFFFF )
      goto LABEL_72;
    if ( v22 > 0xFFFF )
      goto LABEL_72;
    v26 = v22 + v21;
    if ( (unsigned __int64)(v22 + (unsigned int)v21) + 2 > 0xFFFF )
      goto LABEL_72;
    *(_DWORD *)FatDate = v26 + 2;
    v27 = (ITEMIDLIST *)CoTaskMemAlloc((unsigned int)(v26 + 4));
    if ( !v27 )
      goto LABEL_72;
    v28 = 0;
    ppMalloc[0] = 0;
    if ( CoGetMalloc(1u, ppMalloc) >= 0 )
    {
      v28 = ((__int64 (__fastcall *)(LPMALLOC, ITEMIDLIST *))ppMalloc[0]->lpVtbl->GetSize)(ppMalloc[0], v27);
      ((void (__fastcall *)(LPMALLOC))ppMalloc[0]->lpVtbl->Release)(ppMalloc[0]);
    }
    memset_0(v27, 0, v28);
    *(USHORT *)((char *)&v27->mkid.cb + v21) = v22 + 2;
    v29 = FatDate[0];
    v27->mkid.cb = FatDate[0];
    *(_WORD *)((char *)v27 + v29 - 2) = v21;
    *(_DWORD *)((char *)&v27[1].mkid.cb + 1) = *(_DWORD *)(a2 + 32);
    v27[4].mkid.cb = *(_WORD *)a2;
    FatDate[0] = 0;
    FatTime[0] = 0;
    v30 = (const FILETIME *)(a2 + 20);
    if ( FileTimeToDosDateTime((const FILETIME *)(a2 + 20), FatDate, FatTime) )
    {
      *(_WORD *)v27[2].mkid.abID = FatDate[0];
      *(USHORT *)((char *)&v27[3].mkid.cb + 1) = FatTime[0];
    }
    else if ( *(unsigned int *)(a2 + 20) + ((unsigned __int64)*(unsigned int *)(a2 + 24) << 32) )
    {
      *(_WORD *)v27[2].mkid.abID = 1;
    }
    memcpy_0(v27[4].mkid.abID, v12, LODWORD(Size[0]));
    v31 = ((*(_BYTE *)a2 & 0x10) == 0) + 49;
    v27->mkid.abID[0] = v31;
    v32 = (CFSFolder *)(*((_QWORD *)a1 + 62) - *(_QWORD *)&FOLDERID_PublicDesktop.Data1);
    if ( !v32 )
      v32 = (CFSFolder *)(*((_QWORD *)a1 + 63) - *(_QWORD *)FOLDERID_PublicDesktop.Data4);
    if ( !v32 )
    {
      v31 |= 0x38u;
      v27->mkid.abID[0] = v31;
    }
    if ( *(_DWORD *)v102 )
      v27->mkid.abID[0] = v31 | 0x34;
    v33 = (char *)v27 + (unsigned int)v21;
    if ( (a7 & 8) != 0 )
    {
      CFSFolder::_PopulateIDXHelper(
        v32,
        (const struct tagWIN32_FIND_DATA_EX *)a2,
        (struct IDFOLDEREX_V3 *)((char *)v27 + (unsigned int)v21));
      *((_WORD *)v33 + 1) = 8;
      *((_WORD *)v33 + 8) = 42;
      ualstrcpynW(v33 + 42, v11, v97 >> 1);
      v92 = v106[0];
      if ( v106[0] )
      {
        *((_WORD *)v33 + 18) = v97 + 42;
        ualstrcpynW(&v33[(unsigned __int16)(v97 + 42)], v92, v96);
      }
    }
    else
    {
      *((_DWORD *)v33 + 1) = -1091633148;
      *((_DWORD *)v33 + 7) = *(_DWORD *)(a2 + 28);
      FatTime[0] = 0;
      FatDate[0] = 0;
      if ( FileTimeToDosDateTime((const FILETIME *)(a2 + 4), FatTime, FatDate) )
      {
        *((_WORD *)v33 + 4) = FatTime[0];
        *((_WORD *)v33 + 5) = FatDate[0];
      }
      if ( FileTimeToDosDateTime((const FILETIME *)(a2 + 12), FatTime, FatDate) )
      {
        *((_WORD *)v33 + 6) = FatTime[0];
        *((_WORD *)v33 + 7) = FatDate[0];
      }
      *(_QWORD *)(v33 + 20) = *(_QWORD *)(a2 + 592);
      *((_DWORD *)v33 + 8) = *(_DWORD *)(a2 + 36);
      *((_WORD *)v33 + 1) = 9;
      *((_WORD *)v33 + 8) = 46;
      ualstrcpynW(v33 + 46, v11, v97 >> 1);
      v34 = v106[0];
      if ( v106[0] )
      {
        *((_WORD *)v33 + 18) = v97 + 46;
        ualstrcpynW(&v33[(unsigned __int16)(v97 + 46)], v34, v96);
      }
      *(_DWORD *)(v33 + 42) = 0;
      LOWORD(Size[0]) = 0;
      v102[0] = 0;
      if ( FileTimeToDosDateTime(v30, (LPWORD)Size, v102) )
      {
        ppMalloc[0] = 0;
        if ( DosDateTimeToFileTime(Size[0], v102[0], (LPFILETIME)ppMalloc) )
          *(_DWORD *)(v33 + 42) = LODWORD(ppMalloc[0]) - v30->dwLowDateTime;
      }
    }
    v35 = 0;
    if ( a8 == FEM_NAVIGATION )
    {
      FolderValue = 0;
      CFileSysItemString::CFileSysItemString(
        (CFileSysItemString *)v108,
        a1,
        (const struct _ITEMIDLIST_RELATIVE *)v27,
        0);
      *(_OWORD *)ppMalloc = 0;
      if ( (unsigned int)CFileSysItemString::GetJunctionClsid(v108, 3, ppMalloc) )
        FolderValue = CCLSIDInfoCache::GetFolderValue(v38, ppMalloc, 0x4000);
      v108[0] = &CFileSysItemString::`vftable';
      v39 = v114;
      v114 = 0;
      if ( v39 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      v40 = v112;
      v112 = 0;
      if ( v40 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      v41 = v113;
      v113 = 0;
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v110 )
        CoTaskMemFree(v110);
      if ( v109 )
        CoTaskMemFree(v109);
      if ( FolderValue )
        v35 = 1;
    }
    *(_DWORD *)(v33 + 38) = v35;
    p_cb = &v27->mkid.cb;
    v36 = v27;
  }
  else
  {
    v46 = (unsigned __int16 *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 24LL))(
                                v24,
                                (unsigned int)(v21 + 6));
    *(_QWORD *)FatDate = v46;
    if ( !v46 )
      goto LABEL_72;
    v27 = 0;
    v47 = ILCreateWithHidden(*v46, v22);
    v48 = *(unsigned __int16 **)FatDate;
    if ( v47 )
    {
      p_cb = (unsigned __int16 *)v47;
      memcpy_0((void *)(v47 + 2), (const void *)(*(_QWORD *)FatDate + 2LL), (unsigned __int16)**(_WORD **)FatDate - 2LL);
      *(_DWORD *)(p_cb + 3) = 1179862595;
      v27 = (ITEMIDLIST *)(p_cb + 5);
      p_cb[5] = v21;
      *(_DWORD *)(p_cb + 7) = *(_DWORD *)(a2 + 32);
      p_cb[11] = *(_WORD *)a2;
      FatDate[0] = 0;
      FatTime[0] = 0;
      if ( FileTimeToDosDateTime((const FILETIME *)(a2 + 20), FatDate, FatTime) )
      {
        p_cb[9] = FatDate[0];
        p_cb[10] = FatTime[0];
      }
      else if ( *(unsigned int *)(a2 + 20) + ((unsigned __int64)*(unsigned int *)(a2 + 24) << 32) )
      {
        p_cb[9] = 1;
      }
      memcpy_0(p_cb + 12, v12, LODWORD(Size[0]));
      v49 = ((*(_BYTE *)a2 & 0x10) == 0) + 49;
      *((_BYTE *)p_cb + 12) = v49;
      v50 = (CFSFolder *)(*((_QWORD *)a1 + 62) - *(_QWORD *)&FOLDERID_PublicDesktop.Data1);
      if ( !v50 )
        v50 = (CFSFolder *)(*((_QWORD *)a1 + 63) - *(_QWORD *)FOLDERID_PublicDesktop.Data4);
      if ( !v50 )
      {
        v49 |= 0x38u;
        *((_BYTE *)p_cb + 12) = v49;
      }
      if ( *(_DWORD *)v102 )
        *((_BYTE *)p_cb + 12) = v49 | 0x34;
      v51 = (char *)p_cb + *v48;
      if ( (a7 & 8) != 0 )
        CFSFolder::_PopulateIDXV3(
          v50,
          (const struct tagWIN32_FIND_DATA_EX *)a2,
          v97,
          v106[0],
          v96,
          (struct IDFOLDEREX_V3 *)v51);
      else
        CFSFolder::_PopulateIDXLatest(
          v50,
          (const struct tagWIN32_FIND_DATA_EX *)a2,
          v97,
          v106[0],
          v96,
          (struct IDFOLDEREX_V4 *)v51);
      *(_DWORD *)(v51 + 38) = CFSFolder::_GetEnumMode(a1, (const struct _ITEMID_CHILD *)p_cb, a8);
    }
    CoTaskMemFree(v48);
    if ( !p_cb )
      goto LABEL_72;
    if ( !v27 )
      goto LABEL_110;
    v36 = (ITEMIDLIST *)p_cb;
  }
  if ( (a7 & 2) == 0 )
    goto LABEL_110;
  *(_OWORD *)FatDate = *(_OWORD *)(a2 + 600);
  if ( memcmp_0(FatDate, &GUID_NULL, 0x10u) || (a7 & 4) == 0 )
    goto LABEL_123;
  abID = (char *)v27->mkid.abID;
  v53 = (v27->mkid.abID[0] & 0x37) - 49;
  *(GUID *)FatDate = GUID_NULL;
  if ( (v53 & 0xFB) == 0 )
  {
    v54 = 1;
LABEL_97:
    *(_OWORD *)ppMalloc = 0;
    ExtensionW = PathFindExtensionW(v11);
    if ( ExtensionW )
    {
      if ( *ExtensionW == 46 && ExtensionW[1] == 123 )
      {
        *(_OWORD *)v106 = 0;
        if ( (int)SHCLSIDFromStringEx(ExtensionW + 1, v56, ppMalloc) >= 0
          && (!v54 || !(unsigned int)CCLSIDInfoCache::GetFolderValue(v57, ppMalloc, 4096)) )
        {
          *(_OWORD *)FatDate = *(_OWORD *)ppMalloc;
          goto LABEL_123;
        }
      }
    }
    goto LABEL_137;
  }
  p_cb = &v36->mkid.cb;
  if ( SHRestricted(REST_ALLOWFILECLSIDJUNCTIONS) )
  {
    v54 = 0;
    goto LABEL_97;
  }
LABEL_137:
  if ( (((*abID & 0x37) - 49) & 0xFB) != 0 || *abID < 0 || (v27[4].mkid.cb & 5) == 0 )
    goto LABEL_123;
  if ( Buf1[0] )
  {
    v80 = (unsigned __int16 *)Buf1[0];
    v81 = 2;
    do
    {
      v82 = *v80;
      if ( !(_WORD)v82 )
        break;
      v81 += v82;
      v80 = (unsigned __int16 *)((char *)v80 + v82);
    }
    while ( v80 );
    v83 = (unsigned int)(v81 - 2);
    v84 = v27;
    v85 = 2;
    do
    {
      cb = v84->mkid.cb;
      if ( !(_WORD)cb )
        break;
      v85 += cb;
      v84 = (ITEMIDLIST *)((char *)v84 + cb);
    }
    while ( v84 );
    v87 = (ITEMIDLIST *)WINRT_IMPL_CoTaskMemAlloc(v85 + (unsigned int)v83);
    v88 = v87;
    v98 = v87;
    if ( v87 )
    {
      memset_0(v87, 0, v85 + (unsigned int)v83);
      memcpy_0(v88, Buf1[0], (unsigned int)v83);
      memcpy_0((char *)v88 + v83, v27, v85);
    }
  }
  else
  {
    v88 = ILClone(v27);
    v98 = v88;
  }
  if ( !v88 )
    goto LABEL_123;
  ppMalloc[0] = 0;
  if ( (*(int (__fastcall **)(_QWORD *, LPITEMIDLIST, _QWORD, GUID *, LPMALLOC *))(*((_QWORD *)a1 + 6) + 40LL))(
         (_QWORD *)a1 + 6,
         v88,
         0,
         &GUID_b57046bc_32e5_428a_9887_19f712b907bf,
         ppMalloc) < 0 )
    goto LABEL_160;
  v89 = ppMalloc[0];
  v90 = 0;
  v91 = 0;
  while ( v91 < 3 )
  {
    v106[0] = 0;
    if ( ((int (__fastcall *)(LPMALLOC, const wchar_t *, wchar_t *, _QWORD, _DWORD, unsigned __int16 **))v89->lpVtbl->GetSize)(
           v89,
           L".ShellClassInfo",
           off_18066C640[v91],
           0,
           0,
           v106) >= 0 )
    {
      v93 = v106[0];
      if ( *v106[0] )
      {
        v94 = GUID_NULL;
        *(GUID *)Buf1 = GUID_NULL;
        if ( v106[0] )
        {
          v15 = (unsigned int)GUIDFromStringW(v106[0]) == 0;
          v93 = v106[0];
          if ( !v15 )
          {
            v94 = *(GUID *)Buf1;
            goto LABEL_171;
          }
        }
        else
        {
LABEL_171:
          if ( v91 == 2 )
          {
            v15 = memcmp_0(Buf1, &GUID_7bd29e00_76c1_11cf_9dd0_00a0c9034933, 0x10u) == 0;
            v93 = v106[0];
            if ( v15 )
            {
              *(GUID *)FatDate = GUID_7bd29e01_76c1_11cf_9dd0_00a0c9034933;
              v90 = 1;
              CoTaskMemFree(v106[0]);
              goto LABEL_158;
            }
          }
          else
          {
            *(GUID *)FatDate = v94;
            v90 = 1;
          }
        }
      }
      CoTaskMemFree(v93);
    }
LABEL_158:
    ++v91;
    if ( v90 )
      break;
  }
  ((void (__fastcall *)(LPMALLOC))ppMalloc[0]->lpVtbl->Release)(ppMalloc[0]);
  v25 = 2;
  v88 = v98;
LABEL_160:
  CoTaskMemFree(v88);
LABEL_123:
  ppMalloc[0] = 0;
  if ( !memcmp_0(FatDate, &GUID_NULL, 0x10u) || (int)SHRegGetCLSIDKey(FatDate, 0, 0, 0, 1, ppMalloc) < 0 )
    goto LABEL_110;
  RegCloseKey((HKEY)ppMalloc[0]);
  v27->mkid.abID[0] |= 0x80u;
  ppMalloc[0] = (LPMALLOC)0xBEEF000300000018LL;
  *(_OWORD *)&ppMalloc[1] = *(_OWORD *)FatDate;
  if ( *p_cb )
  {
    v72 = p_cb;
    v73 = 2;
    do
    {
      v74 = *p_cb;
      if ( !(_WORD)v74 )
        break;
      v73 += v74;
      p_cb = (unsigned __int16 *)((char *)p_cb + v74);
    }
    while ( p_cb );
    v75 = (unsigned __int16 *)CoTaskMemAlloc(v73 + 26);
    p_cb = v75;
    if ( v75 )
    {
      v76 = SHGetSize(v75);
      memset_0(p_cb, 0, v76);
      memcpy_0(p_cb, v72, v73);
      v77 = *p_cb;
      if ( *p_cb )
      {
        v78 = (const struct _ITEMIDLIST_RELATIVE *)p_cb;
        do
        {
          v79 = v78;
          v78 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v78 + v77);
          v77 = *(_WORD *)v78;
        }
        while ( *(_WORD *)v78 );
      }
      else
      {
        v79 = (const struct _ITEMIDLIST_RELATIVE *)p_cb;
      }
      if ( ILFindFirstHiddenID(v79) )
        v58 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v79 + *(unsigned __int16 *)v79 - 2);
      else
        v58 = v79;
      v59 = *(_WORD *)v58;
      v60 = (unsigned __int16 *)((char *)p_cb + v73 - 2);
      memcpy_0(v60, ppMalloc, 0x18u);
      v61 = *v60 + 2;
      if ( v61 < *v60 || (*v60 = v61, v62 = *(_WORD *)v79 + v61, v62 < *(_WORD *)v79) )
      {
        CoTaskMemFree(p_cb);
        p_cb = 0;
      }
      else
      {
        *(_WORD *)v79 = v62;
        *(unsigned __int16 *)((char *)v60 + *v60 - 2) = v59;
      }
    }
    CoTaskMemFree(v72);
  }
  if ( p_cb )
  {
LABEL_110:
    if ( !a5 || (p_cb = (unsigned __int16 *)ILAppendHiddenStringW(p_cb, a6, a5)) != 0 )
    {
      v63 = *(_WORD *)(a2 + 2);
      if ( v63 )
      {
        if ( *p_cb )
        {
          v64 = p_cb;
          do
          {
            v65 = *v64;
            if ( !(_WORD)v65 )
              break;
            v25 += v65;
            v64 = (unsigned __int16 *)((char *)v64 + v65);
          }
          while ( v64 );
          v66 = CoTaskMemAlloc(v25 + 12);
          v67 = v66;
          if ( v66 )
          {
            v68 = SHGetSize(v66);
            memset_0(v67, 0, v68);
            memcpy_0(v67, p_cb, v25);
            v69 = *v67;
            if ( *v67 )
            {
              v70 = (const struct _ITEMIDLIST_RELATIVE *)v67;
              do
              {
                v71 = v70;
                v70 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v70 + v69);
                v69 = *(_WORD *)v70;
              }
              while ( *(_WORD *)v70 );
            }
            else
            {
              v71 = (const struct _ITEMIDLIST_RELATIVE *)v67;
            }
            if ( ILFindFirstHiddenID(v71) )
              v42 = (const struct _ITEMIDLIST_RELATIVE *)((char *)v71 + *(unsigned __int16 *)v71 - 2);
            else
              v42 = v71;
            v43 = *(_WORD *)v42;
            v44 = (_WORD *)((char *)v67 + v25 - 2);
            *(_DWORD *)v44 = 10;
            *((_DWORD *)v44 + 1) = -1091633111;
            v44[4] = v63;
            *v44 = 12;
            if ( (unsigned __int16)(*(_WORD *)v71 + 12) < *(_WORD *)v71 )
            {
              CoTaskMemFree(v67);
              v67 = 0;
            }
            else
            {
              *(_WORD *)v71 += 12;
              *(unsigned __int16 *)((char *)v44 + *v44 - 2) = v43;
            }
          }
          CoTaskMemFree(p_cb);
        }
        else
        {
          v67 = p_cb;
        }
        p_cb = v67;
      }
    }
  }
LABEL_72:
  *a9 = p_cb;
  result = 0;
  if ( !p_cb )
    return 2147942414LL;
  return result;
}

```

## disassembly

```asm
0x1800d8af0  push    rbp
0x1800d8af2  push    rbx
0x1800d8af3  push    rsi
0x1800d8af4  push    rdi
0x1800d8af5  push    r12
0x1800d8af7  push    r13
0x1800d8af9  push    r14
0x1800d8afb  push    r15
0x1800d8afd  lea     rbp, [rsp-5C8h]
0x1800d8b05  sub     rsp, 6C8h
0x1800d8b0c  mov     rax, cs:__security_cookie
0x1800d8b13  xor     rax, rsp
0x1800d8b16  mov     [rbp+600h+var_50], rax
0x1800d8b1d  mov     r13, r9
0x1800d8b20  mov     [rbp+600h+var_640], r9
0x1800d8b24  mov     [rbp+600h+Buf1], r8
0x1800d8b28  mov     r14, rdx
0x1800d8b2b  mov     [rsp+700h+var_6A8], rdx
0x1800d8b30  mov     [rsp+700h+var_6B0], rcx
0x1800d8b35  mov     rax, [rbp+600h+arg_20]
0x1800d8b3c  mov     [rsp+700h+var_698], rax
0x1800d8b41  mov     eax, [rbp+600h+arg_28]
0x1800d8b47  mov     [rsp+700h+var_6A0], eax
0x1800d8b4b  mov     rax, [rbp+600h+arg_40]
0x1800d8b52  mov     [rsp+700h+var_690], rax
0x1800d8b57  lea     rbx, [rdx+2Ch]
0x1800d8b5b  mov     r12, rbx
0x1800d8b5e  lea     rdi, [rdx+234h]
0x1800d8b65  cmp     word ptr [rdi], 0
0x1800d8b69  jnz     loc_1800D9033
0x1800d8b6f  mov     r8d, 104h
0x1800d8b75  lea     rdx, [rbp+600h+Src]
0x1800d8b7c  mov     rcx, r12
0x1800d8b7f  call    cs:__imp_DoesStringRoundTripW
0x1800d8b85  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x1800d8b8c  test    eax, eax
0x1800d8b8e  mov     rax, rsi
0x1800d8b91  jz      loc_1800D8F50
0x1800d8b97  lea     rcx, [rbp+600h+Src]
0x1800d8b9e  xchg    ax, ax
0x1800d8ba0  lea     rax, [rax+1]
0x1800d8ba4  cmp     byte ptr [rcx+rax], 0
0x1800d8ba8  jnz     short loc_1800D8BA0
0x1800d8baa  lea     r15d, [rax+1]
0x1800d8bae  lea     r12, [rbp+600h+Src]
0x1800d8bb5  mov     dword ptr [rsp+700h+var_684], 0
0x1800d8bbd  mov     dword ptr [rbp+600h+Size], r15d
0x1800d8bc1  mov     rax, rsi
0x1800d8bc4  lea     rax, [rax+1]
0x1800d8bc8  cmp     word ptr [rbx+rax*2], 0
0x1800d8bcd  jnz     short loc_1800D8BC4
0x1800d8bcf  lea     edx, ds:2[rax*2]
0x1800d8bd6  mov     [rsp+700h+var_6BC], edx
0x1800d8bda  mov     ecx, dword ptr [rbp+600h+arg_30]
0x1800d8be0  mov     eax, ecx
0x1800d8be2  and     eax, 8
0x1800d8be5  mov     dword ptr [rsp+700h+var_6B8], eax
0x1800d8be9  mov     edi, 2Ah ; '*'
0x1800d8bee  mov     r8d, 2Eh ; '.'
0x1800d8bf4  cmovz   edi, r8d
0x1800d8bf8  add     edi, edx
0x1800d8bfa  xor     edx, edx
0x1800d8bfc  mov     [rsp+700h+var_6C0], edx
0x1800d8c00  test    cl, 1
0x1800d8c03  jnz     loc_1800D8ED5
0x1800d8c09  mov     [rbp+600h+var_640], rdx
0x1800d8c0d  add     r15d, 0Fh
0x1800d8c11  and     r15d, 0FFFFFFFEh
0x1800d8c15  lea     r14d, [rdi+1]
0x1800d8c19  and     r14d, 0FFFFFFFEh
0x1800d8c1d  mov     rdi, rdx
0x1800d8c20  mov     rax, [rsp+700h+var_6B0]
0x1800d8c25  mov     rcx, [rax+268h]
0x1800d8c2c  mov     r13d, 2
0x1800d8c32  test    rcx, rcx
0x1800d8c35  jnz     loc_1800D90F8
0x1800d8c3b  cmp     r15d, 0FFFFh
0x1800d8c42  ja      loc_1800D90C0
0x1800d8c48  cmp     r14d, 0FFFFh
0x1800d8c4f  ja      loc_1800D90C0
0x1800d8c55  lea     ecx, [r14+r15]
0x1800d8c59  mov     eax, ecx
0x1800d8c5b  add     rax, r13
0x1800d8c5e  cmp     rax, 0FFFFh
0x1800d8c64  ja      loc_1800D90C0
0x1800d8c6a  lea     eax, [rcx+2]
0x1800d8c6d  mov     dword ptr [rbp+600h+FatDate], eax
0x1800d8c70  lea     ecx, [rax+2]; cb
0x1800d8c73  call    cs:__imp_CoTaskMemAlloc
0x1800d8c79  mov     rsi, rax
0x1800d8c7c  test    rax, rax
0x1800d8c7f  jz      loc_1800D90C0
0x1800d8c85  xor     edi, edi
0x1800d8c87  mov     [rbp+600h+ppMalloc], rdi
0x1800d8c8b  lea     rdx, [rbp+600h+ppMalloc]; ppMalloc
0x1800d8c8f  mov     ecx, 1; dwMemContext
0x1800d8c94  call    cs:__imp_CoGetMalloc
0x1800d8c9a  test    eax, eax
0x1800d8c9c  js      short loc_1800D8CC4
0x1800d8c9e  mov     rcx, [rbp+600h+ppMalloc]
0x1800d8ca2  mov     rdx, [rcx]
0x1800d8ca5  mov     rax, [rdx+30h]
0x1800d8ca9  mov     rdx, rsi
0x1800d8cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8cb1  mov     rdi, rax
0x1800d8cb4  mov     rcx, [rbp+600h+ppMalloc]
0x1800d8cb8  mov     rdx, [rcx]
0x1800d8cbb  mov     rax, [rdx+10h]
0x1800d8cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8cc4  mov     r8, rdi; Size
0x1800d8cc7  xor     edx, edx; Val
0x1800d8cc9  mov     rcx, rsi; void *
0x1800d8ccc  call    memset_0
0x1800d8cd1  add     r14w, r13w
0x1800d8cd5  mov     [r15+rsi], r14w
0x1800d8cda  movzx   eax, [rbp+600h+FatDate]
0x1800d8cde  mov     [rsi], ax
0x1800d8ce1  mov     [rax+rsi-2], r15w
0x1800d8ce7  mov     rcx, [rsp+700h+var_6A8]
0x1800d8cec  mov     eax, [rcx+20h]
0x1800d8cef  mov     [rsi+4], eax
0x1800d8cf2  movzx   eax, word ptr [rcx]
0x1800d8cf5  mov     [rsi+0Ch], ax
0x1800d8cf9  xor     eax, eax
0x1800d8cfb  mov     [rbp+600h+FatDate], ax
0x1800d8cff  mov     [rsp+700h+FatTime], ax
0x1800d8d04  lea     r14, [rcx+14h]
0x1800d8d08  lea     r8, [rsp+700h+FatTime]; lpFatTime
0x1800d8d0d  lea     rdx, [rbp+600h+FatDate]; lpFatDate
0x1800d8d11  mov     rcx, r14; lpFileTime
0x1800d8d14  call    cs:__imp_FileTimeToDosDateTime
0x1800d8d1a  test    eax, eax
0x1800d8d1c  jz      loc_1800D8F2C
0x1800d8d22  movzx   eax, [rbp+600h+FatDate]
0x1800d8d26  mov     [rsi+8], ax
0x1800d8d2a  movzx   eax, [rsp+700h+FatTime]
0x1800d8d2f  mov     [rsi+0Ah], ax
0x1800d8d33  mov     r8d, dword ptr [rbp+600h+Size]; Size
0x1800d8d37  lea     rcx, [rsi+0Eh]; void *
0x1800d8d3b  mov     rdx, r12; Src
0x1800d8d3e  call    memcpy_0
0x1800d8d43  mov     r12, [rsp+700h+var_6A8]
0x1800d8d48  test    byte ptr [r12], 10h
0x1800d8d4d  setz    al
0x1800d8d50  add     al, 31h ; '1'
0x1800d8d52  mov     [rsi+2], al
0x1800d8d55  mov     rdx, [rsp+700h+var_6B0]
0x1800d8d5a  mov     rcx, [rdx+1F0h]
0x1800d8d61  sub     rcx, qword ptr cs:FOLDERID_PublicDesktop.Data1
0x1800d8d68  jnz     short loc_1800D8D78
0x1800d8d6a  mov     rcx, [rdx+1F8h]
0x1800d8d71  sub     rcx, qword ptr cs:FOLDERID_PublicDesktop.Data4; this
0x1800d8d78  test    rcx, rcx
0x1800d8d7b  jnz     short loc_1800D8D82
0x1800d8d7d  or      al, 38h
0x1800d8d7f  mov     [rsi+2], al
0x1800d8d82  cmp     dword ptr [rsp+700h+var_684], 0
0x1800d8d87  jz      short loc_1800D8D8E
0x1800d8d89  or      al, 34h
0x1800d8d8b  mov     [rsi+2], al
0x1800d8d8e  mov     edi, r15d
0x1800d8d91  add     rdi, rsi
0x1800d8d94  cmp     dword ptr [rsp+700h+var_6B8], 0
0x1800d8d99  jnz     loc_1800D975A
0x1800d8d9f  mov     dword ptr [rdi+4], 0BEEF0004h
0x1800d8da6  mov     eax, [r12+1Ch]
0x1800d8dab  mov     [rdi+1Ch], eax
0x1800d8dae  xor     eax, eax
0x1800d8db0  mov     [rsp+700h+FatTime], ax
0x1800d8db5  mov     [rbp+600h+FatDate], ax
0x1800d8db9  lea     rcx, [r12+4]; lpFileTime
0x1800d8dbe  lea     r8, [rbp+600h+FatDate]; lpFatTime
0x1800d8dc2  lea     rdx, [rsp+700h+FatTime]; lpFatDate
0x1800d8dc7  call    cs:__imp_FileTimeToDosDateTime
0x1800d8dcd  test    eax, eax
0x1800d8dcf  jz      short loc_1800D8DE2
0x1800d8dd1  movzx   eax, [rsp+700h+FatTime]
0x1800d8dd6  mov     [rdi+8], ax
0x1800d8dda  movzx   eax, [rbp+600h+FatDate]
0x1800d8dde  mov     [rdi+0Ah], ax
0x1800d8de2  lea     rcx, [r12+0Ch]; lpFileTime
0x1800d8de7  lea     r8, [rbp+600h+FatDate]; lpFatTime
0x1800d8deb  lea     rdx, [rsp+700h+FatTime]; lpFatDate
0x1800d8df0  call    cs:__imp_FileTimeToDosDateTime
0x1800d8df6  test    eax, eax
0x1800d8df8  jz      short loc_1800D8E0B
0x1800d8dfa  movzx   eax, [rsp+700h+FatTime]
0x1800d8dff  mov     [rdi+0Ch], ax
0x1800d8e03  movzx   eax, [rbp+600h+FatDate]
0x1800d8e07  mov     [rdi+0Eh], ax
0x1800d8e0b  mov     rax, [r12+250h]
0x1800d8e13  mov     [rdi+14h], rax
0x1800d8e17  mov     eax, [r12+24h]
0x1800d8e1c  mov     [rdi+20h], eax
0x1800d8e1f  mov     word ptr [rdi+2], 9
0x1800d8e25  mov     word ptr [rdi+10h], 2Eh ; '.'
0x1800d8e2b  mov     r15d, [rsp+700h+var_6BC]
0x1800d8e30  mov     r8d, r15d
0x1800d8e33  shr     r8d, 1
0x1800d8e36  lea     rcx, [rdi+2Eh]
0x1800d8e3a  mov     rdx, rbx
0x1800d8e3d  call    cs:__imp_ualstrcpynW
0x1800d8e43  mov     rax, [rbp+600h+var_640]
0x1800d8e47  test    rax, rax
0x1800d8e4a  jz      short loc_1800D8E6A
0x1800d8e4c  add     r15w, 2Eh ; '.'
0x1800d8e51  movzx   ecx, r15w
0x1800d8e55  mov     [rdi+24h], cx
0x1800d8e59  add     rcx, rdi
0x1800d8e5c  mov     r8d, [rsp+700h+var_6C0]
0x1800d8e61  mov     rdx, rax
0x1800d8e64  call    cs:__imp_ualstrcpynW
0x1800d8e6a  xor     r12d, r12d
0x1800d8e6d  mov     [rdi+2Ah], r12d
0x1800d8e71  mov     word ptr [rbp+600h+Size], r12w
0x1800d8e76  mov     [rsp+700h+var_684], r12w
0x1800d8e7c  lea     r8, [rsp+700h+var_684]; lpFatTime
0x1800d8e81  lea     rdx, [rbp+600h+Size]; lpFatDate
0x1800d8e85  mov     rcx, r14; lpFileTime
0x1800d8e88  call    cs:__imp_FileTimeToDosDateTime
0x1800d8e8e  test    eax, eax
0x1800d8e90  jz      short loc_1800D8EB6
0x1800d8e92  mov     [rbp+600h+ppMalloc], r12
0x1800d8e96  lea     r8, [rbp+600h+ppMalloc]; lpFileTime
0x1800d8e9a  movzx   edx, [rsp+700h+var_684]; wFatTime
0x1800d8e9f  movzx   ecx, word ptr [rbp+600h+Size]; wFatDate
0x1800d8ea3  call    cs:__imp_DosDateTimeToFileTime
0x1800d8ea9  test    eax, eax
0x1800d8eab  jz      short loc_1800D8EB6
0x1800d8ead  mov     eax, dword ptr [rbp+600h+ppMalloc]
0x1800d8eb0  sub     eax, [r14]
0x1800d8eb3  mov     [rdi+2Ah], eax
0x1800d8eb6  mov     r14d, r12d
0x1800d8eb9  cmp     [rbp+600h+arg_38], 1
0x1800d8ec0  jz      loc_1800D8F71
0x1800d8ec6  mov     [rdi+26h], r14d
0x1800d8eca  mov     rdi, rsi
0x1800d8ecd  mov     r14, rsi
0x1800d8ed0  jmp     loc_1800D9266
0x1800d8ed5  test    r13, r13
0x1800d8ed8  jnz     short loc_1800D8F10
0x1800d8eda  lea     r9, [rbp+600h+var_260]; unsigned __int16 *
0x1800d8ee1  mov     r8, r14; struct tagWIN32_FIND_DATA_EX *
0x1800d8ee4  mov     rdx, [rbp+600h+Buf1]; struct _ITEMIDLIST_RELATIVE *
0x1800d8ee8  mov     rcx, [rsp+700h+var_6B0]; this
0x1800d8eed  call    ?_DiscoverLocalizedName@CFSFolder@@IEAAJPEFBU_ITEMIDLIST_RELATIVE@@PEBUtagWIN32_FIND_DATA_EX@@PEAGI@Z; CFSFolder::_DiscoverLocalizedName(_ITEMIDLIST_RELATIVE const *,tagWIN32_FIND_DATA_EX const *,ushort *,uint)
0x1800d8ef2  xor     edx, edx
0x1800d8ef4  test    eax, eax
0x1800d8ef6  js      loc_1800D8C0D
0x1800d8efc  lea     r13, [rbp+600h+var_260]
0x1800d8f03  mov     [rbp+600h+var_640], r13
0x1800d8f07  nop     word ptr [rax+rax+00000000h]
0x1800d8f10  lea     rsi, [rsi+1]
0x1800d8f14  cmp     word ptr [r13+rsi*2+0], 0
0x1800d8f1b  jnz     short loc_1800D8F10
0x1800d8f1d  lea     eax, [rsi+1]
0x1800d8f20  mov     [rsp+700h+var_6C0], eax
0x1800d8f24  lea     edi, [rdi+rax*2]
0x1800d8f27  jmp     loc_1800D8C0D
0x1800d8f2c  mov     ecx, [r14+4]
0x1800d8f30  shl     rcx, 20h
0x1800d8f34  mov     eax, [r14]
0x1800d8f37  add     rcx, rax
0x1800d8f3a  jz      loc_1800D8D33
0x1800d8f40  mov     word ptr [rsi+8], 1
0x1800d8f46  jmp     loc_1800D8D33
0x1800d8f50  lea     rax, [rax+1]
0x1800d8f54  cmp     word ptr [r12+rax*2], 0
0x1800d8f5a  jnz     short loc_1800D8F50
0x1800d8f5c  lea     r15d, ds:2[rax*2]
0x1800d8f64  mov     dword ptr [rsp+700h+var_684], 1
0x1800d8f6c  jmp     loc_1800D8BBD
0x1800d8f71  mov     r15d, r12d
0x1800d8f74  xor     r9d, r9d; struct IDFOLDER *
0x1800d8f77  mov     r8, rsi; struct _ITEMIDLIST_RELATIVE *
0x1800d8f7a  mov     rdx, [rsp+700h+var_6B0]; struct CFSFolder *
0x1800d8f7f  lea     rcx, [rbp+600h+var_620]; this
0x1800d8f83  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x1800d8f88  nop
0x1800d8f89  xorps   xmm0, xmm0
0x1800d8f8c  movups  xmmword ptr [rbp+600h+ppMalloc], xmm0
0x1800d8f90  lea     r8, [rbp+600h+ppMalloc]
0x1800d8f94  mov     edx, 3
0x1800d8f99  lea     rcx, [rbp+600h+var_620]
0x1800d8f9d  call    ?GetJunctionClsid@CFileSysItemString@@QEAAHW4FSIS_JUNCTION_FLAGS@@PEAU_GUID@@@Z; CFileSysItemString::GetJunctionClsid(FSIS_JUNCTION_FLAGS,_GUID *)
0x1800d8fa2  test    eax, eax
0x1800d8fa4  jnz     loc_1800D9057
0x1800d8faa  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x1800d8fb1  mov     [rbp+600h+var_620], rax
0x1800d8fb5  mov     rcx, [rbp+600h+var_5D8]
0x1800d8fb9  mov     [rbp+600h+var_5D8], r12
0x1800d8fbd  test    rcx, rcx
0x1800d8fc0  jz      short loc_1800D8FCE
0x1800d8fc2  mov     rdx, [rcx]
0x1800d8fc5  mov     rax, [rdx+10h]
0x1800d8fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d8fce  mov     rcx, [rbp+600h+var_5E8]
0x1800d8fd2  mov     [rbp+600h+var_5E8], r12
0x1800d8fd6  test    rcx, rcx
0x1800d8fd9  jnz     short loc_1800D9049
  ... truncated ...
```
