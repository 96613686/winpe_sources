# DCRegistryTrackingStore::DeleteAuthority(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,bool *)

- ea: `0x1800cedd0`
- end: `0x1800cf72d`
- name: `?DeleteAuthority@DCRegistryTrackingStore@@UEAAJPEBG0000PEA_N@Z`
- size: `2397`
- prototype: `int(DCRegistryTrackingStore *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, bool *)`
- caller_count: `0`
- callee_count: `22`
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
- `0x1800600bc`
- `0x1800ce974`
- `0x1800cedd0`
- `0x1800d14c4`
- `0x1800d2ecc`
- `0x1801006c8`
- `0x180100ad8`
- `0x180100e3c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cf4aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cf4bf`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cf4aa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800cf4bf`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800cef24`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800cf253`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800cf3a3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800cf253`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800cf3a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800cf361`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800cf361`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cf171`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cf212`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cf2c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cf171`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cf212`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cf2c7`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800cf4d7`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800cf4fb`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800cf4d7`
- `api-ms-win-core-registry-l1-1-1!RegDeleteKeyValueW` at `0x1800cf4fb`

## string_xrefs

- `0x1800cf564`: `registry`
- `0x1800cf583`: `regRedirectPathRefCount`
- `0x1800cf5bc`: `regRedirectPathRefCount`
- `0x1800cee3d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800cf08b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800cf120`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800cf2fc`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800cf42d`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800cf5e5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DCRegistryTrackingStore::DeleteAuthority(
        DCRegistryTrackingStore *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        bool *a7)
{
  __int64 v11; // rdx
  signed int RegistryString; // ebx
  char IsEnabled; // al
  __int64 v15; // r8
  __int64 v16; // r8
  char **v17; // r9
  _QWORD *v18; // rax
  int v19; // r9d
  char **v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  unsigned __int16 **v23; // rax
  unsigned __int16 **v24; // rcx
  unsigned __int16 **v25; // rax
  __int64 v26; // rdx
  unsigned __int16 **v27; // r9
  __int64 v28; // rcx
  char **v29; // r8
  int PMCspRedirectedRegistryPath; // eax
  __int64 v31; // rdx
  unsigned __int64 v32; // r9
  LSTATUS v33; // eax
  LSTATUS v34; // eax
  LSTATUS v35; // eax
  LSTATUS v36; // eax
  __int64 v37; // rdx
  LSTATUS v38; // eax
  LSTATUS v39; // eax
  unsigned __int64 v40; // r9
  __int64 v41; // rdx
  LSTATUS RegistryDWORD; // eax
  DCRegistryTrackingStore *v43; // rcx
  const unsigned __int16 *v44; // r8
  const unsigned __int16 *v45; // r8
  int phkResult; // [rsp+20h] [rbp-348h]
  int phkResulta; // [rsp+20h] [rbp-348h]
  HKEY *phkResultb; // [rsp+20h] [rbp-348h]
  HKEY hKey; // [rsp+60h] [rbp-308h] BYREF
  __int64 *p_lpSubKey; // [rsp+68h] [rbp-300h] BYREF
  HKEY v51; // [rsp+70h] [rbp-2F8h] BYREF
  char v52; // [rsp+78h] [rbp-2F0h]
  __int64 v53; // [rsp+80h] [rbp-2E8h] BYREF
  HKEY v54; // [rsp+88h] [rbp-2E0h] BYREF
  __int64 v55; // [rsp+90h] [rbp-2D8h] BYREF
  LPCWSTR lpSubKey; // [rsp+98h] [rbp-2D0h] BYREF
  DWORD cSubKeys; // [rsp+A0h] [rbp-2C8h] BYREF
  unsigned int v58; // [rsp+A8h] [rbp-2C0h] BYREF
  unsigned __int16 *v59[3]; // [rsp+B0h] [rbp-2B8h] BYREF
  unsigned __int64 v60; // [rsp+C8h] [rbp-2A0h]
  unsigned __int16 *v61[4]; // [rsp+D0h] [rbp-298h] BYREF
  char *v62[3]; // [rsp+F0h] [rbp-278h] BYREF
  unsigned __int64 v63; // [rsp+108h] [rbp-260h]
  WCHAR SubKey[264]; // [rsp+110h] [rbp-258h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+368h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl)
    && !a2 )
  {
    v11 = 507;
LABEL_4:
    RegistryString = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)0x80070057LL,
      phkResulta);
    return (unsigned int)RegistryString;
  }
  if ( !a3 )
  {
    v11 = 509;
    goto LABEL_4;
  }
  if ( !a4 )
  {
    v11 = 510;
    goto LABEL_4;
  }
  if ( !a5 )
  {
    v11 = 511;
    goto LABEL_4;
  }
  if ( !a6 )
  {
    v11 = 512;
    goto LABEL_4;
  }
  if ( a7 )
    *a7 = 0;
  std::wstring::wstring((__int64)v62);
  std::wstring::wstring((__int64)v59);
  try
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl);
    v15 = -1;
    if ( IsEnabled )
    {
      do
        ++v15;
      while ( a3[v15] );
      std::wstring::_Assign<unsigned short>(v62, a3, (char *)v15);
      v17 = v62;
      if ( v63 > 7 )
        v17 = (char **)v62[0];
      v18 = (_QWORD *)std::wstring::end(v62, &v54, v16, v17);
      v20 = v62;
      if ( v63 > 7 )
        LODWORD(v20) = v62[0];
      std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
        (unsigned int)&v58,
        (_DWORD)v20,
        *v18,
        v19,
        *(__int64 *)&_o_towlower);
      std::wstring::operator=(v59, v62);
    }
    else
    {
      do
        ++v15;
      while ( a3[v15] );
      std::wstring::_Assign<unsigned short>((char **)v59, a3, (char *)v15);
    }
    v23 = *(unsigned __int16 ***)std::wstring::end(v59, &v54, v21, v22);
    v24 = v59;
    if ( v60 > 7 )
      v24 = (unsigned __int16 **)v59[0];
    while ( v24 != v23 )
    {
      if ( *(_WORD *)v24 == 47 )
        *(_WORD *)v24 = 92;
      v24 = (unsigned __int16 **)((char *)v24 + 2);
    }
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x218,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)0x8007000ELL,
      phkResult);
    std::wstring::_Tidy_deallocate(v59);
    std::wstring::_Tidy_deallocate(v62);
    return 2147942414LL;
  }
  lpSubKey = 0;
  v51 = 0;
  v52 = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
  {
    v25 = v59;
    if ( v60 > 7 )
      v25 = (unsigned __int16 **)v59[0];
    p_lpSubKey = (__int64 *)&lpSubKey;
    RegistryString = DCStringCchPrintfAllStrings(&v51, qword_18018A5F0, 2, a2, v25);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
    if ( RegistryString < 0 )
    {
      v26 = 547;
LABEL_43:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v26,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)(unsigned int)RegistryString,
        phkResulta);
