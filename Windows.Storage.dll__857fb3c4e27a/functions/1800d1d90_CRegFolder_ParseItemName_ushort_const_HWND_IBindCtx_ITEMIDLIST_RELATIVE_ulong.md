# CRegFolder::_ParseItemName(ushort const *,HWND__ *,IBindCtx *,_ITEMIDLIST_RELATIVE * *,ulong *)

- ea: `0x1800d1d90`
- end: `0x1800d2806`
- name: `?_ParseItemName@CRegFolder@@AEAAJPEBGPEAUHWND__@@PEAUIBindCtx@@PEAPEAU_ITEMIDLIST_RELATIVE@@PEAK@Z`
- size: `2678`
- prototype: `__int64 __usercall@<rax>(CRegFolder *__hidden this@<rcx>, const unsigned __int16 *@<rdx>, HWND@<r8>, struct IBindCtx *@<r9>, struct _ITEMIDLIST_RELATIVE **, unsigned int *)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800d2810`

## callees

- `0x180054860`
- `0x180068330`
- `0x1800945b0`
- `0x180094c70`
- `0x1800d0ac0`
- `0x1800d0ba8`
- `0x1800d1d90`
- `0x1800d998c`
- `0x1800d9b80`
- `0x1800e0c40`
- `0x1800e2c40`
- `0x1800e4810`
- `0x1800e5330`
- `0x1801279b0`
- `0x18014c440`
- `0x18016cd40`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a5bc5`
- `0x1803a96d9`
- `0x1803a96e5`
- `0x1803d3328`
- `0x1804d5814`
- `0x18052bcbc`
- `0x18052c250`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d2170`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d2279`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d2170`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800d2279`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d215e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d2670`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d215e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d2670`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800d22ec`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x1800d22ec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d218b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d233c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d218b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800d233c`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800d21a9`
- `api-ms-win-core-com-l1-1-0!CoGetMalloc` at `0x1800d21a9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d2208`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d23f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d24ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d25f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d262e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d2208`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d23f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d24ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d25f5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800d262e`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800d210b`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1800d210b`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800d242e`
- `SHCORE!__imp_IsAppCompatModeEnabled` at `0x1800d242e`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800d1e2f`
- `SHCORE!__imp_GUIDFromStringW` at `0x1800d1e2f`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x1800d1f8e`
- `api-ms-win-shcore-registry-l1-1-0!SHGetValueW` at `0x1800d1f8e`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1800d1f58`
- `api-ms-win-shcore-registry-l1-1-0!SHQueryValueExW` at `0x1800d1f58`

## string_xrefs

