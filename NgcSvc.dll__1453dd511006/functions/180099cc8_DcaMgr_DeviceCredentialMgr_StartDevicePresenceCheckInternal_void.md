# DcaMgr::DeviceCredentialMgr::StartDevicePresenceCheckInternal(void)

- ea: `0x180099cc8`
- end: `0x18009a7d7`
- name: `?StartDevicePresenceCheckInternal@DeviceCredentialMgr@DcaMgr@@AEAAJXZ`
- size: `2831`
- prototype: `__int64 __fastcall(DcaMgr::DeviceCredentialMgr *__hidden this)`
- caller_count: `2`
- callee_count: `33`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180045de0`
- `0x180099b3c`

## callees

- `0x1800025b4`
- `0x18000782c`
- `0x180007964`
- `0x1800281e0`
- `0x180028200`
- `0x1800288a0`
- `0x180028d18`
- `0x180029940`
- `0x18002fbac`
- `0x1800323d0`
- `0x180032c20`
- `0x180047228`
- `0x180048304`
- `0x180048434`
- `0x180053144`
- `0x1800535f4`
- `0x1800596ec`
- `0x18005bce8`
- `0x18005cee0`
- `0x18005dd44`
- `0x18006060c`
- `0x180060774`
- `0x180081438`
- `0x180097904`
- `0x180097c6c`
- `0x180097c90`
- `0x180097cb4`
- `0x180097d30`
- `0x180097dcc`
- `0x180098960`
- `0x180099cc8`
- `0x18009b3c0`
- `0x1800a6d30`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18009a204`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18009a204`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180099e30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180099fe0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180099e30`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180099fe0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009a050`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009a0b3`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009a050`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18009a0b3`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180099f86`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180099f86`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180099ec8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180099ec8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x180099d21`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x180099d21`
- `ntdll!RtlPublishWnfStateData` at `0x18009a4f5`
- `ntdll!RtlPublishWnfStateData` at `0x18009a4f5`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180099d70`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQueryUserToken` at `0x180099d70`
- `SystemEventsBrokerClient!SebQueryEventPackage` at `0x18009a389`
- `SystemEventsBrokerClient!SebQueryEventPackage` at `0x18009a389`
- `SystemEventsBrokerClient!SebEnumerateEventsByType` at `0x18009a2ad`
- `SystemEventsBrokerClient!SebEnumerateEventsByType` at `0x18009a2ad`
- `SystemEventsBrokerClient!SebSignalEvent` at `0x18009a43a`
- `SystemEventsBrokerClient!SebSignalEvent` at `0x18009a43a`

## string_xrefs

