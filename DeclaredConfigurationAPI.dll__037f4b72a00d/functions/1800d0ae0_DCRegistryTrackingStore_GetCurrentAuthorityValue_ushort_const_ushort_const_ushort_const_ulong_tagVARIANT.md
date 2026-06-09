# DCRegistryTrackingStore::GetCurrentAuthorityValue(ushort const *,ushort const *,ushort const *,ulong *,tagVARIANT *)

- ea: `0x1800d0ae0`
- end: `0x1800d14bc`
- name: `?GetCurrentAuthorityValue@DCRegistryTrackingStore@@UEAAJPEBG00PEAKPEAUtagVARIANT@@@Z`
- size: `2524`
- prototype: `__int64 __fastcall(DCRegistryTrackingStore *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *, struct tagVARIANT *)`
- caller_count: `0`
- callee_count: `26`
- tags: `registry_config`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x180011fe0`
- `0x1800143c8`
- `0x180018ac0`
- `0x180018b30`
- `0x180019d38`
- `0x18001bc98`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18001def8`
- `0x18004bc88`
- `0x18005860c`
- `0x18005fcf8`
- `0x1800600bc`
- `0x1800ce488`
- `0x1800d0ae0`
- `0x1800d14c4`
- `0x180100534`
- `0x1801006c8`
- `0x1801007e8`
- `0x1801009b0`
- `0x180100ad8`
- `0x180102a34`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800d0c21`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d0e58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d0ebb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d0e58`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d0ebb`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d112f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d137b`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d112f`
- `OLEAUT32!__imp_SysAllocString` at `0x1800d137b`

## string_xrefs

- `0x1800d0b4e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d0d78`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d0e09`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d0f37`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d0f96`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d1103`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d11c5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d12c6`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d139b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall DCRegistryTrackingStore::GetCurrentAuthorityValue(
        DCRegistryTrackingStore *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int *a5,
        struct tagVARIANT *a6)
{
  __int64 v9; // rdx
  signed int RegistryString; // ebx
  char IsEnabled; // al
  __int64 v13; // r8
  __int64 v14; // r8
  char **v15; // r9
  _QWORD *v16; // rax
  int v17; // r9d
  char **v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  char **v21; // rax
  char **v22; // rcx
  char **v23; // rax
  __int64 v24; // rdx
  char **v25; // r9
  __int64 v26; // rcx
  char **v27; // r8
  int PMCspRedirectedRegistryPath; // eax
  unsigned __int64 v29; // r9
  __int64 v30; // rdx
  LSTATUS v31; // eax
  LSTATUS v32; // eax
  __int64 v33; // rdx
  unsigned __int64 v34; // r9
  int v35; // eax
  int RegistryDWORD; // eax
  int RegistryQWORD; // eax
  __int64 v38; // rdx
  OLECHAR **p_strIn; // rcx
  BSTR v40; // rax
  OLECHAR **p_psz; // rcx
  __int64 v42; // rdx
  __int64 v43; // rdx
  unsigned __int64 v44; // r9
  int v45; // eax
  int v46; // eax
  unsigned __int64 v47; // r9
  __int64 v48; // rdx
  int v49; // eax
  __int64 v50; // rdx
  BSTR v51; // rax
  int phkResult; // [rsp+20h] [rbp-328h]
  int phkResulta; // [rsp+20h] [rbp-328h]
  HKEY *phkResultb; // [rsp+20h] [rbp-328h]
  int phkResultc; // [rsp+20h] [rbp-328h]
  int phkResultd; // [rsp+20h] [rbp-328h]
  HKEY v57; // [rsp+30h] [rbp-318h] BYREF
  __int64 v58; // [rsp+38h] [rbp-310h] BYREF
  int v59[2]; // [rsp+40h] [rbp-308h] BYREF
  _QWORD *p_lpSubKey; // [rsp+48h] [rbp-300h] BYREF
  HKEY v61; // [rsp+50h] [rbp-2F8h] BYREF
  char v62; // [rsp+58h] [rbp-2F0h]
  OLECHAR *psz; // [rsp+60h] [rbp-2E8h] BYREF
  OLECHAR *v64; // [rsp+68h] [rbp-2E0h] BYREF
  OLECHAR *strIn; // [rsp+70h] [rbp-2D8h] BYREF
  LPCWSTR lpSubKey; // [rsp+78h] [rbp-2D0h] BYREF
  void *Src; // [rsp+80h] [rbp-2C8h] BYREF
  _BYTE v68[32]; // [rsp+88h] [rbp-2C0h] BYREF
  char *v69[3]; // [rsp+A8h] [rbp-2A0h] BYREF
  unsigned __int64 v70; // [rsp+C0h] [rbp-288h]
  char *v71[3]; // [rsp+C8h] [rbp-280h] BYREF
  unsigned __int64 v72; // [rsp+E0h] [rbp-268h]
  unsigned __int16 v73[264]; // [rsp+F0h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+348h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
  {
    if ( !a2 )
    {
      v9 = 230;
LABEL_4:
      RegistryString = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v9,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)0x80070057LL,
        phkResulta);
      return (unsigned int)RegistryString;
    }
    if ( !a4 )
    {
      v9 = 231;
      goto LABEL_4;
    }
  }
  if ( !a3 )
  {
    v9 = 233;
    goto LABEL_4;
  }
  if ( !a5 )
  {
    v9 = 234;
    goto LABEL_4;
  }
  if ( !a6 )
  {
    v9 = 235;
    goto LABEL_4;
  }
  std::wstring::wstring((__int64)v71);
  std::wstring::wstring((__int64)v69);
  try
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl);
    v13 = -1;
    if ( IsEnabled )
    {
      do
        ++v13;
      while ( a3[v13] );
      std::wstring::_Assign<unsigned short>(v71, a3, (char *)v13);
      v15 = v71;
      if ( v72 > 7 )
        v15 = (char **)v71[0];
      v16 = (_QWORD *)std::wstring::end(v71, &v64, v14, v15);
      v18 = v71;
      if ( v72 > 7 )
        LODWORD(v18) = v71[0];
      std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
        (unsigned int)&Src,
        (_DWORD)v18,
        *v16,
        v17,
        *(__int64 *)&_o_towlower);
      std::wstring::operator=(v69, v71);
    }
    else
    {
      do
        ++v13;
      while ( a3[v13] );
      std::wstring::_Assign<unsigned short>(v69, a3, (char *)v13);
    }
    v21 = *(char ***)std::wstring::end(v69, &v64, v19, v20);
    v22 = v69;
    if ( v70 > 7 )
      v22 = (char **)v69[0];
    while ( v22 != v21 )
    {
      if ( *(_WORD *)v22 == 47 )
        *(_WORD *)v22 = 92;
      v22 = (char **)((char *)v22 + 2);
    }
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xFF,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)0x8007000ELL,
      phkResult);
    std::wstring::_Tidy_deallocate(v69);
    std::wstring::_Tidy_deallocate(v71);
    return 2147942414LL;
  }
  lpSubKey = 0;
  v61 = 0;
  v62 = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
  {
    v23 = v69;
    if ( v70 > 7 )
      v23 = (char **)v69[0];
    p_lpSubKey = &lpSubKey;
    RegistryString = DCStringCchPrintfAllStrings(&v61, qword_18018A5F0, 2, a2, v23);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
    if ( RegistryString < 0 )
    {
      v24 = 266;
LABEL_41:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)(unsigned int)RegistryString,
        phkResulta);
