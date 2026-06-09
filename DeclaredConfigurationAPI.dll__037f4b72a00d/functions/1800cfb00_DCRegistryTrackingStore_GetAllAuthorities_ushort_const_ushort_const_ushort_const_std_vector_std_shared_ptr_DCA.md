# DCRegistryTrackingStore::GetAllAuthorities(ushort const *,ushort const *,ushort const *,std::vector<std::shared_ptr<DCAuthorityInfo>,std::allocator<std::shared_ptr<DCAuthorityInfo>>> *)

- ea: `0x1800cfb00`
- end: `0x1800d03df`
- name: `?GetAllAuthorities@DCRegistryTrackingStore@@UEAAJPEBG00PEAV?$vector@V?$shared_ptr@VDCAuthorityInfo@@@std@@V?$allocator@V?$shared_ptr@VDCAuthorityInfo@@@std@@@2@@std@@@Z`
- size: `2271`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000b9e0`
- `0x18000bebc`
- `0x1800117dc`
- `0x1800143c8`
- `0x180018ac0`
- `0x180018b30`
- `0x180019208`
- `0x180019d38`
- `0x180019f08`
- `0x18001bc98`
- `0x18001c300`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x18001def8`
- `0x18004abf8`
- `0x18004bc88`
- `0x1800600bc`
- `0x1800cfb00`
- `0x1800d14c4`
- `0x180100ad8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800cfc3a`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800cffa8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d00d2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800cffa8`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d00d2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800cfed6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d0071`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800cfed6`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d0071`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cfe5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cff2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d0006`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cfe5e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800cff2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d0006`

## string_xrefs

