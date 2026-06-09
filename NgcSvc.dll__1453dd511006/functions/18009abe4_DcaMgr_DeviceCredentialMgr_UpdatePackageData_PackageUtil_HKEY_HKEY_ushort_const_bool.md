# DcaMgr::DeviceCredentialMgr::UpdatePackageData(PackageUtil *,HKEY__ *,HKEY__ *,ushort const *,bool)

- ea: `0x18009abe4`
- end: `0x18009b310`
- name: `?UpdatePackageData@DeviceCredentialMgr@DcaMgr@@AEAAJPEAVPackageUtil@@PEAUHKEY__@@1PEBG_N@Z`
- size: `1836`
- prototype: `__int64 __fastcall(const WCHAR *this, struct PackageUtil *, HKEY, HKEY, LPCWSTR, bool)`
- caller_count: `2`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18005504c`
- `0x180099258`

## callees

- `0x1800024d8`
- `0x18000782c`
- `0x180022e30`
- `0x1800281e0`
- `0x1800288a0`
- `0x180032c20`
- `0x180047228`
- `0x180048304`
- `0x180048394`
- `0x180049a54`
- `0x180053144`
- `0x1800596ec`
- `0x18005bce8`
- `0x180097c6c`
- `0x180097cb4`
- `0x180098960`
- `0x18009982c`
- `0x18009abe4`
- `0x1800a1620`
- `0x1800a1f50`
- `0x1800a5d30`
- `0x1800a7bd4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009b21c`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18009b21c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009ae87`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009b0d7`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009ae87`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18009b0d7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009afba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009b1c7`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009afba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18009b1c7`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18009b25d`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18009b25d`
- `RPCRT4!RpcImpersonateClient` at `0x18009af33`
- `RPCRT4!RpcImpersonateClient` at `0x18009af33`

## string_xrefs

- `0x18009ac56`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009acbf`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009ad2e`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009ad97`: `onecore\ds\security\devicecredential\service\lib\devicecredentialmgr.cpp`
- `0x18009ac98`: `UserSid`

## pseudocode

```c
__int64 __fastcall DcaMgr::DeviceCredentialMgr::UpdatePackageData(
        const WCHAR *this,
        struct PackageUtil *a2,
        HKEY a3,
        HKEY a4,
        LPCWSTR a5,
        bool a6)
{
  int RegStringValue; // ebx
  unsigned int v10; // ebx
  int PackageFullNameFromUserSidPackageFamilyName; // eax
  int v12; // ebx
  const WCHAR *v13; // r15
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  LPCWSTR *p_lpSubKey; // rcx
  unsigned int v17; // ebx
  int v18; // eax
  PCWSTR v19; // rax
  int v20; // edx
  int v21; // ecx
  unsigned int v22; // eax
  int v23; // eax
  unsigned int v24; // eax
  const struct _tlgProvider_t *v25; // rax
  int v26; // r8d
  int v27; // r9d
  int v28; // eax
  int v29; // edx
  int v30; // ecx
  LPCWSTR *v31; // rcx
  int v32; // eax
  unsigned int v33; // ebx
  unsigned int v34; // eax
  const char *v35; // rbx
  unsigned int v36; // eax
  unsigned int v37; // eax
  const struct _tlgProvider_t *v38; // rax
  int v39; // r8d
  int v40; // r9d
  int dwOptions; // [rsp+28h] [rbp-79h]
  unsigned int dwOptionsa; // [rsp+28h] [rbp-79h]
  unsigned int dwOptionsb; // [rsp+28h] [rbp-79h]
  unsigned int dwOptionsc; // [rsp+28h] [rbp-79h]
  bool v46; // [rsp+58h] [rbp-49h] BYREF
  PCWSTR SourceString; // [rsp+60h] [rbp-41h] BYREF
  PCWSTR v48; // [rsp+68h] [rbp-39h] BYREF
  HKEY hKey; // [rsp+70h] [rbp-31h] BYREF
  unsigned __int16 *v50; // [rsp+78h] [rbp-29h] BYREF
  __int64 *p_SourceString; // [rsp+80h] [rbp-21h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp-19h] BYREF
  char v53; // [rsp+90h] [rbp-11h]
  BYTE Data[8]; // [rsp+98h] [rbp-9h] BYREF
  LPCWSTR lpSubKey; // [rsp+A0h] [rbp-1h] BYREF
  DWORD dwDisposition; // [rsp+A8h] [rbp+7h] BYREF
  unsigned __int16 *v57; // [rsp+B0h] [rbp+Fh] BYREF
  __int64 v58; // [rsp+B8h] [rbp+17h] BYREF
  PCWSTR v59; // [rsp+C0h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F0h] [rbp+4Fh]
  LPCWSTR v61; // [rsp+F8h] [rbp+57h] BYREF

  v61 = this;
  *(_DWORD *)Data = 0;
  v57 = 0;
  p_SourceString = (__int64 *)&v57;
  phkResult = 0;
  v53 = 1;
  RegStringValue = ReadRegStringValue(a4, 0, L"AppId");
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_SourceString);
  if ( RegStringValue >= 0 )
  {
    if ( !*v57 )
    {
LABEL_4:
      RegStringValue = 1;
      goto LABEL_71;
    }
    v50 = 0;
    p_SourceString = (__int64 *)&v50;
    phkResult = 0;
    v53 = 1;
    RegStringValue = ReadRegStringValue(a4, 0, L"UserSid");
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_SourceString);
    if ( RegStringValue < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x566,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)(unsigned int)RegStringValue,
        dwOptions);
