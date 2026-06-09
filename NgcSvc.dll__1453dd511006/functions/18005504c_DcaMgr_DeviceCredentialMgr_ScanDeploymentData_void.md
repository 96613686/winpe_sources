# DcaMgr::DeviceCredentialMgr::ScanDeploymentData(void)

- ea: `0x18005504c`
- end: `0x1800555d2`
- name: `?ScanDeploymentData@DeviceCredentialMgr@DcaMgr@@QEAAJXZ`
- size: `1414`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this)`
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18009fc80`

## callees

- `0x18000782c`
- `0x180007964`
- `0x1800281e0`
- `0x180028200`
- `0x180031184`
- `0x180032c20`
- `0x180048304`
- `0x18005504c`
- `0x1800555d8`
- `0x1800596ec`
- `0x180097cb4`
- `0x180097cd8`
- `0x180097cfc`
- `0x180098960`
- `0x18009abe4`
- `0x18009b38c`
- `0x1800a14c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x1800550b9`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x1800550b9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180055110`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800553c2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180055110`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800553c2`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005542e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18005542e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180055300`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180055300`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005547e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005547e`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800554f9`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180055503`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800554f9`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x180055503`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180055371`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x180055371`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005517c`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18005517c`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180055072`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180055072`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005526a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18005526a`

## string_xrefs

- `0x180055085`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18005518e`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180055206`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180055283`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18005531c`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180055382`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x1800553e0`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18005543f`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x1800554c1`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x180055561`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredentialMgr::ScanDeploymentData(RTL_SRWLOCK *this)
{
  int v2; // eax
  unsigned int LastError; // ebx
  unsigned int v5; // ebx
  const char *v6; // r9
  __int64 v7; // rdx
  unsigned int v8; // eax
  DWORD v9; // eax
  WCHAR *v10; // rbx
  int Instance; // edi
  BOOL v12; // edi
  const char *v13; // r9
  unsigned int v14; // edi
  DWORD v15; // esi
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // edi
  unsigned int v19; // eax
  int updated; // eax
  int phkResult; // [rsp+20h] [rbp-99h]
  unsigned int phkResulta; // [rsp+20h] [rbp-99h]
  unsigned int phkResultb; // [rsp+20h] [rbp-99h]
  unsigned int phkResultc; // [rsp+20h] [rbp-99h]
  unsigned int phkResultd; // [rsp+20h] [rbp-99h]
  int phkResulte; // [rsp+20h] [rbp-99h]
  void **p_hKey; // [rsp+60h] [rbp-59h] BYREF
  HKEY v28; // [rsp+68h] [rbp-51h] BYREF
  char v29; // [rsp+70h] [rbp-49h]
  DWORD cbData; // [rsp+78h] [rbp-41h] BYREF
  struct PackageUtil *v31; // [rsp+80h] [rbp-39h] BYREF
  LPWSTR lpName; // [rsp+88h] [rbp-31h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-29h] BYREF
  HKEY hkey; // [rsp+98h] [rbp-21h] BYREF
  HKEY v35; // [rsp+A0h] [rbp-19h] BYREF
  void *v36; // [rsp+A8h] [rbp-11h] BYREF
  BYTE Data[4]; // [rsp+B0h] [rbp-9h] BYREF
  DWORD cchName; // [rsp+B4h] [rbp-5h] BYREF
  unsigned __int64 v39; // [rsp+B8h] [rbp-1h] BYREF
  char *v40; // [rsp+C0h] [rbp+7h] BYREF
  __int16 v41; // [rsp+C8h] [rbp+Fh]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+D0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  char v44; // [rsp+128h] [rbp+6Fh] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+130h] [rbp+77h] BYREF
  DWORD cSubKeys; // [rsp+138h] [rbp+7Fh] BYREF

  v44 = 0;
  v2 = RoInitialize(1);
  LastError = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x668,
      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
      (const char *)(unsigned int)v2,
      phkResult);
    return LastError;
  }
  v44 = 1;
  v40 = &v44;
  v41 = 256;
  v39 = (unsigned __int64)&this[16] & -(__int64)(TryAcquireSRWLockExclusive(this + 16) != 0);
  if ( v39 )
  {
    *(_DWORD *)Data = 0;
    cbData = 0;
    hKey = 0;
    p_hKey = (void **)&hKey;
    v28 = 0;
    v29 = 1;
    v5 = RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor\\Devices",
           0,
           0xF003Fu,
           &v28);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v5 )
    {
      if ( v5 != 2 )
      {
        v6 = (const char *)v5;
        v7 = 1676;
LABEL_10:
        LastError = wil::details::in1diag3::Return_Win32(
                      retaddr,
                      (void *)v7,
                      (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                      v6,
                      phkResulta);
LABEL_37:
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v39);
        wil::details::ScopeExitFnGuard__lambda_d8173cb92363fa7c66c11fc7ee07aa30___::operator()(&v40);
        return LastError;
      }
      goto LABEL_36;
    }
    cSubKeys = 0;
    cbMaxSubKeyLen = 0;
    v8 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
    if ( v8 )
    {
      v6 = (const char *)v8;
      v7 = 1694;
      goto LABEL_10;
    }
    v9 = ++cbMaxSubKeyLen;
    if ( !cSubKeys )
    {
LABEL_36:
      LastError = 0;
      goto LABEL_37;
    }
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &lpName,
      0,
      v9);
    v10 = lpName;
    if ( !lpName )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6A3,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)0x8007000ELL,
        phkResulta);
      goto LABEL_35;
    }
    v31 = 0;
    p_hKey = (void **)&v31;
    v28 = 0;
    v29 = 1;
    Instance = PackageUtil::CreateInstance((struct PackageUtil **)&v28);
    wil::details::out_param_t<wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>>::~out_param_t<wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>>(&p_hKey);
    if ( Instance < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6A7,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)(unsigned int)Instance,
        phkResulta);