- `0x180099d0b`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180099d3b`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180099d8c`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180099de4`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180099e6d`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180099edc`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180099f9a`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009a001`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009a066`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009a173`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009a215`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009a2d5`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009a526`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009a68b`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009a796`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009a0ed`: `UserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall DcaMgr::DeviceCredentialMgr::StartDevicePresenceCheckInternal(DcaMgr::DeviceCredentialMgr *this)
{
  ULONG active; // eax
  int LastError; // ebx
  char v5; // r12
  BOOL v6; // ebx
  const char *v7; // r9
  bool v8; // sf
  unsigned int v9; // eax
  const char *v10; // r9
  WCHAR *v11; // rbx
  char *v12; // rsi
  __int64 v13; // rdx
  unsigned int v14; // r15d
  DWORD v15; // r14d
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // edi
  unsigned int v19; // eax
  wil::details::in1diag3 *v20; // rcx
  __int64 v21; // rdx
  int RegStringValue; // edi
  unsigned __int16 *v23; // rax
  int v24; // edx
  int v25; // ecx
  int v26; // eax
  char v27; // di
  __int64 v28; // rax
  __int64 v29; // rdx
  const char *v30; // r9
  void *v31; // rdx
  wil::details *v32; // rcx
  int v33; // ebx
  void *v34; // rdx
  wil::details *v35; // rcx
  unsigned int i; // ebx
  __int64 v37; // rdi
  int v38; // r14d
  const struct _tlgProvider_t *v39; // rax
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rdx
  unsigned __int16 *v43; // rcx
  char *v44; // r10
  int v45; // eax
  int v46; // r8d
  int v47; // r14d
  const struct _tlgProvider_t *v48; // rax
  __int64 v49; // r8
  __int64 v50; // r9
  int v51; // eax
  void *v52; // rdx
  wil::details *v53; // rcx
  const struct _tlgProvider_t *v54; // rax
  void *v55; // rdx
  wil::details *v56; // rcx
  void *v57; // rdx
  wil::details *v58; // rcx
  unsigned int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultc; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultd; // [rsp+20h] [rbp-E0h]
  const char *lpcbMaxSubKeyLen; // [rsp+28h] [rbp-D8h]
  LPDWORD lpcbMaxClassLen; // [rsp+30h] [rbp-D0h]
  LPDWORD lpcValues; // [rsp+38h] [rbp-C8h]
  LPDWORD lpcbMaxValueNameLen; // [rsp+40h] [rbp-C0h]
  char v68; // [rsp+60h] [rbp-A0h] BYREF
  wil::details *v69; // [rsp+68h] [rbp-98h] BYREF
  HKEY hkey; // [rsp+70h] [rbp-90h] BYREF
  HKEY hKey; // [rsp+78h] [rbp-88h] BYREF
  __int64 v72; // [rsp+80h] [rbp-80h] BYREF
  char *p_hToken; // [rsp+88h] [rbp-78h] BYREF
  void *phToken; // [rsp+90h] [rbp-70h] BYREF
  char v75; // [rsp+98h] [rbp-68h]
  DWORD cSubKeys; // [rsp+A0h] [rbp-60h] BYREF
  int v77; // [rsp+A4h] [rbp-5Ch] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+A8h] [rbp-58h] BYREF
  DWORD cbData; // [rsp+ACh] [rbp-54h] BYREF
  BYTE v80[4]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v81; // [rsp+B4h] [rbp-4Ch] BYREF
  LPWSTR lpName; // [rsp+B8h] [rbp-48h] BYREF
  void *v83; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 *v84; // [rsp+C8h] [rbp-38h] BYREF
  HANDLE hToken; // [rsp+D0h] [rbp-30h] BYREF
  BYTE Data[8]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v87; // [rsp+E0h] [rbp-20h] BYREF
  DWORD cchName; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v89[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v90; // [rsp+100h] [rbp+0h] BYREF
  char v91; // [rsp+110h] [rbp+10h]
  void **v92; // [rsp+120h] [rbp+20h] BYREF
  __int64 v93; // [rsp+128h] [rbp+28h] BYREF
  char v94; // [rsp+130h] [rbp+30h]
  char *v95; // [rsp+140h] [rbp+40h] BYREF
  __int16 v96; // [rsp+148h] [rbp+48h]
  char v97[86]; // [rsp+14Ah] [rbp+4Ah] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  if ( *((_DWORD *)this + 10) != 1 )
    return wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x9F9,
             (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
             (const char *)0x32,
             phkResult);
  active = WTSGetActiveConsoleSessionId();
  if ( active == -1 )
  {
    LastError = -2147467259;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9FD,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)0x80004005LL,
      phkResult);
    return (unsigned int)LastError;
  }
  v5 = 0;
  hToken = 0;
  p_hToken = (char *)&hToken;
  phToken = 0;
  v75 = 1;
  v6 = WTSQueryUserToken(active, &phToken);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_hToken);
  if ( !v6 )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xA02,
                  (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                  v7);
    goto LABEL_102;
  }
  v72 = 0;
  p_hToken = (char *)&v72;
  phToken = 0;
  v75 = 1;
  LastError = GetUserSidAndPackageInfoFromToken(hToken);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hToken);
  if ( LastError < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA08,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)(unsigned int)LastError,
      phkResult);
LABEL_101:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v72);
    goto LABEL_102;
  }
  hKey = 0;
  p_hToken = (char *)&hKey;
  phToken = 0;
  v75 = 1;
  LastError = RegOpenKeyExW(
                HKEY_LOCAL_MACHINE,
                L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor\\Devices",
                0,
                0x20019u,
                (PHKEY)&phToken);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hToken);
  if ( LastError )
  {
    if ( LastError != 2 )
    {
      v8 = LastError < 0;
      if ( LastError > 0 )
      {
        LastError = (unsigned __int16)LastError | 0x80070000;
        v8 = LastError < 0;
      }
      if ( v8 )
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xA16,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
          (const char *)(unsigned int)LastError,
          phkResulta);
      goto LABEL_100;
    }
