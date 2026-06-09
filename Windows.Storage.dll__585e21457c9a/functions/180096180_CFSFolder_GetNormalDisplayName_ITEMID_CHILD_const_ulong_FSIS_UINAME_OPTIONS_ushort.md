# CFSFolder::GetNormalDisplayName(_ITEMID_CHILD const *,ulong,FSIS_UINAME_OPTIONS,ushort * *)

- ea: `0x180096180`
- end: `0x180096ca3`
- name: `?GetNormalDisplayName@CFSFolder@@IEAAJPEFBU_ITEMID_CHILD@@KW4FSIS_UINAME_OPTIONS@@PEAPEAG@Z`
- size: `2851`
- prototype: ``
- caller_count: `5`
- callee_count: `22`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18008f3e0`
- `0x18008f5a0`
- `0x1800909b0`
- `0x180094d10`
- `0x180217e70`

## callees

- `0x18000d6cc`
- `0x1800144c4`
- `0x180015ee0`
- `0x1800432f0`
- `0x180043320`
- `0x180091870`
- `0x180096180`
- `0x1800979d0`
- `0x180099090`
- `0x1800994e0`
- `0x18009df20`
- `0x1800a08d0`
- `0x1800a0ff0`
- `0x1800d13a0`
- `0x1800e1c90`
- `0x180155330`
- `0x180174660`
- `0x180333018`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a96e5`
- `0x18065a010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800966bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800966bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800966ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800966ac`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180096a84`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180096ae0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180096bea`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180096a84`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180096ae0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180096bea`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x180096c73`
- `api-ms-win-core-url-l1-1-0!UrlUnescapeW` at `0x180096c73`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1800968f2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveExtensionW` at `0x1800968f2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180096b67`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x180096b67`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800967b9`
- `api-ms-win-core-string-l2-1-1!SHLoadIndirectString` at `0x1800967b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180096429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180096429`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009653c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009654c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009655c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009656d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096611`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096642`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800966b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096c0a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009653c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009654c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009655c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009656d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096611`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096621`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096631`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096642`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800966b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180096c0a`
- `SHCORE!__imp_StrRetToStrW` at `0x180096b06`
- `SHCORE!__imp_StrRetToStrW` at `0x180096b06`
- `SHCORE!__imp_ualstrcpynW` at `0x18009673a`
- `SHCORE!__imp_ualstrcpynW` at `0x1800968e8`
- `SHCORE!__imp_ualstrcpynW` at `0x180096a56`
- `SHCORE!__imp_ualstrcpynW` at `0x180096abd`
- `SHCORE!__imp_ualstrcpynW` at `0x180096b5a`
- `SHCORE!__imp_ualstrcpynW` at `0x180096bc7`
- `SHCORE!__imp_ualstrcpynW` at `0x18009673a`
- `SHCORE!__imp_ualstrcpynW` at `0x1800968e8`
- `SHCORE!__imp_ualstrcpynW` at `0x180096a56`
- `SHCORE!__imp_ualstrcpynW` at `0x180096abd`
- `SHCORE!__imp_ualstrcpynW` at `0x180096b5a`
- `SHCORE!__imp_ualstrcpynW` at `0x180096bc7`
- `SHCORE!__imp_ualstrlenW` at `0x180096787`
- `SHCORE!__imp_ualstrlenW` at `0x180096787`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180096c46`
- `api-ms-win-shcore-unicodeansi-l1-1-0!SHAnsiToUnicode` at `0x180096c46`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CFSFolder::GetNormalDisplayName(
        struct CFSFolder *a1,
        unsigned __int16 *a2,
        unsigned __int64 *a3,
        unsigned int a4,
        PWSTR *a5)
{
  unsigned int v6; // r14d
  unsigned __int16 *v9; // rdi
  const struct IDFOLDER *v10; // rsi
  char IsEnabled; // al
  unsigned __int64 v12; // r9
  unsigned __int64 *v13; // rdx
  __int64 v14; // r10
  unsigned int v15; // ecx
  unsigned __int64 v16; // rcx
  _BYTE *v17; // rcx
  unsigned __int64 v18; // rdx
  int v19; // r8d
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r9
  unsigned __int64 v23; // rbx
  __int64 v24; // rsi
  const CHAR *v25; // r8
  __int64 v26; // rax
  __int64 v27; // rax
  struct IDFOLDER *v28; // r9
  WCHAR *v29; // rcx
  WCHAR *v30; // rdx
  WCHAR *v31; // rdi
  unsigned __int64 v32; // r14
  WCHAR *v33; // rax
  WCHAR *v34; // r10
  int v35; // esi
  unsigned __int64 v36; // rdx
  WCHAR *v37; // r8
  __int64 v38; // rcx
  WCHAR v39; // ax
  __int64 v40; // r9
  WCHAR *v41; // rcx
  PWSTR v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  unsigned __int16 *v51; // r9
  int ShouldShowExtension; // eax
  const CHAR *v53; // rdi
  unsigned __int64 v54; // r8
  __int64 v55; // rdi
  __int64 v56; // rcx
  WCHAR *v57; // rdx
  __int64 v58; // r9
  unsigned __int16 *v59; // r8
  WCHAR v60; // ax
  unsigned __int16 *v61; // rcx
  struct IDFOLDER *v62; // r8
  unsigned __int16 *v63; // rcx
  WCHAR *v64; // rdx
  unsigned __int16 v65; // ax
  WCHAR *v66; // rcx
  __int64 v67; // r14
  bool v68; // cf
  void **v69; // rax
  HRESULT v70; // ebx
  int v71; // eax
  __int64 v72; // rbx
  __int64 v73; // rax
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // rcx
  __int16 v77; // r11
  LPWSTR *v78; // rax
  __int64 v79; // rdx
  const unsigned __int16 *ExtensionW; // rax
  HRESULT v81; // eax
  int lpWideCharStr; // [rsp+20h] [rbp-E0h]
  PWSTR pszUrl; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v84; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v85; // [rsp+40h] [rbp-C0h] BYREF
  _QWORD v86[2]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID v87; // [rsp+60h] [rbp-A0h]
  LPVOID v88; // [rsp+68h] [rbp-98h]
  LPVOID pv; // [rsp+80h] [rbp-80h]
  __int64 v90; // [rsp+88h] [rbp-78h]
  __int64 v91; // [rsp+90h] [rbp-70h]
  __int64 v92; // [rsp+98h] [rbp-68h]
  struct IDFOLDER *v93; // [rsp+A0h] [rbp-60h]
  const CHAR *v94; // [rsp+A8h] [rbp-58h]
  WCHAR *v95; // [rsp+B8h] [rbp-48h]
  WCHAR *v96; // [rsp+C0h] [rbp-40h]
  int v97; // [rsp+D0h] [rbp-30h]
  WCHAR pszOutBuf[278]; // [rsp+D4h] [rbp-2Ch] BYREF
  STRRET pszSource; // [rsp+300h] [rbp+200h] BYREF
  unsigned __int16 v100[264]; // [rsp+510h] [rbp+410h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+778h] [rbp+678h]

  v6 = (unsigned int)a3;
  *a5 = 0;
  v9 = 0;
  if ( a2 )
  {
    v50 = *a2;
    if ( (unsigned int)v50 > 0xB )
    {
      if ( (a2[1] & 0x70) == 0x30 )
      {
        v9 = a2;
        v10 = 0;
        goto LABEL_3;
      }
      if ( *(_DWORD *)(a2 + 3) == 1179862595 )
      {
        if ( a2[2] > (unsigned __int64)(v50 - 4)
          || (v9 = a2 + 5, !IDListContainerIsConsistent((LPCITEMIDLIST)(a2 + 5), a2[2]))
          || v77 != *v9 + 6
          || (unsigned __int16)(*v9 + 6) < *v9 )
        {
          v10 = 0;
          goto LABEL_23;
        }
      }
    }
  }
  v10 = 0;
  if ( !v9 )
    goto LABEL_23;
LABEL_3:
  if ( *v9 < 0xEu )
    goto LABEL_23;
  if ( a2 )
  {
    if ( *a2 )
    {
      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl'::`2'::impl);
      v12 = *a2;
      if ( !IsEnabled || (unsigned int)v12 >= 2 )
      {
        v13 = 0;
        v14 = *(unsigned __int16 *)((char *)a2 + v12 - 2);
        if ( (_WORD)v14 )
        {
          if ( v14 + 8 < v12 )
          {
            v13 = (unsigned __int64 *)((char *)a2 + v14);
            v15 = *(unsigned __int16 *)((char *)a2 + v14);
            if ( v15 < 8 || HIWORD(*((_DWORD *)v13 + 1)) != 0xBEEF || (unsigned int)v14 + v15 > (unsigned int)v12 )
              v13 = 0;
          }
        }
        v16 = (unsigned __int64)a2 + v12;
        if ( v13 )
        {
          while ( *((_DWORD *)v13 + 1) != -1091633148 )
          {
            a3 = 0;
            if ( (unsigned __int64)(v13 + 1) <= v16 )
            {
              v51 = (unsigned __int16 *)((char *)v13 + *(unsigned __int16 *)v13);
              if ( v51 == (unsigned __int16 *)v16 )
                goto LABEL_104;
              if ( (unsigned __int64)v51 <= v16 )
              {
                if ( (unsigned __int64)(v51 + 4) > v16
                  || HIWORD(*((_DWORD *)v51 + 1)) != 0xBEEF
                  || (unsigned __int64)v51 + *v51 > v16
                  || v51 < (unsigned __int16 *)v13 + 4 )
                {
                  goto LABEL_104;
                }
                a3 = (unsigned __int64 *)((char *)v13 + *(unsigned __int16 *)v13);
              }
            }
            v13 = a3;
            if ( !a3 )
              goto LABEL_104;
          }
          goto LABEL_14;
        }
      }
    }
  }
