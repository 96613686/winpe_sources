# CFSFolder::GetDisplayNameOf(_ITEMID_CHILD const *,ulong,_STRRET *)

- ea: `0x180094d10`
- end: `0x1800956a4`
- name: `?GetDisplayNameOf@CFSFolder@@UEAAJPEFBU_ITEMID_CHILD@@KPEAU_STRRET@@@Z`
- size: `2452`
- prototype: `int(CFSFolder *__hidden this, const struct _ITEMID_CHILD *, unsigned int, struct _STRRET *)`
- caller_count: `0`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000d6cc`
- `0x1800144c4`
- `0x18001b340`
- `0x1800412a0`
- `0x1800432f0`
- `0x180043320`
- `0x1800481a0`
- `0x180091870`
- `0x180094d10`
- `0x180096180`
- `0x1800a08d0`
- `0x1800d13a0`
- `0x1800d1410`
- `0x1800e4330`
- `0x180148460`
- `0x18014be50`
- `0x1801cd1d0`
- `0x180333018`
- `0x18035dbd8`
- `0x1803a4cb0`
- `0x1803a570a`
- `0x1803a57e0`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180095648`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180095648`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180095445`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180095445`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800952cf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800952cf`
- `OLEAUT32!__imp_SysAllocString` at `0x18009552e`
- `OLEAUT32!__imp_SysAllocString` at `0x18009552e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180095282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180095282`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095004`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095151`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009520f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009521f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009522f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095523`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800955c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095004`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095151`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009520f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009521f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009522f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180095523`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800955c3`
- `SHCORE!__imp_ualstrcpynW` at `0x180095336`
- `SHCORE!__imp_ualstrcpynW` at `0x180095336`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800952e5`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800952e5`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CFSFolder::GetDisplayNameOf(
        CFSFolder *this,
        const struct _ITEMID_CHILD *a2,
        unsigned int a3,
        struct _STRRET *a4)
{
  __int64 v8; // rdi
  __int64 v9; // rax
  HRESULT v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  __int64 v13; // r9
  __int64 v14; // rcx
  const struct _ITEMID_CHILD *v15; // r14
  char IsEnabled; // al
  unsigned __int16 v17; // r8
  unsigned __int16 *v18; // rdx
  __int64 v19; // r9
  unsigned int v20; // ecx
  unsigned __int16 *v21; // rcx
  _BYTE *v22; // rax
  unsigned __int64 v23; // rcx
  int v24; // edx
  unsigned __int16 *v26; // r8
  _WORD *v27; // rax
  unsigned __int16 *v28; // r9
  _WORD *v29; // rcx
  int v30; // ebx
  int v31; // eax
  unsigned int v32; // r14d
  int NormalDisplayName; // eax
  WCHAR *v34; // rdx
  WCHAR *v35; // rdx
  ITEMIDLIST *v36; // r14
  unsigned __int16 **v37; // rdx
  int LocalizedFolderPath; // eax
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rcx
  _BYTE *v42; // rbx
  char *v43; // rax
  size_t v44; // rsi
  size_t v45; // r14
  WCHAR *v46; // rax
  WCHAR *v47; // rdi
  const WCHAR *FileNameW; // rax
  HRESULT v49; // eax
  unsigned int v50; // ebx
  _WORD *CLSIDExtension; // rax
  __int16 v52; // r11
  __int64 (__fastcall *v53)(char *, GUID *, __int64); // rbx
  __int64 v54; // rax
  int v55; // eax
  unsigned int v56; // ebx
  PWSTR v57; // rcx
  unsigned __int16 **v58; // rax
  int UnescapedHttpUri; // eax
  const ITEMIDLIST *v60; // rcx
  HRESULT v61; // eax
  void **v62; // rax
  __int64 v63; // rdx
  __int64 v64; // rcx
  const ITEMIDLIST *v65; // rcx
  int lpWideCharStr; // [rsp+20h] [rbp-E0h]
  int lpWideCharStra; // [rsp+20h] [rbp-E0h]
  LPCITEMIDLIST ppidlLast; // [rsp+30h] [rbp-D0h] BYREF
  PWSTR ppszPath; // [rsp+38h] [rbp-C8h] BYREF
  LPVOID v70[2]; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v71[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v72; // [rsp+60h] [rbp-A0h]
  LPVOID v73; // [rsp+68h] [rbp-98h]
  LPVOID pv; // [rsp+80h] [rbp-80h]
  __int64 v75; // [rsp+88h] [rbp-78h]
  __int64 v76; // [rsp+90h] [rbp-70h]
  __int64 v77; // [rsp+98h] [rbp-68h]
  __int64 v78; // [rsp+A0h] [rbp-60h]
  __int64 v79; // [rsp+A8h] [rbp-58h]
  WCHAR *v80; // [rsp+B8h] [rbp-48h]
  int v81; // [rsp+D0h] [rbp-30h]
  WCHAR WideCharStr[278]; // [rsp+D4h] [rbp-2Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+358h] [rbp+258h]

  v8 = 0x7FFFFFFF;
  if ( !a2 )
  {
LABEL_2:
    if ( (a3 & 0xC001) == 0x8000 )
    {
      ppszPath = 0;
      v9 = *((_QWORD *)this + 56) - *(_QWORD *)&GUID_NULL.Data1;
      if ( !v9 )
        v9 = *((_QWORD *)this + 57) - *(_QWORD *)GUID_NULL.Data4;
      if ( v9 )
      {
        v10 = SHGetKnownFolderPath((const KNOWNFOLDERID *const)this + 28, 0x4000u, 0, &ppszPath);
        v11 = v10;
        if ( v10 < 0 )
        {
          v12 = 1163;
LABEL_8:
          v13 = (unsigned int)v10;
LABEL_112:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v12,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
            (const char *)v13,
            lpWideCharStr);
LABEL_113:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1431,
            (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
            (const char *)v11,
            lpWideCharStr);
          goto LABEL_74;
        }
      }
      else
      {
        v42 = (_BYTE *)*((_QWORD *)this + 50);
        if ( v42 )
        {
          v43 = (char *)*((_QWORD *)this + 50);
          do
          {
            if ( !*(_WORD *)v43 )
              break;
            v43 += 2;
            --v8;
          }
          while ( v8 );
          v44 = 2 * ((v43 - v42) >> 1);
          v45 = v44 + 2;
          v46 = (WCHAR *)CoTaskMemAlloc(v44 + 2);
          v47 = v46;
          if ( !v46 )
          {
            ppszPath = 0;
            v11 = -2147024882;
            v13 = 2147942414LL;
            v12 = 1171;
            goto LABEL_112;
          }
          if ( v44 )
          {
            if ( v45 < v44 )
            {
              memset_0(v46, 0, v45);
              *(_DWORD *)_o__errno(v64) = 34;
              invalid_parameter_noinfo();
            }
            else
            {
              memcpy_0(v46, v42, v44);
            }
          }
          v47[v44 / 2] = 0;
          goto LABEL_105;
        }
        v60 = (const ITEMIDLIST *)*((_QWORD *)this + 49);
        if ( v60 )
        {
          v61 = SHGetNameFromIDList(v60, SIGDN_DESKTOPABSOLUTEPARSING, &ppszPath);
          v11 = v61;
          if ( v61 < 0 )
          {
            v12 = 1177;
            v13 = (unsigned int)v61;
            goto LABEL_112;
          }
        }
        else
        {
          v65 = (const ITEMIDLIST *)*((_QWORD *)this + 48);
          if ( v65 )
          {
            v10 = SHGetNameFromIDList(v65, SIGDN_DESKTOPABSOLUTEPARSING, &ppszPath);
            v11 = v10;
            if ( v10 < 0 )
            {
              v12 = 1181;
              goto LABEL_8;
            }
          }
        }
        if ( !ppszPath )
        {
          v11 = -2147024893;
          goto LABEL_113;
        }
        *((_QWORD *)this + 50) = SysAllocString(ppszPath);
      }
      v47 = ppszPath;
LABEL_105:
      a4->uType = 0;
      a4->pOleStr = v47;
      return 0;
    }
    if ( *((_QWORD *)this + 49) && !a3 )
      return 2147500033LL;
    v37 = (unsigned __int16 **)((char *)this + 424);
    if ( !*v37 )
    {
      LocalizedFolderPath = CFSFolder::_GetLocalizedFolderPath((CFSFolder *)((char *)this - 48), v37);
      v11 = LocalizedFolderPath;
      if ( LocalizedFolderPath < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1446,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)(unsigned int)LocalizedFolderPath,
          lpWideCharStr);
        return v11;
      }
    }
    FileNameW = PathFindFileNameW(*((LPCWSTR *)this + 53));
    a4->uType = 0;
    v49 = SHStrDupW(FileNameW, &a4->pOleStr);
    v50 = v49;
    if ( v49 >= 0 )
      return 0;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1447,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v49,
      lpWideCharStr);
    return v50;
  }
  v14 = *(unsigned __int16 *)a2;
  if ( (unsigned int)v14 <= 0xB )
    goto LABEL_30;
  if ( (*((_BYTE *)a2 + 2) & 0x70) == 0x30 )
  {
    v15 = a2;
    goto LABEL_12;
  }
  if ( *(_DWORD *)((char *)a2 + 6) != 1179862595
    || *((unsigned __int16 *)a2 + 2) > (unsigned __int64)(v14 - 4)
    || (v15 = (const struct _ITEMID_CHILD *)((char *)a2 + 10),
        !IDListContainerIsConsistent((LPCITEMIDLIST)((char *)a2 + 10), *((unsigned __int16 *)a2 + 2)))
    || v52 != *(_WORD *)v15 + 6
    || (unsigned __int16)(*(_WORD *)v15 + 6) < *(_WORD *)v15 )
  {
LABEL_30:
    if ( *(_WORD *)a2 )
      return 2147942487LL;
    goto LABEL_2;
  }
LABEL_12:
  if ( *(_WORD *)v15 < 0xEu )
    goto LABEL_30;
  if ( !*(_WORD *)a2 )
    goto LABEL_38;
  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl);
  v17 = *(_WORD *)a2;
  if ( IsEnabled )
  {
    if ( v17 < 2u )
      goto LABEL_38;
  }
  v18 = 0;
  v19 = *(unsigned __int16 *)((char *)a2 + v17 - 2);
  if ( (_WORD)v19 )
  {
    if ( v19 + 8 < (unsigned __int64)v17 )
    {
      v18 = (unsigned __int16 *)((char *)a2 + v19);
      v20 = *(unsigned __int16 *)((char *)a2 + v19);
      if ( v20 < 8 || HIWORD(*((_DWORD *)v18 + 1)) != 0xBEEF || (unsigned int)v19 + v20 > v17 )
        v18 = 0;
    }
  }
  v21 = (unsigned __int16 *)((char *)a2 + v17);
  if ( v18 )
  {
    while ( *((_DWORD *)v18 + 1) != -1091633148 )
    {
      v26 = 0;
      if ( v18 + 4 <= v21 )
      {
        v28 = (unsigned __int16 *)((char *)v18 + *v18);
        if ( v28 == v21 )
          goto LABEL_38;
        if ( v28 <= v21 )
        {
          if ( v28 + 4 > v21
            || HIWORD(*((_DWORD *)v28 + 1)) != 0xBEEF
            || (unsigned __int16 *)((char *)v28 + *v28) > v21
            || v28 < v18 + 4 )
          {
            goto LABEL_38;
          }
          v26 = (unsigned __int16 *)((char *)v18 + *v18);
        }
      }
      v18 = v26;
      if ( !v26 )
        goto LABEL_38;
    }
  }
  else
  {
LABEL_38:
    if ( (*((_BYTE *)v15 + 2) & 0x34) == 0x34 )
    {
      v27 = (_WORD *)((char *)v15 + 14);
      if ( v15 != (const struct _ITEMID_CHILD *)-14LL )
      {
        v23 = ((unsigned __int64)*(unsigned __int16 *)v15 - 14) >> 1;
        if ( v23 <= 0x7FFFFFFF )
        {
          for ( ; v23; --v23 )
          {
            if ( !*v27 )
              break;
            ++v27;
          }
          goto LABEL_27;
        }
      }
LABEL_139:
      v24 = -2147024809;
      goto LABEL_29;
    }
  }
  v22 = (char *)v15 + 14;
  if ( v15 == (const struct _ITEMID_CHILD *)-14LL )
    goto LABEL_139;
  v23 = *(unsigned __int16 *)v15 - 14LL;
  if ( v23 > 0x7FFFFFFF )
    goto LABEL_139;
  if ( *(_WORD *)v15 != 14 )
  {
    do
    {
      if ( !*v22 )
        break;
      ++v22;
      --v23;
    }
    while ( v23 );
  }
LABEL_27:
  v24 = -2147024809;
  if ( v23 )
    v24 = 0;
LABEL_29:
  if ( v24 < 0 )
    goto LABEL_30;
  v29 = (_WORD *)((char *)a2 + *(unsigned __int16 *)a2);
  if ( !v29 || !*v29 )
  {
    ppszPath = 0;
    if ( (a3 & 0x8000) == 0 )
    {
      ppszPath = 0;
      NormalDisplayName = CFSFolder::GetNormalDisplayName(
                            (CFSFolder *)((char *)this - 48),
                            (unsigned __int16 *)a2,
                            (unsigned __int64 *)a3,
                            0,
                            &ppszPath);
      v11 = NormalDisplayName;
      if ( NormalDisplayName < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1406,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)(unsigned int)NormalDisplayName,
          lpWideCharStr);
LABEL_74:
        if ( ppszPath )
          CoTaskMemFree(ppszPath);
        return v11;
      }
      v30 = a3 & 1;
      goto LABEL_59;
    }
    v30 = a3 & 1;
    if ( (a3 & 1) == 0 )
    {
      ppszPath = 0;
      v31 = (*(__int64 (__fastcall **)(char *, const struct _ITEMID_CHILD *, PWSTR *))(*((_QWORD *)this + 33) + 128LL))(
              (char *)this + 264,
              a2,
              &ppszPath);
      v32 = v31;
      if ( v31 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1401,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)(unsigned int)v31,
          lpWideCharStr);
        if ( ppszPath )
          CoTaskMemFree(ppszPath);
        return v32;
      }
LABEL_59:
      if ( (a3 & 0x4000) != 0 )
      {
        if ( !v30 && (*((_BYTE *)this + 488) & 0x20) != 0 )
        {
          v70[0] = 0;
          v58 = (unsigned __int16 **)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(v70);
          UnescapedHttpUri = CFSFolder::GetUnescapedHttpUri((CFSFolder *)((char *)this - 48), a2, v58);
          v11 = UnescapedHttpUri;
          if ( UnescapedHttpUri < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x140F,
              (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
              (const char *)(unsigned int)UnescapedHttpUri,
              lpWideCharStr);
            if ( v70[0] )
              CoTaskMemFree(v70[0]);
            goto LABEL_74;
          }
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
            &ppszPath,
            v70);
          if ( v70[0] )
            CoTaskMemFree(v70[0]);
        }
        else
        {
          CLSIDExtension = (_WORD *)PathFindCLSIDExtension(ppszPath, 0);
          if ( CLSIDExtension )
            *CLSIDExtension = 0;
        }
      }
      a4->uType = 0;
      a4->pOleStr = ppszPath;
      return 0;
    }
    CFileSysItemString::CFileSysItemString((CFileSysItemString *)v71, (CFSFolder *)((char *)this - 48), a2, v15);
    if ( v80 )
      goto LABEL_95;
    if ( (v81 & 1) != 0 )
    {
LABEL_69:
      v35 = WideCharStr;
LABEL_70:
      wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &ppidlLast,
        v35,
        -1);
      v36 = (ITEMIDLIST *)ppidlLast;
      if ( ppszPath )
        wil::details::close_invoke_helper<1,void (*)(void *),&void CoTaskMemFree(void *),unsigned short *>::close_reset(ppszPath);
      ppszPath = &v36->mkid.cb;
      if ( !v36 )
      {
        v11 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x13FD,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)0x8007000ELL,
          lpWideCharStr);
        CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v71);
        goto LABEL_74;
      }
      v71[0] = &CFileSysItemString::`vftable';
      v39 = v77;
      v77 = 0;
      if ( v39 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
      v40 = v75;
      v75 = 0;
      if ( v40 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
      v41 = v76;
      v76 = 0;
      if ( v41 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v73 )
        CoTaskMemFree(v73);
      if ( v72 )
        CoTaskMemFree(v72);
      goto LABEL_59;
    }
    if ( v79 )
    {
      v34 = (WCHAR *)(v79 + *(unsigned __int16 *)(v79 + 16));
      if ( ((unsigned __int8)v34 & 1) == 0 )
      {
        if ( v34 != WideCharStr )
        {
          v80 = (WCHAR *)(v79 + *(unsigned __int16 *)(v79 + 16));
          goto LABEL_68;
        }
LABEL_110:
        v81 = 1;
LABEL_68:
        if ( !v80 )
          goto LABEL_69;
LABEL_95:
        v35 = v80;
        goto LABEL_70;
      }
    }
    else
    {
      if ( (*(_BYTE *)(v78 + 2) & 0x34) != 0x34 )
      {
        MultiByteToWideChar(0, 0, (LPCCH)(v78 + 14), -1, WideCharStr, 260);
        goto LABEL_110;
      }
      v34 = (WCHAR *)(v78 + 14);
    }
    ualstrcpynW(WideCharStr, v34, 260);
    goto LABEL_110;
  }
  ppszPath = 0;
  v53 = (__int64 (__fastcall *)(char *, GUID *, __int64))**((_QWORD **)this - 6);
  v54 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(&ppszPath);
  v55 = v53((char *)this - 48, &GUID_000214e6_0000_0000_c000_000000000046, v54);
  v56 = v55;
  if ( v55 >= 0 )
  {
    v70[0] = 0;
    ppidlLast = 0;
    v62 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(v70);
    v11 = SHBindToFolderIDListParentEx(
            (IShellFolder *)ppszPath,
            (LPCITEMIDLIST)a2,
            0,
            &GUID_000214e6_0000_0000_c000_000000000046,
            v62,
            &ppidlLast);
    if ( (v11 & 0x80000000) == 0 )
    {
      v11 = (*(__int64 (__fastcall **)(LPVOID, LPCITEMIDLIST, _QWORD, struct _STRRET *))(*(_QWORD *)v70[0] + 88LL))(
              v70[0],
              ppidlLast,
              a3,
              a4);
      if ( (v11 & 0x80000000) == 0 )
      {
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v70);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppszPath);
        return 0;
      }
      v63 = 5159;
    }
    else
    {
      v63 = 5158;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v63,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)v11,
      lpWideCharStra);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v70);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppszPath);
    return v11;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1422,
    (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
    (const char *)(unsigned int)v55,
    lpWideCharStr);
  v57 = ppszPath;
  if ( ppszPath )
  {
    ppszPath = 0;
    (*(void (__fastcall **)(PWSTR))(*(_QWORD *)v57 + 16LL))(v57);
  }
  return v56;
}