LABEL_97:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v72);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
    return 0;
  }
  cSubKeys = 0;
  cbMaxSubKeyLen = 0;
  v9 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v9 )
  {
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0xA2A,
                  (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                  (const char *)v9,
                  phkResultb);
LABEL_100:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    goto LABEL_101;
  }
  if ( !cSubKeys )
    goto LABEL_97;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &lpName,
    0,
    ++cbMaxSubKeyLen,
    v10);
  v11 = lpName;
  if ( !lpName )
  {
    v13 = 2607;
    goto LABEL_99;
  }
  wil::make_unique_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>> [0]>(
    &v83,
    cSubKeys);
  v12 = (char *)v83;
  if ( !v83 )
  {
    v13 = 2611;
LABEL_99:
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)0x8007000ELL,
      phkResultb);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpName);
    goto LABEL_100;
  }
  v14 = 0;
  *(_DWORD *)Data = 0;
  cbData = 0;
  *(_DWORD *)v80 = 0;
  v15 = 0;
  if ( !cSubKeys )
  {
LABEL_94:
    if ( v12 )
    {
      `eh vector destructor iterator'(
        v12,
        8u,
        *((_QWORD *)v12 - 1),
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
      operator delete[](v12 - 8, 8LL * *((_QWORD *)v12 - 1) + 8);
    }
    goto LABEL_96;
  }
  do
  {
    cchName = cbMaxSubKeyLen;
    v16 = RegEnumKeyExW(hKey, v15, v11, &cchName, 0, 0, 0, 0);
    if ( v16 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0xA43,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)v16,
        phkResultc);
      goto LABEL_46;
    }
    hkey = 0;
    p_hToken = (char *)&hkey;
    phToken = 0;
    v75 = 1;
    v17 = RegOpenKeyExW(hKey, v11, 0, 0xF003Fu, (PHKEY)&phToken);
    v18 = wil::details::in1diag3::Log_IfWin32ErrorMsg(
            retaddr,
            (void *)0xA50,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
            (const char *)v17,
            (unsigned int)"DeviceId=%ws",
            (const char *)v11);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hToken);
    if ( !v18 )
    {
      cbData = 4;
      v19 = RegQueryValueExW(hkey, L"State", 0, 0, Data, &cbData);
      v20 = retaddr;
      if ( v19 )
      {
        v21 = 2652;
      }
      else
      {
        if ( *(_DWORD *)Data != 1 )
          goto LABEL_45;
        *(_DWORD *)v80 = 0;
        cbData = 4;
        v19 = RegQueryValueExW(hkey, L"PresenceMonitoringMode", 0, 0, v80, &cbData);
        v20 = retaddr;
        if ( !v19 )
        {
          if ( *(_DWORD *)v80 == 1 )
          {
            v84 = 0;
            p_hToken = (char *)&v84;
            phToken = 0;
            v75 = 1;
            RegStringValue = ReadRegStringValue(hkey, 0, L"UserSid");
            wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hToken);
            if ( RegStringValue < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xA7D,
                (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                (const char *)(unsigned int)RegStringValue,
                (int)phkResultd);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v84);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
              if ( v12 )
              {
                `eh vector destructor iterator'(
                  v12,
                  8u,
                  *((_QWORD *)v12 - 1),
                  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
                operator delete[](v12 - 8, 8LL * *((_QWORD *)v12 - 1) + 8);
              }
              goto LABEL_93;
            }
            v23 = v84;
            do
            {
              v24 = *(unsigned __int16 *)((char *)v23 + v72 - (_QWORD)v84);
              v25 = *v23 - v24;
              if ( v25 )
                break;
              ++v23;
            }
            while ( v24 );
            if ( !v25 )
            {
              v87 = 0;
              p_hToken = (char *)&v87;
              phToken = 0;
              v75 = 1;
              v26 = ReadRegStringValue(hkey, 0, L"PackageFullName");
              if ( v26 >= 0 )
              {
                v27 = 0;
              }
              else
              {
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0xA89,
                  (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                  (const char *)(unsigned int)v26,
                  (int)phkResultd);
                v27 = 1;
              }
              wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_hToken);
              if ( !v27 )
              {
                v28 = v14++;
                v29 = v87;
                v87 = 0;
                wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
                  &v12[8 * v28],
                  v29);
              }
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v87);
            }
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v84);
          }
          goto LABEL_45;
        }
        v21 = 2670;
      }
      wil::details::in1diag3::_Log_Win32(
        v20,
        (void *)v21,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)v19,
        (unsigned int)phkResultd);
    }
