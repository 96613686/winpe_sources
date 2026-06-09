# DCRegistryTrackingStore::MigratePolicyToRegistryProviderAuthorityTracking(ushort const *,ushort const *,ushort const *)

- ea: `0x1800d24e4`
- end: `0x1800d2bb1`
- name: `?MigratePolicyToRegistryProviderAuthorityTracking@DCRegistryTrackingStore@@CAJPEBG00@Z`
- size: `1741`
- prototype: `static int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config`

## callers

- `0x1800d2050`

## callees

- `0x18000b9e0`
- `0x1800117dc`
- `0x1800143c8`
- `0x180018ac0`
- `0x18001ce5c`
- `0x18001ce80`
- `0x18001d03c`
- `0x18001d0b0`
- `0x1800600bc`
- `0x1800ce974`
- `0x1800cf734`
- `0x1800d24e4`
- `0x180100ad8`
- `0x180100e3c`
- `0x18010136c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800d2a5a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800d2a5a`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d29cf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d2ab9`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d29cf`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800d2ab9`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d27fc`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800d27fc`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d27a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d28a2`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d27a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800d28a2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d25b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d2846`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d25b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800d2846`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800d2a23`
- `api-ms-win-core-registry-l1-1-0!RegCopyTreeW` at `0x1800d2a23`

## string_xrefs

- `0x1800d2930`: `registry`
- `0x1800d2b1f`: `regRedirectPath`
- `0x1800d2ae6`: `regRedirectPathRefCount`
- `0x1800d256b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d25e5`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d264e`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d26c0`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d274b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d28d7`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d2967`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`
- `0x1800d29f7`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcregistrytrackingstore.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DCRegistryTrackingStore::MigratePolicyToRegistryProviderAuthorityTracking(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  int v3; // esi
  signed int RegistryString; // ebx
  LSTATUS v6; // eax
  int PolicyRegistryRedirectedPath; // eax
  unsigned __int64 v8; // r9
  __int64 v9; // rdx
  LSTATUS v10; // eax
  unsigned int v11; // esi
  DWORD i; // edi
  LSTATUS v13; // eax
  LSTATUS v14; // eax
  LSTATUS v15; // eax
  __int64 v16; // rdx
  unsigned __int16 **v17; // rax
  LSTATUS v18; // eax
  __int64 v19; // rdx
  unsigned __int64 v20; // r9
  LSTATUS v21; // eax
  LSTATUS v22; // eax
  LSTATUS v23; // eax
  int v24; // eax
  const unsigned __int16 *v25; // r9
  int v26; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int phkResultb; // [rsp+20h] [rbp-E0h]
  int phkResultc; // [rsp+20h] [rbp-E0h]
  int phkResultd; // [rsp+20h] [rbp-E0h]
  int phkResulte; // [rsp+20h] [rbp-E0h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v35; // [rsp+68h] [rbp-98h] BYREF
  __int64 v36; // [rsp+70h] [rbp-90h] BYREF
  __int64 *p_lpSubKey; // [rsp+78h] [rbp-88h] BYREF
  HKEY v38; // [rsp+80h] [rbp-80h] BYREF
  char v39; // [rsp+88h] [rbp-78h]
  HKEY hKeyDest; // [rsp+90h] [rbp-70h] BYREF
  LPCWSTR v41; // [rsp+98h] [rbp-68h] BYREF
  DWORD cSubKeys; // [rsp+A0h] [rbp-60h] BYREF
  DWORD v43; // [rsp+A4h] [rbp-5Ch] BYREF
  HKEY v44; // [rsp+A8h] [rbp-58h] BYREF
  LPCWSTR lpSubKey; // [rsp+B0h] [rbp-50h] BYREF
  DWORD cchName; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 *v47[3]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int64 v48; // [rsp+D8h] [rbp-28h]
  WCHAR Name[264]; // [rsp+E0h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+238h]

  v3 = (int)a2;
  lpSubKey = 0;
  p_lpSubKey = (__int64 *)&lpSubKey;
  v38 = 0;
  v39 = 1;
  phkResult = (int)a2;
  RegistryString = DCStringCchPrintfAllStrings(&v38, qword_18018A600, 3, a1);
  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
  if ( RegistryString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4EB,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)(unsigned int)RegistryString,
      phkResult);
    goto LABEL_70;
  }
  hKey = 0;
  p_lpSubKey = (__int64 *)&hKey;
  v38 = 0;
  v39 = 1;
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0xF003Fu, &v38);
  RegistryString = v6;
  if ( v6 > 0 )
    RegistryString = (unsigned __int16)v6 | 0x80070000;
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
  if ( RegistryString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F3,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)(unsigned int)RegistryString,
      phkResulta);
    goto LABEL_7;
  }
  v35 = 0;
  p_lpSubKey = &v35;
  v38 = 0;
  v39 = 1;
  RegistryString = DCCDNUtil_GetRegistryString(hKey, 0, L"authorityId", (unsigned __int16 **)&v38);
  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
  if ( RegistryString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4F7,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)(unsigned int)RegistryString,
      phkResulta);
    goto LABEL_10;
  }
  v36 = 0;
  p_lpSubKey = &v36;
  v38 = 0;
  v39 = 1;
  phkResultb = v3;
  RegistryString = DCStringCchPrintfAllStrings(&v38, qword_18018A608, 3, a1);
  wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
  if ( RegistryString < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x500,
      (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
      (const char *)(unsigned int)RegistryString,
      v3);
    goto LABEL_13;
  }
  std::wstring::wstring((__int64)v47);
  PolicyRegistryRedirectedPath = DCRegistryTrackingStore::FindPolicyRegistryRedirectedPath(v36, v35, v47);
  RegistryString = PolicyRegistryRedirectedPath;
  if ( PolicyRegistryRedirectedPath == -2147024894 )
  {
    std::wstring::_Tidy_deallocate(v47);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v36);
    std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v35);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    RegistryString = 1;
    goto LABEL_70;
  }
  if ( PolicyRegistryRedirectedPath < 0 )
  {
    v8 = (unsigned int)PolicyRegistryRedirectedPath;
    v9 = 1289;
    goto LABEL_18;
  }
  cSubKeys = 0;
  v10 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  RegistryString = v10;
  if ( v10 > 0 )
    RegistryString = (unsigned __int16)v10 | 0x80070000;
  if ( RegistryString < 0 )
  {
    v8 = (unsigned int)RegistryString;
    v9 = 1294;
    goto LABEL_18;
  }
  v11 = 0;
  for ( i = 0; ; ++i )
  {
    if ( i >= cSubKeys )
    {
      v41 = 0;
      v17 = v47;
      if ( v48 > 7 )
        v17 = (unsigned __int16 **)v47[0];
      p_lpSubKey = (__int64 *)&v41;
      v38 = 0;
      v39 = 1;
      RegistryString = DCStringCchPrintfAllStrings(&v38, qword_18018A5F0, 2, L"registry", v17);
      wil::details::out_param_t<std::unique_ptr<unsigned short>>::~out_param_t<std::unique_ptr<unsigned short>>(&p_lpSubKey);
      if ( RegistryString < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x534,
          (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
          (const char *)(unsigned int)RegistryString,
          phkResultd);
LABEL_44:
        std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v41);
        goto LABEL_19;
      }
      hKeyDest = 0;
      p_lpSubKey = (__int64 *)&hKeyDest;
      v38 = 0;
      v39 = 1;
      v18 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, v41, 0, 0, 0, 0xF003Fu, 0, &v38, 0);
      RegistryString = v18;
      if ( v18 > 0 )
        RegistryString = (unsigned __int16)v18 | 0x80070000;
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
      if ( RegistryString >= 0 )
      {
        v21 = RegCopyTreeW(hKey, 0, hKeyDest);
        RegistryString = v21;
        if ( v21 > 0 )
          RegistryString = (unsigned __int16)v21 | 0x80070000;
        if ( RegistryString >= 0 )
        {
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(&hKey);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::operator=(&hKeyDest);
          v22 = RegDeleteTreeW(HKEY_LOCAL_MACHINE, lpSubKey);
          RegistryString = v22;
          if ( v22 > 0 )
            RegistryString = (unsigned __int16)v22 | 0x80070000;
          if ( RegistryString >= 0 )
          {
            p_lpSubKey = (__int64 *)&hKey;
            v38 = 0;
            v39 = 1;
            v23 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x2011Fu, 0, &v38, 0);
            RegistryString = v23;
            if ( v23 > 0 )
              RegistryString = (unsigned __int16)v23 | 0x80070000;
            wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
            if ( RegistryString >= 0 )
            {
              v24 = DCCDNUtil_SetRegistryDWORD(hKey, 0, L"regRedirectPathRefCount", v11);
              RegistryString = v24;
              if ( v24 >= 0 )
              {
                v25 = (const unsigned __int16 *)v47;
                if ( v48 > 7 )
                  v25 = v47[0];
                v26 = DCCDNUtil_SetRegistryString(hKey, 0, L"regRedirectPath", v25, 0);
                RegistryString = v26;
                if ( v26 >= 0 )
                {
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeyDest);
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v41);
                  std::wstring::_Tidy_deallocate(v47);
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v36);
                  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v35);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
                  RegistryString = 0;
                  goto LABEL_70;
                }
                v20 = (unsigned int)v26;
                v19 = 1365;
              }
              else
              {
                v20 = (unsigned int)v24;
                v19 = 1364;
              }
              goto LABEL_50;
            }
            v19 = 1362;
          }
          else
          {
            v19 = 1351;
          }
        }
        else
        {
          v19 = 1346;
        }
      }
      else
      {
        v19 = 1344;
      }
      v20 = (unsigned int)RegistryString;