- `0x1800cfb65`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800cfd33`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d02da`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d0316`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d033a`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall DCRegistryTrackingStore::GetAllAuthorities(
        __int64 a1,
        __int64 a2,
        _WORD *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v8; // rdx
  signed int RegistryString; // ebx
  char IsEnabled; // al
  __int64 v12; // r8
  __int64 v13; // r8
  char **v14; // r9
  _QWORD *v15; // rax
  int v16; // r9d
  char **v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r9
  char **v20; // rax
  char **v21; // rcx
  char v22; // al
  char **v23; // r9
  __int64 v24; // rdx
  char **v25; // rax
  __int64 v26; // rcx
  char **v27; // r8
  int PMCspRedirectedRegistryPath; // eax
  unsigned __int64 v29; // r9
  __int64 v30; // rdx
  LSTATUS v31; // eax
  LSTATUS v32; // eax
  LSTATUS v33; // eax
  DWORD v34; // r12d
  LSTATUS v35; // eax
  LSTATUS v36; // eax
  LSTATUS v37; // eax
  DWORD v38; // r14d
  LSTATUS v39; // eax
  HKEY v40; // rbx
  __int64 v41; // r8
  __int64 v42; // r8
  __int64 v43; // r8
  _QWORD *v44; // rcx
  __int64 v45; // rdx
  int phkResult; // [rsp+20h] [rbp-568h]
  int phkResulta; // [rsp+20h] [rbp-568h]
  HKEY *phkResultb; // [rsp+20h] [rbp-568h]
  int phkResultc; // [rsp+20h] [rbp-568h]
  HKEY hKey; // [rsp+60h] [rbp-528h] BYREF
  HKEY v51; // [rsp+68h] [rbp-520h] BYREF
  void *p_lpSubKey; // [rsp+70h] [rbp-518h] BYREF
  HKEY v53; // [rsp+78h] [rbp-510h] BYREF
  char v54; // [rsp+80h] [rbp-508h]
  DWORD cchName; // [rsp+88h] [rbp-500h] BYREF
  DWORD v56; // [rsp+8Ch] [rbp-4FCh] BYREF
  DWORD cSubKeys; // [rsp+90h] [rbp-4F8h] BYREF
  LPCWSTR lpSubKey; // [rsp+98h] [rbp-4F0h] BYREF
  _WORD *v59; // [rsp+A0h] [rbp-4E8h] BYREF
  int v60; // [rsp+A8h] [rbp-4E0h]
  HKEY *v61; // [rsp+B0h] [rbp-4D8h] BYREF
  HKEY v62; // [rsp+B8h] [rbp-4D0h] BYREF
  char v63; // [rsp+C0h] [rbp-4C8h]
  HKEY v64; // [rsp+C8h] [rbp-4C0h]
  char *v65[3]; // [rsp+D0h] [rbp-4B8h] BYREF
  unsigned __int64 v66; // [rsp+E8h] [rbp-4A0h]
  char *v67[3]; // [rsp+F0h] [rbp-498h] BYREF
  unsigned __int64 v68; // [rsp+108h] [rbp-480h]
  _BYTE v69[32]; // [rsp+110h] [rbp-478h] BYREF
  WCHAR Name[264]; // [rsp+130h] [rbp-458h] BYREF
  WCHAR v71[264]; // [rsp+340h] [rbp-248h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+588h] [rbp+0h]

  v60 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
  {
    if ( !a2 )
    {
      v8 = 775;
LABEL_4:
      RegistryString = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)0x80070057LL,
        phkResulta);
      return (unsigned int)RegistryString;
    }
    if ( !a4 )
    {
      v8 = 776;
      goto LABEL_4;
    }
  }
  if ( !a3 )
  {
    v8 = 778;
    goto LABEL_4;
  }
  if ( !a5 )
  {
    v8 = 779;
    goto LABEL_4;
  }
  std::wstring::wstring((__int64)v67);
  std::wstring::wstring((__int64)v65);
  try
  {
    IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl);
    v12 = -1;
    do
      ++v12;
    while ( a3[v12] );
    if ( IsEnabled )
    {
      std::wstring::_Assign<unsigned short>(v67, a3, (char *)v12);
      v14 = v67;
      if ( v68 > 7 )
        v14 = (char **)v67[0];
      v15 = (_QWORD *)std::wstring::end(v67, &v59, v13, v14);
      v17 = v67;
      if ( v68 > 7 )
        LODWORD(v17) = v67[0];
      std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
        (unsigned int)&v51,
        (_DWORD)v17,
        *v15,
        v16,
        *(__int64 *)&_o_towlower);
      std::wstring::operator=(v65, v67);
    }
    else
    {
      std::wstring::_Assign<unsigned short>(v65, a3, (char *)v12);
    }
    v20 = *(char ***)std::wstring::end(v65, &v59, v18, v19);
    v21 = v65;
    if ( v66 > 7 )
      v21 = (char **)v65[0];
    while ( v21 != v20 )
    {
      if ( *(_WORD *)v21 == 47 )
        *(_WORD *)v21 = 92;
      v21 = (char **)((char *)v21 + 2);
    }
  }
  catch ( std::bad_alloc )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x31F,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)0x8007000ELL,
      phkResult);
    std::wstring::_Tidy_deallocate(v65);
    std::wstring::_Tidy_deallocate(v67);
    return 2147942414LL;
  }
  lpSubKey = 0;
  v22 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl);
  v53 = 0;
  v54 = 1;
  if ( v22 )
  {
    v25 = v65;
    if ( v66 > 7 )
      v25 = (char **)v65[0];
    p_lpSubKey = &lpSubKey;
    RegistryString = DCStringCchPrintfAllStrings(&v53, qword_18018A5F0, 2, a2, v25);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
    if ( RegistryString < 0 )
    {
      v24 = 810;
      goto LABEL_34;
    }
  }
  else
  {
    v23 = v65;
    if ( v66 > 7 )
      v23 = (char **)v65[0];
    p_lpSubKey = &lpSubKey;
    RegistryString = DCStringCchPrintfAllStrings(&v53, qword_18018A5E8, 1, v23);
    wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
    if ( RegistryString < 0 )
    {
      v24 = 818;
LABEL_34:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)(unsigned int)RegistryString,
        phkResulta);