LABEL_45:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
LABEL_46:
    ++v15;
  }
  while ( v15 < cSubKeys );
  if ( !v14 )
    goto LABEL_94;
  v81 = 0;
  v69 = 0;
  v68 = 0;
  p_hToken = &v68;
  LOWORD(phToken) = 256;
  if ( !ImpersonateLoggedOnUser(hToken) )
  {
    RegStringValue = wil::details::in1diag3::Return_GetLastError(
                       retaddr,
                       (void *)0xAA2,
                       (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                       v30);
    wil::details::ScopeExitFnGuard__lambda_d8886c3ae6bc14ec25a8aa644be9bd61___::operator()(&p_hToken);
    v32 = v69;
    v69 = 0;
    if ( v32 )
      wil::details::FreeProcessHeap(v32, v31);
    if ( v12 )
      goto LABEL_52;
    goto LABEL_93;
  }
  v68 = 1;
  *(_QWORD *)&v90 = &v69;
  *((_QWORD *)&v90 + 1) = 0;
  v91 = 1;
  v33 = SebEnumerateEventsByType(&v81, (char *)&v90 + 8, L"*.*", 66);
  wil::details::out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>::~out_param_t<wistd::unique_ptr<unsigned short,wil::process_heap_deleter>>(&v90);
  wil::details::ScopeExitFnGuard__lambda_d8886c3ae6bc14ec25a8aa644be9bd61___::operator()(&p_hToken);
  if ( v33 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xAAD,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)(unsigned int)v33,
      (int)phkResultd);
    goto LABEL_55;
  }
  if ( !v81 )
  {
LABEL_55:
    wil::details::ScopeExitFnGuard__lambda_d8886c3ae6bc14ec25a8aa644be9bd61___::operator()(&p_hToken);
    v35 = v69;
    v69 = 0;
    if ( v35 )
      wil::details::FreeProcessHeap(v35, v34);
    if ( v12 )
    {
LABEL_90:
      `eh vector destructor iterator'(
        v12,
        8u,
        *((_QWORD *)v12 - 1),
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
      operator delete[](v12 - 8, 8LL * *((_QWORD *)v12 - 1) + 8);
    }
LABEL_96:
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpName);
    goto LABEL_97;
  }
  for ( i = 0; i < v81; ++i )
  {
    v83 = 0;
    v92 = &v83;
    v93 = 0;
    v94 = 1;
    v37 = 16LL * i;
    v90 = *(_OWORD *)((char *)v69 + v37);
    v38 = SebQueryEventPackage(&v90, &v93);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&v92);
    if ( v38 >= 0 )
    {
      v42 = 0;
      while ( 1 )
      {
        v43 = *(unsigned __int16 **)&v12[8 * v42];
        v44 = (char *)((_BYTE *)v83 - (_BYTE *)v43);
        do
        {
          v45 = *(unsigned __int16 *)&v44[(_QWORD)v43];
          v46 = *v43 - v45;
          if ( v46 )
            break;
          ++v43;
        }
        while ( v45 );
        if ( !v46 )
          break;
        v42 = (unsigned int)(v42 + 1);
        if ( (unsigned int)v42 >= v14 )
          goto LABEL_73;
      }
      v90 = *(_OWORD *)((char *)v69 + v37);
      v47 = SebSignalEvent(
              &v90,
              0,
              0,
              v83,
              phkResultd,
              lpcbMaxSubKeyLen,
              lpcbMaxClassLen,
              lpcValues,
              lpcbMaxValueNameLen);
      v5 = 1;
      v48 = DevCredSvcTraceLoggingProvider::Provider();
      if ( *(_DWORD *)v48 > 4u )
      {
        v77 = v47;
        v89[0] = (__int64)v83;
        *(_QWORD *)&v90 = (char *)v69 + v37;
        lpcbMaxClassLen = (LPDWORD)&v77;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (__int64)v48,
          (__int64)&word_180108546,
          v49,
          v50,
          (__int64)&v90,
          v89);
      }
LABEL_73:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v83,
        0);
    }
    else
    {
      v39 = DevCredSvcTraceLoggingProvider::Provider();
      if ( *(_DWORD *)v39 > 4u )
      {
        v77 = v38;
        v89[0] = (__int64)v69 + v37;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
          (__int64)v39,
          (unsigned __int8 *)&dword_1801085BC,
          v40,
          v41,
          v89,
          (__int64)&v77);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void wil::details::FreeProcessHeap(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v83);
  }
  if ( !v5 )
  {
    wil::details::ScopeExitFnGuard__lambda_d8886c3ae6bc14ec25a8aa644be9bd61___::operator()(&p_hToken);
    v58 = v69;
    v69 = 0;
    if ( v58 )
      wil::details::FreeProcessHeap(v58, v57);
    if ( v12 )
      goto LABEL_90;
    goto LABEL_96;
  }
  memset_0(v97, 0, 0x52u);
  LODWORD(v95) = 8;
  HIDWORD(v95) = *((_DWORD *)this + 10);
  v96 = 0;
  v51 = RtlPublishWnfStateData(WNF_SFA_AUTHENTICATION_STAGE_CHANGED, 0, &v95, 92, 0);
  RegStringValue = v51 | 0x10000000;
  if ( v51 >= 0 )
  {
    v54 = DevCredSvcTraceLoggingProvider::Provider();
    if ( *(_DWORD *)v54 > 4u )
    {
      v77 = (int)v95;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)v54,
        (unsigned __int8 *)byte_180108585,
        0,
        0,
        (__int64)&v77);
    }
    wil::details::ScopeExitFnGuard__lambda_d8886c3ae6bc14ec25a8aa644be9bd61___::operator()(&p_hToken);
    v56 = v69;
    v69 = 0;
    if ( v56 )
      wil::details::FreeProcessHeap(v56, v55);
    if ( v12 )
      goto LABEL_90;
    goto LABEL_96;
  }
  LODWORD(lpcbMaxSubKeyLen) = (_DWORD)v95;
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0xAEB,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
    (const char *)(unsigned int)RegStringValue,
    (int)"AuthStage=%d",
    lpcbMaxSubKeyLen);
  wil::details::ScopeExitFnGuard__lambda_d8886c3ae6bc14ec25a8aa644be9bd61___::operator()(&p_hToken);
  v53 = v69;
  v69 = 0;
  if ( v53 )
    wil::details::FreeProcessHeap(v53, v52);
  if ( v12 )
  {
LABEL_52:
    `eh vector destructor iterator'(
      v12,
      8u,
      *((_QWORD *)v12 - 1),
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>);
    operator delete[](v12 - 8, 8LL * *((_QWORD *)v12 - 1) + 8);
  }
