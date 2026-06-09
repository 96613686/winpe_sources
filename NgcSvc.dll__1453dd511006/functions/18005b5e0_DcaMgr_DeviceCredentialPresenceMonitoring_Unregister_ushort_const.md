# DcaMgr::DeviceCredentialPresenceMonitoring::Unregister(ushort const *)

- ea: `0x18005b5e0`
- end: `0x18005b9d8`
- name: `?Unregister@DeviceCredentialPresenceMonitoring@DcaMgr@@SAJPEBG@Z`
- size: `1016`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey)`
- caller_count: `3`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18009fe40`
- `0x1800a44a8`
- `0x1800a4c30`

## callees

- `0x18000782c`
- `0x18000926c`
- `0x1800281e0`
- `0x1800323d0`
- `0x180032b6c`
- `0x180032c20`
- `0x180047228`
- `0x180048304`
- `0x1800535f4`
- `0x1800596ec`
- `0x18005b5e0`
- `0x18005bce8`
- `0x180097c6c`
- `0x180097cb4`
- `0x1800a41ac`
- `0x1800a6d30`
- `0x1800a7b74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b661`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b6a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b661`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18005b6a3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005b7e3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005b7e3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005b892`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005b892`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005b8e8`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x18005b8e8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b945`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b972`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b945`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18005b972`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005b8b2`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18005b8b2`
- `NaturalAuthClient!CdfPluginUnregisterDevice` at `0x18005b84a`
- `NaturalAuthClient!CdfPluginUnregisterDevice` at `0x18005b84a`

## string_xrefs

- `0x18005b803`: `DeviceInstancePath`
- `0x18005b96b`: `DeviceInstancePath`
- `0x18005b60d`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x18005b6ec`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x18005b76e`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x18005b821`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x18005b858`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x18005b8c0`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x18005b953`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x18005b980`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`
- `0x18005b9bf`: `onecore\ds\security\devicecredential\service\lib\devicecredentialpresence.cpp`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredentialPresenceMonitoring::Unregister(LPCWSTR lpSubKey)
{
  int v2; // eax
  int UserSidAndPackageInfoFromToken; // ebx
  char v4; // di
  __int64 v5; // rcx
  const unsigned __int16 *v6; // r9
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  int v9; // eax
  int v10; // ebx
  LSTATUS v11; // eax
  int RegStringValue; // eax
  int v13; // eax
  unsigned int v14; // eax
  HKEY v15; // rcx
  unsigned int v17; // eax
  unsigned int v18; // eax
  bool v19; // sf
  int phkResult; // [rsp+20h] [rbp-49h]
  int phkResulta; // [rsp+20h] [rbp-49h]
  int phkResultb; // [rsp+20h] [rbp-49h]
  unsigned int phkResultc; // [rsp+20h] [rbp-49h]
  HANDLE TokenHandle; // [rsp+40h] [rbp-29h] BYREF
  unsigned __int16 *v25; // [rsp+48h] [rbp-21h] BYREF
  HKEY v26; // [rsp+50h] [rbp-19h] BYREF
  void *p_hKey; // [rsp+58h] [rbp-11h] BYREF
  HKEY v28; // [rsp+60h] [rbp-9h] BYREF
  char v29; // [rsp+68h] [rbp-1h]
  __int64 v30; // [rsp+70h] [rbp+7h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+Fh] BYREF
  unsigned __int16 **v32; // [rsp+80h] [rbp+17h] BYREF
  __int64 v33; // [rsp+88h] [rbp+1Fh]
  char v34; // [rsp+90h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  int Data; // [rsp+D8h] [rbp+6Fh] BYREF
  DWORD cbData; // [rsp+E0h] [rbp+77h] BYREF
  HKEY hkey; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = ValidateInputString(lpSubKey, 40);
  UserSidAndPackageInfoFromToken = v2;
  if ( v2 >= 0 )
  {
    hKey = 0;
    p_hKey = &hKey;
    hkey = 0;
    v4 = 1;
    v28 = 0;
    v29 = 1;
    UserSidAndPackageInfoFromToken = RegOpenKeyExW(
                                       HKEY_LOCAL_MACHINE,
                                       L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor\\Devices",
                                       0,
                                       0xF003Fu,
                                       &v28);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( UserSidAndPackageInfoFromToken
      || (p_hKey = &hkey,
          v28 = 0,
          v29 = 1,
          UserSidAndPackageInfoFromToken = RegOpenKeyExW(hKey, lpSubKey, 0, 0xF003Fu, &v28),
          wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey),
          UserSidAndPackageInfoFromToken) )
    {
      if ( UserSidAndPackageInfoFromToken != 2 )
      {
        v19 = UserSidAndPackageInfoFromToken < 0;
        if ( UserSidAndPackageInfoFromToken > 0 )
        {
          UserSidAndPackageInfoFromToken = (unsigned __int16)UserSidAndPackageInfoFromToken | 0x80070000;
          v19 = UserSidAndPackageInfoFromToken < 0;
        }
        if ( v19 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x180,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
            (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
            phkResulta);
        goto LABEL_27;
      }
    }
    else
    {
      TokenHandle = 0;
      p_hKey = &TokenHandle;
      v28 = 0;
      v29 = 1;
      UserSidAndPackageInfoFromToken = OpenCallerImpersonationToken(v5, &v28);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hKey);
      if ( UserSidAndPackageInfoFromToken < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x189,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
          (const char *)(unsigned int)UserSidAndPackageInfoFromToken,
          phkResulta);
LABEL_7:
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
LABEL_27:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        return (unsigned int)UserSidAndPackageInfoFromToken;
      }
      v32 = &v25;
      v26 = 0;
      p_hKey = &v26;
      v25 = 0;
      v33 = 0;
      v34 = 1;
      v28 = 0;
      v29 = 1;
      UserSidAndPackageInfoFromToken = GetUserSidAndPackageInfoFromToken(TokenHandle);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hKey);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v32);
      if ( UserSidAndPackageInfoFromToken < 0 )
      {
        v7 = (unsigned int)UserSidAndPackageInfoFromToken;
        v8 = 400;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
          (const char *)v7,
          phkResulta);