LABEL_7:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v50);
      goto LABEL_71;
    }
    v48 = 0;
    p_SourceString = (__int64 *)&v48;
    phkResult = 0;
    v53 = 1;
    v10 = ReadRegStringValue(a4, 0, L"PackageFullName");
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_SourceString);
    if ( (int)(v10 + 0x80000000) >= 0 && v10 != -2147024894 )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x570,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)v10,
        dwOptions);
LABEL_11:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v48);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v50);
      goto LABEL_4;
    }
    SourceString = 0;
    hKey = 0;
    LOBYTE(v61) = 0;
    p_SourceString = (__int64 *)&SourceString;
    phkResult = 0;
    v53 = 1;
    PackageFullNameFromUserSidPackageFamilyName = PackageUtil::FindPackageFullNameFromUserSidPackageFamilyName(
                                                    a2,
                                                    v50,
                                                    v57,
                                                    (unsigned __int16 **)&phkResult,
                                                    (bool *)&v61);
    v12 = PackageFullNameFromUserSidPackageFamilyName;
    if ( PackageFullNameFromUserSidPackageFamilyName < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x57D,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)(unsigned int)PackageFullNameFromUserSidPackageFamilyName,
        dwOptionsa);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_SourceString);
    v13 = a5;
    if ( v12 < 0 )
    {
      if ( v12 != -2144927148 )
      {
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&SourceString);
        goto LABEL_11;
      }
      *(_DWORD *)Data = 3;
      v34 = RegSetValueExW(a4, L"State", 0, 4u, Data, 4u);
      if ( v34 )
      {
        RegStringValue = wil::details::in1diag3::Return_Win32(
                           retaddr,
                           (void *)0x605,
                           (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                           (const char *)v34,
                           dwOptionsb);
        goto LABEL_21;
      }
      goto LABEL_56;
    }
    if ( (_BYTE)v61 )
      goto LABEL_70;
    lpSubKey = 0;
    p_SourceString = (__int64 *)&lpSubKey;
    phkResult = 0;
    v53 = 1;
    RegStringValue = ConvertPackageFullNameToHashString(SourceString);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_SourceString);
    if ( RegStringValue < 0 )
    {
      v14 = (unsigned int)RegStringValue;
      v15 = 1414;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)v14,
        dwOptionsa);
LABEL_19:
      p_lpSubKey = &lpSubKey;