LABEL_93:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpName);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v72);
  LastError = RegStringValue;
LABEL_102:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hToken);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180099cc8  push    rbp
0x180099cca  push    rbx
0x180099ccb  push    rsi
0x180099ccc  push    rdi
0x180099ccd  push    r12
0x180099ccf  push    r13
0x180099cd1  push    r14
0x180099cd3  push    r15
0x180099cd5  lea     rbp, [rsp-0B8h]
0x180099cdd  sub     rsp, 1B8h
0x180099ce4  mov     rax, cs:__security_cookie
0x180099ceb  xor     rax, rsp
0x180099cee  mov     [rbp+0F0h+var_50], rax
0x180099cf5  mov     r13, rcx
0x180099cf8  cmp     dword ptr [rcx+28h], 1
0x180099cfc  jz      short loc_180099D21
0x180099cfe  mov     rcx, [rbp+0F8h]; this
0x180099d05  mov     r9d, 32h ; '2'; char *
0x180099d0b  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180099d12  mov     edx, 9F9h; void *
0x180099d17  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180099d1c  jmp     loc_18009A766
0x180099d21  call    cs:__imp_WTSGetActiveConsoleSessionId
0x180099d27  cmp     eax, 0FFFFFFFFh
0x180099d2a  jnz     short loc_180099D53
0x180099d2c  mov     rcx, [rbp+0F8h]; this
0x180099d33  mov     ebx, 80004005h
0x180099d38  mov     r9d, ebx; char *
0x180099d3b  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180099d42  mov     edx, 9FDh; void *
0x180099d47  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099d4c  mov     eax, ebx
0x180099d4e  jmp     loc_18009A766
0x180099d53  xor     r12d, r12d
0x180099d56  mov     [rbp+0F0h+hToken], r12
0x180099d5a  lea     rcx, [rbp+0F0h+hToken]
0x180099d5e  mov     [rbp+0F0h+var_168], rcx
0x180099d62  mov     [rbp+0F0h+phToken], r12
0x180099d66  mov     [rbp+0F0h+var_158], 1
0x180099d6a  lea     rdx, [rbp+0F0h+phToken]; phToken
0x180099d6e  mov     ecx, eax; SessionId
0x180099d70  call    cs:__imp_WTSQueryUserToken
0x180099d76  mov     ebx, eax
0x180099d78  lea     rcx, [rbp+0F0h+var_168]
0x180099d7c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x180099d81  test    ebx, ebx
0x180099d83  jnz     short loc_180099DA4
0x180099d85  mov     rcx, [rbp+0F8h]; this
0x180099d8c  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180099d93  mov     edx, 0A02h; void *
0x180099d98  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180099d9d  mov     ebx, eax
0x180099d9f  jmp     loc_18009A7C9
0x180099da4  mov     [rbp+0F0h+var_170], r12
0x180099da8  lea     rax, [rbp+0F0h+var_170]
0x180099dac  mov     [rbp+0F0h+var_168], rax
0x180099db0  mov     [rbp+0F0h+phToken], r12
0x180099db4  mov     [rbp+0F0h+var_158], 1
0x180099db8  xor     r9d, r9d
0x180099dbb  xor     r8d, r8d
0x180099dbe  lea     rdx, [rbp+0F0h+phToken]
0x180099dc2  mov     rcx, [rbp+0F0h+hToken]; TokenHandle
0x180099dc6  call    GetUserSidAndPackageInfoFromToken
0x180099dcb  mov     ebx, eax
0x180099dcd  lea     rcx, [rbp+0F0h+var_168]
0x180099dd1  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x180099dd6  test    ebx, ebx
0x180099dd8  jns     short loc_180099DFA
0x180099dda  mov     rcx, [rbp+0F8h]; this
0x180099de1  mov     r9d, ebx; char *
0x180099de4  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180099deb  mov     edx, 0A08h; void *
0x180099df0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099df5  jmp     loc_18009A7BF
0x180099dfa  mov     [rsp+1F0h+hKey], r12
0x180099dff  lea     rax, [rsp+1F0h+hKey]
0x180099e04  mov     [rbp+0F0h+var_168], rax
0x180099e08  mov     [rbp+0F0h+phToken], r12
0x180099e0c  mov     [rbp+0F0h+var_158], 1
0x180099e10  lea     rax, [rbp+0F0h+phToken]
0x180099e14  mov     [rsp+1F0h+phkResult], rax; int
0x180099e19  mov     r9d, 20019h; samDesired
0x180099e1f  xor     r8d, r8d; ulOptions
0x180099e22  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180099e29  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180099e30  call    cs:__imp_RegOpenKeyExW
0x180099e36  mov     ebx, eax
0x180099e38  lea     rcx, [rbp+0F0h+var_168]
0x180099e3c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180099e41  test    ebx, ebx
0x180099e43  jz      short loc_180099E83
0x180099e45  cmp     ebx, 2
0x180099e48  jz      loc_18009A746
0x180099e4e  test    ebx, ebx
0x180099e50  jle     short loc_180099E5D
0x180099e52  movzx   ebx, bx
0x180099e55  or      ebx, 80070000h
0x180099e5b  test    ebx, ebx
0x180099e5d  jns     loc_18009A7B4
0x180099e63  mov     rcx, [rbp+0F8h]; this
0x180099e6a  mov     r9d, ebx; char *
0x180099e6d  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180099e74  mov     edx, 0A16h; void *
0x180099e79  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099e7e  jmp     loc_18009A7B4
0x180099e83  mov     [rbp+0F0h+cSubKeys], r12d
0x180099e87  mov     [rbp+0F0h+cbMaxSubKeyLen], r12d
0x180099e8b  mov     [rsp+1F0h+lpftLastWriteTime], r12; lpftLastWriteTime
0x180099e90  mov     [rsp+1F0h+lpcbSecurityDescriptor], r12; lpcbSecurityDescriptor
0x180099e95  mov     [rsp+1F0h+lpcbMaxValueLen], r12; lpcbMaxValueLen
0x180099e9a  mov     [rsp+1F0h+lpcbMaxValueNameLen], r12; lpcbMaxValueNameLen
0x180099e9f  mov     [rsp+1F0h+lpcValues], r12; lpcValues
0x180099ea4  mov     [rsp+1F0h+lpcbMaxClassLen], r12; lpcbMaxClassLen
0x180099ea9  lea     rax, [rbp+0F0h+cbMaxSubKeyLen]
0x180099ead  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180099eb2  lea     rax, [rbp+0F0h+cSubKeys]
0x180099eb6  mov     [rsp+1F0h+phkResult], rax; int
0x180099ebb  xor     r9d, r9d; lpReserved
0x180099ebe  xor     r8d, r8d; lpcchClass
0x180099ec1  xor     edx, edx; lpClass
0x180099ec3  mov     rcx, [rsp+1F0h+hKey]; hKey
0x180099ec8  call    cs:__imp_RegQueryInfoKeyW
0x180099ece  test    eax, eax
0x180099ed0  jz      short loc_180099EF4
0x180099ed2  mov     rcx, [rbp+0F8h]; this
0x180099ed9  mov     r9d, eax; char *
0x180099edc  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180099ee3  mov     edx, 0A2Ah; void *
0x180099ee8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180099eed  mov     ebx, eax
0x180099eef  jmp     loc_18009A7B4
0x180099ef4  cmp     [rbp+0F0h+cSubKeys], r12d
0x180099ef8  jz      loc_18009A746
0x180099efe  mov     eax, [rbp+0F0h+cbMaxSubKeyLen]
0x180099f01  inc     eax
0x180099f03  mov     [rbp+0F0h+cbMaxSubKeyLen], eax
0x180099f06  mov     r8d, eax
0x180099f09  xor     edx, edx
0x180099f0b  lea     rcx, [rbp+0F0h+lpName]
0x180099f0f  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180099f14  nop
0x180099f15  mov     rbx, [rbp+0F0h+lpName]
0x180099f19  test    rbx, rbx
0x180099f1c  jz      loc_18009A789
0x180099f22  mov     edx, [rbp+0F0h+cSubKeys]
0x180099f25  lea     rcx, [rbp+0F0h+var_130]
0x180099f29  call    ??$make_unique_nothrow@$$BY0A@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_ptr@$$BY0A@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@U?$default_delete@$$BY0A@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> [0]>(unsigned __int64)
0x180099f2e  mov     rsi, [rbp+0F0h+var_130]
0x180099f32  test    rsi, rsi
0x180099f35  jnz     short loc_180099F41
0x180099f37  mov     edx, 0A33h
0x180099f3c  jmp     loc_18009A78E
0x180099f41  mov     r15d, r12d
0x180099f44  mov     dword ptr [rbp+0F0h+Data], r12d
0x180099f48  mov     [rbp+0F0h+cbData], r12d
0x180099f4c  mov     dword ptr [rbp+0F0h+var_140], r12d
0x180099f50  mov     r14d, r12d
0x180099f53  cmp     [rbp+0F0h+cSubKeys], r12d
0x180099f57  jbe     loc_18009A708
0x180099f5d  mov     eax, [rbp+0F0h+cbMaxSubKeyLen]
0x180099f60  mov     [rbp+0F0h+cchName], eax
0x180099f63  mov     [rsp+1F0h+lpcValues], r12; lpftLastWriteTime
0x180099f68  mov     [rsp+1F0h+lpcbMaxClassLen], r12; lpcchClass
0x180099f6d  mov     [rsp+1F0h+lpcbMaxSubKeyLen], r12; lpClass
0x180099f72  mov     [rsp+1F0h+phkResult], r12; unsigned int
0x180099f77  lea     r9, [rbp+0F0h+cchName]; lpcchName
0x180099f7b  mov     r8, rbx; lpName
0x180099f7e  mov     edx, r14d; dwIndex
0x180099f81  mov     rcx, [rsp+1F0h+hKey]; hKey
0x180099f86  call    cs:__imp_RegEnumKeyExW
0x180099f8c  mov     rcx, [rbp+0F8h]; this
0x180099f93  test    eax, eax
0x180099f95  jz      short loc_180099FB0
0x180099f97  mov     r9d, eax; char *
0x180099f9a  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180099fa1  mov     edx, 0A43h; void *
0x180099fa6  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180099fab  jmp     loc_18009A1CD
0x180099fb0  mov     [rsp+1F0h+hkey], r12
0x180099fb5  lea     rax, [rsp+1F0h+hkey]
0x180099fba  mov     [rbp+0F0h+var_168], rax
0x180099fbe  mov     [rbp+0F0h+phToken], r12
0x180099fc2  mov     [rbp+0F0h+var_158], 1
0x180099fc6  lea     rax, [rbp+0F0h+phToken]
0x180099fca  mov     [rsp+1F0h+phkResult], rax; phkResult
0x180099fcf  mov     r9d, 0F003Fh; samDesired
0x180099fd5  xor     r8d, r8d; ulOptions
0x180099fd8  mov     rdx, rbx; lpSubKey
0x180099fdb  mov     rcx, [rsp+1F0h+hKey]; hKey
0x180099fe0  call    cs:__imp_RegOpenKeyExW
0x180099fe6  mov     rcx, [rbp+0F8h]; this
0x180099fed  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rbx; char *
0x180099ff2  lea     rdx, aDeviceidWs; "DeviceId=%ws"
0x180099ff9  mov     [rsp+1F0h+phkResult], rdx; unsigned int
0x180099ffe  mov     r9d, eax; char *
0x18009a001  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18009a008  mov     edx, 0A50h; void *
0x18009a00d  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x18009a012  mov     edi, eax
0x18009a014  lea     rcx, [rbp+0F0h+var_168]
0x18009a018  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18009a01d  test    edi, edi
0x18009a01f  jnz     loc_18009A1C3
0x18009a025  mov     [rbp+0F0h+cbData], 4
0x18009a02c  lea     rax, [rbp+0F0h+cbData]
0x18009a030  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18009a035  lea     rax, [rbp+0F0h+Data]
0x18009a039  mov     [rsp+1F0h+phkResult], rax; unsigned int
0x18009a03e  xor     r9d, r9d; lpType
0x18009a041  xor     r8d, r8d; lpReserved
0x18009a044  lea     rdx, aState; "State"
0x18009a04b  mov     rcx, [rsp+1F0h+hkey]; hKey
0x18009a050  call    cs:__imp_RegQueryValueExW
0x18009a056  mov     rcx, [rbp+0F8h]; this
0x18009a05d  test    eax, eax
0x18009a05f  jz      short loc_18009A07A
0x18009a061  mov     edx, 0A5Ch; void *
0x18009a066  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18009a06d  mov     r9d, eax; char *
0x18009a070  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18009a075  jmp     loc_18009A1C3
0x18009a07a  cmp     dword ptr [rbp+0F0h+Data], 1
0x18009a07e  jnz     loc_18009A1C3
0x18009a084  mov     dword ptr [rbp+0F0h+var_140], r12d
0x18009a088  mov     [rbp+0F0h+cbData], 4
0x18009a08f  lea     rax, [rbp+0F0h+cbData]
0x18009a093  mov     [rsp+1F0h+lpcbMaxSubKeyLen], rax; lpcbData
0x18009a098  lea     rax, [rbp+0F0h+var_140]
0x18009a09c  mov     [rsp+1F0h+phkResult], rax; int
0x18009a0a1  xor     r9d, r9d; lpType
0x18009a0a4  xor     r8d, r8d; lpReserved
0x18009a0a7  lea     rdx, aPresencemonito; "PresenceMonitoringMode"
0x18009a0ae  mov     rcx, [rsp+1F0h+hkey]; hKey
0x18009a0b3  call    cs:__imp_RegQueryValueExW
0x18009a0b9  mov     rcx, [rbp+0F8h]
0x18009a0c0  test    eax, eax
0x18009a0c2  jz      short loc_18009A0CB
0x18009a0c4  mov     edx, 0A6Eh
0x18009a0c9  jmp     short loc_18009A066
0x18009a0cb  cmp     dword ptr [rbp+0F0h+var_140], 1
0x18009a0cf  jnz     loc_18009A1C3
0x18009a0d5  mov     [rbp+0F0h+var_128], r12
0x18009a0d9  lea     rax, [rbp+0F0h+var_128]
0x18009a0dd  mov     [rbp+0F0h+var_168], rax
0x18009a0e1  mov     [rbp+0F0h+phToken], r12
0x18009a0e5  mov     [rbp+0F0h+var_158], 1
0x18009a0e9  lea     r9, [rbp+0F0h+phToken]
0x18009a0ed  lea     r8, aUsersid; "UserSid"
0x18009a0f4  xor     edx, edx; lpSubKey
0x18009a0f6  mov     rcx, [rsp+1F0h+hkey]; hkey
0x18009a0fb  call    ReadRegStringValue
0x18009a100  mov     edi, eax
0x18009a102  lea     rcx, [rbp+0F0h+var_168]
0x18009a106  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18009a10b  test    edi, edi
0x18009a10d  js      loc_18009A681
0x18009a113  mov     rax, [rbp+0F0h+var_128]
0x18009a117  mov     r8, [rbp+0F0h+var_170]
0x18009a11b  sub     r8, rax
0x18009a11e  movzx   ecx, word ptr [rax]
0x18009a121  movzx   edx, word ptr [rax+r8]
0x18009a126  sub     ecx, edx
0x18009a128  jnz     short loc_18009A132
0x18009a12a  add     rax, 2
0x18009a12e  test    edx, edx
0x18009a130  jnz     short loc_18009A11E
0x18009a132  test    ecx, ecx
0x18009a134  jnz     loc_18009A1BA
0x18009a13a  mov     [rbp+0F0h+var_110], r12
0x18009a13e  lea     rax, [rbp+0F0h+var_110]
0x18009a142  mov     [rbp+0F0h+var_168], rax
0x18009a146  mov     [rbp+0F0h+phToken], r12
0x18009a14a  mov     [rbp+0F0h+var_158], 1
0x18009a14e  lea     r9, [rbp+0F0h+phToken]
0x18009a152  lea     r8, aPackagefullnam; "PackageFullName"
0x18009a159  xor     edx, edx; lpSubKey
0x18009a15b  mov     rcx, [rsp+1F0h+hkey]; hkey
0x18009a160  call    ReadRegStringValue
0x18009a165  mov     rcx, [rbp+0F8h]; this
0x18009a16c  test    eax, eax
0x18009a16e  jns     short loc_18009A189
0x18009a170  mov     r9d, eax; char *
0x18009a173  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18009a17a  mov     edx, 0A89h; void *
0x18009a17f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009a184  mov     dil, 1
0x18009a187  jmp     short loc_18009A18C
0x18009a189  mov     dil, r12b
0x18009a18c  lea     rcx, [rbp+0F0h+var_168]
0x18009a190  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18009a195  test    dil, dil
0x18009a198  jnz     short loc_18009A1B1
0x18009a19a  mov     eax, r15d
0x18009a19d  inc     r15d
0x18009a1a0  mov     rdx, [rbp+0F0h+var_110]
0x18009a1a4  mov     [rbp+0F0h+var_110], r12
0x18009a1a8  lea     rcx, [rsi+rax*8]
0x18009a1ac  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009a1b1  lea     rcx, [rbp+0F0h+var_110]; void *
0x18009a1b5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
  ... truncated ...
```