- `0x1800d1e53`: `BlockRegItemParsing`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRegFolder::_ParseItemName(
        CRegFolder *this,
        const unsigned __int16 *a2,
        IMalloc *a3,
        struct IBindCtx *a4,
        struct _ITEMIDLIST_RELATIVE **a5,
        unsigned int *a6)
{
  struct IBindCtx *v6; // r15
  CRegFolder *v8; // r12
  const WCHAR *v9; // rsi
  const unsigned __int16 *v10; // rdi
  unsigned __int16 v11; // ax
  unsigned int v12; // ebx
  HKEY v13; // rax
  HKEY v14; // rsi
  int v15; // eax
  char v16; // bl
  unsigned int v17; // r14d
  CRegFolder *v18; // rcx
  __int64 result; // rax
  unsigned __int64 v20; // rax
  __int64 v21; // rdx
  unsigned __int64 v22; // rax
  __int64 v23; // r8
  HKEY v24; // rax
  GUID *v25; // rax
  int v26; // edx
  _QWORD *v27; // r8
  __int64 v28; // rax
  size_t v29; // rdi
  void *v30; // rbx
  size_t v31; // r14
  int v32; // r14d
  unsigned __int16 *v33; // rdx
  __int64 v34; // rcx
  int v35; // r15d
  int DisplayName; // eax
  HKEY v37; // rbx
  unsigned __int16 *v38; // rdx
  unsigned int v39; // r15d
  __int64 v40; // rcx
  ITEMIDLIST *v41; // rax
  ITEMIDLIST *v42; // r12
  size_t v43; // rax
  const struct _ITEMIDLIST_RELATIVE *ID; // r13
  const struct _ITEMIDLIST_RELATIVE *v45; // rax
  unsigned __int16 v46; // r8
  unsigned __int16 *v47; // rdx
  unsigned __int16 v48; // cx
  unsigned __int16 v49; // cx
  const struct _GUID *PIDLRCLSID; // rax
  __int64 v51; // rcx
  __int64 v52; // rax
  int v53; // eax
  int v54; // ebx
  char *v55; // rbx
  int v56; // eax
  __int64 v57; // rdx
  _BYTE v58[36]; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int *v59; // [rsp+68h] [rbp-98h]
  CRegFolder *v60; // [rsp+70h] [rbp-90h]
  HKEY hkey; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  DWORD v63[2]; // [rsp+88h] [rbp-78h] BYREF
  struct _ITEMIDLIST_ABSOLUTE **v64; // [rsp+90h] [rbp-70h] BYREF
  LPMALLOC ppMalloc; // [rsp+98h] [rbp-68h] BYREF
  DWORD pcbData[2]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned int pvData; // [rsp+A8h] [rbp-58h] BYREF
  GUID rguid; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v69; // [rsp+C0h] [rbp-40h] BYREF
  struct _GUID v70; // [rsp+C8h] [rbp-38h] BYREF
  _OWORD FileInformation[2]; // [rsp+D8h] [rbp-28h] BYREF
  int v72; // [rsp+F8h] [rbp-8h]
  OLECHAR sz[40]; // [rsp+100h] [rbp+0h] BYREF
  WCHAR SubKey[264]; // [rsp+150h] [rbp+50h] BYREF

  v6 = a4;
  *(_QWORD *)&rguid.Data1 = a4;
  ppMalloc = a3;
  v8 = this;
  v60 = this;
  v64 = a5;
  v59 = a6;
  v9 = 0;
  v10 = a2 + 2;
  v11 = a2[2];
  if ( v11 )
  {
    do
    {
      if ( v11 == 92 )
        break;
      if ( v11 == 44 && !v9 )
        v9 = v10 + 1;
      v11 = *++v10;
    }
    while ( *v10 );
  }
  v70 = GUID_NULL;
  if ( !(unsigned int)GUIDFromStringW(a2 + 2) )
    return 2147746291LL;
  hkey = 0;
  if ( v6
    && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, HKEY *))v6->lpVtbl->GetObjectParam)(
         v6,
         L"BlockRegItemParsing",
         &hkey) >= 0 )
  {
    (*(void (__fastcall **)(HKEY))(*(_QWORD *)hkey + 16LL))(hkey);
    return 2147942450LL;
  }
  if ( !v9 )
  {
    hkey = 0;
    v12 = *((_DWORD *)v8 + 89) + 22;
    v13 = (HKEY)WINRT_IMPL_CoTaskMemAlloc(v12);
    v14 = v13;
    if ( !v13 )
      return 2147942414LL;
    memset_0(v13, 0, v12);
    *(_WORD *)v14 = *((_WORD *)v8 + 178) + 20;
    *((_BYTE *)v14 + 2) = *((_BYTE *)v8 + 328);
    *(struct _GUID *)((char *)v14 + *((unsigned int *)v8 + 89) + 4) = v70;
    memset_0(v14 + 1, 0, *((unsigned int *)v8 + 89));
    phkResult = v14;
    v15 = CRegFolder::_ReqItemIndex(v8, (const struct IDLREGITEM *)v14);
    if ( v15 == -1 )
    {
      v16 = 0x80;
      hkey = 0;
      if ( CRegFolder::_OpenItemKey(v8, (const struct IDLREGITEM *)v14, 0, &hkey) >= 0 )
      {
        pvData = 0;
        pcbData[0] = 4;
        v63[0] = 4;
        if ( !SHQueryValueExW(hkey, L"SortOrderIndex", 0, 0, &pvData, pcbData)
          || !SHGetValueW(hkey, L"ShellFolder", L"SortOrderIndex", 0, &pvData, v63) )
        {
          if ( (unsigned int)IsAppCompatModeEnabled(4) && pvData <= 0x50 )
          {
            pvData = 81;
          }
          else if ( pvData - 66 <= 1 )
          {
            pvData = 71;
          }
          PIDLRCLSID = CRegFolder::_GetPIDLRCLSID(v8, (const struct IDLREGITEM *)phkResult);
          v51 = *(_QWORD *)&PIDLRCLSID->Data1 - *(_QWORD *)&CLSID_OneDriveRegItem.Data1;
          if ( *(_QWORD *)&PIDLRCLSID->Data1 == *(_QWORD *)&CLSID_OneDriveRegItem.Data1 )
            v51 = *(_QWORD *)PIDLRCLSID->Data4 - *(_QWORD *)CLSID_OneDriveRegItem.Data4;
          if ( !v51 )
            pvData = 67;
          v52 = _lambda_b461f0d585b4e5be4448ff82c363a670_::_lambda_b461f0d585b4e5be4448ff82c363a670_(
                  v58,
                  v8,
                  &phkResult,
                  &pvData);
          lambda_765ffb8db86ed4afb5abae4e5fbaf899_::operator()(v52);
          v16 = pvData;
        }
      }
      if ( hkey )
        RegCloseKey(hkey);
    }
    else
    {
      v16 = *(_BYTE *)(*((_QWORD *)v8 + 43) + 48LL * v15 + 28);
    }
    *((_BYTE *)v14 + 3) = v16;
    v69 = 0;
    CRegFolder::_AttributesOf(v8, (const struct IDLREGITEM *)v14, 0x60000000u, &v69);
    v17 = 2;
    if ( (v69 & 0x60000000) == 0x60000000 )
    {
      v35 = 0;
      phkResult = 0;
      DisplayName = CRegFolder::_GetDisplayName(
                      (struct IShellItem2 *)v8,
                      (const struct IDLREGITEM *)v14,
                      0x8000u,
                      (unsigned __int16 **)&phkResult);
      v37 = phkResult;
      if ( DisplayName >= 0 )
      {
        memset(&v58[12], 0, 24);
        *(_QWORD *)v58 = 0xBEEF002600010024uLL;
        *(_DWORD *)&v58[8] = 16;
        memset(FileInformation, 0, sizeof(FileInformation));
        v72 = 0;
        if ( GetFileAttributesExW((LPCWSTR)phkResult, GetFileExInfoStandard, FileInformation) )
        {
          *(_DWORD *)&v58[8] = FileInformation[0];
          *(_QWORD *)&v58[12] = *(_QWORD *)((char *)FileInformation + 4);
          *(_QWORD *)&v58[20] = *(_QWORD *)((char *)&FileInformation[1] + 4);
          *(_QWORD *)&v58[28] = *(_QWORD *)((char *)FileInformation + 12);
        }
        if ( *(_WORD *)v14 )
        {
          v38 = (unsigned __int16 *)v14;
          v39 = 2;
          do
          {
            v40 = *v38;
            if ( !(_WORD)v40 )
              break;
            v39 += v40;
            v38 = (unsigned __int16 *)((char *)v38 + v40);
          }
          while ( v38 );
          v41 = (ITEMIDLIST *)CoTaskMemAlloc(v39 + 38);
          v42 = v41;
          if ( v41 )
          {
            v43 = SHGetSize(v41);
            memset_0(v42, 0, v43);
            memcpy_0(v42, v14, v39);
            ID = (const struct _ITEMIDLIST_RELATIVE *)ILFindLastID(v42);
            if ( ILFindFirstHiddenID(ID) )
              v45 = (const struct _ITEMIDLIST_RELATIVE *)((char *)ID + *(unsigned __int16 *)ID - 2);
            else
              v45 = ID;
            v46 = *(_WORD *)v45;
            v47 = (unsigned __int16 *)((char *)v42 + v39 - 2);
            *(_OWORD *)v47 = *(_OWORD *)v58;
            *((_OWORD *)v47 + 1) = *(_OWORD *)&v58[16];
            *((_DWORD *)v47 + 8) = *(_DWORD *)&v58[32];
            v48 = *v47 + 2;
            if ( v48 < *v47 || (*v47 = v48, v49 = *(_WORD *)ID + v48, v49 < *(_WORD *)ID) )
            {
              CoTaskMemFree(v42);
              v42 = 0;
            }
            else
            {
              *(_WORD *)ID = v49;
              *(unsigned __int16 *)((char *)v47 + *v47 - 2) = v46;
            }
          }
          CoTaskMemFree(v14);
        }
        else
        {
          v42 = (ITEMIDLIST *)v14;
        }
        v14 = (HKEY)v42;
        v35 = -2147024882;
        if ( v42 )
          v35 = 0;
        v8 = v60;
      }
      if ( v37 )
        CoTaskMemFree(v37);
      if ( v35 < 0 )
        return (unsigned int)v35;
      v6 = *(struct IBindCtx **)&rguid.Data1;
    }
    hkey = v14;
    phkResult = 0;
    if ( v6
      && ((int (__fastcall *)(struct IBindCtx *, const wchar_t *, HKEY *))v6->lpVtbl->GetObjectParam)(
           v6,
           L"HomeGroup Capabilities",
           &phkResult) >= 0 )
    {
      (*(void (__fastcall **)(HKEY))(*(_QWORD *)phkResult + 16LL))(phkResult);
      result = CRegFolder::_AppendCapabilities(v18, (struct IDLREGITEM **)&hkey, v6);
      if ( (int)result < 0 )
        return result;
      v14 = hkey;
    }
    if ( !v14 )
      goto LABEL_26;
    v20 = *(_WORD *)v14;
    if ( (unsigned int)v20 > 7 )
    {
      v21 = *((unsigned __int16 *)v14 + 2);
      if ( v20 >= v21 + 38 )
      {
        rguid = *(GUID *)((char *)v14 + v21 + 6);
        if ( !memcmp_0(&rguid, &unk_1806FB0A8, 0x10u) )
          goto LABEL_104;
      }
    }
    v22 = *(_WORD *)v14;
    if ( (unsigned int)v22 > 7
      && (v23 = *((unsigned __int16 *)v14 + 2), v22 >= v23 + 38)
      && (v55 = (char *)v14 + v23, rguid = *(GUID *)((char *)v14 + v23 + 6), !memcmp_0(&rguid, &unk_1806FB0A8, 0x10u)) )
    {
      v25 = (GUID *)(v55 + 22);
    }
    else
    {
LABEL_26:
      if ( *((_BYTE *)v14 + 2) == *((_BYTE *)v8 + 360) )
        v24 = v14;
      else
        v24 = (HKEY)((char *)v14 + *((unsigned int *)v8 + 89));
      v25 = (GUID *)(v24 + 1);
    }
    rguid = *v25;
    v26 = *((_DWORD *)v8 + 84) - 1;
    if ( v26 >= 0 )
    {
      do
      {
        v27 = *(_QWORD **)(*((_QWORD *)v8 + 43) + 48LL * v26);
        v28 = *(_QWORD *)&rguid.Data1 - *v27;
        if ( *(_QWORD *)&rguid.Data1 == *v27 )
          v28 = *(_QWORD *)rguid.Data4 - v27[1];
        if ( !v28 )
          goto LABEL_46;
      }
      while ( --v26 >= 0 );
    }
    rguid = *CRegFolder::_GetPIDLRCLSID(v8, (const struct IDLREGITEM *)v14);
    StringFromGUID2(&rguid, sz, 39);
    StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", *((_QWORD *)v8 + 38), sz);
    phkResult = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, SubKey, 0, 1u, &phkResult)
      || (phkResult = 0, !RegOpenKeyExW(HKEY_CURRENT_USER, SubKey, 0, 1u, &phkResult)) )
    {
      RegCloseKey(phkResult);
      goto LABEL_46;
    }
    rguid = *CRegFolder::_GetPIDLRCLSID(v8, (const struct IDLREGITEM *)v14);
    if ( !memcmp_0(&CLSID_ControlPanel, &rguid, 0x10u)
      || !memcmp_0(&CLSID_Printers, &rguid, 0x10u)
      || !memcmp_0(&CLSID_NetworkConnections, &rguid, 0x10u)
      || !memcmp_0(&CLSID_ScheduledTasks, &rguid, 0x10u) )
    {
LABEL_46:
      if ( *v10 )
      {
        v63[0] = 0;
        *(_QWORD *)pcbData = 0;
        v32 = CRegFolder::_BindToItem(
                v8,
                (const struct IDLREGITEM *)v14,
                v6,
                0,
                &GUID_000214e6_0000_0000_c000_000000000046,
                (void **)pcbData);
        if ( v32 >= 0 )
        {
          hkey = 0;
          v32 = (*(__int64 (__fastcall **)(_QWORD, LPMALLOC, struct IBindCtx *, const unsigned __int16 *, DWORD *, HKEY *, unsigned int *))(**(_QWORD **)pcbData + 24LL))(
                  *(_QWORD *)pcbData,
                  ppMalloc,
                  v6,
                  v10 + 1,
                  v63,
                  &hkey,
                  v59);
          if ( v32 >= 0 )
          {
            v32 = SHILCombine((const struct _ITEMIDLIST_ABSOLUTE *)v14, (const struct _ITEMIDLIST_RELATIVE *)hkey, v64);
            CoTaskMemFree(hkey);
          }
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)pcbData + 16LL))(*(_QWORD *)pcbData);
        }
      }
      else
      {
        if ( v59 && *v59 )
          CRegFolder::_AttributesOf(v8, (const struct IDLREGITEM *)v14, *v59, v59);
        if ( v14 )
        {
          v33 = (unsigned __int16 *)v14;
          do
          {
            v34 = *v33;
            if ( !(_WORD)v34 )
              break;
            v17 += v34;
            v33 = (unsigned __int16 *)((char *)v33 + v34);
          }
          while ( v33 );
          v29 = v17;
          v30 = CoTaskMemAlloc(v17);
          if ( v30 )
          {
            v31 = 0;
            ppMalloc = 0;
            if ( CoGetMalloc(1u, &ppMalloc) >= 0 )
            {
              v31 = ((__int64 (__fastcall *)(LPMALLOC, void *))ppMalloc->lpVtbl->GetSize)(ppMalloc, v30);
              ((void (__fastcall *)(LPMALLOC))ppMalloc->lpVtbl->Release)(ppMalloc);
            }
            memset_0(v30, 0, v31);
            memcpy_0(v30, v14, v29);
          }
          v32 = 0;
          if ( !v30 )
            v32 = -2147024882;
        }
        else
        {
          v30 = 0;
          v32 = -2147024809;
        }
        *v64 = (struct _ITEMIDLIST_ABSOLUTE *)v30;
      }
      goto LABEL_44;
    }