LABEL_20:
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(p_lpSubKey);
LABEL_21:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&SourceString);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v48);
      goto LABEL_7;
    }
    dwDisposition = 0;
    p_SourceString = (__int64 *)&hKey;
    phkResult = 0;
    v53 = 1;
    v17 = RegCreateKeyExW(a3, lpSubKey, 0, 0, 0, 0xF003Fu, 0, &phkResult, &dwDisposition);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_SourceString);
    if ( v17 )
    {
      v18 = wil::details::in1diag3::Return_Win32Msg(
              retaddr,
              (void *)0x595,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
              (const char *)v17,
              (unsigned int)"PackageNameHash=%ws",
              (const char *)lpSubKey);
LABEL_24:
      RegStringValue = v18;
      goto LABEL_19;
    }
    v19 = v48;
    if ( dwDisposition != 1 )
    {
      if ( v48 )
      {
        do
        {
          v29 = *(PCWSTR)((char *)v19 + (char *)SourceString - (char *)v48);
          v30 = *v19 - v29;
          if ( v30 )
            break;
          ++v19;
        }
        while ( v29 );
        if ( !v30 )
        {
          v31 = &lpSubKey;
LABEL_69:
          wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(v31);
          goto LABEL_70;
        }
      }
      goto LABEL_44;
    }
    if ( !v48 )
      goto LABEL_31;
    do
    {
      v20 = *(PCWSTR)((char *)v19 + (char *)SourceString - (char *)v48);
      v21 = *v19 - v20;
      if ( v21 )
        break;
      ++v19;
    }
    while ( v20 );
    if ( v21 )
    {
      *(_DWORD *)Data = 1;
    }
    else
    {
LABEL_31:
      *(_DWORD *)Data = 2;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v48,
        0);
    }
    if ( !a6 )
    {
LABEL_40:
      v24 = RegSetValueExW(hKey, L"DeploymentFlag", 0, 4u, Data, 4u);
      if ( v24 )
      {
        v18 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0x5CB,
                (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                (const char *)v24,
                dwOptionsa);
        goto LABEL_24;
      }
      v25 = DevCredSvcTraceLoggingProvider::Provider();
      if ( *(_DWORD *)v25 > 4u )
      {
        LODWORD(v61) = *(_DWORD *)Data;
        v59 = SourceString;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
          (_DWORD)v25,
          (unsigned int)&word_180108C56,
          v26,
          v27,
          (__int64)&v59,
          (__int64)&v61);
      }
LABEL_44:
      v28 = WriteRegStringValue(hKey, 0, (char *)L"PackageFullName", SourceString);
      RegStringValue = v28;
      if ( v28 < 0 )
      {
        v14 = (unsigned int)v28;
        v15 = 1504;
        goto LABEL_18;
      }
      v32 = WriteRegStringValue(a4, 0, (char *)L"PackageFullName", SourceString);
      RegStringValue = v32;
      if ( v32 < 0 )
      {
        v14 = (unsigned int)v32;
        v15 = 1510;
        goto LABEL_18;
      }
      v58 = 0;
      p_SourceString = &v58;
      phkResult = 0;
      v53 = 1;
      v33 = RegCreateKeyExW(hKey, v13, 0, 0, 0, 0xF003Fu, 0, &phkResult, 0);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_SourceString);
      if ( v33 )
      {
        RegStringValue = wil::details::in1diag3::Return_Win32(
                           retaddr,
                           (void *)0x5F4,
                           (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                           (const char *)v33,
                           dwOptionsb);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v58);
        goto LABEL_19;
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v58);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&lpSubKey);
LABEL_56:
      if ( v48 )
      {
        v61 = 0;
        p_SourceString = (__int64 *)&v61;
        phkResult = 0;
        v53 = 1;
        RegStringValue = ConvertPackageFullNameToHashString(v48);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&p_SourceString);
        if ( RegStringValue < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x60E,
            (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
            (const char *)(unsigned int)RegStringValue,
            dwOptionsb);
          p_lpSubKey = &v61;
          goto LABEL_20;
        }
        v35 = (const char *)v61;
        p_SourceString = (__int64 *)&hKey;
        phkResult = 0;
        v53 = 1;
        v36 = RegOpenKeyExW(a3, v61, 0, 0xF003Fu, &phkResult);
        LODWORD(v35) = wil::details::in1diag3::Log_IfWin32ErrorMsg(
                         retaddr,
                         (void *)0x617,
                         (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
                         (const char *)v36,
                         (unsigned int)"PackageNameHash=%ws",
                         v35);
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&p_SourceString);
        if ( !(_DWORD)v35 )
        {
          v37 = RegDeleteTreeW(hKey, v13);
          if ( v37 )
            wil::details::in1diag3::_Log_Win32(
              retaddr,
              (void *)0x61B,
              (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
              (const char *)v37,
              dwOptionsc);
          v38 = DevCredSvcTraceLoggingProvider::Provider();
          if ( *(_DWORD *)v38 > 4u )
          {
            v59 = v13;
            p_SourceString = (__int64 *)v48;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              (_DWORD)v38,
              (unsigned int)&dword_180108C1C,
              v39,
              v40,
              (__int64)&p_SourceString,
              (__int64)&v59);
          }
        }
        v31 = &v61;
        goto LABEL_69;
      }