LABEL_113:
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
      std::wstring::_Tidy_deallocate(v69);
      std::wstring::_Tidy_deallocate(v71);
      return (unsigned int)RegistryString;
    }
  }
  else
  {
    v25 = v69;
    if ( v70 > 7 )
      v25 = (char **)v69[0];
    p_lpSubKey = &lpSubKey;
    RegistryString = DCStringCchPrintfAllStrings(&v61, qword_18018A5E8, 1, v25);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
    if ( RegistryString < 0 )
    {
      v24 = 274;
      goto LABEL_41;
    }
  }
  v57 = 0;
  std::wstring::wstring((__int64)v68);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
  {
    v27 = v71;
    if ( v72 > 7 )
      v27 = (char **)v71[0];
    phkResultb = &v57;
    PMCspRedirectedRegistryPath = DCRegistryTrackingStore::GetPMCspRedirectedRegistryPath(v26, a2, v27, a4);
    RegistryString = PMCspRedirectedRegistryPath;
    if ( PMCspRedirectedRegistryPath < 0 )
    {
      v29 = (unsigned int)PMCspRedirectedRegistryPath;
      v30 = 281;
LABEL_47:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)v29,
        (int)phkResultb);
LABEL_112:
      std::wstring::_Tidy_deallocate(v68);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v57);
      goto LABEL_113;
    }
    if ( !v57 )
    {
      p_lpSubKey = &v57;
      v61 = 0;
      v62 = 1;
      v31 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &v61);
      RegistryString = v31;
      if ( v31 > 0 )
        RegistryString = (unsigned __int16)v31 | 0x80070000;
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
      if ( RegistryString < 0 )
      {
        v29 = (unsigned int)RegistryString;
        v30 = 290;
        goto LABEL_47;
      }
    }
  }
  else
  {
    p_lpSubKey = &v57;
    v61 = 0;
    v62 = 1;
    v32 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &v61);
    RegistryString = v32;
    if ( v32 > 0 )
      RegistryString = (unsigned __int16)v32 | 0x80070000;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
    if ( RegistryString < 0 )
    {
      v29 = (unsigned int)RegistryString;
      v30 = 300;
      goto LABEL_47;
    }
  }
  v58 = 0;
  p_lpSubKey = &v58;
  v61 = 0;
  v62 = 1;
  RegistryString = DCCDNUtil_GetRegistryString(v57, 0, L"authorityId", (unsigned __int16 **)&v61);
  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
  if ( RegistryString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x131,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)(unsigned int)RegistryString,
      (int)phkResultb);