LABEL_107:
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
      std::wstring::_Tidy_deallocate(v59);
      std::wstring::_Tidy_deallocate(v62);
      return (unsigned int)RegistryString;
    }
  }
  else
  {
    v27 = v59;
    if ( v60 > 7 )
      v27 = (unsigned __int16 **)v59[0];
    p_lpSubKey = (__int64 *)&lpSubKey;
    RegistryString = DCStringCchPrintfAllStrings(&v51, qword_18018A5E8, 1, v27);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
    if ( RegistryString < 0 )
    {
      v26 = 555;
      goto LABEL_43;
    }
  }
  hKey = 0;
  std::wstring::wstring((__int64)v61);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
  {
    v29 = v62;
    if ( v63 > 7 )
      v29 = (char **)v62[0];
    phkResultb = &hKey;
    PMCspRedirectedRegistryPath = DCRegistryTrackingStore::GetPMCspRedirectedRegistryPath(v28, a2, v29, a4);
    RegistryString = PMCspRedirectedRegistryPath;
    if ( PMCspRedirectedRegistryPath < 0 )
    {
      v31 = 562;
LABEL_49:
      v32 = (unsigned int)PMCspRedirectedRegistryPath;
LABEL_50:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v31,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)v32,
        (int)phkResultb);
LABEL_106:
      std::wstring::_Tidy_deallocate(v61);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_107;
    }
    if ( !hKey )
    {
      p_lpSubKey = (__int64 *)&hKey;
      v51 = 0;
      v52 = 1;
      v33 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x3011Fu, &v51);
      RegistryString = v33;
      if ( v33 > 0 )
        RegistryString = (unsigned __int16)v33 | 0x80070000;
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
      if ( RegistryString < 0 )
      {
        v32 = (unsigned int)RegistryString;
        v31 = 571;
        goto LABEL_50;
      }
    }
  }
  else
  {
    p_lpSubKey = (__int64 *)&hKey;
    v51 = 0;
    v52 = 1;
    v34 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x3011Fu, &v51);
    RegistryString = v34;
    if ( v34 > 0 )
      RegistryString = (unsigned __int16)v34 | 0x80070000;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
    if ( RegistryString < 0 )
    {
      v32 = (unsigned int)RegistryString;
      v31 = 581;
      goto LABEL_50;
    }
  }
  PMCspRedirectedRegistryPath = StringCchPrintfW(SubKey, 0x104u, L"%s\\%s", a4, a5);
  RegistryString = PMCspRedirectedRegistryPath;
  if ( PMCspRedirectedRegistryPath < 0 )
  {
    v31 = 590;
    goto LABEL_49;
  }
  v35 = RegDeleteTreeW(hKey, SubKey);
  RegistryString = v35;
  if ( v35 > 0 )
    RegistryString = (unsigned __int16)v35 | 0x80070000;
  if ( RegistryString != -2147024894 )
  {
    if ( RegistryString < 0 )
    {
      v32 = (unsigned int)RegistryString;
      v31 = 599;
      goto LABEL_50;
    }
    v54 = 0;
    p_lpSubKey = (__int64 *)&v54;
    v51 = 0;
    v52 = 1;
    v36 = RegOpenKeyExW(hKey, a4, 0, 0x30119u, &v51);
    RegistryString = v36;
    if ( v36 > 0 )
      RegistryString = (unsigned __int16)v36 | 0x80070000;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
    if ( RegistryString < 0 )
    {
      v37 = 607;
LABEL_71:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v37,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)(unsigned int)RegistryString,
        (int)phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
      goto LABEL_106;
    }
    cSubKeys = 0;
    v38 = RegQueryInfoKeyW(v54, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    RegistryString = v38;
    if ( v38 > 0 )
      RegistryString = (unsigned __int16)v38 | 0x80070000;
    if ( RegistryString < 0 )
    {
      v37 = 611;
      goto LABEL_71;
    }
    if ( !cSubKeys )
    {
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(&v54);
      v39 = RegDeleteTreeW(hKey, a4);
      RegistryString = v39;
      if ( v39 > 0 )
        RegistryString = (unsigned __int16)v39 | 0x80070000;
      if ( RegistryString < 0 )
      {
        v37 = 616;
        goto LABEL_71;
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v54);
  }
  v53 = 0;
  p_lpSubKey = &v53;
  v51 = 0;
  v52 = 1;
  RegistryString = DCCDNUtil_GetRegistryString(hKey, 0, L"authorityId", (unsigned __int16 **)&v51);
  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
  if ( RegistryString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x26D,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)(unsigned int)RegistryString,
      (int)phkResultb);