LABEL_50:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)v20,
        phkResulte);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKeyDest);
      goto LABEL_44;
    }
    cchName = 260;
    v13 = RegEnumKeyExW(hKey, i, Name, &cchName, 0, 0, 0, 0);
    RegistryString = v13;
    if ( v13 > 0 )
      RegistryString = (unsigned __int16)v13 | 0x80070000;
    if ( RegistryString < 0 )
      break;
    v44 = 0;
    p_lpSubKey = (__int64 *)&v44;
    v38 = 0;
    v39 = 1;
    v14 = RegOpenKeyExW(hKey, Name, 0, 0x20119u, &v38);
    RegistryString = v14;
    if ( v14 > 0 )
      RegistryString = (unsigned __int16)v14 | 0x80070000;
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_lpSubKey);
    if ( RegistryString < 0 )
    {
      v16 = 1316;
      goto LABEL_38;
    }
    v43 = 0;
    v15 = RegQueryInfoKeyW(v44, 0, 0, 0, &v43, 0, 0, 0, 0, 0, 0, 0);
    RegistryString = v15;
    if ( v15 > 0 )
      RegistryString = (unsigned __int16)v15 | 0x80070000;
    if ( RegistryString < 0 )
    {
      v16 = 1320;
LABEL_38:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v16,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
        (const char *)(unsigned int)RegistryString,
        phkResultc);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v44);
      goto LABEL_19;
    }
    v11 += v43;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v44);
  }
  v8 = (unsigned int)RegistryString;
  v9 = 1308;