LABEL_11:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v25);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v26);
        goto LABEL_7;
      }
      v9 = DcaMgr::ValidateOwnership(hkey, v26, v25, v6);
      UserSidAndPackageInfoFromToken = v9;
      if ( v9 < 0 )
      {
        v7 = (unsigned int)v9;
        v8 = 405;
        goto LABEL_10;
      }
      Data = 0;
      cbData = 4;
      v10 = 0;
      v11 = RegQueryValueExW(hkey, L"PresenceMonitoringMode", 0, 0, (LPBYTE)&Data, &cbData);
      v30 = 0;
      v33 = 0;
      if ( v11 >= 0 )
        v10 = Data;
      v32 = (unsigned __int16 **)&v30;
      v34 = 1;
      RegStringValue = ReadRegStringValue(hkey, 0, L"DeviceInstancePath");
      if ( RegStringValue < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1AA,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
          (const char *)(unsigned int)RegStringValue,
          phkResultb);
        v4 = 0;
      }
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v32);
      if ( v4 )
      {
        v13 = CdfPluginUnregisterDevice(v30);
        if ( v13 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1AC,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
            (const char *)(unsigned int)v13,
            phkResultb);
      }
      if ( RegGetValueW(hkey, 0, L"AuthKey", 8u, 0, 0, &cbData) )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
          &hkey,
          0);
        v14 = RegDeleteTreeW(hKey, lpSubKey);
        if ( v14 )
        {
          UserSidAndPackageInfoFromToken = wil::details::in1diag3::Return_Win32(
                                             retaddr,
                                             (void *)0x1BC,
                                             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\device"
                                                           "credentialpresence.cpp",
                                             (const char *)v14,
                                             phkResultc);
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v30);
          goto LABEL_11;
        }
        v15 = hKey;
      }
      else
      {
        Data = v10;
        v17 = RegDeleteValueW(hkey, L"PresenceMonitoringMode");
        if ( v17 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x1C6,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
            (const char *)v17,
            phkResultc);
        v18 = RegDeleteValueW(hkey, L"DeviceInstancePath");
        if ( v18 )
          wil::details::in1diag3::_Log_Win32(
            retaddr,
            (void *)0x1CA,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
            (const char *)v18,
            phkResultc);
        v15 = hkey;
      }
      RegFlushKey(v15);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v30);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v25);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v26);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
    UserSidAndPackageInfoFromToken = 0;
    goto LABEL_27;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x168,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialpresence.cpp",
    (const char *)(unsigned int)v2,
    phkResult);
  return (unsigned int)UserSidAndPackageInfoFromToken;
}