LABEL_104:
    if ( *((_DWORD *)v8 + 209)
      || (unsigned int)BindCtx_ContainsObject(v6, L"ValidateRegItems")
      || (BindCtx_GetMode(v6, 0) & 0x1000) == 0 )
    {
      v32 = -2147024809;
LABEL_44:
      CoTaskMemFree(v14);
      return (unsigned int)v32;
    }
    goto LABEL_46;
  }
  *(_QWORD *)v63 = 0;
  result = CRegFolder::_CreateCachedDelegateFolder(v8, &v70, (struct IShellFolder **)v63, 0);
  if ( (int)result >= 0 )
  {
    if ( (unsigned int)BindCtx_ContainsObject(v6, L"DelegateNamedProperties") )
    {
      v53 = (*(__int64 (__fastcall **)(_QWORD, IMalloc *, struct IBindCtx *, const WCHAR *, _QWORD, struct _ITEMIDLIST_RELATIVE **, unsigned int *))(**(_QWORD **)v63 + 24LL))(
              *(_QWORD *)v63,
              a3,
              v6,
              v9,
              0,
              a5,
              a6);
    }
    else
    {
      hkey = 0;
      v56 = SHGetPropertyStoreFromPropertyParsingName(v9, &GUID_55272a00_42cb_11ce_8135_00aa004bb851, (void **)&hkey);
      v54 = v56;
      if ( v56 >= 0 )
      {
        v64 = 0;
        v54 = BindCtx_RegisterObjectParam_5(v6, v57, hkey, &v64);
        if ( v54 >= 0 )
        {
          v54 = (*(__int64 (__fastcall **)(_QWORD, LPMALLOC, struct _ITEMIDLIST_ABSOLUTE **, const WCHAR *, _QWORD, struct _ITEMIDLIST_RELATIVE **, unsigned int *))(**(_QWORD **)v63 + 24LL))(
                  *(_QWORD *)v63,
                  ppMalloc,
                  v64,
                  v9,
                  0,
                  a5,
                  a6);
          (*((void (__fastcall **)(struct _ITEMIDLIST_ABSOLUTE **))*v64 + 2))(v64);
        }
        (*(void (__fastcall **)(HKEY))(*(_QWORD *)hkey + 16LL))(hkey);
        goto LABEL_87;
      }
      if ( v56 != -2147024809 )
      {
LABEL_87:
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v63 + 16LL))(*(_QWORD *)v63);
        return (unsigned int)v54;
      }
      v53 = (*(__int64 (__fastcall **)(_QWORD, LPMALLOC, struct IBindCtx *, const WCHAR *, _QWORD, struct _ITEMIDLIST_ABSOLUTE **, unsigned int *))(**(_QWORD **)v63 + 24LL))(
              *(_QWORD *)v63,
              ppMalloc,
              v6,
              v9,
              0,
              v64,
              a6);
    }
    v54 = v53;
    goto LABEL_87;
  }
  return result;
}