LABEL_96:
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
      std::wstring::_Tidy_deallocate(v65);
      std::wstring::_Tidy_deallocate(v67);
      return (unsigned int)RegistryString;
    }
  }
  hKey = 0;
  std::wstring::wstring((__int64)v69);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl'::`2'::impl) )
  {
    v27 = v67;
    if ( v68 > 7 )
      v27 = (char **)v67[0];
    phkResultb = &hKey;
    PMCspRedirectedRegistryPath = DCRegistryTrackingStore::GetPMCspRedirectedRegistryPath(v26, a2, v27, a4);
    RegistryString = PMCspRedirectedRegistryPath;
    if ( PMCspRedirectedRegistryPath < 0 )
    {
      v29 = (unsigned int)PMCspRedirectedRegistryPath;
      v30 = 825;
LABEL_94:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v30,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)v29,
        (int)phkResultb);
LABEL_95:
      std::wstring::_Tidy_deallocate(v69);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_96;
    }
    if ( !hKey )
    {
      p_lpSubKey = &hKey;
      v53 = 0;
      v54 = 1;
      v31 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &v53);
      RegistryString = v31;
      if ( v31 > 0 )
        RegistryString = (unsigned __int16)v31 | 0x80070000;
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
      if ( RegistryString < 0 )
      {
        v30 = 834;
LABEL_93:
        v29 = (unsigned int)RegistryString;
        goto LABEL_94;
      }
    }
  }
  else
  {
    p_lpSubKey = &hKey;
    v53 = 0;
    v54 = 1;
    v33 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0x20119u, &v53);
    RegistryString = v33;
    if ( v33 > 0 )
      RegistryString = (unsigned __int16)v33 | 0x80070000;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
    if ( RegistryString < 0 )
    {
      v30 = 844;
      goto LABEL_93;
    }
  }
  cSubKeys = 0;
  v32 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  RegistryString = v32;
  if ( v32 > 0 )
    RegistryString = (unsigned __int16)v32 | 0x80070000;
  if ( RegistryString < 0 )
  {
    v30 = 849;
    goto LABEL_93;
  }
  v34 = 0;
  if ( cSubKeys )
  {
    while ( 1 )
    {
      cchName = 260;
      v35 = RegEnumKeyExW(hKey, v34, Name, &cchName, 0, 0, 0, 0);
      RegistryString = v35;
      if ( v35 > 0 )
        RegistryString = (unsigned __int16)v35 | 0x80070000;
      if ( RegistryString < 0 )
      {
        v30 = 862;
        goto LABEL_93;
      }
      v51 = 0;
      v61 = &v51;
      v62 = 0;
      v63 = 1;
      v36 = RegOpenKeyExW(hKey, Name, 0, 0x20119u, &v62);
      RegistryString = v36;
      if ( v36 > 0 )
        RegistryString = (unsigned __int16)v36 | 0x80070000;
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v61);
      if ( RegistryString < 0 )
      {
        v45 = 870;
        goto LABEL_89;
      }
      v56 = 0;
      v37 = RegQueryInfoKeyW(v51, 0, 0, 0, &v56, 0, 0, 0, 0, 0, 0, 0);
      RegistryString = v37;
      if ( v37 > 0 )
        RegistryString = (unsigned __int16)v37 | 0x80070000;
      if ( RegistryString < 0 )
      {
        v45 = 874;
        goto LABEL_89;
      }
      v38 = 0;
      if ( v56 )
        break;
LABEL_84:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v51);
      if ( ++v34 >= cSubKeys )
        goto LABEL_85;
    }
    while ( 1 )
    {
      cchName = 260;
      v39 = RegEnumKeyExW(v51, v38, v71, &cchName, 0, 0, 0, 0);
      RegistryString = v39;
      if ( v39 > 0 )
        RegistryString = (unsigned __int16)v39 | 0x80070000;
      if ( RegistryString < 0 )
        break;
      v59 = 0;
      v61 = (HKEY *)&v59;
      v62 = 0;
      v63 = 1;
      RegistryString = DCCDNUtil_GetRegistryString(v51, v71, L"ducumentContext", (unsigned __int16 **)&v62);
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&v61);
      if ( RegistryString < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x37A,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
          (const char *)(unsigned int)RegistryString,
          phkResultc);
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v59);
        goto LABEL_87;
      }
      v40 = (HKEY)operator new(0x70u);
      v64 = v40;
      *(_OWORD *)v40 = 0;
      *((_DWORD *)v40 + 2) = 1;
      *((_DWORD *)v40 + 3) = 1;
      *(_QWORD *)v40 = &std::_Ref_count_obj2<DCAuthorityInfo>::`vftable';
      DCAuthorityInfo::DCAuthorityInfo((DCAuthorityInfo *)(v40 + 4));
      v60 |= 1u;
      p_lpSubKey = v40 + 4;
      v53 = v40;
      v41 = -1;
      do
        ++v41;
      while ( Name[v41] );
      std::wstring::_Assign<unsigned short>((char **)v40 + 2, Name, (char *)v41);
      v42 = -1;
      do
        ++v42;
      while ( v71[v42] );
      std::wstring::_Assign<unsigned short>((char **)v40 + 6, v71, (char *)v42);
      v43 = -1;
      do
        ++v43;
      while ( v59[v43] );
      std::wstring::_Assign<unsigned short>((char **)v40 + 10, v59, (char *)v43);
      v44 = *(_QWORD **)(a5 + 8);
      if ( v44 == *(_QWORD **)(a5 + 16) )
      {
        std::vector<std::shared_ptr<DCURI>>::_Emplace_reallocate<std::shared_ptr<DCURI> const &>(
          (__int64 *)a5,
          *(void **)(a5 + 8),
          (__int64)&p_lpSubKey);
        v40 = v53;
      }
      else
      {
        std::shared_ptr<SCDSetting>::shared_ptr<SCDSetting>(v44, &p_lpSubKey);
        *(_QWORD *)(a5 + 8) += 16LL;
      }
      if ( v40 )
        std::_Ref_count_base::_Decref((std::_Ref_count_base *)v40);
      std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v59);
      if ( ++v38 >= v56 )
        goto LABEL_84;
    }
    v45 = 887;
LABEL_89:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v45,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)(unsigned int)RegistryString,
      phkResultc);
LABEL_87:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v51);
    goto LABEL_95;
  }
LABEL_85:
  std::wstring::_Tidy_deallocate(v69);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
  std::wstring::_Tidy_deallocate(v65);
  std::wstring::_Tidy_deallocate(v67);
  return 0;
}

```