```

## disassembly

```asm
0x18005b5e0  push    rbp
0x18005b5e2  push    rbx
0x18005b5e3  push    rsi
0x18005b5e4  push    rdi
0x18005b5e5  push    r14
0x18005b5e7  lea     rbp, [rsp-37h]
0x18005b5ec  sub     rsp, 0A0h
0x18005b5f3  mov     edx, 28h ; '('
0x18005b5f8  mov     rsi, rcx
0x18005b5fb  call    ValidateInputString
0x18005b600  xor     r14d, r14d
0x18005b603  mov     ebx, eax
0x18005b605  test    eax, eax
0x18005b607  jns     short loc_18005B626
0x18005b609  mov     rcx, [rbp+5Fh]; this
0x18005b60d  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x18005b614  mov     r9d, eax; char *
0x18005b617  mov     edx, 168h; void *
0x18005b61c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b621  jmp     loc_18005B927
0x18005b626  lea     rax, [rbp+57h+hKey]
0x18005b62a  mov     [rbp+57h+hKey], r14
0x18005b62e  mov     [rbp+57h+var_68], rax
0x18005b632  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005b639  lea     rax, [rbp+57h+var_60]
0x18005b63d  mov     [rbp+57h+hkey], r14
0x18005b641  mov     dil, 1
0x18005b644  mov     [rsp+0C0h+phkResult], rax; int
0x18005b649  mov     r9d, 0F003Fh; samDesired
0x18005b64f  mov     [rbp+57h+var_60], r14
0x18005b653  xor     r8d, r8d; ulOptions
0x18005b656  mov     [rbp+57h+var_58], dil
0x18005b65a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18005b661  call    cs:__imp_RegOpenKeyExW
0x18005b667  lea     rcx, [rbp+57h+var_68]
0x18005b66b  mov     ebx, eax
0x18005b66d  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18005b672  test    ebx, ebx
0x18005b674  jnz     loc_18005B99D
0x18005b67a  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b67e  lea     rax, [rbp+57h+hkey]
0x18005b682  mov     [rbp+57h+var_68], rax
0x18005b686  mov     r9d, 0F003Fh; samDesired
0x18005b68c  lea     rax, [rbp+57h+var_60]
0x18005b690  mov     [rbp+57h+var_60], r14
0x18005b694  xor     r8d, r8d; ulOptions
0x18005b697  mov     [rsp+0C0h+phkResult], rax; int
0x18005b69c  mov     rdx, rsi; lpSubKey
0x18005b69f  mov     [rbp+57h+var_58], dil
0x18005b6a3  call    cs:__imp_RegOpenKeyExW
0x18005b6a9  lea     rcx, [rbp+57h+var_68]
0x18005b6ad  mov     ebx, eax
0x18005b6af  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18005b6b4  test    ebx, ebx
0x18005b6b6  jnz     loc_18005B99D
0x18005b6bc  lea     rax, [rbp+57h+TokenHandle]
0x18005b6c0  mov     [rbp+57h+TokenHandle], r14
0x18005b6c4  lea     rdx, [rbp+57h+var_60]
0x18005b6c8  mov     [rbp+57h+var_68], rax
0x18005b6cc  mov     [rbp+57h+var_60], r14
0x18005b6d0  mov     [rbp+57h+var_58], dil
0x18005b6d4  call    OpenCallerImpersonationToken
0x18005b6d9  lea     rcx, [rbp+57h+var_68]
0x18005b6dd  mov     ebx, eax
0x18005b6df  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18005b6e4  test    ebx, ebx
0x18005b6e6  jns     short loc_18005B70E
0x18005b6e8  mov     rcx, [rbp+5Fh]; this
0x18005b6ec  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x18005b6f3  mov     r9d, ebx; char *
0x18005b6f6  mov     edx, 189h; void *
0x18005b6fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b700  lea     rcx, [rbp+57h+TokenHandle]
0x18005b704  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005b709  jmp     loc_18005B915
0x18005b70e  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18005b712  lea     rax, [rbp+57h+var_78]
0x18005b716  mov     [rbp+57h+var_40], rax
0x18005b71a  lea     r8, [rbp+57h+var_38]
0x18005b71e  lea     rax, [rbp+57h+var_70]
0x18005b722  mov     [rbp+57h+var_70], r14
0x18005b726  xor     r9d, r9d
0x18005b729  mov     [rbp+57h+var_68], rax
0x18005b72d  lea     rdx, [rbp+57h+var_60]
0x18005b731  mov     [rbp+57h+var_78], r14
0x18005b735  mov     [rbp+57h+var_38], r14
0x18005b739  mov     [rbp+57h+var_30], dil
0x18005b73d  mov     [rbp+57h+var_60], r14
0x18005b741  mov     [rbp+57h+var_58], dil
0x18005b745  call    GetUserSidAndPackageInfoFromToken
0x18005b74a  lea     rcx, [rbp+57h+var_68]
0x18005b74e  mov     ebx, eax
0x18005b750  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005b755  lea     rcx, [rbp+57h+var_40]
0x18005b759  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005b75e  test    ebx, ebx
0x18005b760  jns     short loc_18005B791
0x18005b762  mov     r9d, ebx; char *
0x18005b765  mov     edx, 190h; void *
0x18005b76a  mov     rcx, [rbp+5Fh]; this
0x18005b76e  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x18005b775  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b77a  lea     rcx, [rbp+57h+var_78]; void *
0x18005b77e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005b783  lea     rcx, [rbp+57h+var_70]; void *
0x18005b787  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005b78c  jmp     loc_18005B700
0x18005b791  mov     r8, [rbp+57h+var_78]; unsigned __int16 *
0x18005b795  mov     rdx, [rbp+57h+var_70]; HKEY
0x18005b799  mov     rcx, [rbp+57h+hkey]; hkey
0x18005b79d  call    ?ValidateOwnership@DcaMgr@@YAJPEAUHKEY__@@PEBG1@Z; DcaMgr::ValidateOwnership(HKEY__ *,ushort const *,ushort const *)
0x18005b7a2  mov     ebx, eax
0x18005b7a4  test    eax, eax
0x18005b7a6  jns     short loc_18005B7B2
0x18005b7a8  mov     r9d, eax
0x18005b7ab  mov     edx, 195h
0x18005b7b0  jmp     short loc_18005B76A
0x18005b7b2  mov     rcx, [rbp+57h+hkey]; hKey
0x18005b7b6  lea     rax, [rbp+57h+cbData]
0x18005b7ba  mov     [rsp+0C0h+lpcbData], rax; lpcbData
0x18005b7bf  lea     rdx, aPresencemonito; "PresenceMonitoringMode"
0x18005b7c6  lea     rax, [rbp+57h+Data]
0x18005b7ca  mov     [rbp+57h+Data], r14d
0x18005b7ce  xor     r9d, r9d; lpType
0x18005b7d1  mov     [rsp+0C0h+phkResult], rax; int
0x18005b7d6  xor     r8d, r8d; lpReserved
0x18005b7d9  mov     [rbp+57h+cbData], 4
0x18005b7e0  mov     ebx, r14d
0x18005b7e3  call    cs:__imp_RegQueryValueExW
0x18005b7e9  mov     rcx, [rbp+57h+hkey]; hkey
0x18005b7ed  lea     r9, [rbp+57h+var_38]
0x18005b7f1  test    eax, eax
0x18005b7f3  mov     [rbp+57h+var_50], r14
0x18005b7f7  lea     rax, [rbp+57h+var_50]
0x18005b7fb  mov     [rbp+57h+var_38], r14
0x18005b7ff  cmovns  ebx, [rbp+57h+Data]
0x18005b803  lea     r8, aDeviceinstance; "DeviceInstancePath"
0x18005b80a  xor     edx, edx; lpSubKey
0x18005b80c  mov     [rbp+57h+var_40], rax
0x18005b810  mov     [rbp+57h+var_30], dil
0x18005b814  call    ReadRegStringValue
0x18005b819  test    eax, eax
0x18005b81b  jns     short loc_18005B838
0x18005b81d  mov     rcx, [rbp+5Fh]; this
0x18005b821  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x18005b828  mov     r9d, eax; char *
0x18005b82b  mov     edx, 1AAh; void *
0x18005b830  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b835  mov     dil, r14b
0x18005b838  lea     rcx, [rbp+57h+var_40]
0x18005b83c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18005b841  test    dil, dil
0x18005b844  jz      short loc_18005B86C
0x18005b846  mov     rcx, [rbp+57h+var_50]
0x18005b84a  call    cs:__imp_CdfPluginUnregisterDevice
0x18005b850  test    eax, eax
0x18005b852  jns     short loc_18005B86C
0x18005b854  mov     rcx, [rbp+5Fh]; this
0x18005b858  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x18005b85f  mov     r9d, eax; char *
0x18005b862  mov     edx, 1ACh; void *
0x18005b867  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18005b86c  mov     rcx, [rbp+57h+hkey]; hkey
0x18005b870  lea     rax, [rbp+57h+cbData]
0x18005b874  mov     [rsp+0C0h+pcbData], rax; pcbData
0x18005b879  lea     r8, aAuthkey; "AuthKey"
0x18005b880  mov     [rsp+0C0h+lpcbData], r14; pvData
0x18005b885  mov     r9d, 8; dwFlags
0x18005b88b  xor     edx, edx; lpSubKey
0x18005b88d  mov     [rsp+0C0h+phkResult], r14; unsigned int
0x18005b892  call    cs:__imp_RegGetValueW
0x18005b898  test    eax, eax
0x18005b89a  jz      loc_18005B937
0x18005b8a0  xor     edx, edx
0x18005b8a2  lea     rcx, [rbp+57h+hkey]
0x18005b8a6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005b8ab  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b8af  mov     rdx, rsi; lpSubKey
0x18005b8b2  call    cs:__imp_RegDeleteTreeW
0x18005b8b8  test    eax, eax
0x18005b8ba  jz      short loc_18005B8E4
0x18005b8bc  mov     rcx, [rbp+5Fh]; this
0x18005b8c0  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x18005b8c7  mov     r9d, eax; char *
0x18005b8ca  mov     edx, 1BCh; void *
0x18005b8cf  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005b8d4  lea     rcx, [rbp+57h+var_50]; void *
0x18005b8d8  mov     ebx, eax
0x18005b8da  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005b8df  jmp     loc_18005B77A
0x18005b8e4  mov     rcx, [rbp+57h+hKey]; hKey
0x18005b8e8  call    cs:__imp_RegFlushKey
0x18005b8ee  lea     rcx, [rbp+57h+var_50]; void *
0x18005b8f2  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005b8f7  lea     rcx, [rbp+57h+var_78]; void *
0x18005b8fb  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005b900  lea     rcx, [rbp+57h+var_70]; void *
0x18005b904  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005b909  lea     rcx, [rbp+57h+TokenHandle]
0x18005b90d  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005b912  mov     ebx, r14d
0x18005b915  lea     rcx, [rbp+57h+hkey]
0x18005b919  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005b91e  lea     rcx, [rbp+57h+hKey]
0x18005b922  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18005b927  mov     eax, ebx
0x18005b929  add     rsp, 0A0h
0x18005b930  pop     r14
0x18005b932  pop     rdi
0x18005b933  pop     rsi
0x18005b934  pop     rbx
0x18005b935  pop     rbp
0x18005b936  retn
0x18005b937  mov     rcx, [rbp+57h+hkey]; hKey
0x18005b93b  lea     rdx, aPresencemonito; "PresenceMonitoringMode"
0x18005b942  mov     [rbp+57h+Data], ebx
0x18005b945  call    cs:__imp_RegDeleteValueW
0x18005b94b  test    eax, eax
0x18005b94d  jz      short loc_18005B967
0x18005b94f  mov     rcx, [rbp+5Fh]; this
0x18005b953  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x18005b95a  mov     r9d, eax; char *
0x18005b95d  mov     edx, 1C6h; void *
0x18005b962  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18005b967  mov     rcx, [rbp+57h+hkey]; hKey
0x18005b96b  lea     rdx, aDeviceinstance; "DeviceInstancePath"
0x18005b972  call    cs:__imp_RegDeleteValueW
0x18005b978  test    eax, eax
0x18005b97a  jz      short loc_18005B994
0x18005b97c  mov     rcx, [rbp+5Fh]; this
0x18005b980  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x18005b987  mov     r9d, eax; char *
0x18005b98a  mov     edx, 1CAh; void *
0x18005b98f  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18005b994  mov     rcx, [rbp+57h+hkey]
0x18005b998  jmp     loc_18005B8E8
0x18005b99d  cmp     ebx, 2
0x18005b9a0  jz      loc_18005B912
0x18005b9a6  test    ebx, ebx
0x18005b9a8  jle     short loc_18005B9B5
0x18005b9aa  movzx   ebx, bx
0x18005b9ad  or      ebx, 80070000h
0x18005b9b3  test    ebx, ebx
0x18005b9b5  jns     loc_18005B915
0x18005b9bb  mov     rcx, [rbp+5Fh]; this
0x18005b9bf  lea     r8, aOnecoreDsSecur_29; "onecore\\ds\\security\\devicecredential"...
0x18005b9c6  mov     r9d, ebx; char *
0x18005b9c9  mov     edx, 180h; void *
0x18005b9ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005b9d3  jmp     loc_18005B915
```
