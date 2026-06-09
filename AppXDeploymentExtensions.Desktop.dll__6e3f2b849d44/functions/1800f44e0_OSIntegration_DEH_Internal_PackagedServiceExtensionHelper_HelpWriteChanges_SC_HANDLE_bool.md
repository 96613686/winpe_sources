# OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::HelpWriteChanges(SC_HANDLE__ *,bool)

- ea: `0x1800f44e0`
- end: `0x1800f4bf7`
- name: `?HelpWriteChanges@PackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@AEAAXPEAUSC_HANDLE__@@_N@Z`
- size: `1815`
- prototype: `void __fastcall(OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *this, SC_HANDLE hService, char)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800f52ac`

## callees

- `0x180001ef4`
- `0x18001f678`
- `0x180033e50`
- `0x18004227c`
- `0x180048cd4`
- `0x1800490c4`
- `0x18004dd78`
- `0x180059570`
- `0x180064a88`
- `0x180072114`
- `0x18007cdc0`
- `0x18007daf0`
- `0x1800861b8`
- `0x1800e2c4c`
- `0x1800e50d0`
- `0x1800f2b14`
- `0x1800f3d68`
- `0x1800f44e0`
- `0x1800f5624`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800f48af`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x1800f48af`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800f48d8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x1800f48d8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f47ef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f4811`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f47ef`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x1800f4811`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x1800f4672`
- `api-ms-win-service-management-l1-1-0!CreateServiceW` at `0x1800f4672`
- `api-ms-win-service-winsvc-l1-1-0!ChangeServiceConfig2A` at `0x1800f46ce`
- `api-ms-win-service-winsvc-l1-1-0!ChangeServiceConfig2A` at `0x1800f46ce`
- `api-ms-win-service-management-l2-1-0!SetServiceObjectSecurity` at `0x1800f48fe`
- `api-ms-win-service-management-l2-1-0!SetServiceObjectSecurity` at `0x1800f48fe`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800f4939`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800f4974`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800f49be`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800f49eb`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800f4939`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800f4974`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800f49be`
- `api-ms-win-service-management-l2-1-0!ChangeServiceConfig2W` at `0x1800f49eb`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800f488d`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x1800f488d`

## string_xrefs

- `0x1800f46fa`: `System\CurrentControlSet\Services`
- `0x1800f4a53`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4a6e`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4a89`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4aa4`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4abf`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4ad4`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4ae9`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4afe`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4b13`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4b28`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4b3d`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4b52`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4b64`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4b79`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4b8e`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4ba3`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4bb8`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4bcd`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`
- `0x1800f4be2`: `onecore\admin\appmodel\osim\src\deh\appx\packagedservices\packagedserviceextensionhelper.cpp`

## pseudocode

```c
void __fastcall OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::HelpWriteChanges(
        OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *this,
        SC_HANDLE hService,
        char a3)
{
  char v6; // cl
  bool v7; // zf
  char v8; // al
  const struct _tlgProvider_t *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  const WCHAR *lpServiceStartName; // rax
  const WCHAR *v13; // r8
  SC_HANDLE ServiceW; // rax
  const char *v15; // r9
  int v16; // eax
  int v17; // eax
  unsigned int v18; // r9d
  int v19; // eax
  unsigned int v20; // r9d
  int v21; // eax
  int v22; // eax
  const char *v23; // r9
  const char *v24; // r9
  const char *v25; // r9
  const char *v26; // r9
  const char *v27; // r9
  const char *v28; // r9
  const char *v29; // r9
  const char *v30; // r9
  DWORD dwServiceType; // [rsp+20h] [rbp-E0h]
  DWORD dwServiceTypea; // [rsp+20h] [rbp-E0h]
  DWORD dwServiceTypeb; // [rsp+20h] [rbp-E0h]
  SC_HANDLE hServicea; // [rsp+70h] [rbp-90h] BYREF
  __int64 v35; // [rsp+78h] [rbp-88h] BYREF
  PSID v36; // [rsp+80h] [rbp-80h] BYREF
  PSID Sid; // [rsp+88h] [rbp-78h] BYREF
  int v38; // [rsp+90h] [rbp-70h] BYREF
  PACL NewAcl; // [rsp+98h] [rbp-68h] BYREF
  HKEY phkResult; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v42; // [rsp+B0h] [rbp-50h]
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+C0h] [rbp-40h] BYREF
  int v44; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+F4h] [rbp-Ch]
  __int64 v46; // [rsp+100h] [rbp+0h]
  __int64 v47; // [rsp+108h] [rbp+8h]
  int v48; // [rsp+110h] [rbp+10h]
  PSID v49; // [rsp+118h] [rbp+18h]
  _SERVICE_TRIGGER_INFO v50; // [rsp+120h] [rbp+20h] BYREF
  _OWORD pSecurityDescriptor[2]; // [rsp+138h] [rbp+38h] BYREF
  __int64 v52; // [rsp+158h] [rbp+58h]
  SC_HANDLE *p_hServicea; // [rsp+160h] [rbp+60h]
  char v54; // [rsp+168h] [rbp+68h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]
  __int64 Info; // [rsp+1C8h] [rbp+C8h] BYREF

  OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::CheckRegistrationState(this, &v41, hService);
  v6 = v42;
  if ( (v42 & 1) != 0 )
    goto LABEL_23;
  v7 = v41 == 0;
  if ( !v41 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v6 = v42;
    v7 = v41 == 0;
  }
  if ( v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x29E,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)0x8000FFFFLL,
      dwServiceType);
  if ( (v6 & 0x40) != 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A1,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)0x80073D27LL,
      dwServiceType);
  if ( (v6 & 0x20) == 0 )
  {
    if ( (v6 & 0x10) != 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2A8,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        (const char *)0x80073D26LL,
        dwServiceType);
    if ( a3 || (v8 = 1, (v6 & 8) != 0) )
      v8 = 0;
    if ( v8 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x2AD,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        (const char *)0x80073D26LL,
        dwServiceType);
  }
  if ( (v6 & 2) == 0 )
  {
    MicrosoftTelemetryAssertTriggeredNoArgs();
    v6 = v42;
  }
  if ( (v6 & 0x24) != 0 )
  {
    if ( !a3 )
      goto LABEL_22;
LABEL_18:
    if ( (v6 & 0x20) == 0 )
    {
      v9 = AppXDeploymentServerTelemetry::Provider();
      if ( *(_DWORD *)v9 > 5u )
      {
        if ( (unsigned __int8)tlgKeywordOn(v9, 0x400000000000LL, v10, v9) )
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
            v11,
            &dword_18021E214,
            0);
      }
    }
    goto LABEL_22;
  }
  if ( a3 )
    goto LABEL_18;
  MicrosoftTelemetryAssertTriggeredNoArgs();