```

## disassembly

```asm
0x1800d1d90  push    rbp
0x1800d1d92  push    rbx
0x1800d1d93  push    rsi
0x1800d1d94  push    rdi
0x1800d1d95  push    r12
0x1800d1d97  push    r13
0x1800d1d99  push    r14
0x1800d1d9b  push    r15
0x1800d1d9d  lea     rbp, [rsp-278h]
0x1800d1da5  sub     rsp, 378h
0x1800d1dac  mov     rax, cs:__security_cookie
0x1800d1db3  xor     rax, rsp
0x1800d1db6  mov     [rbp+2B0h+var_50], rax
0x1800d1dbd  mov     r15, r9
0x1800d1dc0  mov     qword ptr [rbp+2B0h+rguid.Data1], r9
0x1800d1dc4  mov     rbx, r8
0x1800d1dc7  mov     [rbp+2B0h+ppMalloc], rbx
0x1800d1dcb  mov     r8, rdx
0x1800d1dce  mov     r12, rcx
0x1800d1dd1  mov     [rsp+3B0h+var_340], rcx
0x1800d1dd6  mov     r14, [rbp+2B0h+arg_20]
0x1800d1ddd  mov     [rbp+2B0h+var_320], r14
0x1800d1de1  mov     r13, [rbp+2B0h+arg_28]
0x1800d1de8  mov     [rsp+3B0h+var_348], r13
0x1800d1ded  xor     esi, esi
0x1800d1def  lea     rdi, [rdx+4]
0x1800d1df3  movzx   eax, word ptr [rdx+4]
0x1800d1df7  test    ax, ax
0x1800d1dfa  jz      short loc_1800D1E1C
0x1800d1dfc  nop     dword ptr [rax+00h]
0x1800d1e00  cmp     ax, 5Ch ; '\'
0x1800d1e04  jz      short loc_1800D1E1C
0x1800d1e06  cmp     ax, 2Ch ; ','
0x1800d1e0a  jz      loc_1800D263C
0x1800d1e10  add     rdi, 2
0x1800d1e14  movzx   eax, word ptr [rdi]
0x1800d1e17  test    ax, ax
0x1800d1e1a  jnz     short loc_1800D1E00
0x1800d1e1c  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800d1e23  movups  xmmword ptr [rbp+2B0h+var_2E8.Data1], xmm0
0x1800d1e27  lea     rdx, [rbp+2B0h+var_2E8]
0x1800d1e2b  lea     rcx, [r8+4]
0x1800d1e2f  call    cs:__imp_GUIDFromStringW
0x1800d1e35  test    eax, eax
0x1800d1e37  jz      loc_1800D217B
0x1800d1e3d  mov     [rsp+3B0h+hkey], 0
0x1800d1e46  test    r15, r15
0x1800d1e49  jz      short loc_1800D1E6E
0x1800d1e4b  mov     rax, [r15]
0x1800d1e4e  lea     r8, [rsp+3B0h+hkey]
0x1800d1e53  lea     rdx, aBlockregitempa; "BlockRegItemParsing"
0x1800d1e5a  mov     rcx, r15
0x1800d1e5d  mov     rax, [rax+50h]
0x1800d1e61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d1e66  test    eax, eax
0x1800d1e68  jns     loc_1800D274D
0x1800d1e6e  test    rsi, rsi
0x1800d1e71  jnz     loc_1800D24B8
0x1800d1e77  xor     r14d, r14d
0x1800d1e7a  mov     [rsp+3B0h+hkey], r14
0x1800d1e7f  mov     eax, [r12+164h]
0x1800d1e87  add     eax, 16h
0x1800d1e8a  mov     ebx, eax
0x1800d1e8c  mov     ecx, eax; cb
0x1800d1e8e  call    WINRT_IMPL_CoTaskMemAlloc
0x1800d1e93  mov     rsi, rax
0x1800d1e96  test    rax, rax
0x1800d1e99  jz      loc_1800D24A0
0x1800d1e9f  mov     r8d, ebx; Size
0x1800d1ea2  xor     edx, edx; Val
0x1800d1ea4  mov     rcx, rax; void *
0x1800d1ea7  call    memset_0
0x1800d1eac  movzx   eax, word ptr [r12+164h]
0x1800d1eb5  add     ax, 14h
0x1800d1eb9  mov     [rsi], ax
0x1800d1ebc  movzx   eax, byte ptr [r12+148h]
0x1800d1ec5  mov     [rsi+2], al
0x1800d1ec8  mov     eax, [r12+164h]
0x1800d1ed0  movups  xmm0, xmmword ptr [rbp+2B0h+var_2E8.Data1]
0x1800d1ed4  movups  xmmword ptr [rax+rsi+4], xmm0
0x1800d1ed9  mov     r8d, [r12+164h]; Size
0x1800d1ee1  lea     rcx, [rsi+4]; void *
0x1800d1ee5  xor     edx, edx; Val
0x1800d1ee7  call    memset_0
0x1800d1eec  mov     [rbp+2B0h+phkResult], rsi
0x1800d1ef0  mov     rdx, rsi; struct IDLREGITEM *
0x1800d1ef3  mov     rcx, r12; this
0x1800d1ef6  call    ?_ReqItemIndex@CRegFolder@@AEAAHPEFBUIDLREGITEM@@@Z; CRegFolder::_ReqItemIndex(IDLREGITEM const *)
0x1800d1efb  cmp     eax, 0FFFFFFFFh
0x1800d1efe  jnz     loc_1800D2610
0x1800d1f04  mov     bl, 80h
0x1800d1f06  mov     [rsp+3B0h+hkey], r14
0x1800d1f0b  lea     r9, [rsp+3B0h+hkey]; HKEY *
0x1800d1f10  xor     r8d, r8d; bool *
0x1800d1f13  mov     rdx, rsi; struct IDLREGITEM *
0x1800d1f16  mov     rcx, r12; this
0x1800d1f19  call    ?_OpenItemKey@CRegFolder@@AEAAJPEFBUIDLREGITEM@@PEA_NPEAPEAUHKEY__@@@Z; CRegFolder::_OpenItemKey(IDLREGITEM const *,bool *,HKEY__ * *)
0x1800d1f1e  test    eax, eax
0x1800d1f20  js      short loc_1800D1F9C
0x1800d1f22  mov     [rbp+2B0h+var_308], r14d
0x1800d1f26  mov     [rbp+2B0h+var_310], 4
0x1800d1f2d  mov     [rbp+2B0h+var_328], 4
0x1800d1f34  lea     rax, [rbp+2B0h+var_310]
0x1800d1f38  mov     [rsp+3B0h+pcbData], rax; pcbData
0x1800d1f3d  lea     rax, [rbp+2B0h+var_308]
0x1800d1f41  mov     [rsp+3B0h+pvData], rax; pvData
0x1800d1f46  xor     r9d, r9d; pdwType
0x1800d1f49  xor     r8d, r8d; pdwReserved
0x1800d1f4c  lea     rdx, aSortorderindex; "SortOrderIndex"
0x1800d1f53  mov     rcx, [rsp+3B0h+hkey]; hkey
0x1800d1f58  call    cs:__imp_SHQueryValueExW
0x1800d1f5e  test    eax, eax
0x1800d1f60  jz      loc_1800D2429
0x1800d1f66  lea     rax, [rbp+2B0h+var_328]
0x1800d1f6a  mov     [rsp+3B0h+pcbData], rax; pcbData
0x1800d1f6f  lea     rax, [rbp+2B0h+var_308]
0x1800d1f73  mov     [rsp+3B0h+pvData], rax; pvData
0x1800d1f78  xor     r9d, r9d; pdwType
0x1800d1f7b  lea     r8, aSortorderindex; "SortOrderIndex"
0x1800d1f82  lea     rdx, aShellfolder; "ShellFolder"
0x1800d1f89  mov     rcx, [rsp+3B0h+hkey]; hkey
0x1800d1f8e  call    cs:__imp_SHGetValueW
0x1800d1f94  test    eax, eax
0x1800d1f96  jz      loc_1800D2429
0x1800d1f9c  mov     rcx, [rsp+3B0h+hkey]; hKey
0x1800d1fa1  test    rcx, rcx
0x1800d1fa4  jnz     loc_1800D2279
0x1800d1faa  mov     [rsi+3], bl
0x1800d1fad  mov     [rbp+2B0h+var_2F0], r14d
0x1800d1fb1  lea     r9, [rbp+2B0h+var_2F0]; unsigned int *
0x1800d1fb5  mov     r8d, 60000000h; unsigned int
0x1800d1fbb  mov     rdx, rsi; struct IDLREGITEM *
0x1800d1fbe  mov     rcx, r12; this
0x1800d1fc1  call    ?_AttributesOf@CRegFolder@@AEAAJPEFBUIDLREGITEM@@KPEAK@Z; CRegFolder::_AttributesOf(IDLREGITEM const *,ulong,ulong *)
0x1800d1fc6  mov     eax, [rbp+2B0h+var_2F0]
0x1800d1fc9  and     eax, 60000000h
0x1800d1fce  mov     r14d, 2
0x1800d1fd4  mov     r13d, 8007000Eh
0x1800d1fda  cmp     eax, 60000000h
0x1800d1fdf  jz      loc_1800D2284
0x1800d1fe5  mov     [rsp+3B0h+hkey], rsi
0x1800d1fea  mov     [rbp+2B0h+phkResult], 0
0x1800d1ff2  test    r15, r15
0x1800d1ff5  jz      short loc_1800D203F
0x1800d1ff7  mov     rax, [r15]
0x1800d1ffa  lea     r8, [rbp+2B0h+phkResult]
0x1800d1ffe  lea     rdx, aHomegroupCapab; "HomeGroup Capabilities"
0x1800d2005  mov     rcx, r15
0x1800d2008  mov     rax, [rax+50h]
0x1800d200c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2011  test    eax, eax
0x1800d2013  js      short loc_1800D203F
0x1800d2015  mov     rcx, [rbp+2B0h+phkResult]
0x1800d2019  mov     rax, [rcx]
0x1800d201c  mov     rax, [rax+10h]
0x1800d2020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d2025  mov     r8, r15; struct IBindCtx *
0x1800d2028  lea     rdx, [rsp+3B0h+hkey]; struct IDLREGITEM **
0x1800d202d  call    ?_AppendCapabilities@CRegFolder@@AEAAJPEAPEFAUIDLREGITEM@@PEAUIBindCtx@@@Z; CRegFolder::_AppendCapabilities(IDLREGITEM * *,IBindCtx *)
0x1800d2032  test    eax, eax
0x1800d2034  js      loc_1800D2211
0x1800d203a  mov     rsi, [rsp+3B0h+hkey]
0x1800d203f  test    rsi, rsi
0x1800d2042  jz      short loc_1800D2077
0x1800d2044  movzx   eax, word ptr [rsi]
0x1800d2047  cmp     eax, 7
0x1800d204a  jbe     short loc_1800D205D
0x1800d204c  movzx   edx, word ptr [rsi+4]
0x1800d2050  lea     rcx, [rdx+26h]
0x1800d2054  cmp     rax, rcx
0x1800d2057  jnb     loc_1800D2786
0x1800d205d  movzx   eax, word ptr [rsi]
0x1800d2060  cmp     eax, 7
0x1800d2063  jbe     short loc_1800D2077
0x1800d2065  movzx   r8d, word ptr [rsi+4]
0x1800d206a  lea     rcx, [r8+26h]
0x1800d206e  cmp     rax, rcx
0x1800d2071  jnb     loc_1800D27B2
0x1800d2077  movzx   eax, byte ptr [r12+168h]
0x1800d2080  cmp     [rsi+2], al
0x1800d2083  jz      loc_1800D2771
0x1800d2089  mov     eax, [r12+164h]
0x1800d2091  add     rax, rsi
0x1800d2094  add     rax, 4
0x1800d2098  movups  xmm0, xmmword ptr [rax]
0x1800d209b  movups  xmmword ptr [rbp+2B0h+rguid.Data1], xmm0
0x1800d209f  mov     edx, [r12+150h]
0x1800d20a7  sub     edx, 1
0x1800d20aa  js      short loc_1800D20EB
0x1800d20ac  mov     r10, [r12+158h]
0x1800d20b4  mov     r9, qword ptr [rbp+2B0h+rguid.Data4]
0x1800d20b8  mov     r11, qword ptr [rbp+2B0h+rguid.Data1]
0x1800d20bc  nop     dword ptr [rax+00h]
0x1800d20c0  movsxd  rax, edx
0x1800d20c3  lea     rcx, [rax+rax*2]
0x1800d20c7  add     rcx, rcx
0x1800d20ca  mov     r8, [r10+rcx*8]
0x1800d20ce  mov     rax, r11
0x1800d20d1  sub     rax, [r8]
0x1800d20d4  jnz     short loc_1800D20DD
0x1800d20d6  mov     rax, r9
0x1800d20d9  sub     rax, [r8+8]
0x1800d20dd  test    rax, rax
0x1800d20e0  jz      loc_1800D2234
0x1800d20e6  sub     edx, 1
0x1800d20e9  jns     short loc_1800D20C0
0x1800d20eb  mov     rdx, rsi; struct IDLREGITEM *
0x1800d20ee  mov     rcx, r12; this
0x1800d20f1  call    ?_GetPIDLRCLSID@CRegFolder@@AEAAAEFBU_GUID@@PEFBUIDLREGITEM@@@Z; CRegFolder::_GetPIDLRCLSID(IDLREGITEM const *)
0x1800d20f6  movups  xmm0, xmmword ptr [rax]
0x1800d20f9  movups  xmmword ptr [rbp+2B0h+rguid.Data1], xmm0
0x1800d20fd  mov     r8d, 27h ; '''; cchMax
0x1800d2103  lea     rdx, [rbp+2B0h+sz]; lpsz
0x1800d2107  lea     rcx, [rbp+2B0h+rguid]; rguid
0x1800d210b  call    cs:__imp_StringFromGUID2
0x1800d2111  lea     rax, [rbp+2B0h+sz]
0x1800d2115  mov     [rsp+3B0h+pvData], rax
0x1800d211a  mov     r9, [r12+130h]
0x1800d2122  lea     r8, aSS_2; "%s\\%s"
0x1800d2129  mov     edx, 104h; unsigned __int64
0x1800d212e  lea     rcx, [rbp+2B0h+SubKey]; unsigned __int16 *
0x1800d2132  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d2137  mov     [rbp+2B0h+phkResult], 0
0x1800d213f  lea     rax, [rbp+2B0h+phkResult]
0x1800d2143  mov     [rsp+3B0h+pvData], rax; phkResult
0x1800d2148  mov     ebx, 1
0x1800d214d  mov     r9d, ebx; samDesired
0x1800d2150  xor     r8d, r8d; ulOptions
0x1800d2153  lea     rdx, [rbp+2B0h+SubKey]; lpSubKey
0x1800d2157  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d215e  call    cs:__imp_RegOpenKeyExW
0x1800d2164  test    eax, eax
0x1800d2166  jnz     loc_1800D264E
0x1800d216c  mov     rcx, [rbp+2B0h+phkResult]; hKey
0x1800d2170  call    cs:__imp_RegCloseKey
0x1800d2176  jmp     loc_1800D223C
0x1800d217b  mov     eax, 800401F3h
0x1800d2180  jmp     loc_1800D2211
0x1800d2185  mov     edi, r14d
0x1800d2188  mov     ecx, r14d; cb
0x1800d218b  call    cs:__imp_CoTaskMemAlloc
0x1800d2191  mov     rbx, rax
0x1800d2194  test    rax, rax
0x1800d2197  jz      short loc_1800D21F4
0x1800d2199  xor     r14d, r14d
0x1800d219c  mov     [rbp+2B0h+ppMalloc], r14
0x1800d21a0  lea     rdx, [rbp+2B0h+ppMalloc]; ppMalloc
0x1800d21a4  mov     ecx, 1; dwMemContext
0x1800d21a9  call    cs:__imp_CoGetMalloc
0x1800d21af  test    eax, eax
0x1800d21b1  js      short loc_1800D21D9
0x1800d21b3  mov     rcx, [rbp+2B0h+ppMalloc]
0x1800d21b7  mov     rdx, [rcx]
0x1800d21ba  mov     rax, [rdx+30h]
0x1800d21be  mov     rdx, rbx
0x1800d21c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d21c6  mov     r14, rax
0x1800d21c9  mov     rcx, [rbp+2B0h+ppMalloc]
0x1800d21cd  mov     rdx, [rcx]
0x1800d21d0  mov     rax, [rdx+10h]
0x1800d21d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800d21d9  mov     r8, r14; Size
0x1800d21dc  xor     edx, edx; Val
0x1800d21de  mov     rcx, rbx; void *
0x1800d21e1  call    memset_0
0x1800d21e6  mov     r8, rdi; Size
0x1800d21e9  mov     rdx, rsi; Src
0x1800d21ec  mov     rcx, rbx; void *
0x1800d21ef  call    memcpy_0
0x1800d21f4  xor     r14d, r14d
0x1800d21f7  test    rbx, rbx
0x1800d21fa  cmovz   r14d, r13d
0x1800d21fe  mov     rdx, [rbp+2B0h+var_320]
0x1800d2202  mov     [rdx], rbx
0x1800d2205  mov     rcx, rsi; pv
0x1800d2208  call    cs:__imp_CoTaskMemFree
0x1800d220e  mov     eax, r14d
0x1800d2211  mov     rcx, [rbp+2B0h+var_50]
0x1800d2218  xor     rcx, rsp; StackCookie
0x1800d221b  call    __security_check_cookie
0x1800d2220  add     rsp, 378h
0x1800d2227  pop     r15
0x1800d2229  pop     r14
0x1800d222b  pop     r13
0x1800d222d  pop     r12
0x1800d222f  pop     rdi
0x1800d2230  pop     rsi
0x1800d2231  pop     rbx
0x1800d2232  pop     rbp
0x1800d2233  retn
0x1800d2234  test    edx, edx
0x1800d2236  js      loc_1800D20EB
0x1800d223c  cmp     word ptr [rdi], 0
0x1800d2240  jnz     loc_1800D255E
0x1800d2246  mov     rdx, [rsp+3B0h+var_348]
0x1800d224b  test    rdx, rdx
0x1800d224e  jnz     loc_1800D2537
0x1800d2254  test    rsi, rsi
0x1800d2257  jz      loc_1800D2779
0x1800d225d  mov     rdx, rsi
  ... truncated ...
```