LABEL_70:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&SourceString);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v48);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v50);
      RegStringValue = 0;
      goto LABEL_71;
    }
    LOBYTE(v61) = 0;
    p_SourceString = (__int64 *)&v61;
    LOWORD(phkResult) = 256;
    v22 = RpcImpersonateClient(0);
    v46 = 0;
    if ( v22 )
    {
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x5C1,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)v22,
        dwOptionsa);
LABEL_39:
      wil::details::ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c___::operator()(&p_SourceString);
      goto LABEL_40;
    }
    LOBYTE(v61) = 1;
    v23 = PackageUtil::ValidateCapabilityInManifest((char *)SourceString, &v46);
    if ( v23 >= 0 )
    {
      if ( v46 )
        goto LABEL_39;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x5BB,
        (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
        (const char *)(unsigned int)v23,
        dwOptionsa);
    }
    *(_DWORD *)Data = 0;
    goto LABEL_39;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x55C,
    (unsigned int)"onecore\\ds\\security\\devicecredential\\service\\lib\\devicecredentialmgr.cpp",
    (const char *)(unsigned int)RegStringValue,
    dwOptions);
LABEL_71:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v57);
  return (unsigned int)RegStringValue;
}

```

## disassembly

```asm
0x18009abe4  mov     rax, rsp
0x18009abe7  mov     [rax+10h], rbx
0x18009abeb  mov     [rax+18h], rdi
0x18009abef  mov     [rax+8], rcx
0x18009abf3  push    rbp
0x18009abf4  push    r12
0x18009abf6  push    r13
0x18009abf8  push    r14
0x18009abfa  push    r15
0x18009abfc  lea     rbp, [rax-4Fh]
0x18009ac00  sub     rsp, 0C0h
0x18009ac07  mov     r14, r9
0x18009ac0a  mov     r12, r8
0x18009ac0d  mov     rdi, rdx
0x18009ac10  xor     r13d, r13d
0x18009ac13  mov     dword ptr [rbp+47h+Data], r13d
0x18009ac17  mov     [rbp+47h+var_38], r13
0x18009ac1b  lea     rax, [rbp+47h+var_38]
0x18009ac1f  mov     [rbp+47h+var_68], rax
0x18009ac23  mov     [rbp+47h+var_60], r13
0x18009ac27  mov     [rbp+47h+var_58], 1
0x18009ac2b  lea     r9, [rbp+47h+var_60]
0x18009ac2f  lea     r8, aAppid; "AppId"
0x18009ac36  xor     edx, edx; lpSubKey
0x18009ac38  mov     rcx, r14; hkey
0x18009ac3b  call    ReadRegStringValue
0x18009ac40  mov     ebx, eax
0x18009ac42  lea     rcx, [rbp+47h+var_68]
0x18009ac46  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18009ac4b  test    ebx, ebx
0x18009ac4d  jns     short loc_18009AC6C
0x18009ac4f  mov     rcx, [rbp+4Fh]; this
0x18009ac53  mov     r9d, ebx; char *
0x18009ac56  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18009ac5d  mov     edx, 55Ch; void *
0x18009ac62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009ac67  jmp     loc_18009B2E8
0x18009ac6c  mov     rax, [rbp+47h+var_38]
0x18009ac70  cmp     [rax], r13w
0x18009ac74  jnz     short loc_18009AC80
0x18009ac76  mov     ebx, 1
0x18009ac7b  jmp     loc_18009B2E8
0x18009ac80  mov     [rbp+47h+var_70], r13
0x18009ac84  lea     rax, [rbp+47h+var_70]
0x18009ac88  mov     [rbp+47h+var_68], rax
0x18009ac8c  mov     [rbp+47h+var_60], r13
0x18009ac90  mov     [rbp+47h+var_58], 1
0x18009ac94  lea     r9, [rbp+47h+var_60]
0x18009ac98  lea     r8, aUsersid; "UserSid"
0x18009ac9f  xor     edx, edx; lpSubKey
0x18009aca1  mov     rcx, r14; hkey
0x18009aca4  call    ReadRegStringValue
0x18009aca9  mov     ebx, eax
0x18009acab  lea     rcx, [rbp+47h+var_68]
0x18009acaf  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18009acb4  test    ebx, ebx
0x18009acb6  jns     short loc_18009ACDF
0x18009acb8  mov     rcx, [rbp+4Fh]; this
0x18009acbc  mov     r9d, ebx; char *
0x18009acbf  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18009acc6  mov     edx, 566h; void *
0x18009accb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009acd0  nop
0x18009acd1  lea     rcx, [rbp+47h+var_70]; void *
0x18009acd5  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18009acda  jmp     loc_18009B2E8
0x18009acdf  mov     [rbp+47h+var_80], r13
0x18009ace3  lea     rax, [rbp+47h+var_80]
0x18009ace7  mov     [rbp+47h+var_68], rax
0x18009aceb  mov     [rbp+47h+var_60], r13
0x18009acef  mov     [rbp+47h+var_58], 1
0x18009acf3  lea     r9, [rbp+47h+var_60]
0x18009acf7  lea     r8, aPackagefullnam; "PackageFullName"
0x18009acfe  xor     edx, edx; lpSubKey
0x18009ad00  mov     rcx, r14; hkey
0x18009ad03  call    ReadRegStringValue
0x18009ad08  mov     ebx, eax
0x18009ad0a  lea     rcx, [rbp+47h+var_68]
0x18009ad0e  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18009ad13  mov     eax, 80000000h
0x18009ad18  lea     ecx, [rbx+rax]
0x18009ad1b  test    eax, ecx
0x18009ad1d  jnz     short loc_18009AD58
0x18009ad1f  cmp     ebx, 80070002h
0x18009ad25  jz      short loc_18009AD58
0x18009ad27  mov     rcx, [rbp+4Fh]; this
0x18009ad2b  mov     r9d, ebx; char *
0x18009ad2e  lea     r8, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18009ad35  mov     edx, 570h; void *
0x18009ad3a  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18009ad3f  nop
0x18009ad40  lea     rcx, [rbp+47h+var_80]; void *
0x18009ad44  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18009ad49  nop
0x18009ad4a  lea     rcx, [rbp+47h+var_70]; void *
0x18009ad4e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18009ad53  jmp     loc_18009AC76
0x18009ad58  mov     [rbp+47h+SourceString], r13
0x18009ad5c  mov     [rbp+47h+hKey], r13
0x18009ad60  mov     byte ptr [rbp+47h+arg_0], r13b
0x18009ad64  lea     rax, [rbp+47h+SourceString]
0x18009ad68  mov     [rbp+47h+var_68], rax
0x18009ad6c  mov     [rbp+47h+var_60], r13
0x18009ad70  mov     [rbp+47h+var_58], 1
0x18009ad74  lea     rax, [rbp+47h+arg_0]
0x18009ad78  mov     qword ptr [rsp+0E0h+dwOptions], rax; int
0x18009ad7d  lea     r9, [rbp+47h+var_60]; unsigned __int16 **
0x18009ad81  mov     r8, [rbp+47h+var_38]; unsigned __int16 *
0x18009ad85  mov     rdx, [rbp+47h+var_70]; unsigned __int16 *
0x18009ad89  mov     rcx, rdi; this
0x18009ad8c  call    ?FindPackageFullNameFromUserSidPackageFamilyName@PackageUtil@@QEAAJPEBG0PEAPEAGPEA_N@Z; PackageUtil::FindPackageFullNameFromUserSidPackageFamilyName(ushort const *,ushort const *,ushort * *,bool *)
0x18009ad91  mov     ebx, eax
0x18009ad93  mov     rcx, [rbp+4Fh]; this
0x18009ad97  lea     rdi, aOnecoreDsSecur_19; "onecore\\ds\\security\\devicecredential"...
0x18009ad9e  test    eax, eax
0x18009ada0  jns     short loc_18009ADB3
0x18009ada2  mov     r9d, eax; char *
0x18009ada5  mov     r8, rdi; unsigned int
0x18009ada8  mov     edx, 57Dh; void *
0x18009adad  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009adb2  nop
0x18009adb3  lea     rcx, [rbp+47h+var_68]
0x18009adb7  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18009adbc  mov     r15, [rbp+47h+arg_20]
0x18009adc0  test    ebx, ebx
0x18009adc2  js      loc_18009B17C
0x18009adc8  cmp     byte ptr [rbp+47h+arg_0], r13b
0x18009adcc  jnz     loc_18009B2BE
0x18009add2  mov     [rbp+47h+lpSubKey], r13
0x18009add6  lea     rax, [rbp+47h+lpSubKey]
0x18009adda  mov     [rbp+47h+var_68], rax
0x18009adde  mov     [rbp+47h+var_60], r13
0x18009ade2  mov     [rbp+47h+var_58], 1
0x18009ade6  lea     rdx, [rbp+47h+var_60]
0x18009adea  mov     rcx, [rbp+47h+SourceString]; SourceString
0x18009adee  call    ConvertPackageFullNameToHashString
0x18009adf3  mov     ebx, eax
0x18009adf5  lea     rcx, [rbp+47h+var_68]
0x18009adf9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18009adfe  test    ebx, ebx
0x18009ae00  jns     short loc_18009AE42
0x18009ae02  mov     r9d, ebx; char *
0x18009ae05  mov     edx, 586h; void *
0x18009ae0a  mov     rcx, [rbp+4Fh]; this
0x18009ae0e  mov     r8, rdi; unsigned int
0x18009ae11  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009ae16  lea     rcx, [rbp+47h+lpSubKey]; void *
0x18009ae1a  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18009ae1f  nop
0x18009ae20  lea     rcx, [rbp+47h+hKey]
0x18009ae24  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18009ae29  nop
0x18009ae2a  lea     rcx, [rbp+47h+SourceString]; void *
0x18009ae2e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18009ae33  nop
0x18009ae34  lea     rcx, [rbp+47h+var_80]; void *
0x18009ae38  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x18009ae3d  jmp     loc_18009ACD1
0x18009ae42  mov     [rbp+47h+dwDisposition], r13d
0x18009ae46  lea     rax, [rbp+47h+hKey]
0x18009ae4a  mov     [rbp+47h+var_68], rax
0x18009ae4e  mov     [rbp+47h+var_60], r13
0x18009ae52  mov     [rbp+47h+var_58], 1
0x18009ae56  lea     rax, [rbp+47h+dwDisposition]
0x18009ae5a  mov     [rsp+0E0h+lpdwDisposition], rax; lpdwDisposition
0x18009ae5f  lea     rax, [rbp+47h+var_60]
0x18009ae63  mov     [rsp+0E0h+phkResult], rax; phkResult
0x18009ae68  mov     [rsp+0E0h+lpSecurityAttributes], r13; lpSecurityAttributes
0x18009ae6d  mov     [rsp+0E0h+samDesired], 0F003Fh; samDesired
0x18009ae75  mov     [rsp+0E0h+dwOptions], r13d; int
0x18009ae7a  xor     r9d, r9d; lpClass
0x18009ae7d  xor     r8d, r8d; Reserved
0x18009ae80  mov     rdx, [rbp+47h+lpSubKey]; lpSubKey
0x18009ae84  mov     rcx, r12; hKey
0x18009ae87  call    cs:__imp_RegCreateKeyExW
0x18009ae8d  mov     ebx, eax
0x18009ae8f  lea     rcx, [rbp+47h+var_68]
0x18009ae93  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18009ae98  test    ebx, ebx
0x18009ae9a  jz      short loc_18009AECC
0x18009ae9c  mov     rdx, [rbp+47h+lpSubKey]
0x18009aea0  mov     rcx, [rbp+4Fh]; this
0x18009aea4  mov     qword ptr [rsp+0E0h+samDesired], rdx; char *
0x18009aea9  lea     rdx, aPackagenamehas; "PackageNameHash=%ws"
0x18009aeb0  mov     qword ptr [rsp+0E0h+dwOptions], rdx; unsigned int
0x18009aeb5  mov     r9d, ebx; char *
0x18009aeb8  mov     r8, rdi; unsigned int
0x18009aebb  mov     edx, 595h; void *
0x18009aec0  call    ?Return_Win32Msg@in1diag3@details@wil@@YAJPEAXIPEBDK1ZZ; wil::details::in1diag3::Return_Win32Msg(void *,uint,char const *,ulong,char const *,...)
0x18009aec5  mov     ebx, eax
0x18009aec7  jmp     loc_18009AE16
0x18009aecc  mov     rax, [rbp+47h+var_80]
0x18009aed0  cmp     [rbp+47h+dwDisposition], 1
0x18009aed4  jnz     loc_18009B041
0x18009aeda  test    rax, rax
0x18009aedd  jz      short loc_18009AF07
0x18009aedf  mov     r8, [rbp+47h+SourceString]
0x18009aee3  sub     r8, rax
0x18009aee6  movzx   ecx, word ptr [rax]
0x18009aee9  movzx   edx, word ptr [rax+r8]
0x18009aeee  sub     ecx, edx
0x18009aef0  jnz     short loc_18009AEFA
0x18009aef2  add     rax, 2
0x18009aef6  test    edx, edx
0x18009aef8  jnz     short loc_18009AEE6
0x18009aefa  test    ecx, ecx
0x18009aefc  jz      short loc_18009AF07
0x18009aefe  mov     dword ptr [rbp+47h+Data], 1
0x18009af05  jmp     short loc_18009AF19
0x18009af07  mov     dword ptr [rbp+47h+Data], 2
0x18009af0e  xor     edx, edx
0x18009af10  lea     rcx, [rbp+47h+var_80]
0x18009af14  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009af19  cmp     [rbp+47h+arg_28], r13b
0x18009af1d  jz      short loc_18009AF95
0x18009af1f  mov     byte ptr [rbp+47h+arg_0], r13b
0x18009af23  lea     rax, [rbp+47h+arg_0]
0x18009af27  mov     [rbp+47h+var_68], rax
0x18009af2b  mov     word ptr [rbp+47h+var_60], 100h
0x18009af31  xor     ecx, ecx; BindingHandle
0x18009af33  call    cs:__imp_RpcImpersonateClient
0x18009af39  mov     [rbp+47h+var_90], r13b
0x18009af3d  test    eax, eax
0x18009af3f  jz      short loc_18009AF57
0x18009af41  mov     rcx, [rbp+4Fh]; this
0x18009af45  mov     r9d, eax; char *
0x18009af48  mov     r8, rdi; unsigned int
0x18009af4b  mov     edx, 5C1h; void *
0x18009af50  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x18009af55  jmp     short loc_18009AF8C
0x18009af57  mov     byte ptr [rbp+47h+arg_0], 1
0x18009af5b  lea     rdx, [rbp+47h+var_90]; bool *
0x18009af5f  mov     rcx, [rbp+47h+SourceString]; char *
0x18009af63  call    ?ValidateCapabilityInManifest@PackageUtil@@SAJPEBGPEA_N@Z; PackageUtil::ValidateCapabilityInManifest(ushort const *,bool *)
0x18009af68  mov     rcx, [rbp+4Fh]; this
0x18009af6c  test    eax, eax
0x18009af6e  jns     short loc_18009AF82
0x18009af70  mov     r9d, eax; char *
0x18009af73  mov     r8, rdi; unsigned int
0x18009af76  mov     edx, 5BBh; void *
0x18009af7b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18009af80  jmp     short loc_18009AF88
0x18009af82  cmp     [rbp+47h+var_90], r13b
0x18009af86  jnz     short loc_18009AF8C
0x18009af88  mov     dword ptr [rbp+47h+Data], r13d
0x18009af8c  lea     rcx, [rbp+47h+var_68]
0x18009af90  call    wil__details__ScopeExitFnGuard__lambda_7f3d40de85dbd45b8cf192816ff9c04c_____operator__
0x18009af95  mov     [rsp+0E0h+samDesired], 4; cbData
0x18009af9d  lea     rax, [rbp+47h+Data]
0x18009afa1  mov     qword ptr [rsp+0E0h+dwOptions], rax; unsigned int
0x18009afa6  mov     r9d, 4; dwType
0x18009afac  xor     r8d, r8d; Reserved
0x18009afaf  lea     rdx, aDeploymentflag; "DeploymentFlag"
0x18009afb6  mov     rcx, [rbp+47h+hKey]; hKey
0x18009afba  call    cs:__imp_RegSetValueExW
0x18009afc0  test    eax, eax
0x18009afc2  jz      short loc_18009AFDD
0x18009afc4  mov     rcx, [rbp+4Fh]; this
0x18009afc8  mov     r9d, eax; char *
0x18009afcb  mov     r8, rdi; unsigned int
0x18009afce  mov     edx, 5CBh; void *
0x18009afd3  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18009afd8  jmp     loc_18009AEC5
0x18009afdd  call    ?Provider@DevCredSvcTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; DevCredSvcTraceLoggingProvider::Provider(void)
0x18009afe2  mov     ecx, [rax]
0x18009afe4  cmp     ecx, 4
0x18009afe7  jbe     short loc_18009B018
0x18009afe9  mov     ecx, dword ptr [rbp+47h+Data]
0x18009afec  mov     dword ptr [rbp+47h+arg_0], ecx
0x18009afef  mov     rcx, [rbp+47h+SourceString]
0x18009aff3  mov     [rbp+47h+var_28], rcx
0x18009aff7  lea     rcx, [rbp+47h+arg_0]
0x18009affb  mov     qword ptr [rsp+0E0h+samDesired], rcx
0x18009b000  lea     rcx, [rbp+47h+var_28]
0x18009b004  mov     qword ptr [rsp+0E0h+dwOptions], rcx
0x18009b009  lea     rdx, word_180108C56
0x18009b010  mov     rcx, rax
0x18009b013  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x18009b018  mov     r9, [rbp+47h+SourceString]; lpData
0x18009b01c  lea     r8, aPackagefullnam; "PackageFullName"
0x18009b023  xor     edx, edx; lpSubKey
0x18009b025  mov     rcx, [rbp+47h+hKey]; hKey
0x18009b029  call    WriteRegStringValue
0x18009b02e  mov     ebx, eax
0x18009b030  test    eax, eax
0x18009b032  jns     short loc_18009B06E
0x18009b034  mov     r9d, eax
0x18009b037  mov     edx, 5E0h
0x18009b03c  jmp     loc_18009AE0A
0x18009b041  test    rax, rax
0x18009b044  jz      short loc_18009B018
0x18009b046  mov     r8, [rbp+47h+SourceString]
0x18009b04a  sub     r8, rax
0x18009b04d  movzx   ecx, word ptr [rax]
0x18009b050  movzx   edx, word ptr [rax+r8]
0x18009b055  sub     ecx, edx
0x18009b057  jnz     short loc_18009B061
0x18009b059  add     rax, 2
0x18009b05d  test    edx, edx
0x18009b05f  jnz     short loc_18009B04D
  ... truncated ...
```