LABEL_18:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\declaredconfiguration\\objectmodel\\lib\\dcregistrytrackingstore.cpp",
    (const char *)v8,
    phkResultb);
LABEL_19:
  std::wstring::_Tidy_deallocate(v47);
LABEL_13:
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v36);
LABEL_10:
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&v35);
LABEL_7:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
LABEL_70:
  std::unique_ptr<unsigned short>::~unique_ptr<unsigned short>(&lpSubKey);
  return (unsigned int)RegistryString;
}

```

## disassembly

```asm
0x1800d24e4  push    rbp
0x1800d24e6  push    rbx
0x1800d24e7  push    rsi
0x1800d24e8  push    rdi
0x1800d24e9  push    r12
0x1800d24eb  push    r14
0x1800d24ed  push    r15
0x1800d24ef  lea     rbp, [rsp-200h]
0x1800d24f7  sub     rsp, 300h
0x1800d24fe  mov     rax, cs:__security_cookie
0x1800d2505  xor     rax, rsp
0x1800d2508  mov     [rbp+230h+var_40], rax
0x1800d250f  mov     r14, r8
0x1800d2512  mov     rsi, rdx
0x1800d2515  mov     rdi, rcx
0x1800d2518  xor     r15d, r15d
0x1800d251b  mov     [rbp+230h+lpSubKey], r15
0x1800d251f  lea     rax, [rbp+230h+lpSubKey]
0x1800d2523  mov     [rsp+330h+var_2B8], rax
0x1800d2528  mov     [rbp+230h+var_2B0], r15
0x1800d252c  mov     [rbp+230h+var_2A8], 1
0x1800d2530  mov     [rsp+330h+lpcbMaxSubKeyLen], r8
0x1800d2535  mov     [rsp+330h+phkResult], rdx; int
0x1800d253a  mov     r9, rcx
0x1800d253d  lea     r8d, [r15+3]
0x1800d2541  mov     rdx, cs:qword_18018A600
0x1800d2548  lea     rcx, [rbp+230h+var_2B0]
0x1800d254c  call    DCStringCchPrintfAllStrings
0x1800d2551  mov     ebx, eax
0x1800d2553  lea     rcx, [rsp+330h+var_2B8]
0x1800d2558  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800d255d  test    ebx, ebx
0x1800d255f  jns     short loc_1800D2581
0x1800d2561  mov     rcx, [rbp+238h]; this
0x1800d2568  mov     r9d, ebx; char *
0x1800d256b  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d2572  mov     edx, 4EBh; void *
0x1800d2577  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d257c  jmp     loc_1800D2B85
0x1800d2581  mov     [rsp+330h+hKey], r15
0x1800d2586  lea     rax, [rsp+330h+hKey]
0x1800d258b  mov     [rsp+330h+var_2B8], rax
0x1800d2590  mov     [rbp+230h+var_2B0], r15
0x1800d2594  mov     [rbp+230h+var_2A8], 1
0x1800d2598  lea     rax, [rbp+230h+var_2B0]
0x1800d259c  mov     [rsp+330h+phkResult], rax; int
0x1800d25a1  mov     r9d, 0F003Fh; samDesired
0x1800d25a7  xor     r8d, r8d; ulOptions
0x1800d25aa  mov     rdx, [rbp+230h+lpSubKey]; lpSubKey
0x1800d25ae  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800d25b5  call    cs:__imp_RegOpenKeyExW
0x1800d25bb  mov     ebx, eax
0x1800d25bd  mov     r12d, 80070000h
0x1800d25c3  test    eax, eax
0x1800d25c5  jle     short loc_1800D25CD
0x1800d25c7  movzx   ebx, ax
0x1800d25ca  or      ebx, r12d
0x1800d25cd  lea     rcx, [rsp+330h+var_2B8]
0x1800d25d2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800d25d7  test    ebx, ebx
0x1800d25d9  jns     short loc_1800D2606
0x1800d25db  mov     rcx, [rbp+238h]; this
0x1800d25e2  mov     r9d, ebx; char *
0x1800d25e5  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d25ec  mov     edx, 4F3h; void *
0x1800d25f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d25f6  nop
0x1800d25f7  lea     rcx, [rsp+330h+hKey]
0x1800d25fc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d2601  jmp     loc_1800D2B85
0x1800d2606  mov     [rsp+330h+var_2C8], r15
0x1800d260b  lea     rax, [rsp+330h+var_2C8]
0x1800d2610  mov     [rsp+330h+var_2B8], rax
0x1800d2615  mov     [rbp+230h+var_2B0], r15
0x1800d2619  mov     [rbp+230h+var_2A8], 1
0x1800d261d  lea     r9, [rbp+230h+var_2B0]; unsigned __int16 **
0x1800d2621  lea     r8, aAuthorityid; "authorityId"
0x1800d2628  xor     edx, edx; unsigned __int16 *
0x1800d262a  mov     rcx, [rsp+330h+hKey]; HKEY
0x1800d262f  call    ?DCCDNUtil_GetRegistryString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; DCCDNUtil_GetRegistryString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x1800d2634  mov     ebx, eax
0x1800d2636  lea     rcx, [rsp+330h+var_2B8]
0x1800d263b  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800d2640  test    ebx, ebx
0x1800d2642  jns     short loc_1800D266C
0x1800d2644  mov     rcx, [rbp+238h]; this
0x1800d264b  mov     r9d, ebx; char *
0x1800d264e  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d2655  mov     edx, 4F7h; void *
0x1800d265a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d265f  nop
0x1800d2660  lea     rcx, [rsp+330h+var_2C8]
0x1800d2665  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800d266a  jmp     short loc_1800D25F7
0x1800d266c  mov     [rsp+330h+var_2C0], r15
0x1800d2671  lea     rax, [rsp+330h+var_2C0]
0x1800d2676  mov     [rsp+330h+var_2B8], rax
0x1800d267b  mov     [rbp+230h+var_2B0], r15
0x1800d267f  mov     [rbp+230h+var_2A8], 1
0x1800d2683  mov     [rsp+330h+lpcbMaxSubKeyLen], r14
0x1800d2688  mov     [rsp+330h+phkResult], rsi; int
0x1800d268d  mov     r9, rdi
0x1800d2690  mov     r8d, 3
0x1800d2696  mov     rdx, cs:qword_18018A608
0x1800d269d  lea     rcx, [rbp+230h+var_2B0]
0x1800d26a1  call    DCStringCchPrintfAllStrings
0x1800d26a6  mov     ebx, eax
0x1800d26a8  lea     rcx, [rsp+330h+var_2B8]
0x1800d26ad  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800d26b2  test    ebx, ebx
0x1800d26b4  jns     short loc_1800D26DE
0x1800d26b6  mov     rcx, [rbp+238h]; this
0x1800d26bd  mov     r9d, ebx; char *
0x1800d26c0  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d26c7  mov     edx, 500h; void *
0x1800d26cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d26d1  nop
0x1800d26d2  lea     rcx, [rsp+330h+var_2C0]
0x1800d26d7  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800d26dc  jmp     short loc_1800D2660
0x1800d26de  lea     rcx, [rbp+230h+var_270]
0x1800d26e2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800d26e7  nop
0x1800d26e8  lea     r8, [rbp+230h+var_270]
0x1800d26ec  mov     rdx, [rsp+330h+var_2C8]
0x1800d26f1  mov     rcx, [rsp+330h+var_2C0]
0x1800d26f6  call    ?FindPolicyRegistryRedirectedPath@DCRegistryTrackingStore@@CAJPEBG0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; DCRegistryTrackingStore::FindPolicyRegistryRedirectedPath(ushort const *,ushort const *,std::wstring &)
0x1800d26fb  mov     ebx, eax
0x1800d26fd  cmp     eax, 80070002h
0x1800d2702  jnz     short loc_1800D2738
0x1800d2704  lea     rcx, [rbp+230h+var_270]
0x1800d2708  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d270d  nop
0x1800d270e  lea     rcx, [rsp+330h+var_2C0]
0x1800d2713  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800d2718  nop
0x1800d2719  lea     rcx, [rsp+330h+var_2C8]
0x1800d271e  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800d2723  nop
0x1800d2724  lea     rcx, [rsp+330h+hKey]
0x1800d2729  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d272e  mov     ebx, 1
0x1800d2733  jmp     loc_1800D2B85
0x1800d2738  test    eax, eax
0x1800d273a  jns     short loc_1800D2766
0x1800d273c  mov     r9d, eax; char *
0x1800d273f  mov     edx, 509h; void *
0x1800d2744  mov     rcx, [rbp+238h]; this
0x1800d274b  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d2752  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2757  nop
0x1800d2758  lea     rcx, [rbp+230h+var_270]
0x1800d275c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800d2761  jmp     loc_1800D26D2
0x1800d2766  mov     [rbp+230h+cSubKeys], r15d
0x1800d276a  mov     [rsp+330h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800d276f  mov     [rsp+330h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800d2774  mov     [rsp+330h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800d2779  mov     [rsp+330h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800d277e  mov     [rsp+330h+lpcValues], r15; lpcValues
0x1800d2783  mov     [rsp+330h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800d2788  mov     [rsp+330h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800d278d  lea     rax, [rbp+230h+cSubKeys]
0x1800d2791  mov     [rsp+330h+phkResult], rax; lpcSubKeys
0x1800d2796  xor     r9d, r9d; lpReserved
0x1800d2799  xor     r8d, r8d; lpcchClass
0x1800d279c  xor     edx, edx; lpClass
0x1800d279e  mov     rcx, [rsp+330h+hKey]; hKey
0x1800d27a3  call    cs:__imp_RegQueryInfoKeyW
0x1800d27a9  mov     ebx, eax
0x1800d27ab  test    eax, eax
0x1800d27ad  jle     short loc_1800D27B5
0x1800d27af  movzx   ebx, ax
0x1800d27b2  or      ebx, r12d
0x1800d27b5  test    ebx, ebx
0x1800d27b7  jns     short loc_1800D27C3
0x1800d27b9  mov     r9d, ebx
0x1800d27bc  mov     edx, 50Eh
0x1800d27c1  jmp     short loc_1800D2744
0x1800d27c3  mov     esi, r15d
0x1800d27c6  mov     edi, r15d
0x1800d27c9  cmp     edi, [rbp+230h+cSubKeys]
0x1800d27cc  jnb     loc_1800D2908
0x1800d27d2  mov     [rbp+230h+cchName], 104h
0x1800d27d9  mov     [rsp+330h+lpcValues], r15; lpftLastWriteTime
0x1800d27de  mov     [rsp+330h+lpcbMaxClassLen], r15; lpcchClass
0x1800d27e3  mov     [rsp+330h+lpcbMaxSubKeyLen], r15; lpClass
0x1800d27e8  mov     [rsp+330h+phkResult], r15; lpReserved
0x1800d27ed  lea     r9, [rbp+230h+cchName]; lpcchName
0x1800d27f1  lea     r8, [rbp+230h+Name]; lpName
0x1800d27f5  mov     edx, edi; dwIndex
0x1800d27f7  mov     rcx, [rsp+330h+hKey]; hKey
0x1800d27fc  call    cs:__imp_RegEnumKeyExW
0x1800d2802  mov     ebx, eax
0x1800d2804  test    eax, eax
0x1800d2806  jle     short loc_1800D280E
0x1800d2808  movzx   ebx, ax
0x1800d280b  or      ebx, r12d
0x1800d280e  test    ebx, ebx
0x1800d2810  js      loc_1800D28FB
0x1800d2816  mov     [rbp+230h+var_288], r15
0x1800d281a  lea     rax, [rbp+230h+var_288]
0x1800d281e  mov     [rsp+330h+var_2B8], rax
0x1800d2823  mov     [rbp+230h+var_2B0], r15
0x1800d2827  mov     [rbp+230h+var_2A8], 1
0x1800d282b  lea     rax, [rbp+230h+var_2B0]
0x1800d282f  mov     [rsp+330h+phkResult], rax; int
0x1800d2834  mov     r9d, 20119h; samDesired
0x1800d283a  xor     r8d, r8d; ulOptions
0x1800d283d  lea     rdx, [rbp+230h+Name]; lpSubKey
0x1800d2841  mov     rcx, [rsp+330h+hKey]; hKey
0x1800d2846  call    cs:__imp_RegOpenKeyExW
0x1800d284c  mov     ebx, eax
0x1800d284e  test    eax, eax
0x1800d2850  jle     short loc_1800D2858
0x1800d2852  movzx   ebx, ax
0x1800d2855  or      ebx, r12d
0x1800d2858  lea     rcx, [rsp+330h+var_2B8]
0x1800d285d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800d2862  test    ebx, ebx
0x1800d2864  js      short loc_1800D28D2
0x1800d2866  mov     [rbp+230h+var_28C], r15d
0x1800d286a  mov     [rsp+330h+lpftLastWriteTime], r15; lpftLastWriteTime
0x1800d286f  mov     [rsp+330h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x1800d2874  mov     [rsp+330h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x1800d2879  mov     [rsp+330h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x1800d287e  mov     [rsp+330h+lpcValues], r15; lpcValues
0x1800d2883  mov     [rsp+330h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x1800d2888  mov     [rsp+330h+lpcbMaxSubKeyLen], r15; lpcbMaxSubKeyLen
0x1800d288d  lea     rax, [rbp+230h+var_28C]
0x1800d2891  mov     [rsp+330h+phkResult], rax; lpcSubKeys
0x1800d2896  xor     r9d, r9d; lpReserved
0x1800d2899  xor     r8d, r8d; lpcchClass
0x1800d289c  xor     edx, edx; lpClass
0x1800d289e  mov     rcx, [rbp+230h+var_288]; hKey
0x1800d28a2  call    cs:__imp_RegQueryInfoKeyW
0x1800d28a8  mov     ebx, eax
0x1800d28aa  test    eax, eax
0x1800d28ac  jle     short loc_1800D28B4
0x1800d28ae  movzx   ebx, ax
0x1800d28b1  or      ebx, r12d
0x1800d28b4  test    ebx, ebx
0x1800d28b6  js      short loc_1800D28CB
0x1800d28b8  add     esi, [rbp+230h+var_28C]
0x1800d28bb  lea     rcx, [rbp+230h+var_288]
0x1800d28bf  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d28c4  inc     edi
0x1800d28c6  jmp     loc_1800D27C9
0x1800d28cb  mov     edx, 528h
0x1800d28d0  jmp     short loc_1800D28D7
0x1800d28d2  mov     edx, 524h; void *
0x1800d28d7  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d28de  mov     r9d, ebx; char *
0x1800d28e1  mov     rcx, [rbp+238h]; this
0x1800d28e8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d28ed  lea     rcx, [rbp+230h+var_288]
0x1800d28f1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800d28f6  jmp     loc_1800D2758
0x1800d28fb  mov     r9d, ebx
0x1800d28fe  mov     edx, 51Ch
0x1800d2903  jmp     loc_1800D2744
0x1800d2908  mov     [rbp+230h+var_298], r15
0x1800d290c  lea     rax, [rbp+230h+var_270]
0x1800d2910  cmp     [rbp+230h+var_258], 7
0x1800d2915  cmova   rax, [rbp+230h+var_270]
0x1800d291a  lea     rcx, [rbp+230h+var_298]
0x1800d291e  mov     [rsp+330h+var_2B8], rcx
0x1800d2923  mov     [rbp+230h+var_2B0], r15
0x1800d2927  mov     [rbp+230h+var_2A8], 1
0x1800d292b  mov     [rsp+330h+phkResult], rax; int
0x1800d2930  lea     r9, aRegistry_0; "registry"
0x1800d2937  mov     r8d, 2
0x1800d293d  mov     rdx, cs:qword_18018A5F0
0x1800d2944  lea     rcx, [rbp+230h+var_2B0]
0x1800d2948  call    DCStringCchPrintfAllStrings
0x1800d294d  mov     ebx, eax
0x1800d294f  lea     rcx, [rsp+330h+var_2B8]
0x1800d2954  call    ??1?$out_param_t@V?$unique_ptr@GU?$default_delete@G@std@@@std@@@details@wil@@QEAA@XZ; wil::details::out_param_t<std::unique_ptr<ushort>>::~out_param_t<std::unique_ptr<ushort>>(void)
0x1800d2959  test    ebx, ebx
0x1800d295b  jns     short loc_1800D2986
0x1800d295d  mov     rcx, [rbp+238h]; this
0x1800d2964  mov     r9d, ebx; char *
0x1800d2967  lea     r8, aOnecoreuapAdmi_11; "onecoreuap\\admin\\enterprisemgmt\\decl"...
0x1800d296e  mov     edx, 534h; void *
0x1800d2973  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d2978  lea     rcx, [rbp+230h+var_298]
0x1800d297c  call    ??1?$unique_ptr@GU?$default_delete@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort>::~unique_ptr<ushort>(void)
0x1800d2981  jmp     loc_1800D2758
0x1800d2986  mov     [rbp+230h+hKeyDest], r15
0x1800d298a  lea     rax, [rbp+230h+hKeyDest]
0x1800d298e  mov     [rsp+330h+var_2B8], rax
0x1800d2993  mov     [rbp+230h+var_2B0], r15
0x1800d2997  mov     [rbp+230h+var_2A8], 1
0x1800d299b  mov     [rsp+330h+lpcbMaxValueNameLen], r15; lpdwDisposition
0x1800d29a0  lea     rax, [rbp+230h+var_2B0]
0x1800d29a4  mov     [rsp+330h+lpcValues], rax; phkResult
0x1800d29a9  mov     [rsp+330h+lpcbMaxClassLen], r15; lpSecurityAttributes
0x1800d29ae  mov     dword ptr [rsp+330h+lpcbMaxSubKeyLen], 0F003Fh; samDesired
0x1800d29b6  mov     dword ptr [rsp+330h+phkResult], r15d; int
0x1800d29bb  xor     r9d, r9d; lpClass
  ... truncated ...
```