LABEL_22:
  OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::HelpDeleteService(this, hService);
LABEL_23:
  hServicea = 0;
  if ( *((_DWORD *)this + 18) )
    lpServiceStartName = (const WCHAR *)*((_QWORD *)this + 10);
  else
    lpServiceStartName = 0;
  if ( *((_DWORD *)this + 12) )
    v13 = (const WCHAR *)*((_QWORD *)this + 7);
  else
    v13 = 0;
  ServiceW = CreateServiceW(
               hService,
               *((LPCWSTR *)this + 1),
               v13,
               0x50002u,
               0x210u,
               *((_DWORD *)this + 42),
               0,
               *((LPCWSTR *)this + 4),
               0,
               0,
               *((LPCWSTR *)this + 16),
               lpServiceStartName,
               0);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
    &hServicea,
    ServiceW);
  if ( !hServicea )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x2D0,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)retaddr);
  p_hServicea = &hServicea;
  v54 = 1;
  if ( *((_BYTE *)this + 172) )
  {
    LODWORD(Info) = 1;
    if ( !ChangeServiceConfig2A(hServicea, 3u, &Info) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x2E6,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        v15);
  }
  phkResult = 0;
  v35 = 0;
  v16 = Common::RegistryKey::Open(&phkResult, HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services", 0xF003Fu);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2EF,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)v16,
      dwServiceTypea);
  v17 = Common::RegistryKey::OpenSubKey(
          (Common::RegistryKey *)&phkResult,
          *((const unsigned __int16 **)this + 1),
          0xF003Fu,
          (struct Common::AutoHandleHKEY *)&v35);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F0,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)v17,
      dwServiceTypea);
  v19 = Common::RegistryKey::SetStringValue(
          (Common::RegistryKey *)&v35,
          L"PackageFullName",
          *((const unsigned __int16 **)this + 23),
          v18);
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F2,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)v19,
      dwServiceTypea);
  v21 = Common::RegistryKey::SetStringValue(
          (Common::RegistryKey *)&v35,
          L"AppUserModelId",
          *((const unsigned __int16 **)this + 26),
          v20);
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F3,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)v21,
      dwServiceTypea);
  LODWORD(Info) = *((_DWORD *)this + 56);
  v22 = Common::RegistryKey::SetValue((Common::RegistryKey *)&v35, L"PackageOrigin", &Info, 4u, 4u);
  if ( v22 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2F4,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      (const char *)(unsigned int)v22,
      dwServiceTypeb);
  Sid = 0;
  v36 = 0;
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &Sid,
    0);
  ConvertStringSidToSidW(L"S-1-5-11", &Sid);
  wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
    &v36,
    0);
  ConvertStringSidToSidW(L"S-1-5-80-1949724575-2387902436-65106593-1201171665-3967308604", &v36);
  pListOfExplicitEntries.grfAccessPermissions = 131581;
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  memset(&pListOfExplicitEntries.Trustee, 0, 20);
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)Sid;
  v44 = 983551;
  v45 = 1;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = v36;
  memset(pSecurityDescriptor, 0, sizeof(pSecurityDescriptor));
  v52 = 0;
  NewAcl = 0;
  if ( SetEntriesInAclW(2u, &pListOfExplicitEntries, 0, &NewAcl) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x31A,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      v23);
  if ( !InitializeSecurityDescriptor(pSecurityDescriptor, 1u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x31B,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      v24);
  if ( !SetSecurityDescriptorDacl(pSecurityDescriptor, 1, NewAcl, 0) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x31C,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      v25);
  if ( !SetServiceObjectSecurity(hServicea, 4u, pSecurityDescriptor) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x31D,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      v26);
  if ( *((_DWORD *)this + 24) )
  {
    Info = *((_QWORD *)this + 13);
    if ( !ChangeServiceConfig2W(hServicea, 1u, &Info) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x323,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        v27);
  }
  if ( *((_BYTE *)this + 304) )
  {
    LODWORD(Info) = 4;
    if ( !ChangeServiceConfig2W(hServicea, 0xCu, &Info) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x32A,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
        v28);
  }
  memset(&v50, 0, sizeof(v50));
  if ( OSIntegration::DEH::Internal::PackagedServiceTriggerData::GetServiceTriggerInfo(
         (OSIntegration::DEH::Internal::PackagedServiceExtensionHelper *)((char *)this + 256),
         &v50)
    && !ChangeServiceConfig2W(hServicea, 8u, &v50) )
  {
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x330,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      v29);
  }
  v38 = 1;
  if ( !ChangeServiceConfig2W(hServicea, 5u, &v38) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x336,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\appx\\packagedservices\\packagedserviceextensionhelper.cpp",
      v30);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&NewAcl);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v36);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
  Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&v35);
  Common::RegistryKey::~RegistryKey((Common::RegistryKey *)&phkResult);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&hServicea);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(&v41);
}