LABEL_15:
      wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>::reset(&v31, 0);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpName);
      LastError = Instance;
      goto LABEL_37;
    }
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    SecurityAttributes.lpSecurityDescriptor = 0;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    v36 = 0;
    p_hKey = &v36;
    v28 = 0;
    v29 = 1;
    v12 = ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:P(A;CI;KR;;;AU)(A;CI;KA;;;SY)",
            1u,
            (PSECURITY_DESCRIPTOR *)&v28,
            0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(&p_hKey);
    if ( !v12 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x6AF,
                    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                    v13);
LABEL_18:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v36);
      wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>::reset(&v31, 0);
LABEL_35:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpName);
      goto LABEL_37;
    }
    SecurityAttributes.lpSecurityDescriptor = v36;
    v35 = 0;
    p_hKey = (void **)&v35;
    v28 = 0;
    v29 = 1;
    v14 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\SecondaryAuthFactor\\Applications",
            0,
            0,
            0,
            0xF003Fu,
            &SecurityAttributes,
            &v28,
            0);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
    if ( v14 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0x6BC,
                    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                    (const char *)v14,
                    phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v35);
      goto LABEL_18;
    }
    v15 = cSubKeys;
    while ( v15 )
    {
      cchName = cbMaxSubKeyLen;
      v16 = RegEnumKeyExW(hKey, --v15, v10, &cchName, 0, 0, 0, 0);
      if ( v16 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x6CA,
          (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
          (const char *)v16,
          phkResultc);
      }
      else
      {
        hkey = 0;
        p_hKey = (void **)&hkey;
        v28 = 0;
        v29 = 1;
        v17 = RegOpenKeyExW(hKey, v10, 0, 0xF003Fu, &v28);
        v18 = wil::details::in1diag3::Log_IfWin32ErrorMsg(
                retaddr,
                (void *)0x6D7,
                (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                (const char *)v17,
                (unsigned int)"DeviceId=%ws",
                (const char *)v10);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_hKey);
        if ( !v18 )
        {
          cbData = 4;
          v19 = RegQueryValueExW(hkey, L"State", 0, 0, Data, &cbData);
          if ( v19 )
          {
            wil::details::in1diag3::_Log_Win32(
              retaddr,
              (void *)0x6E3,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
              (const char *)v19,
              phkResultd);
          }
          else if ( *(_DWORD *)Data == 1 && !RegGetValueW(hkey, 0, L"AuthKey", 8u, 0, 0, &cbData) )
          {
            updated = DcaMgr::DeviceCredentialMgr::UpdatePackageData((const WCHAR *)this, v31, v35, hkey, v10, 0);
            Instance = updated;
            if ( updated < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x6FA,
                (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                (const char *)(unsigned int)updated,
                phkResulte);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v35);
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v36);
              goto LABEL_15;
            }
          }
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
      }
    }
    RegFlushKey(v35);
    RegFlushKey(hKey);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v35);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v36);
    wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>::reset(&v31, 0);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpName);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v39);
    wil::details::ScopeExitFnGuard__lambda_d8173cb92363fa7c66c11fc7ee07aa30___::operator()(&v40);
    return 0;
  }
  else
  {
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v39);
    wil::details::ScopeExitFnGuard__lambda_d8173cb92363fa7c66c11fc7ee07aa30___::operator()(&v40);
    return 1;
  }
}

