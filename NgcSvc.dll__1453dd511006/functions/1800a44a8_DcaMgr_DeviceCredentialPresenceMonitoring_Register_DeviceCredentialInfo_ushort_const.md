# DcaMgr::DeviceCredentialPresenceMonitoring::Register(_DeviceCredentialInfo *,ushort const *)

- ea: `0x1800a44a8`
- end: `0x1800a4c27`
- name: `?Register@DeviceCredentialPresenceMonitoring@DcaMgr@@SAJPEAU_DeviceCredentialInfo@@PEBG@Z`
- size: `1919`
- prototype: `__int64 __fastcall(BYTE *lpData, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009fbe0`

## callees

- `0x18000782c`
- `0x18000926c`
- `0x1800281e0`
- `0x1800323d0`
- `0x180032c20`
- `0x180048304`
- `0x180050b30`
- `0x1800535f4`
- `0x18005b5e0`
- `0x18005cee0`
- `0x180069c28`
- `0x180097c6c`
- `0x180097cb4`
- `0x1800a41ac`
- `0x1800a4334`
- `0x1800a43a8`
- `0x1800a4444`
- `0x1800a447c`
- `0x1800a44a8`
- `0x1800a5164`
- `0x1800a6408`
- `0x1800a6d30`
- `0x1800a7b74`
- `0x1800a7bd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a4734`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a47c7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a4734`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800a47c7`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a483a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800a483a`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800a4b65`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800a4b65`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4933`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4a47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4a84`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4ae0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4b49`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4933`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4a47`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4a84`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4ae0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800a4b49`
- `NaturalAuthClient!CdfPluginRegisterDevice` at `0x1800a4b7d`
- `NaturalAuthClient!CdfPluginRegisterDevice` at `0x1800a4b7d`

## string_xrefs