```

## disassembly

```asm
0x1800f44e0  push    rbp
0x1800f44e2  push    rbx
0x1800f44e3  push    rsi
0x1800f44e4  push    rdi
0x1800f44e5  push    r14
0x1800f44e7  push    r15
0x1800f44e9  lea     rbp, [rsp-78h]
0x1800f44ee  sub     rsp, 178h
0x1800f44f5  mov     dil, r8b
0x1800f44f8  mov     rsi, rdx
0x1800f44fb  mov     rbx, rcx
0x1800f44fe  mov     r8, rdx
0x1800f4501  lea     rdx, [rbp+0A0h+var_F8]
0x1800f4505  call    ?CheckRegistrationState@PackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@AEAA?AV?$tuple@W4ServiceRegistrationState@PackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@PEAUSC_HANDLE__@@@Z; OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::CheckRegistrationState(SC_HANDLE__ *)
0x1800f450a  nop
0x1800f450b  mov     rcx, [rbp+0A0h+var_F0]
0x1800f450f  xor     r14d, r14d
0x1800f4512  lea     r15d, [r14+1]
0x1800f4516  test    r15b, cl
0x1800f4519  jnz     loc_1800F4600
0x1800f451f  mov     rax, [rbp+0A0h+var_F8]
0x1800f4523  test    rax, rax
0x1800f4526  jnz     short loc_1800F4538
0x1800f4528  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "existingSvcHandle")
0x1800f452d  mov     rcx, [rbp+0A0h+var_F0]
0x1800f4531  mov     rax, [rbp+0A0h+var_F8]
0x1800f4535  test    rax, rax
0x1800f4538  setz    al
0x1800f453b  mov     r10, [rbp+0A8h]
0x1800f4542  test    al, al
0x1800f4544  jnz     loc_1800F4A68
0x1800f454a  mov     rax, [rbp+0A8h]
0x1800f4551  test    cl, 40h
0x1800f4554  jnz     loc_1800F4A83
0x1800f455a  test    cl, 20h
0x1800f455d  jnz     short loc_1800F458E
0x1800f455f  mov     rax, [rbp+0A8h]
0x1800f4566  test    cl, 10h
0x1800f4569  jnz     loc_1800F4A9E
0x1800f456f  test    dil, dil
0x1800f4572  jnz     short loc_1800F457C
0x1800f4574  test    cl, 8
0x1800f4577  mov     al, r15b
0x1800f457a  jz      short loc_1800F457F
0x1800f457c  mov     al, r14b
0x1800f457f  mov     r10, [rbp+0A8h]
0x1800f4586  test    al, al
0x1800f4588  jnz     loc_1800F4AB9
0x1800f458e  test    cl, 2
0x1800f4591  jnz     short loc_1800F459C
0x1800f4593  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "WI_IsFlagSet(registrationStatus, ServiceRegistrationState::Packaged)")
0x1800f4598  mov     rcx, [rbp+0A0h+var_F0]
0x1800f459c  test    cl, 24h
0x1800f459f  jnz     short loc_1800F45AD
0x1800f45a1  test    dil, dil
0x1800f45a4  jnz     short loc_1800F45B2
0x1800f45a6  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "WI_IsFlagSet(registrationStatus, ServiceRegistrationState::Corrupted) || WI_IsFlagSet(registrationStatus, ServiceRegistrationState::SamePackageFamily) || isInstall")
0x1800f45ab  jmp     short loc_1800F45EE
0x1800f45ad  test    dil, dil
0x1800f45b0  jz      short loc_1800F45EE
0x1800f45b2  test    cl, 20h
0x1800f45b5  jnz     short loc_1800F45EE
0x1800f45b7  call    ?Provider@AppXDeploymentServerTelemetry@@SAPEBU_tlgProvider_t@@XZ; AppXDeploymentServerTelemetry::Provider(void)
0x1800f45bc  mov     r9, rax
0x1800f45bf  mov     ecx, [rax]
0x1800f45c1  cmp     ecx, 5
0x1800f45c4  jbe     short loc_1800F45EE
0x1800f45c6  mov     rdx, 400000000000h
0x1800f45d0  mov     rcx, rax
0x1800f45d3  call    _tlgKeywordOn
0x1800f45d8  test    al, al
0x1800f45da  jz      short loc_1800F45EE
0x1800f45dc  xor     r8d, r8d
0x1800f45df  lea     rdx, dword_18021E214
0x1800f45e6  mov     rcx, r9
0x1800f45e9  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800f45ee  xor     r9d, r9d
0x1800f45f1  lea     r8, [rbp+0A0h+var_F8]
0x1800f45f5  mov     rdx, rsi; hService
0x1800f45f8  mov     rcx, rbx; this
0x1800f45fb  call    ?HelpDeleteService@PackagedServiceExtensionHelper@Internal@DEH@OSIntegration@@AEAAXPEAUSC_HANDLE__@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@_N@Z; OSIntegration::DEH::Internal::PackagedServiceExtensionHelper::HelpDeleteService(SC_HANDLE__ *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>> &,bool)
0x1800f4600  mov     [rsp+1A0h+hService], r14
0x1800f4605  cmp     [rbx+48h], r14d
0x1800f4609  jbe     short loc_1800F4611
0x1800f460b  mov     rax, [rbx+50h]
0x1800f460f  jmp     short loc_1800F4614
0x1800f4611  mov     rax, r14
0x1800f4614  mov     rcx, [rbx+80h]
0x1800f461b  mov     rdx, [rbx+20h]
0x1800f461f  mov     r9d, [rbx+0A8h]
0x1800f4626  cmp     [rbx+30h], r14d
0x1800f462a  jbe     short loc_1800F4632
0x1800f462c  mov     r8, [rbx+38h]
0x1800f4630  jmp     short loc_1800F4635
0x1800f4632  mov     r8, r14; lpDisplayName
0x1800f4635  mov     [rsp+1A0h+lpPassword], r14; lpPassword
0x1800f463a  mov     [rsp+1A0h+lpServiceStartName], rax; lpServiceStartName
0x1800f463f  mov     [rsp+1A0h+lpDependencies], rcx; lpDependencies
0x1800f4644  mov     [rsp+1A0h+lpdwTagId], r14; lpdwTagId
0x1800f4649  mov     [rsp+1A0h+lpLoadOrderGroup], r14; lpLoadOrderGroup
0x1800f464e  mov     [rsp+1A0h+lpBinaryPathName], rdx; lpBinaryPathName
0x1800f4653  mov     [rsp+1A0h+dwErrorControl], r14d; dwErrorControl
0x1800f4658  mov     [rsp+1A0h+dwStartType], r9d; dwStartType
0x1800f465d  mov     [rsp+1A0h+dwServiceType], 210h; int
0x1800f4665  mov     r9d, 50002h; dwDesiredAccess
0x1800f466b  mov     rdx, [rbx+8]; lpServiceName
0x1800f466f  mov     rcx, rsi; hSCManager
0x1800f4672  call    cs:__imp_CreateServiceW
0x1800f4679  nop     dword ptr [rax+rax+00h]
0x1800f467e  mov     rdx, rax
0x1800f4681  lea     rcx, [rsp+1A0h+hService]
0x1800f4686  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x1800f468b  mov     rcx, [rsp+1A0h+hService]; hService
0x1800f4690  test    rcx, rcx
0x1800f4693  setz    al
0x1800f4696  mov     r9, [rbp+0A8h]; char *
0x1800f469d  test    al, al
0x1800f469f  jnz     loc_1800F4AD4
0x1800f46a5  lea     rax, [rsp+1A0h+hService]
0x1800f46aa  mov     [rbp+0A0h+var_40], rax
0x1800f46ae  mov     [rbp+0A0h+var_38], r15b
0x1800f46b2  cmp     [rbx+0ACh], r14b
0x1800f46b9  jz      short loc_1800F46E9
0x1800f46bb  mov     dword ptr [rbp+0A0h+Info], r15d
0x1800f46c2  lea     r8, [rbp+0A0h+Info]; lpInfo
0x1800f46c9  mov     edx, 3; dwInfoLevel
0x1800f46ce  call    cs:__imp_ChangeServiceConfig2A
0x1800f46d5  nop     dword ptr [rax+rax+00h]
0x1800f46da  mov     rcx, [rbp+0A8h]; this
0x1800f46e1  test    eax, eax
0x1800f46e3  jz      loc_1800F4AE9
0x1800f46e9  mov     [rbp+0A0h+phkResult], r14
0x1800f46ed  mov     [rsp+1A0h+var_128], r14
0x1800f46f2  mov     edi, 0F003Fh
0x1800f46f7  mov     r9d, edi; samDesired
0x1800f46fa  lea     r8, aSystemCurrentc_1; "System\\CurrentControlSet\\Services"
0x1800f4701  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800f4708  lea     rcx, [rbp+0A0h+phkResult]; phkResult
0x1800f470c  call    ?Open@RegistryKey@Common@@QEAAJQEAUHKEY__@@PEBGK@Z; Common::RegistryKey::Open(HKEY__ * const,ushort const *,ulong)
0x1800f4711  mov     rcx, [rbp+0A8h]; this
0x1800f4718  test    eax, eax
0x1800f471a  js      loc_1800F4AFB
0x1800f4720  lea     r9, [rsp+1A0h+var_128]; struct Common::AutoHandleHKEY *
0x1800f4725  mov     r8d, edi; unsigned int
0x1800f4728  mov     rdx, [rbx+8]; unsigned __int16 *
0x1800f472c  lea     rcx, [rbp+0A0h+phkResult]; this
0x1800f4730  call    ?OpenSubKey@RegistryKey@Common@@QEAAJPEBGKAEAVAutoHandleHKEY@2@@Z; Common::RegistryKey::OpenSubKey(ushort const *,ulong,Common::AutoHandleHKEY &)
0x1800f4735  mov     rcx, [rbp+0A8h]; this
0x1800f473c  test    eax, eax
0x1800f473e  js      loc_1800F4B10
0x1800f4744  mov     r8, [rbx+0B8h]; unsigned __int16 *
0x1800f474b  lea     rdx, aPackagefullnam_0; "PackageFullName"
0x1800f4752  lea     rcx, [rsp+1A0h+var_128]; this
0x1800f4757  call    ?SetStringValue@RegistryKey@Common@@QEAAJPEBG0K@Z; Common::RegistryKey::SetStringValue(ushort const *,ushort const *,ulong)
0x1800f475c  mov     rcx, [rbp+0A8h]; this
0x1800f4763  test    eax, eax
0x1800f4765  js      loc_1800F4B25
0x1800f476b  mov     r8, [rbx+0D0h]; unsigned __int16 *
0x1800f4772  lea     rdx, aAppusermodelid; "AppUserModelId"
0x1800f4779  lea     rcx, [rsp+1A0h+var_128]; this
0x1800f477e  call    ?SetStringValue@RegistryKey@Common@@QEAAJPEBG0K@Z; Common::RegistryKey::SetStringValue(ushort const *,ushort const *,ulong)
0x1800f4783  mov     rcx, [rbp+0A8h]; this
0x1800f478a  test    eax, eax
0x1800f478c  js      loc_1800F4B3A
0x1800f4792  mov     eax, [rbx+0E0h]
0x1800f4798  mov     dword ptr [rbp+0A0h+Info], eax
0x1800f479e  mov     esi, 4
0x1800f47a3  mov     [rsp+1A0h+dwServiceType], esi; int
0x1800f47a7  mov     r9d, esi; unsigned int
0x1800f47aa  lea     r8, [rbp+0A0h+Info]; void *
0x1800f47b1  lea     rdx, aPackageorigin; "PackageOrigin"
0x1800f47b8  lea     rcx, [rsp+1A0h+var_128]; this
0x1800f47bd  call    ?SetValue@RegistryKey@Common@@QEAAJPEBGPEBXKK@Z; Common::RegistryKey::SetValue(ushort const *,void const *,ulong,ulong)
0x1800f47c2  mov     rcx, [rbp+0A8h]; this
0x1800f47c9  test    eax, eax
0x1800f47cb  js      loc_1800F4B4F
0x1800f47d1  mov     [rbp+0A0h+Sid], r14
0x1800f47d5  mov     [rbp+0A0h+var_120], r14
0x1800f47d9  xor     edx, edx
0x1800f47db  lea     rcx, [rbp+0A0h+Sid]
0x1800f47df  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800f47e4  lea     rdx, [rbp+0A0h+Sid]; Sid
0x1800f47e8  lea     rcx, aS1511; "S-1-5-11"
0x1800f47ef  call    cs:__imp_ConvertStringSidToSidW
0x1800f47f6  nop     dword ptr [rax+rax+00h]
0x1800f47fb  xor     edx, edx
0x1800f47fd  lea     rcx, [rbp+0A0h+var_120]
0x1800f4801  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800f4806  lea     rdx, [rbp+0A0h+var_120]; Sid
0x1800f480a  lea     rcx, aS1580194972457; "S-1-5-80-1949724575-2387902436-65106593"...
0x1800f4811  call    cs:__imp_ConvertStringSidToSidW
0x1800f4818  nop     dword ptr [rax+rax+00h]
0x1800f481d  mov     [rbp+0A0h+pListOfExplicitEntries.grfAccessPermissions], 201FDh
0x1800f4824  mov     qword ptr [rbp+0A0h+pListOfExplicitEntries.grfAccessMode], 2
0x1800f482c  mov     [rbp+0A0h+pListOfExplicitEntries.Trustee.pMultipleTrustee], r14
0x1800f4830  mov     qword ptr [rbp+0A0h+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r14
0x1800f4834  mov     [rbp+0A0h+pListOfExplicitEntries.Trustee.TrusteeType], r14d
0x1800f4838  mov     rax, [rbp+0A0h+Sid]
0x1800f483c  mov     [rbp+0A0h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800f4840  mov     [rbp+0A0h+var_B0], 0F01FFh
0x1800f4847  mov     [rbp+0A0h+var_AC], 1
0x1800f484f  mov     [rbp+0A0h+var_A0], r14
0x1800f4853  mov     [rbp+0A0h+var_98], r14
0x1800f4857  mov     [rbp+0A0h+var_90], r14d
0x1800f485b  mov     rax, [rbp+0A0h+var_120]
0x1800f485f  mov     [rbp+0A0h+var_88], rax
0x1800f4863  xorps   xmm0, xmm0
0x1800f4866  xor     eax, eax
0x1800f4868  movups  [rbp+0A0h+pSecurityDescriptor], xmm0
0x1800f486c  movups  [rbp+0A0h+var_58], xmm0
0x1800f4870  mov     [rbp+0A0h+var_48], rax
0x1800f4874  mov     [rbp+0A0h+NewAcl], r14
0x1800f4878  mov     rdi, [rbp+0A8h]
0x1800f487f  lea     r9, [rbp+0A0h+NewAcl]; NewAcl
0x1800f4883  xor     r8d, r8d; OldAcl
0x1800f4886  lea     rdx, [rbp+0A0h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800f488a  lea     ecx, [rsi-2]; cCountOfExplicitEntries
0x1800f488d  call    cs:__imp_SetEntriesInAclW
0x1800f4894  nop     dword ptr [rax+rax+00h]
0x1800f4899  test    eax, eax
0x1800f489b  jnz     loc_1800F4B64
0x1800f48a1  mov     rdi, [rbp+0A8h]
0x1800f48a8  mov     edx, r15d; dwRevision
0x1800f48ab  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x1800f48af  call    cs:__imp_InitializeSecurityDescriptor
0x1800f48b6  nop     dword ptr [rax+rax+00h]
0x1800f48bb  test    eax, eax
0x1800f48bd  jz      loc_1800F4B79
0x1800f48c3  mov     rdi, [rbp+0A8h]
0x1800f48ca  xor     r9d, r9d; bDaclDefaulted
0x1800f48cd  mov     r8, [rbp+0A0h+NewAcl]; pDacl
0x1800f48d1  mov     edx, r15d; bDaclPresent
0x1800f48d4  lea     rcx, [rbp+0A0h+pSecurityDescriptor]; pSecurityDescriptor
0x1800f48d8  call    cs:__imp_SetSecurityDescriptorDacl
0x1800f48df  nop     dword ptr [rax+rax+00h]
0x1800f48e4  test    eax, eax
0x1800f48e6  jz      loc_1800F4B8E
0x1800f48ec  mov     rdi, [rbp+0A8h]
0x1800f48f3  lea     r8, [rbp+0A0h+pSecurityDescriptor]; lpSecurityDescriptor
0x1800f48f7  mov     edx, esi; dwSecurityInformation
0x1800f48f9  mov     rcx, [rsp+1A0h+hService]; hService
0x1800f48fe  call    cs:__imp_SetServiceObjectSecurity
0x1800f4905  nop     dword ptr [rax+rax+00h]
0x1800f490a  test    eax, eax
0x1800f490c  jz      loc_1800F4BA3
0x1800f4912  cmp     [rbx+60h], r14d
0x1800f4916  jbe     short loc_1800F494D
0x1800f4918  mov     rax, [rbx+68h]
0x1800f491c  mov     [rbp+0A0h+Info], rax
0x1800f4923  mov     rdi, [rbp+0A8h]
0x1800f492a  lea     r8, [rbp+0A0h+Info]; lpInfo
0x1800f4931  mov     edx, r15d; dwInfoLevel
0x1800f4934  mov     rcx, [rsp+1A0h+hService]; hService
0x1800f4939  call    cs:__imp_ChangeServiceConfig2W
0x1800f4940  nop     dword ptr [rax+rax+00h]
0x1800f4945  test    eax, eax
0x1800f4947  jz      loc_1800F4BB8
0x1800f494d  cmp     [rbx+130h], r14b
0x1800f4954  jz      short loc_1800F4988
0x1800f4956  mov     dword ptr [rbp+0A0h+Info], esi
0x1800f495c  mov     rdi, [rbp+0A8h]
0x1800f4963  lea     r8, [rbp+0A0h+Info]; lpInfo
0x1800f496a  mov     edx, 0Ch; dwInfoLevel
0x1800f496f  mov     rcx, [rsp+1A0h+hService]; hService
0x1800f4974  call    cs:__imp_ChangeServiceConfig2W
0x1800f497b  nop     dword ptr [rax+rax+00h]
0x1800f4980  test    eax, eax
0x1800f4982  jz      loc_1800F4BCD
0x1800f4988  xorps   xmm0, xmm0
0x1800f498b  xor     eax, eax
0x1800f498d  movups  xmmword ptr [rbp+0A0h+var_80.cTriggers], xmm0
0x1800f4991  mov     [rbp+0A0h+var_80.pReserved], rax
0x1800f4995  lea     rcx, [rbx+100h]; this
0x1800f499c  lea     rdx, [rbp+0A0h+var_80]; struct _SERVICE_TRIGGER_INFO *
0x1800f49a0  call    ?GetServiceTriggerInfo@PackagedServiceTriggerData@Internal@DEH@OSIntegration@@QEAA_NPEAU_SERVICE_TRIGGER_INFO@@@Z; OSIntegration::DEH::Internal::PackagedServiceTriggerData::GetServiceTriggerInfo(_SERVICE_TRIGGER_INFO *)
0x1800f49a5  test    al, al
0x1800f49a7  jz      short loc_1800F49D2
0x1800f49a9  mov     rbx, [rbp+0A8h]
0x1800f49b0  lea     r8, [rbp+0A0h+var_80]; lpInfo
0x1800f49b4  mov     edx, 8; dwInfoLevel
0x1800f49b9  mov     rcx, [rsp+1A0h+hService]; hService
0x1800f49be  call    cs:__imp_ChangeServiceConfig2W
0x1800f49c5  nop     dword ptr [rax+rax+00h]
0x1800f49ca  test    eax, eax
0x1800f49cc  jz      loc_1800F4BE2
0x1800f49d2  mov     [rbp+0A0h+var_110], r15d
0x1800f49d6  mov     rbx, [rbp+0A8h]
0x1800f49dd  lea     r8, [rbp+0A0h+var_110]; lpInfo
0x1800f49e1  mov     edx, 5; dwInfoLevel
0x1800f49e6  mov     rcx, [rsp+1A0h+hService]; hService
0x1800f49eb  call    cs:__imp_ChangeServiceConfig2W
0x1800f49f2  nop     dword ptr [rax+rax+00h]
0x1800f49f7  test    eax, eax
0x1800f49f9  jz      short loc_1800F4A53
0x1800f49fb  lea     rcx, [rbp+0A0h+NewAcl]
0x1800f49ff  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800f4a04  nop
0x1800f4a05  lea     rcx, [rbp+0A0h+var_120]
0x1800f4a09  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800f4a0e  nop
  ... truncated ...
```