LABEL_105:
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v53);
    goto LABEL_106;
  }
  v55 = 0;
  p_lpSubKey = &v55;
  v51 = 0;
  v52 = 1;
  RegistryString = DCCDNUtil_GetRegistryString(hKey, 0, L"documentId", (unsigned __int16 **)&v51);
  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
  if ( RegistryString < 0 )
  {
    v40 = (unsigned int)RegistryString;
    v41 = 624;
LABEL_104:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)v40,
      (int)phkResultb);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v55);
    goto LABEL_105;
  }
  if ( !(unsigned int)_o__wcsicmp(v53, a4) && !(unsigned int)_o__wcsicmp(v55, a5) )
  {
    RegistryDWORD = RegDeleteKeyValueW(hKey, 0, L"authorityId");
    RegistryString = RegistryDWORD;
    if ( RegistryDWORD < 0 )
    {
      v41 = 629;
LABEL_103:
      v40 = (unsigned int)RegistryDWORD;
      goto LABEL_104;
    }
    RegistryDWORD = RegDeleteKeyValueW(hKey, 0, L"documentId");
    RegistryString = RegistryDWORD;
    if ( RegistryDWORD < 0 )
    {
      v41 = 630;
      goto LABEL_103;
    }
    if ( a7 )
      *a7 = 1;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(&hKey);
    goto LABEL_109;
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(&hKey);
  v43 = this;
  if ( !v61[2] )
  {
LABEL_110:
    v45 = (const unsigned __int16 *)v59;
    if ( v60 > 7 )
      v45 = v59[0];
    DCRegistryTrackingStore::RegDeleteTreeRecusively(v43, a2, v45);
    goto LABEL_113;
  }
  v44 = (const unsigned __int16 *)v61;
  if ( v61[3] > (unsigned __int16 *)7 )
    v44 = v61[0];
  DCRegistryTrackingStore::RegDeleteTreeRecusively(this, L"registry", v44);
  v58 = 0;
  RegistryDWORD = DCCDNUtil_GetRegistryDWORD(HKEY_LOCAL_MACHINE, lpSubKey, L"regRedirectPathRefCount", &v58);
  RegistryString = RegistryDWORD;
  if ( RegistryDWORD < 0 )
  {
    v41 = 653;
    goto LABEL_103;
  }
  if ( v58 <= 1 )
  {
LABEL_109:
    v43 = this;
    goto LABEL_110;
  }
  RegistryDWORD = DCCDNUtil_SetRegistryDWORD(HKEY_LOCAL_MACHINE, lpSubKey, L"regRedirectPathRefCount", v58 - 1);
  RegistryString = RegistryDWORD;
  if ( RegistryDWORD < 0 )
  {
    v41 = 661;
    goto LABEL_103;
  }
LABEL_113:
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v55);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v53);
  std::wstring::_Tidy_deallocate(v61);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
  std::wstring::_Tidy_deallocate(v59);
  std::wstring::_Tidy_deallocate(v62);
  return 0;
}