LABEL_104:
  if ( (v9[1] & 0x34) != 0x34 )
  {
LABEL_14:
    v17 = v9 + 7;
    if ( v9 == (unsigned __int16 *)-14LL || (v18 = *v9 - 14LL, v18 > 0x7FFFFFFF) )
    {
      v19 = -2147024809;
    }
    else
    {
      if ( *v9 != 14 )
      {
        do
        {
          if ( !*v17 )
            break;
          ++v17;
          --v18;
        }
        while ( v18 );
      }
      v19 = -2147024809;
      if ( v18 )
        v19 = 0;
    }
    goto LABEL_21;
  }
  v19 = UnalignedStringCbLengthW(v9 + 7, *v9 - 14LL, a3);
LABEL_21:
  if ( v19 >= 0 )
    v10 = (const struct IDFOLDER *)v9;
LABEL_23:
  pszUrl = 0;
  CFileSysItemString::CFileSysItemString((CFileSysItemString *)v86, a1, (const struct _ITEMIDLIST_RELATIVE *)a2, v10);
  v85 = 0;
  if ( (unsigned int)CFileSysItemString::GetJunctionClsid(v86, 3, &v85)
    && (unsigned int)CCLSIDInfoCache::GetFolderValue(v21, &v85, 1) )
  {
    v84 = 0;
    v69 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<IPersistSerializedPropStoragePriv>>(&v84);
    v70 = CFSFolder::_Bind(
            a1,
            0,
            (const struct _ITEMIDLIST_RELATIVE *)a2,
            &GUID_000214e6_0000_0000_c000_000000000046,
            v69);
    if ( v70 < 0 )
    {
      v79 = 5069;
      goto LABEL_197;
    }
    memset_0(&pszSource, 0, sizeof(pszSource));
    v71 = (*(__int64 (__fastcall **)(__int64, const ITEMIDLIST *, _QWORD, STRRET *))(*(_QWORD *)v84 + 88LL))(
            v84,
            &c_idlDesktop,
            v6,
            &pszSource);
    v70 = v71;
    if ( v71 )
    {
      if ( v71 == -2147467263 )
      {
        v72 = wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszUrl);
        v73 = CFileSysItemString::UIName(v86, a4);
        v70 = _AllocString<CTCoAllocPolicy>(v75, v74, v73, v72);
        if ( v70 >= 0 )
          goto LABEL_151;
        v79 = 5079;
LABEL_197:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v79,
          (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
          (const char *)(unsigned int)v70,
          lpWideCharStr);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v84);
        goto LABEL_185;
      }
      if ( v71 < 0 )
      {
        v79 = 5083;
        goto LABEL_197;
      }
    }
    else
    {
      v78 = (LPWSTR *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::put(&pszUrl);
      v70 = StrRetToStrW(&pszSource, &c_idlDesktop, v78);
      if ( v70 < 0 )
      {
        v79 = 5075;
        goto LABEL_197;
      }
    }
LABEL_151:
    v76 = v84;
    if ( v84 )
    {
      v84 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v76 + 16LL))(v76);
    }
    goto LABEL_66;
  }
  pszUrl = 0;
  v23 = -1;
  if ( v96 )
    goto LABEL_44;
  if ( (v97 & 2) == 0 )
  {
    LOWORD(pszSource.uType) = 0;
    v24 = 260;
    v25 = v94;
    if ( !v94 )
      goto LABEL_30;
    if ( *((_WORD *)v94 + 1) >= 7u && (v26 = *((unsigned __int16 *)v94 + 18), (_WORD)v26) )
    {
      v53 = &v94[v26];
      v54 = ualstrlenW(&v94[v26], v20, v94, v22) + 1;
      if ( v54 > 0x104 )
      {
LABEL_122:
        v25 = v94;
LABEL_30:
        if ( a4 == 2 )
        {
          if ( !(unsigned int)IsFolder(v93) )
            goto LABEL_142;
        }
        else
        {
          if ( a4 )
          {
            v28 = v93;
            goto LABEL_33;
          }
          ShouldShowExtension = CFileSysItemString::ShouldShowExtension((CFileSysItemString *)v86);
          v25 = v94;
          v28 = v93;
          if ( !ShouldShowExtension )
          {
LABEL_142:
            if ( (v97 & 1) == 0 )
            {
              if ( v25 )
              {
                ualstrcpynW(pszOutBuf, &v25[*((unsigned __int16 *)v25 + 8)], 260);
              }
              else if ( (*((_BYTE *)v28 + 2) & 0x34) == 0x34 )
              {
                ualstrcpynW(pszOutBuf, (char *)v28 + 14, 260);
              }
              else
              {
                MultiByteToWideChar(0, 0, (LPCCH)v28 + 14, -1, pszOutBuf, 260);
              }
            }
            PathRemoveExtensionW(pszOutBuf);
            v97 = 2;
            goto LABEL_43;
          }
        }
LABEL_33:
        v29 = v95;
        if ( v95 )
        {
LABEL_41:
          if ( pszOutBuf == v29 )
            goto LABEL_40;
          v96 = v29;
LABEL_43:
          if ( v96 )
          {
LABEL_44:
            v31 = v96;
            goto LABEL_45;
          }
          goto LABEL_109;
        }
        if ( (v97 & 1) != 0 )
        {
LABEL_40:
          v97 = 3;
          goto LABEL_43;
        }
        if ( v25 )
        {
          v30 = (WCHAR *)&v25[*((unsigned __int16 *)v25 + 8)];
          if ( ((unsigned __int8)v30 & 1) == 0 )
          {
            if ( v30 != pszOutBuf )
            {
              v29 = (WCHAR *)&v25[*((unsigned __int16 *)v25 + 8)];
              v95 = v29;
              goto LABEL_39;
            }
            goto LABEL_116;
          }
          ualstrcpynW(pszOutBuf, v30, 260);
        }
        else
        {
          if ( (*((_BYTE *)v28 + 2) & 0x34) == 0x34 )
          {
            ualstrcpynW(pszOutBuf, (char *)v28 + 14, 260);
            v29 = v95;
            v97 = 1;
LABEL_39:
            if ( !v29 )
              goto LABEL_40;
            goto LABEL_41;
          }
          MultiByteToWideChar(0, 0, (LPCCH)v28 + 14, -1, pszOutBuf, 260);
        }
        v29 = v95;
LABEL_116:
        v97 = 1;
        goto LABEL_39;
      }
      memcpy_0(&pszSource, v53, 2 * v54);
    }
    else
    {
      v27 = *((unsigned __int16 *)v94 + 9);
      if ( !(_WORD)v27 )
        goto LABEL_30;
      SHAnsiToUnicode(&v94[v27], (PWSTR)&pszSource, 260);
    }
    if ( SHLoadIndirectString((PCWSTR)&pszSource, pszOutBuf, 0x104u, 0) < 0 )
      goto LABEL_122;
    v97 = 2;
    v55 = 2147483646;
    v56 = 2147483646;
    v57 = pszOutBuf;
    v58 = 260;
    v59 = v100;
    do
    {
      if ( !v56 )
        break;
      v60 = *v57;
      if ( !*v57 )
        break;
      ++v57;
      *v59++ = v60;
      --v56;
      --v58;
    }
    while ( v58 );
    v61 = v59 - 1;
    if ( v58 )
      v61 = v59;
    *v61 = 0;
    v62 = v93;
    if ( (((*((_BYTE *)v93 + 2) & 0x37) - 49) & 0xFB) == 0 )
    {
LABEL_130:
      v63 = v100;
      v64 = pszOutBuf;
      do
      {
        if ( !v55 )
          break;
        v65 = *v63;
        if ( !*v63 )
          break;
        ++v63;
        *v64++ = v65;
        --v55;
        --v24;
      }
      while ( v24 );
      v66 = v64 - 1;
      if ( v24 )
        v66 = v64;
      *v66 = 0;
      v97 = 2;
      goto LABEL_43;
    }
    if ( a4 != 1 )
    {
      if ( a4 || !(unsigned int)CFileSysItemString::ShouldShowExtension((CFileSysItemString *)v86) )
        goto LABEL_130;
      v62 = v93;
    }
    if ( v94 )
    {
      ualstrcpynW(&pszSource, &v94[*((unsigned __int16 *)v94 + 8)], 260);
    }
    else if ( (*((_BYTE *)v62 + 2) & 0x34) == 0x34 )
    {
      ualstrcpynW(&pszSource, (char *)v62 + 14, 260);
    }
    else
    {
      MultiByteToWideChar(0, 0, (LPCCH)v62 + 14, -1, (LPWSTR)&pszSource, 260);
    }
    ExtensionW = PathFindExtensionW((LPCWSTR)&pszSource);
    if ( ExtensionW )
      StringCchCatW(v100, 0x104u, ExtensionW);
    goto LABEL_130;
  }