## disassembly

```asm
0x1800cfb00  mov     [rsp+arg_0], rbx
0x1800cfb05  push    rdi
0x1800cfb06  push    r12
0x1800cfb08  push    r13
0x1800cfb0a  push    r14
0x1800cfb0c  push    r15
0x1800cfb0e  sub     rsp, 560h
0x1800cfb15  mov     rax, cs:__security_cookie
0x1800cfb1c  xor     rax, rsp
0x1800cfb1f  mov     [rsp+588h+var_38], rax
0x1800cfb27  mov     r14, r9
0x1800cfb2a  mov     rbx, r8
0x1800cfb2d  mov     rdi, rdx
0x1800cfb30  mov     r13, [rsp+588h+arg_20]
0x1800cfb38  xor     r15d, r15d
0x1800cfb3b  mov     [rsp+588h+var_4E0], r15d
0x1800cfb43  lea     r12, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider> `wil::Feature<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::GetImpl(void)'::`2'::impl
0x1800cfb4a  mov     rcx, r12
0x1800cfb4d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800cfb52  test    al, al
0x1800cfb54  jz      short loc_1800CFB8F
0x1800cfb56  test    rdi, rdi
0x1800cfb59  jnz     short loc_1800CFB83
0x1800cfb5b  mov     edx, 307h; void *
0x1800cfb60  mov     ebx, 80070057h
0x1800cfb65  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800cfb6c  mov     r9d, ebx; char *
0x1800cfb6f  mov     rcx, [rsp+588h]; this
0x1800cfb77  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cfb7c  mov     eax, ebx
0x1800cfb7e  jmp     loc_1800D03B6
0x1800cfb83  test    r14, r14
0x1800cfb86  jnz     short loc_1800CFB8F
0x1800cfb88  mov     edx, 308h
0x1800cfb8d  jmp     short loc_1800CFB60
0x1800cfb8f  test    rbx, rbx
0x1800cfb92  jnz     short loc_1800CFB9B
0x1800cfb94  mov     edx, 30Ah
0x1800cfb99  jmp     short loc_1800CFB60
0x1800cfb9b  test    r13, r13
0x1800cfb9e  jnz     short loc_1800CFBA7
0x1800cfba0  mov     edx, 30Bh
0x1800cfba5  jmp     short loc_1800CFB60
0x1800cfba7  lea     rcx, [rsp+588h+var_498]
0x1800cfbaf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cfbb4  nop
0x1800cfbb5  lea     rcx, [rsp+588h+var_4B8]
0x1800cfbbd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cfbc2  nop
0x1800cfbc3  mov     rcx, r12
0x1800cfbc6  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800cfbcb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800cfbcf  inc     r8
0x1800cfbd2  cmp     [rbx+r8*2], r15w
0x1800cfbd7  jnz     short loc_1800CFBCF
0x1800cfbd9  mov     rdx, rbx
0x1800cfbdc  test    al, al
0x1800cfbde  jz      loc_1800CFC6A
0x1800cfbe4  lea     rcx, [rsp+588h+var_498]
0x1800cfbec  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800cfbf1  lea     r9, [rsp+588h+var_498]
0x1800cfbf9  cmp     [rsp+588h+var_480], 7
0x1800cfc02  cmova   r9, [rsp+588h+var_498]
0x1800cfc0b  lea     rdx, [rsp+588h+var_4E8]
0x1800cfc13  lea     rcx, [rsp+588h+var_498]
0x1800cfc1b  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1800cfc20  lea     rdx, [rsp+588h+var_498]
0x1800cfc28  cmp     [rsp+588h+var_480], 7
0x1800cfc31  cmova   rdx, [rsp+588h+var_498]
0x1800cfc3a  mov     rcx, cs:__imp__o_towlower
0x1800cfc41  mov     [rsp+588h+phkResult], rcx
0x1800cfc46  mov     r8, [rax]
0x1800cfc49  lea     rcx, [rsp+588h+var_520]
0x1800cfc4e  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x1800cfc53  lea     rdx, [rsp+588h+var_498]
0x1800cfc5b  lea     rcx, [rsp+588h+var_4B8]
0x1800cfc63  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800cfc68  jmp     short loc_1800CFC77
0x1800cfc6a  lea     rcx, [rsp+588h+var_4B8]
0x1800cfc72  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800cfc77  lea     rdx, [rsp+588h+var_4E8]
0x1800cfc7f  lea     rcx, [rsp+588h+var_4B8]
0x1800cfc87  call    ?end@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@2@XZ; std::wstring::end(void)
0x1800cfc8c  mov     rax, [rax]
0x1800cfc8f  lea     rcx, [rsp+588h+var_4B8]
0x1800cfc97  cmp     [rsp+588h+var_4A0], 7
0x1800cfca0  cmova   rcx, [rsp+588h+var_4B8]
0x1800cfca9  jmp     short loc_1800CFCBA
0x1800cfcab  cmp     word ptr [rcx], 2Fh ; '/'
0x1800cfcaf  jnz     short loc_1800CFCB6
0x1800cfcb1  mov     word ptr [rcx], 5Ch ; '\'
0x1800cfcb6  add     rcx, 2
0x1800cfcba  cmp     rcx, rax
0x1800cfcbd  jnz     short loc_1800CFCAB
0x1800cfcbf  mov     [rsp+588h+lpSubKey], r15
0x1800cfcc7  mov     rcx, r12
0x1800cfcca  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800cfccf  mov     [rsp+588h+var_510], r15
0x1800cfcd4  mov     [rsp+588h+var_508], 1
0x1800cfcdc  test    al, al
0x1800cfcde  jnz     short loc_1800CFD4F
0x1800cfce0  lea     r9, [rsp+588h+var_4B8]
0x1800cfce8  cmp     [rsp+588h+var_4A0], 7
0x1800cfcf1  cmova   r9, [rsp+588h+var_4B8]
0x1800cfcfa  lea     rax, [rsp+588h+lpSubKey]
0x1800cfd02  mov     [rsp+588h+var_518], rax
0x1800cfd07  mov     r8d, 1
0x1800cfd0d  mov     rdx, cs:qword_18018A5E8
0x1800cfd14  lea     rcx, [rsp+588h+var_510]
0x1800cfd19  call    DCStringCchPrintfAllStrings
0x1800cfd1e  mov     ebx, eax
0x1800cfd20  lea     rcx, [rsp+588h+var_518]
0x1800cfd25  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800cfd2a  test    ebx, ebx
0x1800cfd2c  jns     short loc_1800CFDAC
0x1800cfd2e  mov     edx, 332h; void *
0x1800cfd33  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800cfd3a  mov     r9d, ebx; char *
0x1800cfd3d  mov     rcx, [rsp+588h]; this
0x1800cfd45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cfd4a  jmp     loc_1800D0368
0x1800cfd4f  lea     rax, [rsp+588h+var_4B8]
0x1800cfd57  cmp     [rsp+588h+var_4A0], 7
0x1800cfd60  cmova   rax, [rsp+588h+var_4B8]
0x1800cfd69  lea     rcx, [rsp+588h+lpSubKey]
0x1800cfd71  mov     [rsp+588h+var_518], rcx
0x1800cfd76  mov     [rsp+588h+phkResult], rax
0x1800cfd7b  mov     r9, rdi
0x1800cfd7e  mov     r8d, 2
0x1800cfd84  mov     rdx, cs:qword_18018A5F0
0x1800cfd8b  lea     rcx, [rsp+588h+var_510]
0x1800cfd90  call    DCStringCchPrintfAllStrings
0x1800cfd95  mov     ebx, eax
0x1800cfd97  lea     rcx, [rsp+588h+var_518]
0x1800cfd9c  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800cfda1  test    ebx, ebx
0x1800cfda3  jns     short loc_1800CFDAC
0x1800cfda5  mov     edx, 32Ah
0x1800cfdaa  jmp     short loc_1800CFD33
0x1800cfdac  mov     [rsp+588h+hKey], r15
0x1800cfdb1  lea     rcx, [rsp+588h+var_478]
0x1800cfdb9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800cfdbe  nop
0x1800cfdbf  mov     rcx, r12
0x1800cfdc2  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_OsConfigurationRegistryProvider@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_OsConfigurationRegistryProvider>::__private_IsEnabled(void)
0x1800cfdc7  test    al, al
0x1800cfdc9  jz      loc_1800CFEF5
0x1800cfdcf  lea     r8, [rsp+588h+var_498]
0x1800cfdd7  cmp     [rsp+588h+var_480], 7
0x1800cfde0  cmova   r8, [rsp+588h+var_498]
0x1800cfde9  lea     rax, [rsp+588h+var_478]
0x1800cfdf1  mov     [rsp+588h+lpcbMaxSubKeyLen], rax
0x1800cfdf6  lea     rax, [rsp+588h+hKey]
0x1800cfdfb  mov     [rsp+588h+phkResult], rax
0x1800cfe00  mov     r9, r14
0x1800cfe03  mov     rdx, rdi
0x1800cfe06  call    ?GetPMCspRedirectedRegistryPath@DCRegistryTrackingStore@@AEAAJPEBG00AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DCRegistryTrackingStore::GetPMCspRedirectedRegistryPath(ushort const *,ushort const *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,std::wstring &)
0x1800cfe0b  mov     ebx, eax
0x1800cfe0d  test    eax, eax
0x1800cfe0f  jns     short loc_1800CFE1E
0x1800cfe11  mov     r9d, eax
0x1800cfe14  mov     edx, 339h
0x1800cfe19  jmp     loc_1800D033A
0x1800cfe1e  cmp     [rsp+588h+hKey], r15
0x1800cfe23  jnz     short loc_1800CFE8C
0x1800cfe25  lea     rax, [rsp+588h+hKey]
0x1800cfe2a  mov     [rsp+588h+var_518], rax
0x1800cfe2f  mov     [rsp+588h+var_510], r15
0x1800cfe34  mov     [rsp+588h+var_508], 1
0x1800cfe3c  lea     rax, [rsp+588h+var_510]
0x1800cfe41  mov     [rsp+588h+phkResult], rax; phkResult
0x1800cfe46  mov     r9d, 20119h; samDesired
0x1800cfe4c  xor     r8d, r8d; ulOptions
0x1800cfe4f  mov     rdx, [rsp+588h+lpSubKey]; lpSubKey
0x1800cfe57  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800cfe5e  call    cs:__imp_RegOpenKeyExW
0x1800cfe64  mov     ebx, eax
0x1800cfe66  mov     edi, 80070000h
0x1800cfe6b  test    eax, eax
0x1800cfe6d  jle     short loc_1800CFE74
0x1800cfe6f  movzx   ebx, ax
0x1800cfe72  or      ebx, edi
0x1800cfe74  lea     rcx, [rsp+588h+var_518]
0x1800cfe79  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800cfe7e  test    ebx, ebx
0x1800cfe80  jns     short loc_1800CFE91
0x1800cfe82  mov     edx, 342h
0x1800cfe87  jmp     loc_1800D0337
0x1800cfe8c  mov     edi, 80070000h
0x1800cfe91  mov     [rsp+588h+cSubKeys], r15d
0x1800cfe99  mov     [rsp+588h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800cfe9e  mov     [rsp+588h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800cfea3  mov     [rsp+588h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800cfea8  mov     [rsp+588h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800cfead  mov     [rsp+588h+lpcValues], r15; lpcValues
0x1800cfeb2  mov     [rsp+588h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800cfeb7  mov     [rsp+588h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800cfebc  lea     rax, [rsp+588h+cSubKeys]
0x1800cfec4  mov     [rsp+588h+phkResult], rax; lpcSubKeys
0x1800cfec9  xor     r9d, r9d; lpReserved
0x1800cfecc  xor     r8d, r8d; lpcchClass
0x1800cfecf  xor     edx, edx; lpClass
0x1800cfed1  mov     rcx, [rsp+588h+hKey]; hKey
0x1800cfed6  call    cs:__imp_RegQueryInfoKeyW
0x1800cfedc  mov     ebx, eax
0x1800cfede  test    eax, eax
0x1800cfee0  jle     short loc_1800CFEE7
0x1800cfee2  movzx   ebx, ax
0x1800cfee5  or      ebx, edi
0x1800cfee7  test    ebx, ebx
0x1800cfee9  jns     short loc_1800CFF60
0x1800cfeeb  mov     edx, 351h
0x1800cfef0  jmp     loc_1800D0337
0x1800cfef5  lea     rax, [rsp+588h+hKey]
0x1800cfefa  mov     [rsp+588h+var_518], rax
0x1800cfeff  mov     [rsp+588h+var_510], r15
0x1800cff04  mov     [rsp+588h+var_508], 1
0x1800cff0c  lea     rax, [rsp+588h+var_510]
0x1800cff11  mov     [rsp+588h+phkResult], rax; phkResult
0x1800cff16  mov     r9d, 20119h; samDesired
0x1800cff1c  xor     r8d, r8d; ulOptions
0x1800cff1f  mov     rdx, [rsp+588h+lpSubKey]; lpSubKey
0x1800cff27  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800cff2e  call    cs:__imp_RegOpenKeyExW
0x1800cff34  mov     ebx, eax
0x1800cff36  mov     edi, 80070000h
0x1800cff3b  test    eax, eax
0x1800cff3d  jle     short loc_1800CFF44
0x1800cff3f  movzx   ebx, ax
0x1800cff42  or      ebx, edi
0x1800cff44  lea     rcx, [rsp+588h+var_518]
0x1800cff49  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800cff4e  test    ebx, ebx
0x1800cff50  jns     loc_1800CFE91
0x1800cff56  mov     edx, 34Ch
0x1800cff5b  jmp     loc_1800D0337
0x1800cff60  mov     r12d, r15d
0x1800cff63  cmp     [rsp+588h+cSubKeys], r15d
0x1800cff6b  jbe     loc_1800D0286
0x1800cff71  mov     [rsp+588h+cchName], 104h
0x1800cff7c  mov     [rsp+588h+lpcValues], r15; lpftLastWriteTime
0x1800cff81  mov     [rsp+588h+lpcbMaxClassLen], r15; lpcchClass
0x1800cff86  mov     [rsp+588h+lpcbMaxSubKeyLen], r15; lpClass
0x1800cff8b  mov     [rsp+588h+phkResult], r15; int
0x1800cff90  lea     r9, [rsp+588h+cchName]; lpcchName
0x1800cff98  lea     r8, [rsp+588h+Name]; lpName
0x1800cffa0  mov     edx, r12d; dwIndex
0x1800cffa3  mov     rcx, [rsp+588h+hKey]; hKey
0x1800cffa8  call    cs:__imp_RegEnumKeyExW
0x1800cffae  mov     ebx, eax
0x1800cffb0  test    eax, eax
0x1800cffb2  jle     short loc_1800CFFB9
0x1800cffb4  movzx   ebx, ax
0x1800cffb7  or      ebx, edi
0x1800cffb9  test    ebx, ebx
0x1800cffbb  js      loc_1800D0332
0x1800cffc1  mov     [rsp+588h+var_520], r15
0x1800cffc6  lea     rax, [rsp+588h+var_520]
0x1800cffcb  mov     [rsp+588h+var_4D8], rax
0x1800cffd3  mov     [rsp+588h+var_4D0], r15
0x1800cffdb  mov     [rsp+588h+var_4C8], 1
0x1800cffe3  lea     rax, [rsp+588h+var_4D0]
0x1800cffeb  mov     [rsp+588h+phkResult], rax; phkResult
0x1800cfff0  mov     r9d, 20119h; samDesired
0x1800cfff6  xor     r8d, r8d; ulOptions
0x1800cfff9  lea     rdx, [rsp+588h+Name]; lpSubKey
0x1800d0001  mov     rcx, [rsp+588h+hKey]; hKey
0x1800d0006  call    cs:__imp_RegOpenKeyExW
0x1800d000c  mov     ebx, eax
0x1800d000e  test    eax, eax
0x1800d0010  jle     short loc_1800D0017
0x1800d0012  movzx   ebx, ax
0x1800d0015  or      ebx, edi
0x1800d0017  lea     rcx, [rsp+588h+var_4D8]
0x1800d001f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800d0024  test    ebx, ebx
0x1800d0026  js      loc_1800D032B
0x1800d002c  mov     [rsp+588h+var_4FC], r15d
0x1800d0034  mov     [rsp+588h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800d0039  mov     [rsp+588h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800d003e  mov     [rsp+588h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800d0043  mov     [rsp+588h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800d0048  mov     [rsp+588h+lpcValues], r15; lpcValues
0x1800d004d  mov     [rsp+588h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800d0052  mov     [rsp+588h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800d0057  lea     rax, [rsp+588h+var_4FC]
0x1800d005f  mov     [rsp+588h+phkResult], rax; lpcSubKeys
0x1800d0064  xor     r9d, r9d; lpReserved
0x1800d0067  xor     r8d, r8d; lpcchClass
0x1800d006a  xor     edx, edx; lpClass
0x1800d006c  mov     rcx, [rsp+588h+var_520]; hKey
0x1800d0071  call    cs:__imp_RegQueryInfoKeyW
0x1800d0077  mov     ebx, eax
0x1800d0079  test    eax, eax
0x1800d007b  jle     short loc_1800D0082
0x1800d007d  movzx   ebx, ax
0x1800d0080  or      ebx, edi
0x1800d0082  test    ebx, ebx
0x1800d0084  js      loc_1800D0324
0x1800d008a  mov     r14d, r15d
  ... truncated ...
```