LABEL_111:
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v58);
    goto LABEL_112;
  }
  *(_QWORD *)v59 = 0;
  p_lpSubKey = v59;
  v61 = 0;
  v62 = 1;
  RegistryString = DCCDNUtil_GetRegistryString(v57, 0, L"documentId", (unsigned __int16 **)&v61);
  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
  if ( RegistryString < 0 )
  {
    v33 = 308;
LABEL_61:
    v34 = (unsigned int)RegistryString;
LABEL_62:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v33,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)v34,
      (int)phkResultb);
LABEL_110:
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v59);
    goto LABEL_111;
  }
  LODWORD(phkResultb) = v59[0];
  v35 = StringCchPrintfW(v73, 0x104u, L"%s\\%s", v58);
  RegistryString = v35;
  if ( v35 < 0 )
  {
    v34 = (unsigned int)v35;
    v33 = 316;
    goto LABEL_62;
  }
  RegistryDWORD = DCCDNUtil_GetRegistryDWORD(v57, v73, L"typeStored", a5);
  RegistryString = RegistryDWORD;
  if ( RegistryDWORD < 0 )
  {
    v34 = (unsigned int)RegistryDWORD;
    v33 = 318;
    goto LABEL_62;
  }
  switch ( *a5 )
  {
    case 1u:
      v64 = 0;
      p_lpSubKey = &v64;
      v61 = 0;
      v62 = 1;
      RegistryString = DCCDNUtil_GetRegistryString(v57, v73, L"value", (unsigned __int16 **)&v61);
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
      if ( RegistryString >= 0 )
      {
        a6->vt = 8;
        v51 = SysAllocString(v64);
        a6->llVal = (LONGLONG)v51;
        if ( v51 )
        {
          p_psz = &v64;
          goto LABEL_115;
        }
        RegistryString = -2147024882;
        v50 = 330;
      }
      else
      {
        v50 = 327;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v50,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)(unsigned int)RegistryString,
        (int)phkResultb);
      p_strIn = &v64;
      goto LABEL_109;
    case 3u:
      Src = 0;
      LODWORD(psz) = 0;
      p_lpSubKey = &Src;
      v61 = 0;
      v62 = 1;
      RegistryString = DCCDNUtil_GetRegistryBinary(v57, v73, L"value", (unsigned __int8 **)&v61, (unsigned int *)&psz);
      wil::details::out_param_t<std::unique_ptr<unsigned char>>::~out_param_t<std::unique_ptr<unsigned char>>(&p_lpSubKey);
      if ( RegistryString >= 0 )
      {
        v49 = DCInlineSetBinaryToVariant(Src, (unsigned int)psz);
        RegistryString = v49;
        if ( v49 >= 0 )
        {
          std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&Src);
          break;
        }
        v47 = (unsigned int)v49;
        v48 = 338;
      }
      else
      {
        v47 = (unsigned int)RegistryString;
        v48 = 337;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v48,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)v47,
        phkResultd);
      std::unique_ptr<unsigned char>::~unique_ptr<unsigned char>(&Src);
      goto LABEL_110;
    case 4u:
      LODWORD(psz) = 0;
      v46 = DCCDNUtil_GetRegistryDWORD(v57, v73, L"value", (unsigned int *)&psz);
      RegistryString = v46;
      if ( v46 < 0 )
      {
        v34 = (unsigned int)v46;
        v33 = 344;
        goto LABEL_62;
      }
      a6->vt = 3;
      a6->lVal = (int)psz;
      break;
    case 6u:
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
        goto LABEL_78;
      v64 = 0;
      RegistryQWORD = DCCDNUtil_GetRegistryQWORD(v57, v73, L"value", (unsigned __int64 *)&v64);
      RegistryString = RegistryQWORD;
      if ( RegistryQWORD < 0 )
      {
        v34 = (unsigned int)RegistryQWORD;
        v33 = 353;
        goto LABEL_62;
      }
      a6->vt = 20;
      a6->llVal = (LONGLONG)v64;
      break;
    case 7u:
LABEL_85:
      if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
        goto LABEL_73;
      strIn = 0;
      p_lpSubKey = &strIn;
      v61 = 0;
      v62 = 1;
      RegistryString = DCCDNUtil_GetRegistryMultiString(
                         v57,
                         v73,
                         L"value",
                         (unsigned __int16 **)&v61,
                         (unsigned int *)&psz);
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
      if ( RegistryString < 0 )
      {
        v43 = 374;
LABEL_88:
        v44 = (unsigned int)RegistryString;
LABEL_89:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v43,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
          (const char *)v44,
          phkResultc);
        p_strIn = &strIn;
        goto LABEL_109;
      }
      a6->vt = 8200;
      v45 = MultiStringToSafeArray(strIn, v42, &a6->parray);
      RegistryString = v45;
      if ( v45 < 0 )
      {
        v44 = (unsigned int)v45;
        v43 = 376;
        goto LABEL_89;
      }
      if ( !a6->llVal )
      {
        RegistryString = -2147024882;
        v43 = 377;
        goto LABEL_88;
      }
      p_psz = &strIn;
LABEL_115:
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(p_psz);
      break;
    case 8u:
LABEL_78:
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
      {
        psz = 0;
        p_lpSubKey = &psz;
        v61 = 0;
        v62 = 1;
        RegistryString = DCCDNUtil_GetRegistryString(v57, v73, L"value", (unsigned __int16 **)&v61);
        wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
        if ( RegistryString < 0 )
        {
          v38 = 363;
LABEL_81:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v38,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
            (const char *)(unsigned int)RegistryString,
            (int)phkResultb);
          p_strIn = &psz;
LABEL_109:
          std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(p_strIn);
          goto LABEL_110;
        }
        a6->vt = 8;
        v40 = SysAllocString(psz);
        a6->llVal = (LONGLONG)v40;
        if ( !v40 )
        {
          RegistryString = -2147024882;
          v38 = 366;
          goto LABEL_81;
        }
        p_psz = &psz;
        goto LABEL_115;
      }
      goto LABEL_85;
    default:
LABEL_73:
      RegistryString = -2147418113;
      v33 = 381;
      goto LABEL_61;
  }
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(v59);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v58);
  std::wstring::_Tidy_deallocate(v68);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v57);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
  std::wstring::_Tidy_deallocate(v69);
  std::wstring::_Tidy_deallocate(v71);
  return 0;
}