LABEL_109:
  v31 = pszOutBuf;
  do
LABEL_45:
    ++v23;
  while ( v31[v23] );
  pszUrl = 0;
  v32 = v23 + 1;
  if ( v23 + 1 < v23 || (pszUrl = 0, !is_mul_ok(v32, 2u)) )
  {
    v35 = -2147024362;
LABEL_83:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13E0,
      (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
      (const char *)(unsigned int)v35,
      lpWideCharStr);
    v86[0] = &CFileSysItemString::`vftable';
    v47 = v92;
    v92 = 0;
    if ( v47 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v48 = v90;
    v90 = 0;
    if ( v48 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
    v49 = v91;
    v91 = 0;
    if ( v49 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v88 )
      CoTaskMemFree(v88);
    if ( v87 )
      CoTaskMemFree(v87);
    if ( pszUrl )
      CoTaskMemFree(pszUrl);
    return (unsigned int)v35;
  }
  v33 = (WCHAR *)CoTaskMemAlloc(2 * v32);
  v34 = v33;
  pszUrl = v33;
  v35 = -2147024882;
  if ( v33 )
    v35 = 0;
  if ( v35 < 0 )
    goto LABEL_83;
  if ( !v33 && v23 != -1 || v32 > 0x7FFFFFFF )
    goto LABEL_194;
  if ( v23 < 0x7FFFFFFF )
  {
    if ( !v31 )
    {
      v31 = (WCHAR *)&WindowName;
      v23 = 0;
    }
    if ( v32 )
    {
      v36 = v32;
      v37 = v33;
      v38 = 0;
      do
      {
        if ( !v23 )
          break;
        v39 = *v31;
        if ( !*v31 )
          break;
        ++v31;
        *v37++ = v39;
        --v23;
        ++v38;
        --v36;
      }
      while ( v36 );
      v40 = v38 - 1;
      if ( v36 )
        v40 = v38;
      v41 = v37 - 1;
      if ( v36 )
        v41 = v37;
      *v41 = 0;
      if ( v36 )
      {
        v68 = v32 == v40;
        v67 = v32 - v40;
        if ( !v68 && v67 != 1 && (unsigned __int64)(2 * v67) > 2 )
          memset_0(&v34[v40 + 1], 0, 2 * v67 - 2);
      }
    }
    goto LABEL_66;
  }
  if ( v23 != -1 )
LABEL_194:
    *v33 = 0;
LABEL_66:
  if ( (*((_BYTE *)a1 + 536) & 0x20) != 0 )
  {
    v81 = UrlUnescapeW(pszUrl, 0, 0, 0x100000u);
    v70 = v81;
    if ( v81 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x13E5,
        (unsigned int)"onecoreuap\\shell\\windows.storage\\filefldr.cpp",
        (const char *)(unsigned int)v81,
        lpWideCharStr);
LABEL_185:
      CFileSysItemString::~CFileSysItemString((CFileSysItemString *)v86);
      if ( pszUrl )
        CoTaskMemFree(pszUrl);
      return (unsigned int)v70;
    }
  }
  v42 = pszUrl;
  pszUrl = 0;
  *a5 = v42;
  v86[0] = &CFileSysItemString::`vftable';
  v43 = v92;
  v92 = 0;
  if ( v43 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  v44 = v90;
  v90 = 0;
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  v45 = v91;
  v91 = 0;
  if ( v45 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v88 )
    CoTaskMemFree(v88);
  if ( v87 )
    CoTaskMemFree(v87);
  if ( pszUrl )
    CoTaskMemFree(pszUrl);
  return 0;
}

```

## disassembly

```asm
0x180096180  push    rbp
0x180096182  push    rbx
0x180096183  push    rsi
0x180096184  push    rdi
0x180096185  push    r12
0x180096187  push    r13
0x180096189  push    r14
0x18009618b  push    r15
0x18009618d  lea     rbp, [rsp-638h]
0x180096195  sub     rsp, 738h
0x18009619c  mov     rax, cs:__security_cookie
0x1800961a3  xor     rax, rsp
0x1800961a6  mov     [rbp+670h+var_50], rax
0x1800961ad  mov     r15d, r9d
0x1800961b0  mov     r14d, r8d
0x1800961b3  mov     rbx, rdx
0x1800961b6  mov     r12, rcx
0x1800961b9  mov     r13, [rbp+670h+arg_20]
0x1800961c0  mov     qword ptr [r13+0], 0
0x1800961c8  xor     edi, edi
0x1800961ca  test    rdx, rdx
0x1800961cd  jnz     loc_1800966CA
0x1800961d3  xor     esi, esi
0x1800961d5  test    rdi, rdi
0x1800961d8  jz      loc_1800962C4
0x1800961de  cmp     word ptr [rdi], 0Eh
0x1800961e2  jb      loc_1800962C4
0x1800961e8  test    rbx, rbx
0x1800961eb  jz      loc_180096686
0x1800961f1  cmp     word ptr [rbx], 0
0x1800961f5  jz      loc_180096686
0x1800961fb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow> `wil::Feature<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::GetImpl(void)'::`2'::impl
0x180096202  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_ShellDataModel_HiddenPidlUnderflow>::__private_IsEnabled(void)
0x180096207  movzx   r9d, word ptr [rbx]
0x18009620b  test    al, al
0x18009620d  jnz     loc_180096B2B
0x180096213  xor     edx, edx
0x180096215  movzx   r10d, word ptr [rbx+r9-2]
0x18009621b  mov     r11d, 0BEEFh
0x180096221  test    r10w, r10w
0x180096225  jz      short loc_18009625D
0x180096227  lea     rax, [r10+8]
0x18009622b  cmp     rax, r9
0x18009622e  jnb     short loc_18009625D
0x180096230  lea     rdx, [rbx+r10]
0x180096234  movzx   ecx, word ptr [rdx]
0x180096237  cmp     ecx, 8
0x18009623a  jb      loc_18009687D
0x180096240  mov     eax, [rdx+4]
0x180096243  shr     rax, 10h
0x180096247  cmp     ax, r11w
0x18009624b  jnz     loc_18009687D
0x180096251  add     ecx, r10d
0x180096254  cmp     ecx, r9d
0x180096257  ja      loc_18009687D
0x18009625d  lea     rcx, [rbx+r9]
0x180096261  test    rdx, rdx
0x180096264  jz      loc_180096686
0x18009626a  cmp     dword ptr [rdx+4], 0BEEF0004h
0x180096271  jnz     loc_180096708
0x180096277  lea     rcx, [rdi+0Eh]
0x18009627b  test    rcx, rcx
0x18009627e  jz      loc_180096B20
0x180096284  movzx   edx, word ptr [rdi]
0x180096287  add     rdx, 0FFFFFFFFFFFFFFF2h
0x18009628b  cmp     rdx, 7FFFFFFFh
0x180096292  ja      loc_180096B20
0x180096298  test    rdx, rdx
0x18009629b  jz      short loc_1800962AE
0x18009629d  nop     dword ptr [rax]
0x1800962a0  cmp     byte ptr [rcx], 0
0x1800962a3  jz      short loc_1800962AE
0x1800962a5  inc     rcx
0x1800962a8  sub     rdx, 1
0x1800962ac  jnz     short loc_1800962A0
0x1800962ae  xor     eax, eax
0x1800962b0  mov     r8d, 80070057h
0x1800962b6  test    rdx, rdx
0x1800962b9  cmovnz  r8d, eax
0x1800962bd  test    r8d, r8d
0x1800962c0  cmovns  rsi, rdi
0x1800962c4  mov     [rsp+770h+pszUrl], 0
0x1800962cd  mov     r9, rsi; struct IDFOLDER *
0x1800962d0  mov     r8, rbx; struct _ITEMIDLIST_RELATIVE *
0x1800962d3  mov     rdx, r12; struct CFSFolder *
0x1800962d6  lea     rcx, [rsp+770h+var_720]; this
0x1800962db  call    ??0CFileSysItemString@@QEAA@PEAVCFSFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEFBUIDFOLDER@@@Z; CFileSysItemString::CFileSysItemString(CFSFolder *,_ITEMIDLIST_RELATIVE const *,IDFOLDER const *)
0x1800962e0  nop
0x1800962e1  xorps   xmm0, xmm0
0x1800962e4  movups  [rsp+770h+var_730], xmm0
0x1800962e9  lea     r8, [rsp+770h+var_730]
0x1800962ee  mov     edx, 3
0x1800962f3  lea     rcx, [rsp+770h+var_720]
0x1800962f8  call    ?GetJunctionClsid@CFileSysItemString@@QEAAHW4FSIS_JUNCTION_FLAGS@@PEAU_GUID@@@Z; CFileSysItemString::GetJunctionClsid(FSIS_JUNCTION_FLAGS,_GUID *)
0x1800962fd  test    eax, eax
0x1800962ff  jnz     loc_180096913
0x180096305  mov     rdi, [rsp+770h+pszUrl]
0x18009630a  test    rdi, rdi
0x18009630d  jnz     loc_1800966AC
0x180096313  mov     [rsp+770h+pszUrl], 0
0x18009631c  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x180096323  cmp     [rbp+670h+var_6B0], 0
0x180096328  jnz     loc_1800963ED
0x18009632e  test    byte ptr [rbp+670h+var_6A0], 2
0x180096332  jnz     loc_1800966FF
0x180096338  xor     eax, eax
0x18009633a  mov     word ptr [rbp+670h+pszSource.uType], ax
0x180096341  mov     esi, 104h
0x180096346  mov     r8, [rbp+670h+var_6C8]
0x18009634a  test    r8, r8
0x18009634d  jz      short loc_180096373
0x18009634f  cmp     word ptr [r8+2], 7
0x180096355  jb      short loc_180096365
0x180096357  movzx   eax, word ptr [r8+24h]
0x18009635c  test    ax, ax
0x18009635f  jnz     loc_180096780
0x180096365  movzx   eax, word ptr [r8+12h]
0x18009636a  test    ax, ax
0x18009636d  jnz     loc_180096C38
0x180096373  cmp     r15d, 2
0x180096377  jz      loc_1800968B6
0x18009637d  test    r15d, r15d
0x180096380  jz      loc_180096750
0x180096386  mov     r9, [rbp+670h+var_6D0]
0x18009638a  mov     rcx, [rbp+670h+var_6B8]
0x18009638e  test    rcx, rcx
0x180096391  jnz     short loc_1800963D5
0x180096393  test    byte ptr [rbp+670h+var_6A0], 1
0x180096397  jnz     short loc_1800963CC
0x180096399  test    r8, r8
0x18009639c  jz      loc_180096A40
0x1800963a2  movzx   edx, word ptr [r8+10h]
0x1800963a7  add     rdx, r8
0x1800963aa  test    dl, 1
0x1800963ad  jnz     loc_180096733
0x1800963b3  lea     rax, [rbp+670h+pszOutBuf]
0x1800963b7  cmp     rdx, rax
0x1800963ba  jz      loc_180096744
0x1800963c0  mov     rcx, rdx
0x1800963c3  mov     [rbp+670h+var_6B8], rdx
0x1800963c7  test    rcx, rcx
0x1800963ca  jnz     short loc_1800963D5
0x1800963cc  mov     [rbp+670h+var_6A0], 3
0x1800963d3  jmp     short loc_1800963E2
0x1800963d5  lea     rax, [rbp+670h+pszOutBuf]
0x1800963d9  cmp     rax, rcx
0x1800963dc  jz      short loc_1800963CC
0x1800963de  mov     [rbp+670h+var_6B0], rcx
0x1800963e2  cmp     [rbp+670h+var_6B0], 0
0x1800963e7  jz      loc_1800966FF
0x1800963ed  mov     rdi, [rbp+670h+var_6B0]
0x1800963f1  inc     rbx
0x1800963f4  cmp     word ptr [rdi+rbx*2], 0
0x1800963f9  jnz     short loc_1800963F1
0x1800963fb  xor     r15d, r15d
0x1800963fe  mov     [rsp+770h+pszUrl], r15
0x180096403  lea     r14, [rbx+1]
0x180096407  cmp     r14, rbx
0x18009640a  jb      loc_180096598
0x180096410  mov     [rsp+770h+pszUrl], r15
0x180096415  mov     eax, 2
0x18009641a  mul     r14
0x18009641d  test    rdx, rdx
0x180096420  jnz     loc_180096598
0x180096426  mov     rcx, rax; cb
0x180096429  call    cs:__imp_CoTaskMemAlloc
0x18009642f  mov     r10, rax
0x180096432  mov     [rsp+770h+pszUrl], rax
0x180096437  mov     esi, 8007000Eh
0x18009643c  test    rax, rax
0x18009643f  cmovnz  esi, r15d
0x180096443  test    esi, esi
0x180096445  js      loc_18009659D
0x18009644b  test    rax, rax
0x18009644e  jz      loc_180096A99
0x180096454  cmp     r14, 7FFFFFFFh
0x18009645b  ja      loc_180096C5A
0x180096461  cmp     rbx, 7FFFFFFFh
0x180096468  jnb     loc_180096C51
0x18009646e  test    rdi, rdi
0x180096471  jz      loc_180096904
0x180096477  test    r14, r14
0x18009647a  jz      short loc_1800964C7
0x18009647c  mov     rdx, r14
0x18009647f  mov     r8, r10
0x180096482  mov     rcx, r15
0x180096485  test    rbx, rbx
0x180096488  jz      short loc_1800964AA
0x18009648a  movzx   eax, word ptr [rdi]
0x18009648d  test    ax, ax
0x180096490  jz      short loc_1800964AA
0x180096492  add     rdi, 2
0x180096496  mov     [r8], ax
0x18009649a  add     r8, 2
0x18009649e  dec     rbx
0x1800964a1  inc     rcx
0x1800964a4  sub     rdx, 1
0x1800964a8  jnz     short loc_180096485
0x1800964aa  lea     r9, [rcx-1]
0x1800964ae  test    rdx, rdx
0x1800964b1  cmovnz  r9, rcx
0x1800964b5  lea     rcx, [r8-2]
0x1800964b9  cmovnz  rcx, r8
0x1800964bd  mov     [rcx], r15w
0x1800964c1  jnz     loc_180096884
0x1800964c7  test    byte ptr [r12+218h], 20h
0x1800964d0  jnz     loc_180096C63
0x1800964d6  mov     rax, [rsp+770h+pszUrl]
0x1800964db  mov     [rsp+770h+pszUrl], r15
0x1800964e0  mov     [r13+0], rax
0x1800964e4  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x1800964eb  mov     [rsp+770h+var_720], rax
0x1800964f0  mov     rcx, [rbp+670h+var_6D8]
0x1800964f4  mov     [rbp+670h+var_6D8], r15
0x1800964f8  test    rcx, rcx
0x1800964fb  jz      short loc_180096509
0x1800964fd  mov     rax, [rcx]
0x180096500  mov     rax, [rax+10h]
0x180096504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096509  mov     rcx, [rbp+670h+var_6E8]
0x18009650d  mov     [rbp+670h+var_6E8], r15
0x180096511  test    rcx, rcx
0x180096514  jnz     loc_1800966EE
0x18009651a  mov     rcx, [rbp+670h+var_6E0]
0x18009651e  mov     [rbp+670h+var_6E0], r15
0x180096522  test    rcx, rcx
0x180096525  jz      short loc_180096533
0x180096527  mov     rax, [rcx]
0x18009652a  mov     rax, [rax+10h]
0x18009652e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096533  mov     rcx, [rbp+670h+pv]; pv
0x180096537  test    rcx, rcx
0x18009653a  jz      short loc_180096542
0x18009653c  call    cs:__imp_CoTaskMemFree
0x180096542  mov     rcx, [rsp+770h+var_708]; pv
0x180096547  test    rcx, rcx
0x18009654a  jz      short loc_180096552
0x18009654c  call    cs:__imp_CoTaskMemFree
0x180096552  mov     rcx, [rsp+770h+var_710]; pv
0x180096557  test    rcx, rcx
0x18009655a  jz      short loc_180096563
0x18009655c  call    cs:__imp_CoTaskMemFree
0x180096562  nop
0x180096563  mov     rcx, [rsp+770h+pszUrl]; pv
0x180096568  test    rcx, rcx
0x18009656b  jz      short loc_180096573
0x18009656d  call    cs:__imp_CoTaskMemFree
0x180096573  xor     eax, eax
0x180096575  mov     rcx, [rbp+670h+var_50]
0x18009657c  xor     rcx, rsp; StackCookie
0x18009657f  call    __security_check_cookie
0x180096584  add     rsp, 738h
0x18009658b  pop     r15
0x18009658d  pop     r14
0x18009658f  pop     r13
0x180096591  pop     r12
0x180096593  pop     rdi
0x180096594  pop     rsi
0x180096595  pop     rbx
0x180096596  pop     rbp
0x180096597  retn
0x180096598  mov     esi, 80070216h
0x18009659d  mov     rcx, [rbp+678h]; this
0x1800965a4  mov     r9d, esi; char *
0x1800965a7  lea     r8, aOnecoreuapShel_18; "onecoreuap\\shell\\windows.storage\\fil"...
0x1800965ae  mov     edx, 13E0h; void *
0x1800965b3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800965b8  nop
0x1800965b9  lea     rax, ??_7CFileSysItemString@@6B@; const CFileSysItemString::`vftable'
0x1800965c0  mov     [rsp+770h+var_720], rax
0x1800965c5  mov     rcx, [rbp+670h+var_6D8]
0x1800965c9  mov     [rbp+670h+var_6D8], r15
0x1800965cd  test    rcx, rcx
0x1800965d0  jz      short loc_1800965DE
0x1800965d2  mov     rax, [rcx]
0x1800965d5  mov     rax, [rax+10h]
0x1800965d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800965de  mov     rcx, [rbp+670h+var_6E8]
0x1800965e2  mov     [rbp+670h+var_6E8], r15
0x1800965e6  test    rcx, rcx
0x1800965e9  jnz     loc_18009676F
0x1800965ef  mov     rcx, [rbp+670h+var_6E0]
0x1800965f3  mov     [rbp+670h+var_6E0], r15
0x1800965f7  test    rcx, rcx
0x1800965fa  jz      short loc_180096608
0x1800965fc  mov     rax, [rcx]
0x1800965ff  mov     rax, [rax+10h]
0x180096603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180096608  mov     rcx, [rbp+670h+pv]; pv
0x18009660c  test    rcx, rcx
0x18009660f  jz      short loc_180096617
0x180096611  call    cs:__imp_CoTaskMemFree
0x180096617  mov     rcx, [rsp+770h+var_708]; pv
0x18009661c  test    rcx, rcx
0x18009661f  jz      short loc_180096627
0x180096621  call    cs:__imp_CoTaskMemFree
0x180096627  mov     rcx, [rsp+770h+var_710]; pv
0x18009662c  test    rcx, rcx
0x18009662f  jz      short loc_180096638
0x180096631  call    cs:__imp_CoTaskMemFree
  ... truncated ...
```