```

## disassembly

```asm
0x180094d10  push    rbp
0x180094d12  push    rbx
0x180094d13  push    rsi
0x180094d14  push    rdi
0x180094d15  push    r12
0x180094d17  push    r13
0x180094d19  push    r14
0x180094d1b  push    r15
0x180094d1d  lea     rbp, [rsp-218h]
0x180094d25  sub     rsp, 318h
0x180094d2c  mov     rax, cs:__security_cookie
0x180094d33  xor     rax, rsp
0x180094d36  mov     [rbp+250h+var_50], rax
0x180094d3d  mov     r12, r9
0x180094d40  mov     r15d, r8d
0x180094d43  mov     rsi, rdx
0x180094d46  mov     r13, rcx
0x180094d49  mov     edi, 7FFFFFFFh
0x180094d4e  test    rdx, rdx
0x180094d51  jnz     short loc_180094DBF
0x180094d53  mov     eax, r15d
0x180094d56  and     eax, 0C001h
0x180094d5b  cmp     eax, 8000h
0x180094d60  jnz     loc_180095159
0x180094d66  mov     [rsp+350h+ppszPath], 0
0x180094d6f  lea     rcx, [r13+1C0h]; rfid
0x180094d76  mov     rax, [rcx]
0x180094d79  sub     rax, qword ptr cs:GUID_NULL.Data1
0x180094d80  jnz     short loc_180094D8D
0x180094d82  mov     rax, [rcx+8]
0x180094d86  sub     rax, qword ptr cs:GUID_NULL.Data4
0x180094d8d  test    rax, rax
0x180094d90  jz      loc_18009524E
0x180094d96  lea     r9, [rsp+350h+ppszPath]; ppszPath
0x180094d9b  xor     r8d, r8d; hToken
0x180094d9e  mov     edx, 4000h; dwFlags
0x180094da3  call    SHGetKnownFolderPath
0x180094da8  mov     ebx, eax
0x180094daa  test    eax, eax
0x180094dac  jns     loc_18009553B
0x180094db2  mov     edx, 48Bh
0x180094db7  mov     r9d, eax
0x180094dba  jmp     loc_18009535A
0x180094dbf  movzx   ecx, word ptr [rdx]
0x180094dc2  cmp     ecx, 0Bh
0x180094dc5  jbe     loc_180094EC3
0x180094dcb  movzx   eax, byte ptr [rdx+2]
0x180094dcf  and     al, 70h
0x180094dd1  cmp     al, 30h ; '0'
0x180094dd3  jnz     loc_1800953BE
0x180094dd9  mov     r14, rsi
0x180094ddc  cmp     word ptr [r14], 0Eh
0x180094de1  jb      loc_180094EC3
0x180094de7  cmp     word ptr [rsi], 0
0x180094deb  jz      loc_180094F0D
0x180094df1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl(void)'::`2'::impl
0x180094df8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(void)
0x180094dfd  movzx   r8d, word ptr [rsi]
0x180094e01  test    al, al
0x180094e03  jnz     loc_180095595
0x180094e09  movzx   r10d, r8w
0x180094e0d  xor     edx, edx
0x180094e0f  movzx   ecx, r8w
0x180094e13  movzx   r9d, word ptr [rcx+rsi-2]
0x180094e19  mov     ebx, 0BEEFh
0x180094e1e  test    r9w, r9w
0x180094e22  jz      short loc_180094E5C
0x180094e24  lea     rax, [r9+8]
0x180094e28  cmp     rax, rcx
0x180094e2b  jnb     short loc_180094E5C
0x180094e2d  lea     rdx, [r9+rsi]
0x180094e31  movzx   ecx, word ptr [rdx]
0x180094e34  cmp     ecx, 8
0x180094e37  jb      loc_1800951AD
0x180094e3d  mov     eax, [rdx+4]
0x180094e40  shr     rax, 10h
0x180094e44  cmp     ax, bx
0x180094e47  jnz     loc_1800951AD
0x180094e4d  add     ecx, r9d
0x180094e50  movzx   eax, r8w
0x180094e54  cmp     ecx, eax
0x180094e56  ja      loc_1800951AD
0x180094e5c  movzx   ecx, r10w
0x180094e60  add     rcx, rsi
0x180094e63  test    rdx, rdx
0x180094e66  jz      loc_180094F0D
0x180094e6c  cmp     dword ptr [rdx+4], 0BEEF0004h
0x180094e73  jnz     loc_180094F5F
0x180094e79  lea     rax, [r14+0Eh]
0x180094e7d  test    rax, rax
0x180094e80  jz      loc_18009557E
0x180094e86  movzx   ecx, word ptr [r14]
0x180094e8a  add     rcx, 0FFFFFFFFFFFFFFF2h
0x180094e8e  cmp     rcx, rdi
0x180094e91  ja      loc_18009557E
0x180094e97  test    rcx, rcx
0x180094e9a  jz      short loc_180094EAE
0x180094e9c  nop     dword ptr [rax+00h]
0x180094ea0  cmp     byte ptr [rax], 0
0x180094ea3  jz      short loc_180094EAE
0x180094ea5  inc     rax
0x180094ea8  sub     rcx, 1
0x180094eac  jnz     short loc_180094EA0
0x180094eae  xor     eax, eax
0x180094eb0  mov     edx, 80070057h
0x180094eb5  test    rcx, rcx
0x180094eb8  cmovnz  edx, eax
0x180094ebb  test    edx, edx
0x180094ebd  jns     loc_180094F7E
0x180094ec3  cmp     word ptr [rsi], 0
0x180094ec7  jz      loc_180094D53
0x180094ecd  mov     eax, 80070057h
0x180094ed2  jmp     loc_180095063
0x180094ed7  lea     rax, [r9+8]
0x180094edb  cmp     rax, rcx
0x180094ede  ja      short loc_180094F0D
0x180094ee0  mov     eax, [r9+4]
0x180094ee4  shr     rax, 10h
0x180094ee8  cmp     ax, bx
0x180094eeb  jnz     short loc_180094F0D
0x180094eed  movzx   eax, word ptr [r9]
0x180094ef1  add     rax, r9
0x180094ef4  cmp     rax, rcx
0x180094ef7  ja      short loc_180094F0D
0x180094ef9  cmp     r9, r10
0x180094efc  jb      short loc_180094F0D
0x180094efe  mov     r8, r9
0x180094f01  mov     rdx, r8
0x180094f04  test    r8, r8
0x180094f07  jnz     loc_180094E6C
0x180094f0d  movzx   eax, byte ptr [r14+2]
0x180094f12  and     al, 34h
0x180094f14  cmp     al, 34h ; '4'
0x180094f16  jnz     loc_180094E79
0x180094f1c  lea     rax, [r14+0Eh]
0x180094f20  test    rax, rax
0x180094f23  jz      loc_18009557E
0x180094f29  movzx   ecx, word ptr [r14]
0x180094f2d  sub     rcx, 0Eh
0x180094f31  shr     rcx, 1
0x180094f34  cmp     rcx, rdi
0x180094f37  ja      loc_18009557E
0x180094f3d  test    rcx, rcx
0x180094f40  jz      loc_180094EAE
0x180094f46  cmp     word ptr [rax], 0
0x180094f4a  jz      loc_180094EAE
0x180094f50  add     rax, 2
0x180094f54  sub     rcx, 1
0x180094f58  jnz     short loc_180094F46
0x180094f5a  jmp     loc_180094EAE
0x180094f5f  xor     r8d, r8d
0x180094f62  lea     r10, [rdx+8]
0x180094f66  cmp     r10, rcx
0x180094f69  ja      short loc_180094F01
0x180094f6b  movzx   r9d, word ptr [rdx]
0x180094f6f  add     r9, rdx
0x180094f72  cmp     r9, rcx
0x180094f75  jz      short loc_180094F0D
0x180094f77  ja      short loc_180094F01
0x180094f79  jmp     loc_180094ED7
0x180094f7e  movzx   ecx, word ptr [rsi]
0x180094f81  add     rcx, rsi
0x180094f84  jz      short loc_180094F90
0x180094f86  cmp     word ptr [rcx], 0
0x180094f8a  jnz     loc_180095450
0x180094f90  mov     [rsp+350h+ppszPath], 0
0x180094f99  bt      r15d, 0Fh
0x180094f9e  jnb     short loc_18009500F
0x180094fa0  mov     ebx, r15d
0x180094fa3  and     ebx, 1
0x180094fa6  jnz     loc_180095086
0x180094fac  mov     [rsp+350h+ppszPath], 0
0x180094fb5  mov     rax, [r13+108h]
0x180094fbc  lea     rcx, [r13+108h]
0x180094fc3  lea     r8, [rsp+350h+ppszPath]
0x180094fc8  mov     rdx, rsi
0x180094fcb  mov     rax, [rax+80h]
0x180094fd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180094fd7  mov     r14d, eax
0x180094fda  test    eax, eax
0x180094fdc  jns     short loc_180095044
0x180094fde  mov     rcx, [rbp+258h]; this
0x180094fe5  mov     r9d, eax; char *
0x180094fe8  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x180094fef  mov     edx, 1401h; void *
0x180094ff4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180094ff9  nop
0x180094ffa  mov     rcx, [rsp+350h+ppszPath]; pv
0x180094fff  test    rcx, rcx
0x180095002  jz      short loc_18009500A
0x180095004  call    cs:__imp_CoTaskMemFree
0x18009500a  mov     eax, r14d
0x18009500d  jmp     short loc_180095063
0x18009500f  mov     [rsp+350h+ppszPath], 0
0x180095018  lea     rax, [rsp+350h+ppszPath]
0x18009501d  mov     [rsp+350h+lpWideCharStr], rax; int
0x180095022  xor     r9d, r9d
0x180095025  mov     r8d, r15d
0x180095028  mov     rdx, rsi
0x18009502b  lea     rcx, [r13-30h]
0x18009502f  call    ?GetNormalDisplayName@CFSFolder@@IEAAJPEFBU_ITEMID_CHILD@@KW4FSIS_UINAME_OPTIONS@@PEAPEAG@Z; CFSFolder::GetNormalDisplayName(_ITEMID_CHILD const *,ulong,FSIS_UINAME_OPTIONS,ushort * *)
0x180095034  mov     ebx, eax
0x180095036  test    eax, eax
0x180095038  js      loc_18009561E
0x18009503e  mov     ebx, r15d
0x180095041  and     ebx, 1
0x180095044  bt      r15d, 0Eh
0x180095049  jb      loc_18009538D
0x18009504f  mov     dword ptr [r12], 0
0x180095057  mov     rax, [rsp+350h+ppszPath]
0x18009505c  mov     [r12+8], rax
0x180095061  xor     eax, eax
0x180095063  mov     rcx, [rbp+250h+var_50]
0x18009506a  xor     rcx, rsp; StackCookie
0x18009506d  call    __security_check_cookie
0x180095072  add     rsp, 318h
0x180095079  pop     r15
0x18009507b  pop     r14
0x18009507d  pop     r13
0x18009507f  pop     r12
0x180095081  pop     rdi
0x180095082  pop     rsi
0x180095083  pop     rbx
0x180095084  pop     rbp
0x180095085  retn
0x180095086  mov     r9, r14; struct IDFOLDER *
0x180095089  mov     r8, rsi; struct _ITEMIDLIST_RELATIVE *
0x18009508c  lea     rdx, [r13-30h]; struct CFSFolder *
0x180095090  lea     rcx, [rsp+350h+var_300]; this
0x180095095  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x18009509a  nop
0x18009509b  cmp     [rbp+250h+var_298], 0
0x1800950a0  jnz     loc_18009523B
0x1800950a6  test    byte ptr [rbp+250h+var_280], 1
0x1800950aa  jnz     short loc_1800950E5
0x1800950ac  mov     rcx, [rbp+250h+var_2A8]
0x1800950b0  test    rcx, rcx
0x1800950b3  jz      loc_180095413
0x1800950b9  movzx   edx, word ptr [rcx+10h]
0x1800950bd  add     rdx, rcx
0x1800950c0  test    dl, 1
0x1800950c3  jnz     loc_18009532C
0x1800950c9  lea     rax, [rbp+250h+WideCharStr]
0x1800950cd  cmp     rdx, rax
0x1800950d0  jz      loc_18009533C
0x1800950d6  mov     [rbp+250h+var_298], rdx
0x1800950da  cmp     [rbp+250h+var_298], 0
0x1800950df  jnz     loc_18009523B
0x1800950e5  lea     rdx, [rbp+250h+WideCharStr]
0x1800950e9  mov     r8, 0FFFFFFFFFFFFFFFFh
0x1800950f0  lea     rcx, [rsp+350h+ppidlLast]
0x1800950f5  call    ??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800950fa  mov     r14, [rsp+350h+ppidlLast]
0x1800950ff  mov     rcx, [rsp+350h+ppszPath]; pv
0x180095104  test    rcx, rcx
0x180095107  jnz     loc_180095244
0x18009510d  mov     [rsp+350h+ppszPath], r14
0x180095112  test    r14, r14
0x180095115  jnz     loc_1800951B4
0x18009511b  mov     rcx, [rbp+258h]; this
0x180095122  mov     ebx, 8007000Eh
0x180095127  mov     r9d, ebx; char *
0x18009512a  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x180095131  mov     edx, 13FDh; void *
0x180095136  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009513b  nop
0x18009513c  lea     rcx, [rsp+350h+var_300]; this
0x180095141  call    ??1CFileSysItemString@@UEAA@XZ; CFileSysItemString::~CFileSysItemString(void)
0x180095146  nop
0x180095147  mov     rcx, [rsp+350h+ppszPath]; pv
0x18009514c  test    rcx, rcx
0x18009514f  jz      short loc_1800951A6
0x180095151  call    cs:__imp_CoTaskMemFree
0x180095157  jmp     short loc_1800951A6
0x180095159  cmp     qword ptr [r13+188h], 0
0x180095161  jnz     loc_180095691
0x180095167  lea     rcx, [r13-30h]; this
0x18009516b  lea     rdx, [rcx+1D8h]; unsigned __int16 **
0x180095172  cmp     qword ptr [rdx], 0
0x180095176  jnz     loc_1800952C8
0x18009517c  call    ?_GetLocalizedFolderPath@CFSFolder@@IEAAJPEAPEAG@Z; CFSFolder::_GetLocalizedFolderPath(ushort * *)
0x180095181  mov     ebx, eax
0x180095183  test    eax, eax
0x180095185  jns     loc_1800952C8
0x18009518b  mov     rcx, [rbp+258h]; this
0x180095192  mov     r9d, eax; char *
0x180095195  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x18009519c  mov     edx, 1446h; void *
0x1800951a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800951a6  mov     eax, ebx
0x1800951a8  jmp     loc_180095063
0x1800951ad  xor     edx, edx
0x1800951af  jmp     loc_180094E5C
0x1800951b4  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x1800951bb  mov     [rsp+350h+var_300], rax
0x1800951c0  mov     rcx, [rbp+250h+var_2B8]
0x1800951c4  xor     r14d, r14d
0x1800951c7  mov     [rbp+250h+var_2B8], r14
0x1800951cb  test    rcx, rcx
0x1800951ce  jz      short loc_1800951DC
  ... truncated ...
```