```

## disassembly

```asm
0x1800cedd0  push    rbx
0x1800cedd2  push    rsi
0x1800cedd3  push    rdi
0x1800cedd4  push    r12
0x1800cedd6  push    r13
0x1800cedd8  push    r14
0x1800cedda  push    r15
0x1800ceddc  sub     rsp, 330h
0x1800cede3  mov     rax, cs:__security_cookie
0x1800cedea  xor     rax, rsp
0x1800ceded  mov     [rsp+368h+var_48], rax
0x1800cedf5  mov     rsi, r9
0x1800cedf8  mov     rbx, r8
0x1800cedfb  mov     r14, rdx
0x1800cedfe  mov     r12, rcx
0x1800cee01  mov     r13, [rsp+368h+arg_20]
0x1800cee09  mov     r15, [rsp+368h+arg_30]
0x1800cee11  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800cee18  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800cee1d  xor     edi, edi
0x1800cee1f  test    al, al
0x1800cee21  jz      short loc_1800CEE50
0x1800cee23  test    r14, r14
0x1800cee26  jnz     short loc_1800CEE50
0x1800cee28  mov     edx, 1FBh; void *
0x1800cee2d  mov     ebx, 80070057h
0x1800cee32  mov     rcx, [rsp+368h]; this
0x1800cee3a  mov     r9d, ebx; char *
0x1800cee3d  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800cee44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cee49  mov     eax, ebx
0x1800cee4b  jmp     loc_1800CF70A
0x1800cee50  test    rbx, rbx
0x1800cee53  jnz     short loc_1800CEE5C
0x1800cee55  mov     edx, 1FDh
0x1800cee5a  jmp     short loc_1800CEE2D
0x1800cee5c  test    rsi, rsi
0x1800cee5f  jnz     short loc_1800CEE68
0x1800cee61  mov     edx, 1FEh
0x1800cee66  jmp     short loc_1800CEE2D
0x1800cee68  test    r13, r13
0x1800cee6b  jnz     short loc_1800CEE74
0x1800cee6d  mov     edx, 1FFh
0x1800cee72  jmp     short loc_1800CEE2D
0x1800cee74  cmp     [rsp+368h+arg_28], rdi
0x1800cee7c  jnz     short loc_1800CEE85
0x1800cee7e  mov     edx, 200h
0x1800cee83  jmp     short loc_1800CEE2D
0x1800cee85  test    r15, r15
0x1800cee88  jz      short loc_1800CEE8D
0x1800cee8a  mov     [r15], dil
0x1800cee8d  lea     rcx, [rsp+368h+var_278]
0x1800cee95  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cee9a  nop
0x1800cee9b  lea     rcx, [rsp+368h+var_2B8]
0x1800ceea3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800ceea8  nop
0x1800ceea9  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800ceeb0  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800ceeb5  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800ceeb9  test    al, al
0x1800ceebb  jz      loc_1800CEF57
0x1800ceec1  inc     r8
0x1800ceec4  cmp     [rbx+r8*2], di
0x1800ceec9  jnz     short loc_1800CEEC1
0x1800ceecb  mov     rdx, rbx
0x1800ceece  lea     rcx, [rsp+368h+var_278]
0x1800ceed6  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800ceedb  lea     r9, [rsp+368h+var_278]
0x1800ceee3  cmp     [rsp+368h+var_260], 7
0x1800ceeec  cmova   r9, [rsp+368h+var_278]
0x1800ceef5  lea     rdx, [rsp+368h+var_2E0]
0x1800ceefd  lea     rcx, [rsp+368h+var_278]
0x1800cef05  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1800cef0a  lea     rdx, [rsp+368h+var_278]
0x1800cef12  cmp     [rsp+368h+var_260], 7
0x1800cef1b  cmova   rdx, [rsp+368h+var_278]
0x1800cef24  mov     rcx, cs:__imp__o_towlower
0x1800cef2b  mov     [rsp+368h+phkResult], rcx
0x1800cef30  mov     r8, [rax]
0x1800cef33  lea     rcx, [rsp+368h+var_2C0]
0x1800cef3b  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x1800cef40  lea     rdx, [rsp+368h+var_278]
0x1800cef48  lea     rcx, [rsp+368h+var_2B8]
0x1800cef50  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800cef55  jmp     short loc_1800CEF71
0x1800cef57  inc     r8
0x1800cef5a  cmp     [rbx+r8*2], di
0x1800cef5f  jnz     short loc_1800CEF57
0x1800cef61  mov     rdx, rbx
0x1800cef64  lea     rcx, [rsp+368h+var_2B8]
0x1800cef6c  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800cef71  lea     rdx, [rsp+368h+var_2E0]
0x1800cef79  lea     rcx, [rsp+368h+var_2B8]
0x1800cef81  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1800cef86  mov     rax, [rax]
0x1800cef89  lea     rcx, [rsp+368h+var_2B8]
0x1800cef91  cmp     [rsp+368h+var_2A0], 7
0x1800cef9a  cmova   rcx, [rsp+368h+var_2B8]
0x1800cefa3  jmp     short loc_1800CEFB4
0x1800cefa5  cmp     word ptr [rcx], 2Fh ; '/'
0x1800cefa9  jnz     short loc_1800CEFB0
0x1800cefab  mov     word ptr [rcx], 5Ch ; '\'
0x1800cefb0  add     rcx, 2
0x1800cefb4  cmp     rcx, rax
0x1800cefb7  jnz     short loc_1800CEFA5
0x1800cefb9  mov     [rsp+368h+lpSubKey], rdi
0x1800cefc1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800cefc8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800cefcd  mov     [rsp+368h+var_2F8], rdi
0x1800cefd2  mov     [rsp+368h+var_2F0], 1
0x1800cefd7  test    al, al
0x1800cefd9  jz      short loc_1800CF038
0x1800cefdb  lea     rax, [rsp+368h+var_2B8]
0x1800cefe3  cmp     [rsp+368h+var_2A0], 7
0x1800cefec  cmova   rax, [rsp+368h+var_2B8]
0x1800ceff5  lea     rcx, [rsp+368h+lpSubKey]
0x1800ceffd  mov     [rsp+368h+var_300], rcx
0x1800cf002  mov     [rsp+368h+phkResult], rax
0x1800cf007  mov     r9, r14
0x1800cf00a  mov     r8d, 2
0x1800cf010  mov     rdx, cs:qword_18018A5F0
0x1800cf017  lea     rcx, [rsp+368h+var_2F8]
0x1800cf01c  call    DCStringCchPrintfAllStrings
0x1800cf021  mov     ebx, eax
0x1800cf023  lea     rcx, [rsp+368h+var_300]
0x1800cf028  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800cf02d  test    ebx, ebx
0x1800cf02f  jns     short loc_1800CF0A7
0x1800cf031  mov     edx, 223h
0x1800cf036  jmp     short loc_1800CF08B
0x1800cf038  lea     r9, [rsp+368h+var_2B8]
0x1800cf040  cmp     [rsp+368h+var_2A0], 7
0x1800cf049  cmova   r9, [rsp+368h+var_2B8]
0x1800cf052  lea     rax, [rsp+368h+lpSubKey]
0x1800cf05a  mov     [rsp+368h+var_300], rax
0x1800cf05f  mov     r8d, 1
0x1800cf065  mov     rdx, cs:qword_18018A5E8
0x1800cf06c  lea     rcx, [rsp+368h+var_2F8]
0x1800cf071  call    DCStringCchPrintfAllStrings
0x1800cf076  mov     ebx, eax
0x1800cf078  lea     rcx, [rsp+368h+var_300]
0x1800cf07d  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800cf082  test    ebx, ebx
0x1800cf084  jns     short loc_1800CF0A7
0x1800cf086  mov     edx, 22Bh; void *
0x1800cf08b  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800cf092  mov     r9d, ebx; char *
0x1800cf095  mov     rcx, [rsp+368h]; this
0x1800cf09d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cf0a2  jmp     loc_1800CF62F
0x1800cf0a7  mov     [rsp+368h+hKey], rdi
0x1800cf0ac  lea     rcx, [rsp+368h+var_298]
0x1800cf0b4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cf0b9  nop
0x1800cf0ba  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800cf0c1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800cf0c6  test    al, al
0x1800cf0c8  jz      loc_1800CF1D9
0x1800cf0ce  lea     r8, [rsp+368h+var_278]
0x1800cf0d6  cmp     [rsp+368h+var_260], 7
0x1800cf0df  cmova   r8, [rsp+368h+var_278]
0x1800cf0e8  lea     rax, [rsp+368h+var_298]
0x1800cf0f0  mov     [rsp+368h+lpcbMaxSubKeyLen], rax
0x1800cf0f5  lea     rax, [rsp+368h+hKey]
0x1800cf0fa  mov     [rsp+368h+phkResult], rax; int
0x1800cf0ff  mov     r9, rsi
0x1800cf102  mov     rdx, r14
0x1800cf105  call    ?GetPMCspRedirectedRegistryPath@DCRegistryTrackingStore@@AEAAJPEBG00AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DCRegistryTrackingStore::GetPMCspRedirectedRegistryPath(ushort const *,ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,std::wstring &)
0x1800cf10a  mov     ebx, eax
0x1800cf10c  test    eax, eax
0x1800cf10e  jns     short loc_1800CF131
0x1800cf110  mov     edx, 232h; void *
0x1800cf115  mov     r9d, eax; char *
0x1800cf118  mov     rcx, [rsp+368h]; this
0x1800cf120  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800cf127  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cf12c  jmp     loc_1800CF616
0x1800cf131  cmp     [rsp+368h+hKey], rdi
0x1800cf136  jnz     short loc_1800CF1A1
0x1800cf138  lea     rax, [rsp+368h+hKey]
0x1800cf13d  mov     [rsp+368h+var_300], rax
0x1800cf142  mov     [rsp+368h+var_2F8], rdi
0x1800cf147  mov     [rsp+368h+var_2F0], 1
0x1800cf14c  lea     rax, [rsp+368h+var_2F8]
0x1800cf151  mov     [rsp+368h+phkResult], rax; phkResult
0x1800cf156  mov     r9d, 3011Fh; samDesired
0x1800cf15c  xor     r8d, r8d; ulOptions
0x1800cf15f  mov     rdx, [rsp+368h+lpSubKey]; lpSubKey
0x1800cf167  mov     rdi, 0FFFFFFFF80000002h
0x1800cf16e  mov     rcx, rdi; hKey
0x1800cf171  call    cs:__imp_RegOpenKeyExW
0x1800cf177  mov     ebx, eax
0x1800cf179  test    eax, eax
0x1800cf17b  jle     short loc_1800CF186
0x1800cf17d  movzx   ebx, ax
0x1800cf180  or      ebx, 80070000h
0x1800cf186  lea     rcx, [rsp+368h+var_300]
0x1800cf18b  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800cf190  test    ebx, ebx
0x1800cf192  jns     short loc_1800CF1A8
0x1800cf194  mov     r9d, ebx
0x1800cf197  mov     edx, 23Bh
0x1800cf19c  jmp     loc_1800CF118
0x1800cf1a1  mov     rdi, 0FFFFFFFF80000002h
0x1800cf1a8  mov     [rsp+368h+phkResult], r13
0x1800cf1ad  mov     r9, rsi
0x1800cf1b0  lea     r8, aSS; "%s\\%s"
0x1800cf1b7  mov     edx, 104h; unsigned __int64
0x1800cf1bc  lea     rcx, [rsp+368h+SubKey]; unsigned __int16 *
0x1800cf1c4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800cf1c9  mov     ebx, eax
0x1800cf1cb  test    eax, eax
0x1800cf1cd  jns     short loc_1800CF246
0x1800cf1cf  mov     edx, 24Eh
0x1800cf1d4  jmp     loc_1800CF115
0x1800cf1d9  lea     rax, [rsp+368h+hKey]
0x1800cf1de  mov     [rsp+368h+var_300], rax
0x1800cf1e3  mov     [rsp+368h+var_2F8], rdi
0x1800cf1e8  mov     [rsp+368h+var_2F0], 1
0x1800cf1ed  lea     rax, [rsp+368h+var_2F8]
0x1800cf1f2  mov     [rsp+368h+phkResult], rax; phkResult
0x1800cf1f7  mov     r9d, 3011Fh; samDesired
0x1800cf1fd  xor     r8d, r8d; ulOptions
0x1800cf200  mov     rdx, [rsp+368h+lpSubKey]; lpSubKey
0x1800cf208  mov     rdi, 0FFFFFFFF80000002h
0x1800cf20f  mov     rcx, rdi; hKey
0x1800cf212  call    cs:__imp_RegOpenKeyExW
0x1800cf218  mov     ebx, eax
0x1800cf21a  test    eax, eax
0x1800cf21c  jle     short loc_1800CF227
0x1800cf21e  movzx   ebx, ax
0x1800cf221  or      ebx, 80070000h
0x1800cf227  lea     rcx, [rsp+368h+var_300]
0x1800cf22c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800cf231  test    ebx, ebx
0x1800cf233  jns     loc_1800CF1A8
0x1800cf239  mov     r9d, ebx
0x1800cf23c  mov     edx, 245h
0x1800cf241  jmp     loc_1800CF118
0x1800cf246  lea     rdx, [rsp+368h+SubKey]; lpSubKey
0x1800cf24e  mov     rcx, [rsp+368h+hKey]; hKey
0x1800cf253  call    cs:__imp_RegDeleteTreeW
0x1800cf259  mov     ebx, eax
0x1800cf25b  test    eax, eax
0x1800cf25d  jle     short loc_1800CF268
0x1800cf25f  movzx   ebx, ax
0x1800cf262  or      ebx, 80070000h
0x1800cf268  cmp     ebx, 80070002h
0x1800cf26e  jz      loc_1800CF3D3
0x1800cf274  test    ebx, ebx
0x1800cf276  jns     short loc_1800CF285
0x1800cf278  mov     r9d, ebx
0x1800cf27b  mov     edx, 257h
0x1800cf280  jmp     loc_1800CF118
0x1800cf285  mov     [rsp+368h+var_2E0], 0
0x1800cf291  lea     rax, [rsp+368h+var_2E0]
0x1800cf299  mov     [rsp+368h+var_300], rax
0x1800cf29e  mov     [rsp+368h+var_2F8], 0
0x1800cf2a7  mov     [rsp+368h+var_2F0], 1
0x1800cf2ac  lea     rax, [rsp+368h+var_2F8]
0x1800cf2b1  mov     [rsp+368h+phkResult], rax; int
0x1800cf2b6  mov     r9d, 30119h; samDesired
0x1800cf2bc  xor     r8d, r8d; ulOptions
0x1800cf2bf  mov     rdx, rsi; lpSubKey
0x1800cf2c2  mov     rcx, [rsp+368h+hKey]; hKey
0x1800cf2c7  call    cs:__imp_RegOpenKeyExW
0x1800cf2cd  mov     ebx, eax
0x1800cf2cf  test    eax, eax
0x1800cf2d1  jle     short loc_1800CF2DC
0x1800cf2d3  movzx   ebx, ax
0x1800cf2d6  or      ebx, 80070000h
0x1800cf2dc  lea     rcx, [rsp+368h+var_300]
0x1800cf2e1  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800cf2e6  xor     eax, eax
0x1800cf2e8  test    ebx, ebx
0x1800cf2ea  jns     short loc_1800CF31A
0x1800cf2ec  mov     edx, 25Fh; void *
0x1800cf2f1  mov     rcx, [rsp+368h]; this
0x1800cf2f9  mov     r9d, ebx; char *
0x1800cf2fc  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800cf303  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cf308  lea     rcx, [rsp+368h+var_2E0]
0x1800cf310  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800cf315  jmp     loc_1800CF616
0x1800cf31a  mov     [rsp+368h+cSubKeys], eax
0x1800cf321  mov     [rsp+368h+lpftLastWriteTime], rax; lpftLastWriteTime
0x1800cf326  mov     [rsp+368h+lpcbSecurityDescriptor], rax; lpcbSecurityDescriptor
0x1800cf32b  mov     [rsp+368h+lpcbMaxValueLen], rax; lpcbMaxValueLen
0x1800cf330  mov     [rsp+368h+lpcbMaxValueNameLen], rax; lpcbMaxValueNameLen
0x1800cf335  mov     [rsp+368h+lpcValues], rax; lpcValues
0x1800cf33a  mov     [rsp+368h+lpcbMaxClassLen], rax; lpcbMaxClassLen
0x1800cf33f  mov     [rsp+368h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x1800cf344  lea     rax, [rsp+368h+cSubKeys]
0x1800cf34c  mov     [rsp+368h+phkResult], rax; int
0x1800cf351  xor     r9d, r9d; lpReserved
0x1800cf354  xor     r8d, r8d; lpcchClass
0x1800cf357  xor     edx, edx; lpClass
0x1800cf359  mov     rcx, [rsp+368h+var_2E0]; hKey
0x1800cf361  call    cs:__imp_RegQueryInfoKeyW
  ... truncated ...
```