- `0x1800a4a9e`: `DeviceInstancePath`
- `0x1800a496a`: `UserSid`
- `0x1800a4ad4`: `ProtocolVersion`
- `0x1800a450d`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x1800a45f5`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x1800a46b3`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x1800a4753`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x1800a47e4`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x1800a4881`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x1800a48ef`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x1800a4947`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall DcaMgr::DeviceCredentialPresenceMonitoring::Register(BYTE *lpData, const unsigned __int16 *a2)
{
  unsigned int v4; // edx
  int v5; // eax
  unsigned int v6; // edx
  DcaMgr *v7; // rcx
  int UserSidAndPackageInfoFromToken; // ebx
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 v11; // rcx
  __int64 v12; // rcx
  int v13; // eax
  unsigned int v14; // ebx
  unsigned int v15; // ebx
  const unsigned __int16 *v16; // r9
  __int64 v17; // r9
  __int64 v18; // rdx
  unsigned int v19; // ecx
  __int64 v20; // rdx
  unsigned __int64 v21; // r9
  __int64 v22; // rdx
  unsigned int v23; // eax
  int v24; // eax
  int v25; // eax
  int v26; // eax
  const WCHAR *v27; // r9
  int v28; // eax
  unsigned int v29; // eax
  unsigned int v30; // eax
  int v31; // eax
  unsigned int v32; // eax
  int v33; // eax
  unsigned int v34; // eax
  int dwOptions; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-E0h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-E0h]
  int dwOptionsc; // [rsp+20h] [rbp-E0h]
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  LPCVOID v41; // [rsp+58h] [rbp-A8h] BYREF
  HKEY v42; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE TokenHandle; // [rsp+68h] [rbp-98h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-90h] BYREF
  LPCVOID v45; // [rsp+78h] [rbp-88h] BYREF
  BYTE Data[8]; // [rsp+80h] [rbp-80h] BYREF
  void *p_hKey; // [rsp+88h] [rbp-78h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp-70h] BYREF
  char v49; // [rsp+98h] [rbp-68h]
  DWORD dwDisposition; // [rsp+A0h] [rbp-60h] BYREF
  DWORD cbData; // [rsp+A4h] [rbp-5Ch] BYREF
  BYTE *lpDataa; // [rsp+A8h] [rbp-58h] BYREF
  DWORD pcbData; // [rsp+B0h] [rbp-50h] BYREF
  void *p_TokenHandle; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v55; // [rsp+C0h] [rbp-40h] BYREF
  char v56; // [rsp+C8h] [rbp-38h]
  _QWORD v57[2]; // [rsp+D0h] [rbp-30h] BYREF
  char v58; // [rsp+E0h] [rbp-20h]
  _BYTE v59[336]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+278h] [rbp+178h]

  DevCredSvcTraceLoggingProvider::RegisterPresenceMonitoring::Start<>((DevCredSvcTraceLoggingProvider::RegisterPresenceMonitoring *)v59);
  v5 = DcaMgr::ValidateProtocolVersion((DcaMgr *)*(unsigned int *)lpData, v4);
  UserSidAndPackageInfoFromToken = v5;
  if ( v5 >= 0 )
  {
    v5 = DcaMgr::ValidatePolicy(v7, v6);
    UserSidAndPackageInfoFromToken = v5;
    if ( v5 < 0 )
    {
      v9 = 35;
      goto LABEL_5;
    }
    if ( !*((_DWORD *)lpData + 12) )
    {
      UserSidAndPackageInfoFromToken = -2147024809;
      v10 = 2147942487LL;
      v9 = 39;
      goto LABEL_6;
    }
    v5 = ValidateInputString(*((_QWORD *)lpData + 1), 40);
    UserSidAndPackageInfoFromToken = v5;
    if ( v5 < 0 )
    {
      v9 = 43;
      goto LABEL_5;
    }
    v5 = ValidateInputString(*((_QWORD *)lpData + 2), 64);
    UserSidAndPackageInfoFromToken = v5;
    if ( v5 < 0 )
    {
      v9 = 47;
      goto LABEL_5;
    }
    v11 = *((_QWORD *)lpData + 3);
    if ( v11 )
    {
      v5 = ValidateInputString(v11, 32);
      UserSidAndPackageInfoFromToken = v5;
      if ( v5 < 0 )
      {
        v9 = 53;
        goto LABEL_5;
      }
    }
    v5 = ValidateInputString(a2, 512);
    UserSidAndPackageInfoFromToken = v5;
    if ( v5 < 0 )
    {
      v9 = 58;
      goto LABEL_5;
    }
    v13 = *((_DWORD *)lpData + 10);
    if ( *((_QWORD *)lpData + 4) )
    {
      if ( (unsigned int)(v13 - 1) <= 0xFFF )
      {
LABEL_20:
        TokenHandle = 0;
        p_TokenHandle = &TokenHandle;
        v55 = 0;
        v56 = 1;
        UserSidAndPackageInfoFromToken = OpenCallerImpersonationToken(v12, &v55);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
        if ( UserSidAndPackageInfoFromToken < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x44,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
            (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
            dwOptions);
LABEL_22:
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          goto LABEL_75;
        }
        v42 = 0;
        v41 = 0;
        v45 = 0;
        p_hKey = &v45;
        phkResult = 0;
        v49 = 1;
        v57[0] = &v41;
        v57[1] = 0;
        v58 = 1;
        p_TokenHandle = &v42;
        v55 = 0;
        v56 = 1;
        UserSidAndPackageInfoFromToken = GetUserSidAndPackageInfoFromToken(TokenHandle);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_TokenHandle);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v57);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
        if ( UserSidAndPackageInfoFromToken < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x4D,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
            (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
            dwOptions);
LABEL_27:
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v45);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v41);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v42);
          goto LABEL_22;
        }
        hKey = 0;
        p_hKey = &hKey;
        phkResult = 0;
        v49 = 1;
        v14 = RegCreateKeyExW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor\\Devices",
                0,
                0,
                0,
                0xF003Fu,
                0,
                &phkResult,
                0);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
        if ( v14 )
        {
          UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_Win32(
                                             retaddr,
                                             (void *)0x5A,
                                             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\device"
                                                           "credentialpresence.cpp",
                                             (const char *)v14,
                                             dwOptionsa);
LABEL_30:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          goto LABEL_27;
        }
        *(_DWORD *)Data = 0;
        pcbData = 0;
        dwDisposition = 0;
        hkey = 0;
        p_hKey = &hkey;
        phkResult = 0;
        v49 = 1;
        v15 = RegCreateKeyExW(hKey, *((LPCWSTR *)lpData + 1), 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
        if ( v15 )
        {
          v17 = v15;
          v18 = 106;
LABEL_33:
          UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_Win32(
                                             retaddr,
                                             (void *)v18,
                                             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\device"
                                                           "credentialpresence.cpp",
                                             (const char *)v17,
                                             dwOptionsb);
LABEL_34:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          goto LABEL_30;
        }
        hKey = 0;
        if ( dwDisposition == 2 && !RegGetValueW(hkey, 0, L"AuthKey", 8u, 0, 0, &pcbData) )
        {
          v17 = 183;
          v18 = 120;
          goto LABEL_33;
        }
        UserSidAndPackageInfoFromToken = DcaMgr::ValidateOwnership(hkey, v42, (const unsigned __int16 *)v41, v16);
        v19 = UserSidAndPackageInfoFromToken + 0x80000000;
        if ( (int)(UserSidAndPackageInfoFromToken + 0x80000000) >= 0 && UserSidAndPackageInfoFromToken != -2147024894 )
        {
          v20 = 131;
          goto LABEL_41;
        }
        v22 = *((_QWORD *)lpData + 4);
        if ( v22 )
        {
          lpDataa = 0;
          cbData = 0;
          p_hKey = &lpDataa;
          phkResult = 0;
          v49 = 1;
          LOBYTE(v19) = 1;
          UserSidAndPackageInfoFromToken = DpapiProtectUnprotect(
                                             v19,
                                             v22,
                                             *((_DWORD *)lpData + 10),
                                             (unsigned int)&phkResult,
                                             (__int64)&cbData);
          wil::details::out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<unsigned char,wil::hlocal_secure_deleter>>(&p_hKey);
          if ( UserSidAndPackageInfoFromToken < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x90,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
              (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
              dwOptionsc);
LABEL_46:
            wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&lpDataa);
            goto LABEL_34;
          }
          v23 = RegSetValueExW(hkey, L"OpaqueBlob", 0, 3u, lpDataa, cbData);
          if ( v23 )
          {
            UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_Win32(
                                               retaddr,
                                               (void *)0x98,
                                               (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devi"
                                                             "cecredentialpresence.cpp",
                                               (const char *)v23,
                                               dwOptionsb);
            goto LABEL_46;
          }
          wistd::unique_ptr<unsigned char [0],wil::hlocal_secure_deleter>::reset(&lpDataa);
        }
        v24 = WriteRegStringValue(hkey, 0, (char *)L"UserSid", v42);
        UserSidAndPackageInfoFromToken = v24;
        if ( v24 < 0 )
        {
          v21 = (unsigned int)v24;
          v20 = 159;
          goto LABEL_42;
        }
        v25 = WriteRegStringValue(hkey, 0, (char *)L"AppId", v41);
        UserSidAndPackageInfoFromToken = v25;
        if ( v25 < 0 )
        {
          v21 = (unsigned int)v25;
          v20 = 165;
          goto LABEL_42;
        }
        v26 = WriteRegStringValue(hkey, 0, (char *)L"FriendlyName", *((LPCVOID *)lpData + 2));
        UserSidAndPackageInfoFromToken = v26;
        if ( v26 < 0 )
        {
          v21 = (unsigned int)v26;
          v20 = 171;
          goto LABEL_42;
        }
        v27 = &sourceString;
        if ( *((_QWORD *)lpData + 3) )
          v27 = (const WCHAR *)*((_QWORD *)lpData + 3);
        v28 = WriteRegStringValue(hkey, 0, (char *)L"ModelNumber", v27);
        UserSidAndPackageInfoFromToken = v28;
        if ( v28 < 0 )
        {
          v21 = (unsigned int)v28;
          v20 = 182;
          goto LABEL_42;
        }
        *(_DWORD *)Data = *((_DWORD *)lpData + 11);
        v29 = RegSetValueExW(hkey, L"DeviceCapability", 0, 4u, Data, 4u);
        if ( v29 )
        {
          v17 = v29;
          v18 = 191;
          goto LABEL_33;
        }
        *(_DWORD *)Data = *((_DWORD *)lpData + 12);
        v30 = RegSetValueExW(hkey, L"PresenceMonitoringMode", 0, 4u, Data, 4u);
        if ( v30 )
        {
          v17 = v30;
          v18 = 200;
          goto LABEL_33;
        }
        v31 = WriteRegStringValue(hkey, 0, (char *)L"DeviceInstancePath", a2);
        UserSidAndPackageInfoFromToken = v31;
        if ( v31 < 0 )
        {
          v21 = (unsigned int)v31;
          v20 = 206;
          goto LABEL_42;
        }
        v32 = RegSetValueExW(hkey, L"ProtocolVersion", 0, 4u, lpData, 4u);
        if ( v32 )
        {
          v17 = v32;
          v18 = 214;
          goto LABEL_33;
        }
        v33 = WriteRegStringValue(hkey, 0, (char *)L"PackageFullName", v45);
        UserSidAndPackageInfoFromToken = v33;
        if ( v33 < 0 )
        {
          v21 = (unsigned int)v33;
          v20 = 220;
          goto LABEL_42;
        }
        *(_DWORD *)Data = 1;
        v34 = RegSetValueExW(hkey, L"State", 0, 4u, Data, 4u);
        if ( v34 )
        {
          v17 = v34;
          v18 = 229;
          goto LABEL_33;
        }
        RegFlushKey(hkey);
        hkey = 0;
        UserSidAndPackageInfoFromToken = CdfPluginRegisterDevice(a2, *((_DWORD *)lpData + 12) != 1);
        if ( UserSidAndPackageInfoFromToken >= 0 )
        {
          DevCredSvcTraceLoggingProvider::RegisterPresenceMonitoring::Stop(
            v59,
            0,
            v41,
            *((_QWORD *)lpData + 1),
            *((_DWORD *)lpData + 12));
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v45);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v41);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v42);
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          UserSidAndPackageInfoFromToken = 0;
          goto LABEL_75;
        }
        DcaMgr::DeviceCredentialPresenceMonitoring::Unregister(*((LPCWSTR *)lpData + 1));
        v20 = 241;
LABEL_41:
        v21 = (unsigned int)UserSidAndPackageInfoFromToken;
LABEL_42:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v20,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
          (const char *)v21,
          dwOptionsb);
        goto LABEL_34;
      }
    }
    else if ( !v13 )
    {
      goto LABEL_20;
    }
    UserSidAndPackageInfoFromToken = -2147024809;
    v10 = 2147942487LL;
    v9 = 63;
    goto LABEL_6;
  }
  v9 = 34;
LABEL_5:
  v10 = (unsigned int)v5;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
    (const char *)v10,
    dwOptions);
LABEL_75:
  DevCredSvcTraceLoggingProvider::RegisterPresenceMonitoring::~RegisterPresenceMonitoring((DevCredSvcTraceLoggingProvider::RegisterPresenceMonitoring *)v59);
  return (unsigned int)UserSidAndPackageInfoFromToken;
}

```