```

## disassembly

```asm
0x1800d0ae0  push    rbx
0x1800d0ae2  push    rsi
0x1800d0ae3  push    rdi
0x1800d0ae4  push    r12
0x1800d0ae6  push    r13
0x1800d0ae8  push    r14
0x1800d0aea  push    r15
0x1800d0aec  sub     rsp, 310h
0x1800d0af3  mov     rax, cs:__security_cookie
0x1800d0afa  xor     rax, rsp
0x1800d0afd  mov     [rsp+348h+var_48], rax
0x1800d0b05  mov     r15, r9
0x1800d0b08  mov     rbx, r8
0x1800d0b0b  mov     r14, rdx
0x1800d0b0e  mov     rdi, [rsp+348h+arg_28]
0x1800d0b16  mov     rsi, [rsp+348h+arg_20]
0x1800d0b1e  lea     r13, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800d0b25  mov     rcx, r13
0x1800d0b28  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800d0b2d  xor     r12d, r12d
0x1800d0b30  test    al, al
0x1800d0b32  jz      short loc_1800D0B6D
0x1800d0b34  test    r14, r14
0x1800d0b37  jnz     short loc_1800D0B61
0x1800d0b39  mov     edx, 0E6h; void *
0x1800d0b3e  mov     ebx, 80070057h
0x1800d0b43  mov     rcx, [rsp+348h]; this
0x1800d0b4b  mov     r9d, ebx; char *
0x1800d0b4e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d0b55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0b5a  mov     eax, ebx
0x1800d0b5c  jmp     loc_1800D1499
0x1800d0b61  test    r15, r15
0x1800d0b64  jnz     short loc_1800D0B6D
0x1800d0b66  mov     edx, 0E7h
0x1800d0b6b  jmp     short loc_1800D0B3E
0x1800d0b6d  test    rbx, rbx
0x1800d0b70  jnz     short loc_1800D0B79
0x1800d0b72  mov     edx, 0E9h
0x1800d0b77  jmp     short loc_1800D0B3E
0x1800d0b79  test    rsi, rsi
0x1800d0b7c  jnz     short loc_1800D0B85
0x1800d0b7e  mov     edx, 0EAh
0x1800d0b83  jmp     short loc_1800D0B3E
0x1800d0b85  test    rdi, rdi
0x1800d0b88  jnz     short loc_1800D0B91
0x1800d0b8a  mov     edx, 0EBh
0x1800d0b8f  jmp     short loc_1800D0B3E
0x1800d0b91  lea     rcx, [rsp+348h+var_280]
0x1800d0b99  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800d0b9e  nop
0x1800d0b9f  lea     rcx, [rsp+348h+var_2A0]
0x1800d0ba7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800d0bac  nop
0x1800d0bad  mov     rcx, r13
0x1800d0bb0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800d0bb5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800d0bb9  test    al, al
0x1800d0bbb  jz      loc_1800D0C54
0x1800d0bc1  inc     r8
0x1800d0bc4  cmp     [rbx+r8*2], r12w
0x1800d0bc9  jnz     short loc_1800D0BC1
0x1800d0bcb  mov     rdx, rbx
0x1800d0bce  lea     rcx, [rsp+348h+var_280]
0x1800d0bd6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800d0bdb  lea     r9, [rsp+348h+var_280]
0x1800d0be3  cmp     [rsp+348h+var_268], 7
0x1800d0bec  cmova   r9, [rsp+348h+var_280]
0x1800d0bf5  lea     rdx, [rsp+348h+var_2E0]
0x1800d0bfa  lea     rcx, [rsp+348h+var_280]
0x1800d0c02  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1800d0c07  lea     rdx, [rsp+348h+var_280]
0x1800d0c0f  cmp     [rsp+348h+var_268], 7
0x1800d0c18  cmova   rdx, [rsp+348h+var_280]
0x1800d0c21  mov     rcx, cs:__imp__o_towlower
0x1800d0c28  mov     [rsp+348h+phkResult], rcx
0x1800d0c2d  mov     r8, [rax]
0x1800d0c30  lea     rcx, [rsp+348h+Src]
0x1800d0c38  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x1800d0c3d  lea     rdx, [rsp+348h+var_280]
0x1800d0c45  lea     rcx, [rsp+348h+var_2A0]
0x1800d0c4d  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800d0c52  jmp     short loc_1800D0C6E
0x1800d0c54  inc     r8
0x1800d0c57  cmp     [rbx+r8*2], r12w
0x1800d0c5c  jnz     short loc_1800D0C54
0x1800d0c5e  mov     rdx, rbx
0x1800d0c61  lea     rcx, [rsp+348h+var_2A0]
0x1800d0c69  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800d0c6e  lea     rdx, [rsp+348h+var_2E0]
0x1800d0c73  lea     rcx, [rsp+348h+var_2A0]
0x1800d0c7b  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1800d0c80  mov     rax, [rax]
0x1800d0c83  lea     rcx, [rsp+348h+var_2A0]
0x1800d0c8b  cmp     [rsp+348h+var_288], 7
0x1800d0c94  cmova   rcx, [rsp+348h+var_2A0]
0x1800d0c9d  jmp     short loc_1800D0CAE
0x1800d0c9f  cmp     word ptr [rcx], 2Fh ; '/'
0x1800d0ca3  jnz     short loc_1800D0CAA
0x1800d0ca5  mov     word ptr [rcx], 5Ch ; '\'
0x1800d0caa  add     rcx, 2
0x1800d0cae  cmp     rcx, rax
0x1800d0cb1  jnz     short loc_1800D0C9F
0x1800d0cb3  mov     [rsp+348h+lpSubKey], r12
0x1800d0cb8  mov     rcx, r13
0x1800d0cbb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800d0cc0  mov     [rsp+348h+var_2F8], r12
0x1800d0cc5  mov     [rsp+348h+var_2F0], 1
0x1800d0cca  test    al, al
0x1800d0ccc  jz      short loc_1800D0D28
0x1800d0cce  lea     rax, [rsp+348h+var_2A0]
0x1800d0cd6  cmp     [rsp+348h+var_288], 7
0x1800d0cdf  cmova   rax, [rsp+348h+var_2A0]
0x1800d0ce8  lea     rcx, [rsp+348h+lpSubKey]
0x1800d0ced  mov     [rsp+348h+var_300], rcx
0x1800d0cf2  mov     [rsp+348h+phkResult], rax
0x1800d0cf7  mov     r9, r14
0x1800d0cfa  mov     r8d, 2
0x1800d0d00  mov     rdx, cs:qword_18018A5F0
0x1800d0d07  lea     rcx, [rsp+348h+var_2F8]
0x1800d0d0c  call    DCStringCchPrintfAllStrings
0x1800d0d11  mov     ebx, eax
0x1800d0d13  lea     rcx, [rsp+348h+var_300]
0x1800d0d18  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800d0d1d  test    ebx, ebx
0x1800d0d1f  jns     short loc_1800D0D94
0x1800d0d21  mov     edx, 10Ah
0x1800d0d26  jmp     short loc_1800D0D78
0x1800d0d28  lea     r9, [rsp+348h+var_2A0]
0x1800d0d30  cmp     [rsp+348h+var_288], 7
0x1800d0d39  cmova   r9, [rsp+348h+var_2A0]
0x1800d0d42  lea     rax, [rsp+348h+lpSubKey]
0x1800d0d47  mov     [rsp+348h+var_300], rax
0x1800d0d4c  mov     r8d, 1
0x1800d0d52  mov     rdx, cs:qword_18018A5E8
0x1800d0d59  lea     rcx, [rsp+348h+var_2F8]
0x1800d0d5e  call    DCStringCchPrintfAllStrings
0x1800d0d63  mov     ebx, eax
0x1800d0d65  lea     rcx, [rsp+348h+var_300]
0x1800d0d6a  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800d0d6f  test    ebx, ebx
0x1800d0d71  jns     short loc_1800D0D94
0x1800d0d73  mov     edx, 112h; void *
0x1800d0d78  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d0d7f  mov     r9d, ebx; char *
0x1800d0d82  mov     rcx, [rsp+348h]; this
0x1800d0d8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0d8f  jmp     loc_1800D13EA
0x1800d0d94  mov     [rsp+348h+var_318], r12
0x1800d0d99  lea     rcx, [rsp+348h+var_2C0]
0x1800d0da1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800d0da6  nop
0x1800d0da7  mov     rcx, r13
0x1800d0daa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800d0daf  test    al, al
0x1800d0db1  jz      loc_1800D0E88
0x1800d0db7  lea     r8, [rsp+348h+var_280]
0x1800d0dbf  cmp     [rsp+348h+var_268], 7
0x1800d0dc8  cmova   r8, [rsp+348h+var_280]
0x1800d0dd1  lea     rax, [rsp+348h+var_2C0]
0x1800d0dd9  mov     [rsp+348h+var_320], rax
0x1800d0dde  lea     rax, [rsp+348h+var_318]
0x1800d0de3  mov     [rsp+348h+phkResult], rax; int
0x1800d0de8  mov     r9, r15
0x1800d0deb  mov     rdx, r14
0x1800d0dee  call    ?GetPMCspRedirectedRegistryPath@DCRegistryTrackingStore@@AEAAJPEBG00AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DCRegistryTrackingStore::GetPMCspRedirectedRegistryPath(ushort const *,ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,std::wstring &)
0x1800d0df3  mov     ebx, eax
0x1800d0df5  test    eax, eax
0x1800d0df7  jns     short loc_1800D0E1A
0x1800d0df9  mov     r9d, eax; char *
0x1800d0dfc  mov     edx, 119h; void *
0x1800d0e01  mov     rcx, [rsp+348h]; this
0x1800d0e09  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d0e10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0e15  jmp     loc_1800D13D1
0x1800d0e1a  cmp     [rsp+348h+var_318], r12
0x1800d0e1f  jnz     loc_1800D0EEB
0x1800d0e25  lea     rax, [rsp+348h+var_318]
0x1800d0e2a  mov     [rsp+348h+var_300], rax
0x1800d0e2f  mov     [rsp+348h+var_2F8], r12
0x1800d0e34  mov     [rsp+348h+var_2F0], 1
0x1800d0e39  lea     rax, [rsp+348h+var_2F8]
0x1800d0e3e  mov     [rsp+348h+phkResult], rax; phkResult
0x1800d0e43  mov     r9d, 20119h; samDesired
0x1800d0e49  xor     r8d, r8d; ulOptions
0x1800d0e4c  mov     rdx, [rsp+348h+lpSubKey]; lpSubKey
0x1800d0e51  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d0e58  call    cs:__imp_RegOpenKeyExW
0x1800d0e5e  mov     ebx, eax
0x1800d0e60  test    eax, eax
0x1800d0e62  jle     short loc_1800D0E6D
0x1800d0e64  movzx   ebx, ax
0x1800d0e67  or      ebx, 80070000h
0x1800d0e6d  lea     rcx, [rsp+348h+var_300]
0x1800d0e72  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800d0e77  test    ebx, ebx
0x1800d0e79  jns     short loc_1800D0EEB
0x1800d0e7b  mov     r9d, ebx
0x1800d0e7e  mov     edx, 122h
0x1800d0e83  jmp     loc_1800D0E01
0x1800d0e88  lea     rax, [rsp+348h+var_318]
0x1800d0e8d  mov     [rsp+348h+var_300], rax
0x1800d0e92  mov     [rsp+348h+var_2F8], r12
0x1800d0e97  mov     [rsp+348h+var_2F0], 1
0x1800d0e9c  lea     rax, [rsp+348h+var_2F8]
0x1800d0ea1  mov     [rsp+348h+phkResult], rax; phkResult
0x1800d0ea6  mov     r9d, 20119h; samDesired
0x1800d0eac  xor     r8d, r8d; ulOptions
0x1800d0eaf  mov     rdx, [rsp+348h+lpSubKey]; lpSubKey
0x1800d0eb4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d0ebb  call    cs:__imp_RegOpenKeyExW
0x1800d0ec1  mov     ebx, eax
0x1800d0ec3  test    eax, eax
0x1800d0ec5  jle     short loc_1800D0ED0
0x1800d0ec7  movzx   ebx, ax
0x1800d0eca  or      ebx, 80070000h
0x1800d0ed0  lea     rcx, [rsp+348h+var_300]
0x1800d0ed5  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800d0eda  test    ebx, ebx
0x1800d0edc  jns     short loc_1800D0EEB
0x1800d0ede  mov     r9d, ebx
0x1800d0ee1  mov     edx, 12Ch
0x1800d0ee6  jmp     loc_1800D0E01
0x1800d0eeb  mov     [rsp+348h+var_310], r12
0x1800d0ef0  lea     rax, [rsp+348h+var_310]
0x1800d0ef5  mov     [rsp+348h+var_300], rax
0x1800d0efa  mov     [rsp+348h+var_2F8], r12
0x1800d0eff  mov     [rsp+348h+var_2F0], 1
0x1800d0f04  lea     r9, [rsp+348h+var_2F8]; unsigned __int16 **
0x1800d0f09  lea     r8, aAuthorityid; "authorityId"
0x1800d0f10  xor     edx, edx; unsigned __int16 *
0x1800d0f12  mov     rcx, [rsp+348h+var_318]; HKEY
0x1800d0f17  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800d0f1c  mov     ebx, eax
0x1800d0f1e  lea     rcx, [rsp+348h+var_300]
0x1800d0f23  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800d0f28  test    ebx, ebx
0x1800d0f2a  jns     short loc_1800D0F4D
0x1800d0f2c  mov     rcx, [rsp+348h]; this
0x1800d0f34  mov     r9d, ebx; char *
0x1800d0f37  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d0f3e  mov     edx, 131h; void *
0x1800d0f43  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0f48  jmp     loc_1800D13C6
0x1800d0f4d  mov     qword ptr [rsp+348h+var_308], r12
0x1800d0f52  lea     rax, [rsp+348h+var_308]
0x1800d0f57  mov     [rsp+348h+var_300], rax
0x1800d0f5c  mov     [rsp+348h+var_2F8], r12
0x1800d0f61  mov     [rsp+348h+var_2F0], 1
0x1800d0f66  lea     r9, [rsp+348h+var_2F8]; unsigned __int16 **
0x1800d0f6b  lea     r8, aDocumentid_0; "documentId"
0x1800d0f72  xor     edx, edx; unsigned __int16 *
0x1800d0f74  mov     rcx, [rsp+348h+var_318]; HKEY
0x1800d0f79  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800d0f7e  mov     ebx, eax
0x1800d0f80  lea     rcx, [rsp+348h+var_300]
0x1800d0f85  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800d0f8a  test    ebx, ebx
0x1800d0f8c  jns     short loc_1800D0FAF
0x1800d0f8e  mov     edx, 134h; void *
0x1800d0f93  mov     r9d, ebx; char *
0x1800d0f96  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d0f9d  mov     rcx, [rsp+348h]; this
0x1800d0fa5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d0faa  jmp     loc_1800D13BB
0x1800d0faf  mov     rax, qword ptr [rsp+348h+var_308]
0x1800d0fb4  mov     [rsp+348h+phkResult], rax; int
0x1800d0fb9  mov     r9, [rsp+348h+var_310]
0x1800d0fbe  lea     r8, aSS; "%s\\%s"
0x1800d0fc5  mov     edx, 104h; unsigned __int64
0x1800d0fca  lea     rcx, [rsp+348h+var_258]; unsigned __int16 *
0x1800d0fd2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800d0fd7  mov     ebx, eax
0x1800d0fd9  test    eax, eax
0x1800d0fdb  jns     short loc_1800D0FE7
0x1800d0fdd  mov     r9d, eax
0x1800d0fe0  mov     edx, 13Ch
0x1800d0fe5  jmp     short loc_1800D0F96
0x1800d0fe7  mov     r9, rsi; unsigned int *
0x1800d0fea  lea     r8, aTypestored; "typeStored"
0x1800d0ff1  lea     rdx, [rsp+348h+var_258]; unsigned __int16 *
0x1800d0ff9  mov     rcx, [rsp+348h+var_318]; HKEY
0x1800d0ffe  call    ?DCCDNUtil_GetRegistryDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; DCCDNUtil_GetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x1800d1003  mov     ebx, eax
0x1800d1005  test    eax, eax
0x1800d1007  jns     short loc_1800D1013
0x1800d1009  mov     r9d, eax
0x1800d100c  mov     edx, 13Eh
0x1800d1011  jmp     short loc_1800D0F96
0x1800d1013  mov     ecx, [rsi]
0x1800d1015  sub     ecx, 1
0x1800d1018  jz      loc_1800D1323
0x1800d101e  sub     ecx, 2
0x1800d1021  jz      loc_1800D1262
0x1800d1027  sub     ecx, 1
0x1800d102a  jz      loc_1800D121B
0x1800d1030  sub     ecx, 2
0x1800d1033  jz      short loc_1800D1052
0x1800d1035  sub     ecx, 1
0x1800d1038  jz      loc_1800D1154
  ... truncated ...
```