```

## disassembly

```asm
0x18005504c  mov     [rsp-8+arg_0], rbx
0x180055051  push    rbp
0x180055052  push    rsi
0x180055053  push    rdi
0x180055054  push    r14
0x180055056  push    r15
0x180055058  lea     rbp, [rsp-37h]
0x18005505d  sub     rsp, 0F0h
0x180055064  mov     r14, rcx
0x180055067  xor     r15d, r15d
0x18005506a  mov     [rbp+57h+arg_8], r15b
0x18005506e  lea     ecx, [r15+1]
0x180055072  call    cs:__imp_RoInitialize
0x180055078  mov     ebx, eax
0x18005507a  test    eax, eax
0x18005507c  jns     short loc_18005509D
0x18005507e  mov     rcx, [rbp+5Fh]; this
0x180055082  mov     r9d, eax; char *
0x180055085  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18005508c  mov     edx, 668h; void *
0x180055091  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055096  mov     eax, ebx
0x180055098  jmp     loc_1800555BB
0x18005509d  mov     [rbp+57h+arg_8], 1
0x1800550a1  lea     rax, [rbp+57h+arg_8]
0x1800550a5  mov     [rbp+57h+var_50], rax
0x1800550a9  mov     [rbp+57h+var_48], 100h
0x1800550af  lea     rbx, [r14+80h]
0x1800550b6  mov     rcx, rbx; SRWLock
0x1800550b9  call    cs:__imp_TryAcquireSRWLockExclusive
0x1800550bf  neg     al
0x1800550c1  sbb     rcx, rcx
0x1800550c4  and     rcx, rbx
0x1800550c7  mov     [rbp+57h+var_58], rcx
0x1800550cb  jz      loc_1800555A3
0x1800550d1  mov     dword ptr [rbp+57h+Data], r15d
0x1800550d5  mov     [rbp+57h+cbData], r15d
0x1800550d9  mov     [rbp+57h+hKey], r15
0x1800550dd  lea     rax, [rbp+57h+hKey]
0x1800550e1  mov     [rbp+57h+var_B0], rax
0x1800550e5  mov     [rbp+57h+var_A8], r15
0x1800550e9  mov     [rbp+57h+var_A0], 1
0x1800550ed  lea     rax, [rbp+57h+var_A8]
0x1800550f1  mov     [rsp+110h+phkResult], rax; phkResult
0x1800550f6  mov     r9d, 0F003Fh; samDesired
0x1800550fc  xor     r8d, r8d; ulOptions
0x1800550ff  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180055106  mov     rsi, 0FFFFFFFF80000002h
0x18005510d  mov     rcx, rsi; hKey
0x180055110  call    cs:__imp_RegOpenKeyExW
0x180055116  mov     ebx, eax
0x180055118  lea     rcx, [rbp+57h+var_B0]
0x18005511c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180055121  test    ebx, ebx
0x180055123  jz      short loc_180055138
0x180055125  cmp     ebx, 2
0x180055128  jz      loc_18005557E
0x18005512e  mov     r9d, ebx
0x180055131  mov     edx, 68Ch
0x180055136  jmp     short loc_18005518E
0x180055138  mov     [rbp+57h+cSubKeys], r15d
0x18005513c  mov     [rbp+57h+cbMaxSubKeyLen], r15d
0x180055140  mov     [rsp+110h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180055145  mov     [rsp+110h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18005514a  mov     [rsp+110h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x18005514f  mov     [rsp+110h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180055154  mov     [rsp+110h+lpcValues], r15; lpcValues
0x180055159  mov     [rsp+110h+lpcbMaxClassLen], r15; lpcbMaxClassLen
0x18005515e  lea     rax, [rbp+57h+cbMaxSubKeyLen]
0x180055162  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbMaxSubKeyLen
0x180055167  lea     rax, [rbp+57h+cSubKeys]
0x18005516b  mov     [rsp+110h+phkResult], rax; int
0x180055170  xor     r9d, r9d; lpReserved
0x180055173  xor     r8d, r8d; lpcchClass
0x180055176  xor     edx, edx; lpClass
0x180055178  mov     rcx, [rbp+57h+hKey]; hKey
0x18005517c  call    cs:__imp_RegQueryInfoKeyW
0x180055182  test    eax, eax
0x180055184  jz      short loc_1800551A5
0x180055186  mov     r9d, eax; char *
0x180055189  mov     edx, 69Eh; void *
0x18005518e  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180055195  mov     rcx, [rbp+5Fh]; this
0x180055199  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005519e  mov     ebx, eax
0x1800551a0  jmp     loc_180055581
0x1800551a5  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x1800551a8  inc     eax
0x1800551aa  mov     [rbp+57h+cbMaxSubKeyLen], eax
0x1800551ad  cmp     [rbp+57h+cSubKeys], r15d
0x1800551b1  jz      loc_18005557E
0x1800551b7  mov     r8d, eax
0x1800551ba  xor     edx, edx
0x1800551bc  lea     rcx, [rbp+57h+lpName]
0x1800551c0  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x1800551c5  nop
0x1800551c6  mov     rbx, [rbp+57h+lpName]
0x1800551ca  test    rbx, rbx
0x1800551cd  jz      loc_180055555
0x1800551d3  mov     [rbp+57h+var_90], r15
0x1800551d7  lea     rax, [rbp+57h+var_90]
0x1800551db  mov     [rbp+57h+var_B0], rax
0x1800551df  mov     [rbp+57h+var_A8], r15
0x1800551e3  mov     [rbp+57h+var_A0], 1
0x1800551e7  lea     rcx, [rbp+57h+var_A8]; struct PackageUtil **
0x1800551eb  call    ?CreateInstance@PackageUtil@@SAJPEAPEAV1@@Z; PackageUtil::CreateInstance(PackageUtil * *)
0x1800551f0  mov     edi, eax
0x1800551f2  lea     rcx, [rbp+57h+var_B0]
0x1800551f6  call    ??1?$out_param_t@V?$unique_ptr@VPackageUtil@@U?$default_delete@VPackageUtil@@@wistd@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>>::~out_param_t<wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>>(void)
0x1800551fb  test    edi, edi
0x1800551fd  jns     short loc_180055234
0x1800551ff  mov     rcx, [rbp+5Fh]; this
0x180055203  mov     r9d, edi; char *
0x180055206  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18005520d  mov     edx, 6A7h; void *
0x180055212  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055217  nop
0x180055218  xor     edx, edx
0x18005521a  lea     rcx, [rbp+57h+var_90]
0x18005521e  call    ?reset@?$unique_ptr@VPackageUtil@@U?$default_delete@VPackageUtil@@@wistd@@@wistd@@QEAAXPEAVPackageUtil@@@Z; wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>::reset(PackageUtil *)
0x180055223  nop
0x180055224  lea     rcx, [rbp+57h+lpName]; void *
0x180055228  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005522d  mov     ebx, edi
0x18005522f  jmp     loc_180055581
0x180055234  mov     qword ptr [rbp+57h+SecurityAttributes.nLength], 18h
0x18005523c  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], r15
0x180055240  mov     qword ptr [rbp+57h+SecurityAttributes.bInheritHandle], r15
0x180055244  mov     [rbp+57h+var_68], r15
0x180055248  lea     rax, [rbp+57h+var_68]
0x18005524c  mov     [rbp+57h+var_B0], rax
0x180055250  mov     [rbp+57h+var_A8], r15
0x180055254  mov     [rbp+57h+var_A0], 1
0x180055258  xor     r9d, r9d; SecurityDescriptorSize
0x18005525b  lea     r8, [rbp+57h+var_A8]; SecurityDescriptor
0x18005525f  lea     edx, [r9+1]; StringSDRevision
0x180055263  lea     rcx, aDPACiKrAuACiKa; "D:P(A;CI;KR;;;AU)(A;CI;KA;;;SY)"
0x18005526a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180055270  mov     edi, eax
0x180055272  lea     rcx, [rbp+57h+var_B0]
0x180055276  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x18005527b  test    edi, edi
0x18005527d  jnz     short loc_1800552B0
0x18005527f  mov     rcx, [rbp+5Fh]; this
0x180055283  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18005528a  mov     edx, 6AFh; void *
0x18005528f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180055294  mov     ebx, eax
0x180055296  lea     rcx, [rbp+57h+var_68]; void *
0x18005529a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18005529f  nop
0x1800552a0  xor     edx, edx
0x1800552a2  lea     rcx, [rbp+57h+var_90]
0x1800552a6  call    ?reset@?$unique_ptr@VPackageUtil@@U?$default_delete@VPackageUtil@@@wistd@@@wistd@@QEAAXPEAVPackageUtil@@@Z; wistd::unique_ptr<PackageUtil,wistd::default_delete<PackageUtil>>::reset(PackageUtil *)
0x1800552ab  jmp     loc_180055573
0x1800552b0  mov     rax, [rbp+57h+var_68]
0x1800552b4  mov     [rbp+57h+SecurityAttributes.lpSecurityDescriptor], rax
0x1800552b8  mov     [rbp+57h+var_70], r15
0x1800552bc  lea     rax, [rbp+57h+var_70]
0x1800552c0  mov     [rbp+57h+var_B0], rax
0x1800552c4  mov     [rbp+57h+var_A8], r15
0x1800552c8  mov     [rbp+57h+var_A0], 1
0x1800552cc  mov     [rsp+110h+lpcbMaxValueNameLen], r15; lpdwDisposition
0x1800552d1  lea     rax, [rbp+57h+var_A8]
0x1800552d5  mov     [rsp+110h+lpcValues], rax; phkResult
0x1800552da  lea     rax, [rbp+57h+SecurityAttributes]
0x1800552de  mov     [rsp+110h+lpcbMaxClassLen], rax; lpSecurityAttributes
0x1800552e3  mov     dword ptr [rsp+110h+lpcbMaxSubKeyLen], 0F003Fh; samDesired
0x1800552eb  mov     dword ptr [rsp+110h+phkResult], r15d; unsigned int
0x1800552f0  xor     r9d, r9d; lpClass
0x1800552f3  xor     r8d, r8d; Reserved
0x1800552f6  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800552fd  mov     rcx, rsi; hKey
0x180055300  call    cs:__imp_RegCreateKeyExW
0x180055306  mov     edi, eax
0x180055308  lea     rcx, [rbp+57h+var_B0]
0x18005530c  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180055311  test    edi, edi
0x180055313  jz      short loc_18005533D
0x180055315  mov     rcx, [rbp+5Fh]; this
0x180055319  mov     r9d, edi; char *
0x18005531c  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180055323  mov     edx, 6BCh; void *
0x180055328  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18005532d  mov     ebx, eax
0x18005532f  lea     rcx, [rbp+57h+var_70]
0x180055333  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180055338  jmp     loc_180055296
0x18005533d  mov     esi, [rbp+57h+cSubKeys]
0x180055340  test    esi, esi
0x180055342  jz      loc_1800554F5
0x180055348  mov     eax, [rbp+57h+cbMaxSubKeyLen]
0x18005534b  mov     [rbp+57h+cchName], eax
0x18005534e  dec     esi
0x180055350  mov     [rsp+110h+lpcValues], r15; lpftLastWriteTime
0x180055355  mov     [rsp+110h+lpcbMaxClassLen], r15; lpcchClass
0x18005535a  mov     [rsp+110h+lpcbMaxSubKeyLen], r15; lpClass
0x18005535f  mov     [rsp+110h+phkResult], r15; unsigned int
0x180055364  lea     r9, [rbp+57h+cchName]; lpcchName
0x180055368  mov     r8, rbx; lpName
0x18005536b  mov     edx, esi; dwIndex
0x18005536d  mov     rcx, [rbp+57h+hKey]; hKey
0x180055371  call    cs:__imp_RegEnumKeyExW
0x180055377  mov     rcx, [rbp+5Fh]; this
0x18005537b  test    eax, eax
0x18005537d  jz      short loc_180055395
0x18005537f  mov     r9d, eax; char *
0x180055382  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180055389  mov     edx, 6CAh; void *
0x18005538e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180055393  jmp     short loc_180055340
0x180055395  mov     [rbp+57h+hkey], r15
0x180055399  lea     rax, [rbp+57h+hkey]
0x18005539d  mov     [rbp+57h+var_B0], rax
0x1800553a1  mov     [rbp+57h+var_A8], r15
0x1800553a5  mov     [rbp+57h+var_A0], 1
0x1800553a9  lea     rax, [rbp+57h+var_A8]
0x1800553ad  mov     [rsp+110h+phkResult], rax; phkResult
0x1800553b2  mov     r9d, 0F003Fh; samDesired
0x1800553b8  xor     r8d, r8d; ulOptions
0x1800553bb  mov     rdx, rbx; lpSubKey
0x1800553be  mov     rcx, [rbp+57h+hKey]; hKey
0x1800553c2  call    cs:__imp_RegOpenKeyExW
0x1800553c8  mov     rcx, [rbp+5Fh]; this
0x1800553cc  mov     [rsp+110h+lpcbMaxSubKeyLen], rbx; char *
0x1800553d1  lea     rdx, aDeviceidWs; "DeviceId=%ws"
0x1800553d8  mov     [rsp+110h+phkResult], rdx; unsigned int
0x1800553dd  mov     r9d, eax; char *
0x1800553e0  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x1800553e7  mov     edx, 6D7h; void *
0x1800553ec  call    ?Log_IfWin32ErrorMsg@in1diag3@details@wil@@YAKPEAXIPEBDK1ZZ; wil::details::in1diag3::Log_IfWin32ErrorMsg(void *,uint,char const *,ulong,char const *,...)
0x1800553f1  mov     edi, eax
0x1800553f3  lea     rcx, [rbp+57h+var_B0]
0x1800553f7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x1800553fc  test    edi, edi
0x1800553fe  jnz     loc_1800554AC
0x180055404  mov     [rbp+57h+cbData], 4
0x18005540b  lea     rax, [rbp+57h+cbData]
0x18005540f  mov     [rsp+110h+lpcbMaxSubKeyLen], rax; lpcbData
0x180055414  lea     rax, [rbp+57h+Data]
0x180055418  mov     [rsp+110h+phkResult], rax; unsigned int
0x18005541d  xor     r9d, r9d; lpType
0x180055420  xor     r8d, r8d; lpReserved
0x180055423  lea     rdx, aState; "State"
0x18005542a  mov     rcx, [rbp+57h+hkey]; hKey
0x18005542e  call    cs:__imp_RegQueryValueExW
0x180055434  mov     rcx, [rbp+5Fh]; this
0x180055438  test    eax, eax
0x18005543a  jz      short loc_180055452
0x18005543c  mov     r9d, eax; char *
0x18005543f  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x180055446  mov     edx, 6E3h; void *
0x18005544b  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180055450  jmp     short loc_1800554AC
0x180055452  cmp     dword ptr [rbp+57h+Data], 1
0x180055456  jnz     short loc_1800554AC
0x180055458  lea     rax, [rbp+57h+cbData]
0x18005545c  mov     [rsp+110h+lpcbMaxClassLen], rax; pcbData
0x180055461  mov     [rsp+110h+lpcbMaxSubKeyLen], r15; pvData
0x180055466  mov     [rsp+110h+phkResult], r15; pdwType
0x18005546b  mov     r9d, 8; dwFlags
0x180055471  lea     r8, aAuthkey; "AuthKey"
0x180055478  xor     edx, edx; lpSubKey
0x18005547a  mov     rcx, [rbp+57h+hkey]; hkey
0x18005547e  call    cs:__imp_RegGetValueW
0x180055484  test    eax, eax
0x180055486  jnz     short loc_1800554AC
0x180055488  mov     byte ptr [rsp+110h+lpcbMaxSubKeyLen], r15b; bool
0x18005548d  mov     [rsp+110h+phkResult], rbx; int
0x180055492  mov     r9, [rbp+57h+hkey]; HKEY
0x180055496  mov     r8, [rbp+57h+var_70]; HKEY
0x18005549a  mov     rdx, [rbp+57h+var_90]; struct PackageUtil *
0x18005549e  mov     rcx, r14; this
0x1800554a1  call    ?UpdatePackageData@DeviceCredentialMgr@DcaMgr@@AEAAJPEAVPackageUtil@@PEAUHKEY__@@1PEBG_N@Z; DcaMgr::DeviceCredentialMgr::UpdatePackageData(PackageUtil *,HKEY__ *,HKEY__ *,ushort const *,bool)
0x1800554a6  mov     edi, eax
0x1800554a8  test    eax, eax
0x1800554aa  js      short loc_1800554BA
0x1800554ac  lea     rcx, [rbp+57h+hkey]
0x1800554b0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800554b5  jmp     loc_180055340
0x1800554ba  mov     rcx, [rbp+5Fh]; this
0x1800554be  mov     r9d, edi; char *
0x1800554c1  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x1800554c8  mov     edx, 6FAh; void *
0x1800554cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800554d2  nop
0x1800554d3  lea     rcx, [rbp+57h+hkey]
0x1800554d7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800554dc  nop
0x1800554dd  lea     rcx, [rbp+57h+var_70]
0x1800554e1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800554e6  nop
0x1800554e7  lea     rcx, [rbp+57h+var_68]; void *
0x1800554eb  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800554f0  jmp     loc_180055218
0x1800554f5  mov     rcx, [rbp+57h+var_70]; hKey
0x1800554f9  call    cs:__imp_RegFlushKey
0x1800554ff  mov     rcx, [rbp+57h+hKey]; hKey
0x180055503  call    cs:__imp_RegFlushKey
0x180055509  nop
  ... truncated ...
```