## disassembly

```asm
0x1800a44a8  mov     [rsp-8+arg_10], rbx
0x1800a44ad  push    rbp
0x1800a44ae  push    rsi
0x1800a44af  push    rdi
0x1800a44b0  push    r14
0x1800a44b2  push    r15
0x1800a44b4  lea     rbp, [rsp-150h]
0x1800a44bc  sub     rsp, 250h
0x1800a44c3  mov     rax, cs:__security_cookie
0x1800a44ca  xor     rax, rsp
0x1800a44cd  mov     [rbp+170h+var_30], rax
0x1800a44d4  mov     rsi, rdx
0x1800a44d7  mov     rdi, rcx
0x1800a44da  lea     rcx, [rbp+170h+var_180]; this
0x1800a44de  call    ??$Start@$$V@RegisterPresenceMonitoring@DevCredSvcTraceLoggingProvider@@SA?AV01@XZ; DevCredSvcTraceLoggingProvider::RegisterPresenceMonitoring::Start<>(void)
0x1800a44e3  nop
0x1800a44e4  mov     ecx, [rdi]; this
0x1800a44e6  call    ?ValidateProtocolVersion@DcaMgr@@YAJK@Z; DcaMgr::ValidateProtocolVersion(ulong)
0x1800a44eb  mov     ebx, eax
0x1800a44ed  xor     r14d, r14d
0x1800a44f0  test    eax, eax
0x1800a44f2  jns     short loc_1800A44FA
0x1800a44f4  lea     edx, [r14+22h]
0x1800a44f8  jmp     short loc_1800A450A
0x1800a44fa  call    ?ValidatePolicy@DcaMgr@@YAJK@Z; DcaMgr::ValidatePolicy(ulong)
0x1800a44ff  mov     ebx, eax
0x1800a4501  test    eax, eax
0x1800a4503  jns     short loc_1800A4525
0x1800a4505  mov     edx, 23h ; '#'; void *
0x1800a450a  mov     r9d, eax; char *
0x1800a450d  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x1800a4514  mov     rcx, [rbp+178h]; this
0x1800a451b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4520  jmp     loc_1800A4BF6
0x1800a4525  cmp     [rdi+30h], r14d
0x1800a4529  jnz     short loc_1800A453A
0x1800a452b  mov     ebx, 80070057h
0x1800a4530  mov     r9d, ebx
0x1800a4533  mov     edx, 27h ; '''
0x1800a4538  jmp     short loc_1800A450D
0x1800a453a  mov     edx, 28h ; '('
0x1800a453f  mov     rcx, [rdi+8]
0x1800a4543  call    ValidateInputString
0x1800a4548  mov     ebx, eax
0x1800a454a  test    eax, eax
0x1800a454c  jns     short loc_1800A4555
0x1800a454e  mov     edx, 2Bh ; '+'
0x1800a4553  jmp     short loc_1800A450A
0x1800a4555  mov     edx, 40h ; '@'
0x1800a455a  mov     rcx, [rdi+10h]
0x1800a455e  call    ValidateInputString
0x1800a4563  mov     ebx, eax
0x1800a4565  test    eax, eax
0x1800a4567  jns     short loc_1800A4570
0x1800a4569  mov     edx, 2Fh ; '/'
0x1800a456e  jmp     short loc_1800A450A
0x1800a4570  mov     rcx, [rdi+18h]
0x1800a4574  test    rcx, rcx
0x1800a4577  jz      short loc_1800A4593
0x1800a4579  mov     edx, 20h ; ' '
0x1800a457e  call    ValidateInputString
0x1800a4583  mov     ebx, eax
0x1800a4585  test    eax, eax
0x1800a4587  jns     short loc_1800A4593
0x1800a4589  mov     edx, 35h ; '5'
0x1800a458e  jmp     loc_1800A450A
0x1800a4593  mov     edx, 200h
0x1800a4598  mov     rcx, rsi
0x1800a459b  call    ValidateInputString
0x1800a45a0  mov     ebx, eax
0x1800a45a2  test    eax, eax
0x1800a45a4  jns     short loc_1800A45B0
0x1800a45a6  mov     edx, 3Ah ; ':'
0x1800a45ab  jmp     loc_1800A450A
0x1800a45b0  mov     eax, [rdi+28h]
0x1800a45b3  cmp     [rdi+20h], r14
0x1800a45b7  jnz     short loc_1800A4615
0x1800a45b9  test    eax, eax
0x1800a45bb  jnz     short loc_1800A461E
0x1800a45bd  mov     [rsp+270h+TokenHandle], r14
0x1800a45c2  lea     rax, [rsp+270h+TokenHandle]
0x1800a45c7  mov     [rbp+170h+var_1B8], rax
0x1800a45cb  mov     [rbp+170h+var_1B0], r14
0x1800a45cf  mov     [rbp+170h+var_1A8], 1
0x1800a45d3  lea     rdx, [rbp+170h+var_1B0]
0x1800a45d7  call    OpenCallerImpersonationToken
0x1800a45dc  mov     ebx, eax
0x1800a45de  lea     rcx, [rbp+170h+var_1B8]
0x1800a45e2  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1800a45e7  test    ebx, ebx
0x1800a45e9  jns     short loc_1800A4630
0x1800a45eb  mov     rcx, [rbp+178h]; this
0x1800a45f2  mov     r9d, ebx; char *
0x1800a45f5  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x1800a45fc  mov     edx, 44h ; 'D'; void *
0x1800a4601  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4606  lea     rcx, [rsp+270h+TokenHandle]
0x1800a460b  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800a4610  jmp     loc_1800A4BF6
0x1800a4615  dec     eax
0x1800a4617  cmp     eax, 0FFFh
0x1800a461c  jbe     short loc_1800A45BD
0x1800a461e  mov     ebx, 80070057h
0x1800a4623  mov     r9d, ebx
0x1800a4626  mov     edx, 3Fh ; '?'
0x1800a462b  jmp     loc_1800A450D
0x1800a4630  mov     [rsp+270h+var_210], r14
0x1800a4635  mov     [rsp+270h+var_218], r14
0x1800a463a  mov     [rsp+270h+var_1F8], r14
0x1800a463f  lea     rax, [rsp+270h+var_1F8]
0x1800a4644  mov     [rbp+170h+var_1E8], rax
0x1800a4648  mov     [rbp+170h+var_1E0], r14
0x1800a464c  mov     [rbp+170h+var_1D8], 1
0x1800a4650  lea     rax, [rsp+270h+var_218]
0x1800a4655  mov     [rbp+170h+var_1A0], rax
0x1800a4659  mov     [rbp+170h+var_198], r14
0x1800a465d  mov     [rbp+170h+var_190], 1
0x1800a4661  lea     rax, [rsp+270h+var_210]
0x1800a4666  mov     [rbp+170h+var_1B8], rax
0x1800a466a  mov     [rbp+170h+var_1B0], r14
0x1800a466e  mov     [rbp+170h+var_1A8], 1
0x1800a4672  lea     r9, [rbp+170h+var_1E0]
0x1800a4676  lea     r8, [rbp+170h+var_198]
0x1800a467a  lea     rdx, [rbp+170h+var_1B0]
0x1800a467e  mov     rcx, [rsp+270h+TokenHandle]; TokenHandle
0x1800a4683  call    GetUserSidAndPackageInfoFromToken
0x1800a4688  mov     ebx, eax
0x1800a468a  lea     rcx, [rbp+170h+var_1B8]
0x1800a468e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a4693  lea     rcx, [rbp+170h+var_1A0]
0x1800a4697  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a469c  lea     rcx, [rbp+170h+var_1E8]
0x1800a46a0  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800a46a5  test    ebx, ebx
0x1800a46a7  jns     short loc_1800A46E7
0x1800a46a9  mov     rcx, [rbp+178h]; this
0x1800a46b0  mov     r9d, ebx; char *
0x1800a46b3  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x1800a46ba  mov     edx, 4Dh ; 'M'; void *
0x1800a46bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a46c4  lea     rcx, [rsp+270h+var_1F8]; void *
0x1800a46c9  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a46ce  lea     rcx, [rsp+270h+var_218]; void *
0x1800a46d3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a46d8  lea     rcx, [rsp+270h+var_210]; void *
0x1800a46dd  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800a46e2  jmp     loc_1800A4606
0x1800a46e7  mov     [rsp+270h+hKey], r14
0x1800a46ec  lea     rax, [rsp+270h+hKey]
0x1800a46f1  mov     [rbp+170h+var_1E8], rax
0x1800a46f5  mov     [rbp+170h+var_1E0], r14
0x1800a46f9  mov     [rbp+170h+var_1D8], 1
0x1800a46fd  mov     [rsp+270h+lpdwDisposition], r14; lpdwDisposition
0x1800a4702  lea     rax, [rbp+170h+var_1E0]
0x1800a4706  mov     [rsp+270h+phkResult], rax; phkResult
0x1800a470b  mov     [rsp+270h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800a4710  mov     r15d, 0F003Fh
0x1800a4716  mov     [rsp+270h+samDesired], r15d; samDesired
0x1800a471b  mov     [rsp+270h+dwOptions], r14d; unsigned int
0x1800a4720  xor     r9d, r9d; lpClass
0x1800a4723  xor     r8d, r8d; Reserved
0x1800a4726  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800a472d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a4734  call    cs:__imp_RegCreateKeyExW
0x1800a473a  mov     ebx, eax
0x1800a473c  lea     rcx, [rbp+170h+var_1E8]
0x1800a4740  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800a4745  test    ebx, ebx
0x1800a4747  jz      short loc_1800A4775
0x1800a4749  mov     rcx, [rbp+178h]; this
0x1800a4750  mov     r9d, ebx; char *
0x1800a4753  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x1800a475a  mov     edx, 5Ah ; 'Z'; void *
0x1800a475f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a4764  mov     ebx, eax
0x1800a4766  lea     rcx, [rsp+270h+hKey]
0x1800a476b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a4770  jmp     loc_1800A46C4
0x1800a4775  mov     dword ptr [rbp+170h+Data], r14d
0x1800a4779  mov     [rbp+170h+pcbData], r14d
0x1800a477d  mov     [rbp+170h+dwDisposition], r14d
0x1800a4781  mov     [rsp+270h+hkey], r14
0x1800a4786  lea     rax, [rsp+270h+hkey]
0x1800a478b  mov     [rbp+170h+var_1E8], rax
0x1800a478f  mov     [rbp+170h+var_1E0], r14
0x1800a4793  mov     [rbp+170h+var_1D8], 1
0x1800a4797  lea     rax, [rbp+170h+dwDisposition]
0x1800a479b  mov     [rsp+270h+lpdwDisposition], rax; lpdwDisposition
0x1800a47a0  lea     rax, [rbp+170h+var_1E0]
0x1800a47a4  mov     [rsp+270h+phkResult], rax; phkResult
0x1800a47a9  mov     [rsp+270h+lpSecurityAttributes], r14; lpSecurityAttributes
0x1800a47ae  mov     [rsp+270h+samDesired], r15d; samDesired
0x1800a47b3  mov     [rsp+270h+dwOptions], r14d; int
0x1800a47b8  xor     r9d, r9d; lpClass
0x1800a47bb  xor     r8d, r8d; Reserved
0x1800a47be  mov     rdx, [rdi+8]; lpSubKey
0x1800a47c2  mov     rcx, [rsp+270h+hKey]; hKey
0x1800a47c7  call    cs:__imp_RegCreateKeyExW
0x1800a47cd  mov     ebx, eax
0x1800a47cf  lea     rcx, [rbp+170h+var_1E8]
0x1800a47d3  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800a47d8  test    ebx, ebx
0x1800a47da  jz      short loc_1800A4808
0x1800a47dc  mov     r9d, ebx; char *
0x1800a47df  mov     edx, 6Ah ; 'j'; void *
0x1800a47e4  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x1800a47eb  mov     rcx, [rbp+178h]; this
0x1800a47f2  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a47f7  mov     ebx, eax
0x1800a47f9  lea     rcx, [rsp+270h+hkey]
0x1800a47fe  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800a4803  jmp     loc_1800A4766
0x1800a4808  mov     [rsp+270h+hKey], r14
0x1800a480d  cmp     [rbp+170h+dwDisposition], 2
0x1800a4811  jnz     short loc_1800A484F
0x1800a4813  lea     rax, [rbp+170h+pcbData]
0x1800a4817  mov     [rsp+270h+lpSecurityAttributes], rax; pcbData
0x1800a481c  mov     qword ptr [rsp+270h+samDesired], r14; pvData
0x1800a4821  mov     qword ptr [rsp+270h+dwOptions], r14; pdwType
0x1800a4826  mov     r9d, 8; dwFlags
0x1800a482c  lea     r8, aAuthkey; "AuthKey"
0x1800a4833  xor     edx, edx; lpSubKey
0x1800a4835  mov     rcx, [rsp+270h+hkey]; hkey
0x1800a483a  call    cs:__imp_RegGetValueW
0x1800a4840  test    eax, eax
0x1800a4842  jnz     short loc_1800A484F
0x1800a4844  mov     r9d, 0B7h
0x1800a484a  lea     edx, [rax+78h]
0x1800a484d  jmp     short loc_1800A47E4
0x1800a484f  mov     r8, [rsp+270h+var_218]; unsigned __int16 *
0x1800a4854  mov     rdx, [rsp+270h+var_210]; HKEY
0x1800a4859  mov     rcx, [rsp+270h+hkey]; hkey
0x1800a485e  call    ?ValidateOwnership@DcaMgr@@YAJPEAUHKEY__@@PEBG1@Z; DcaMgr::ValidateOwnership(HKEY__ *,ushort const *,ushort const *)
0x1800a4863  mov     ebx, eax
0x1800a4865  mov     eax, 80000000h
0x1800a486a  lea     ecx, [rbx+rax]
0x1800a486d  test    eax, ecx
0x1800a486f  jnz     short loc_1800A4899
0x1800a4871  cmp     ebx, 80070002h
0x1800a4877  jz      short loc_1800A4899
0x1800a4879  mov     edx, 83h; void *
0x1800a487e  mov     r9d, ebx; char *
0x1800a4881  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x1800a4888  mov     rcx, [rbp+178h]; this
0x1800a488f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4894  jmp     loc_1800A47F9
0x1800a4899  mov     rdx, [rdi+20h]
0x1800a489d  test    rdx, rdx
0x1800a48a0  jz      loc_1800A4965
0x1800a48a6  mov     [rbp+170h+lpData], r14
0x1800a48aa  mov     [rbp+170h+cbData], r14d
0x1800a48ae  lea     rax, [rbp+170h+lpData]
0x1800a48b2  mov     [rbp+170h+var_1E8], rax
0x1800a48b6  mov     [rbp+170h+var_1E0], r14
0x1800a48ba  mov     [rbp+170h+var_1D8], 1
0x1800a48be  lea     rax, [rbp+170h+cbData]
0x1800a48c2  mov     qword ptr [rsp+270h+dwOptions], rax; int
0x1800a48c7  lea     r9, [rbp+170h+var_1E0]
0x1800a48cb  mov     r8d, [rdi+28h]
0x1800a48cf  mov     cl, 1
0x1800a48d1  call    DpapiProtectUnprotect
0x1800a48d6  mov     ebx, eax
0x1800a48d8  lea     rcx, [rbp+170h+var_1E8]
0x1800a48dc  call    ??1?$out_param_t@V?$unique_ptr@EUhlocal_secure_deleter@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>::~out_param_t<wistd::unique_ptr<uchar,wil::hlocal_secure_deleter>>(void)
0x1800a48e1  test    ebx, ebx
0x1800a48e3  jns     short loc_1800A490E
0x1800a48e5  mov     rcx, [rbp+178h]; this
0x1800a48ec  mov     r9d, ebx; char *
0x1800a48ef  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x1800a48f6  mov     edx, 90h; void *
0x1800a48fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4900  lea     rcx, [rbp+170h+lpData]
0x1800a4904  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a4909  jmp     loc_1800A47F9
0x1800a490e  mov     rdx, [rbp+170h+lpData]
0x1800a4912  mov     eax, [rbp+170h+cbData]
0x1800a4915  mov     [rsp+270h+samDesired], eax; cbData
0x1800a4919  mov     qword ptr [rsp+270h+dwOptions], rdx; unsigned int
0x1800a491e  mov     r9d, 3; dwType
0x1800a4924  xor     r8d, r8d; Reserved
0x1800a4927  lea     rdx, aOpaqueblob; "OpaqueBlob"
0x1800a492e  mov     rcx, [rsp+270h+hkey]; hKey
0x1800a4933  call    cs:__imp_RegSetValueExW
0x1800a4939  test    eax, eax
0x1800a493b  jz      short loc_1800A495C
0x1800a493d  mov     rcx, [rbp+178h]; this
0x1800a4944  mov     r9d, eax; char *
0x1800a4947  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x1800a494e  mov     edx, 98h; void *
0x1800a4953  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800a4958  mov     ebx, eax
0x1800a495a  jmp     short loc_1800A4900
0x1800a495c  lea     rcx, [rbp+170h+lpData]
0x1800a4960  call    ?reset@?$unique_ptr@$$BY0A@EUhlocal_secure_deleter@wil@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wil::hlocal_secure_deleter>::reset(std::nullptr_t)
0x1800a4965  mov     r9, [rsp+270h+var_210]; lpData
0x1800a496a  lea     r8, aUsersid; "UserSid"
0x1800a4971  xor     edx, edx; lpSubKey
0x1800a4973  mov     rcx, [rsp+270h+hkey]; hKey
0x1800a4978  call    WriteRegStringValue
0x1800a497d  mov     ebx, eax
  ... truncated ...
```
