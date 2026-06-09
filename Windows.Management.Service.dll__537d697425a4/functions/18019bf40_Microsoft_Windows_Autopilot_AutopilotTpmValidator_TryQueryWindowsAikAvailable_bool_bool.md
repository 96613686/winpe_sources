# Microsoft::Windows::Autopilot::AutopilotTpmValidator::TryQueryWindowsAikAvailable(bool &,bool &)

- ea: `0x18019bf40`
- end: `0x18019c731`
- name: `?TryQueryWindowsAikAvailable@AutopilotTpmValidator@Autopilot@Windows@Microsoft@@SAJAEA_N0@Z`
- size: `2033`
- prototype: `__int64 __fastcall(bool *, bool *)`
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d5474`
- `0x1800d6de0`

## callees

- `0x18000b8f0`
- `0x18000be44`
- `0x180067e54`
- `0x180073768`
- `0x1800810f0`
- `0x180081150`
- `0x18008f458`
- `0x1800b2a54`
- `0x1800b3398`
- `0x1800b4778`
- `0x1800d238c`
- `0x180123edc`
- `0x1801243d0`
- `0x180124430`
- `0x180126130`
- `0x18019bf40`
- `0x18019cae0`
- `0x18019cbcc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18019c1d5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18019c1d5`
- `ncrypt!NCryptOpenKey` at `0x18019c2ca`
- `ncrypt!NCryptOpenKey` at `0x18019c2ca`
- `ncrypt!NCryptGetProperty` at `0x18019c3e9`
- `ncrypt!NCryptGetProperty` at `0x18019c555`
- `ncrypt!NCryptGetProperty` at `0x18019c3e9`
- `ncrypt!NCryptGetProperty` at `0x18019c555`
- `ncrypt!NCryptEnumKeys` at `0x18019c19f`
- `ncrypt!NCryptEnumKeys` at `0x18019c19f`
- `ncrypt!NCryptSetProperty` at `0x18019c0cc`
- `ncrypt!NCryptSetProperty` at `0x18019c0cc`
- `ncrypt!NCryptOpenStorageProvider` at `0x18019bfd5`
- `ncrypt!NCryptOpenStorageProvider` at `0x18019bfd5`

## string_xrefs

- `0x18019bff2`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottpmvalidator.cpp`
- `0x18019c056`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottpmvalidator.cpp`
- `0x18019c20c`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottpmvalidator.cpp`
- `0x18019c572`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottpmvalidator.cpp`
- `0x18019c69a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottpmvalidator.cpp`
- `0x18019c2db`: `Windows AIK key access`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::Windows::Autopilot::AutopilotTpmValidator::TryQueryWindowsAikAvailable(
        bool *a1,
        bool *a2)
{
  SECURITY_STATUS v4; // eax
  __int64 v5; // rcx
  unsigned int v6; // ebx
  const char *v7; // r9
  __int64 result; // rax
  int v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r9
  SECURITY_STATUS v12; // ebx
  __int64 v13; // rcx
  unsigned __int8 v14; // di
  int i; // ebx
  unsigned int v16; // esi
  __int64 v17; // rcx
  __int64 v18; // r8
  SECURITY_STATUS Property; // ebx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // r8
  __int64 v23; // rcx
  BYTE *v24; // rax
  SECURITY_STATUS v25; // eax
  unsigned int v26; // ebx
  bool v27; // al
  __int64 v28; // rcx
  __int64 v29; // r8
  __int64 *v30; // rdx
  int dwFlags; // [rsp+20h] [rbp-218h]
  int dwFlagsa; // [rsp+20h] [rbp-218h]
  int dwFlagsb; // [rsp+20h] [rbp-218h]
  int dwFlagsc; // [rsp+20h] [rbp-218h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+30h] [rbp-208h] BYREF
  DWORD pcbResult; // [rsp+38h] [rbp-200h] BYREF
  unsigned __int16 *v37; // [rsp+40h] [rbp-1F8h] BYREF
  PBYTE pbInput; // [rsp+48h] [rbp-1F0h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-1E8h] BYREF
  PVOID ppEnumState; // [rsp+58h] [rbp-1E0h] BYREF
  _QWORD *v41; // [rsp+60h] [rbp-1D8h] BYREF
  NCryptKeyName *ppKeyName; // [rsp+68h] [rbp-1D0h] BYREF
  char v43; // [rsp+70h] [rbp-1C8h]
  _BYTE *v44; // [rsp+78h] [rbp-1C0h]
  unsigned __int16 **v45; // [rsp+80h] [rbp-1B8h]
  char v46; // [rsp+88h] [rbp-1B0h]
  _BYTE v47[336]; // [rsp+90h] [rbp-1A8h] BYREF
  _QWORD v48[4]; // [rsp+1E0h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  *a1 = 0;
  *a2 = 0;
  v37 = L"TryQueryWindowsAikAvailable";
  ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Start<unsigned short const * const &>((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47);
  v44 = v47;
  v45 = &v37;
  v46 = 1;
  phProvider = 0;
  v4 = NCryptOpenStorageProvider(&phProvider, L"Microsoft Platform Crypto Provider", 0);
  try
  {
    v6 = v4;
    if ( v4 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4E,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottpmvalidator.cpp",
        (const char *)(unsigned int)v4,
        dwFlags);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47,
        v37);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47);
      return v6;
    }
    pbInput = 0;
    v9 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
           v5,
           &pbInput);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottpmvalidator.cpp",
        (const char *)(unsigned int)v9,
        dwFlags);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47,
        v37);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47);
      return v10;
    }
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&pbInput[2 * v11] );
    v12 = NCryptSetProperty(phProvider, L"PCP_ALTERNATE_KEY_STORAGE_LOCATION", pbInput, 2 * v11, 0);
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(
      (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47,
      L"Windows AIK location",
      v12);
    if ( v12 < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(v13, AutopilotManagerWindowsAikAltLocationFailed, (unsigned int)v12);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47,
        v37);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47);
      return (unsigned int)v12;
    }
    v14 = 0;
    ppEnumState = 0;
    v48[2] = 0;
    for ( i = 0; i < 20; ++i )
    {
      v48[0] = 0;
      v41 = v48;
      ppKeyName = 0;
      v43 = 1;
      v16 = NCryptEnumKeys(phProvider, 0, &ppKeyName, &ppEnumState, 0x60u);
      wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>(&v41);
      if ( v16 == -2146893782 )
        goto LABEL_20;
      if ( v16 )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x80,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottpmvalidator.cpp",
          (const char *)v16,
          dwFlagsa);
        goto LABEL_20;
      }
      if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)v48[0], L"Windows AIK") )
      {
        v14 = 1;
LABEL_20:
        wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>::reset(
          v48,
          0);
        break;
      }
      wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>::reset(
        v48,
        0);
    }
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(
      (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47,
      L"Windows AIK key status",
      v14);
    if ( !v14 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
        McGenEventWrite_EventWriteTransfer(v17, AutopilotManagerWindowsAikKeyNotFoundByName, v18, 1);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47,
        v37);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47);
      return 0;
    }
    phKey = 0;
    Property = NCryptOpenKey(phProvider, &phKey, L"Windows AIK", 0, 0);
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(
      (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47,
      L"Windows AIK key access",
      Property);
    if ( Property < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(v20, AutopilotManagerWindowsAikKeyFailedOpen, (unsigned int)Property);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      if ( Property == -2146893807 )
      {
LABEL_29:
        ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
          (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47,
          v37);
        ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47);
        return 0;
      }
LABEL_30:
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47,
        v37);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47);
      return (unsigned int)Property;
    }
    *a1 = 1;
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikStatusChange(
      (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47,
      1,
      *a2);
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v21, AutopilotManagerTpmAikKeyFound, v22, 1);
    pcbResult = 0;
    Property = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", 0, 0, &pcbResult, 0);
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(
      (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47,
      L"Windows AIK cert query status",
      Property);
    if ( Property < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(
          v23,
          AutopilotManagerWindowsAikKeyFailedQueryCertificate,
          (unsigned int)Property);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      if ( Property == -2146893807 )
        goto LABEL_29;
      goto LABEL_30;
    }
    if ( !pcbResult )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(v23, AutopilotManagerWindowsAikKeyFailedQueryCertificate, 2147943569LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47,
        v37);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47);
      return 0;
    }
    v24 = (BYTE *)operator new[](pcbResult, (const struct std::nothrow_t *)&std::nothrow);
    v48[0] = v24;
    if ( !v24 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCC,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottpmvalidator.cpp",
        (const char *)0x8007000ELL,
        dwFlagsb);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v48);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47,
        v37);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47);
      return 2147942414LL;
    }
    v25 = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", v24, pcbResult, &pcbResult, 0);
    v26 = v25;
    if ( v25 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD4,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottpmvalidator.cpp",
        (const char *)(unsigned int)v25,
        dwFlagsc);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v48);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47,
        v37);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47);
      return v26;
    }
    v27 = pcbResult != 0;
    *a2 = pcbResult != 0;
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikStatusChange(
      (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47,
      *a1,
      v27);
    if ( *a2 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
      {
        v30 = AutopilotManagerTpmAikCertFound;
LABEL_50:
        McGenEventWrite_EventWriteTransfer(v28, v30, v29, 1);
      }
    }
    else if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
    {
      v30 = AutopilotManagerTpmAikCertNotFound;
      goto LABEL_50;
    }
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v48);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47, v37);
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v47);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xE4,
                           (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottpmvalidator.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x18019bf40  mov     [rsp+arg_10], rbx
0x18019bf45  mov     [rsp+arg_18], rsi
0x18019bf4a  push    rdi
0x18019bf4b  push    r12
0x18019bf4d  push    r13
0x18019bf4f  push    r14
0x18019bf51  push    r15
0x18019bf53  sub     rsp, 210h
0x18019bf5a  mov     rax, cs:__security_cookie
0x18019bf61  xor     rax, rsp
0x18019bf64  mov     [rsp+238h+var_38], rax
0x18019bf6c  mov     r14, rdx
0x18019bf6f  mov     r15, rcx
0x18019bf72  xor     r12d, r12d
0x18019bf75  mov     [rcx], r12b
0x18019bf78  mov     [rdx], r12b
0x18019bf7b  lea     rax, aTryquerywindow; "TryQueryWindowsAikAvailable"
0x18019bf82  mov     [rsp+238h+var_1F8], rax
0x18019bf87  lea     rdx, [rsp+238h+var_1F8]
0x18019bf8c  lea     rcx, [rsp+238h+var_1A8]
0x18019bf94  call    ??$Start@AEBQEBG@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@SA?AV01@AEBQEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Start<ushort const * const &>(ushort const * const &)
0x18019bf99  nop
0x18019bf9a  lea     rax, [rsp+238h+var_1A8]
0x18019bfa2  mov     [rsp+238h+var_1C0], rax
0x18019bfa7  lea     rax, [rsp+238h+var_1F8]
0x18019bfac  mov     [rsp+238h+var_1B8], rax
0x18019bfb4  lea     r13d, [r12+1]
0x18019bfb9  mov     [rsp+238h+var_1B0], r13b
0x18019bfc1  mov     [rsp+238h+phProvider], r12
0x18019bfc6  xor     r8d, r8d; dwFlags
0x18019bfc9  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x18019bfd0  lea     rcx, [rsp+238h+phProvider]; phProvider
0x18019bfd5  call    cs:__imp_NCryptOpenStorageProvider
0x18019bfdc  nop     dword ptr [rax+rax+00h]
0x18019bfe1  mov     ebx, eax
0x18019bfe3  test    eax, eax
0x18019bfe5  jns     short loc_18019C036
0x18019bfe7  mov     rcx, [rsp+238h]; this
0x18019bfef  mov     r9d, eax; char *
0x18019bff2  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019bff9  lea     edx, [r12+4Eh]; void *
0x18019bffe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019c003  nop
0x18019c004  lea     rcx, [rsp+238h+phProvider]
0x18019c009  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18019c00e  nop
0x18019c00f  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x18019c014  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c01c  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x18019c021  nop
0x18019c022  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c02a  call    ??1AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator(void)
0x18019c02f  mov     eax, ebx
0x18019c031  jmp     loc_18019C703
0x18019c036  mov     [rsp+238h+pbInput], r12
0x18019c03b  lea     rdx, [rsp+238h+pbInput]
0x18019c040  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18019c045  mov     ebx, eax
0x18019c047  test    eax, eax
0x18019c049  jns     short loc_18019C0A5
0x18019c04b  mov     rcx, [rsp+238h]; this
0x18019c053  mov     r9d, eax; char *
0x18019c056  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019c05d  mov     edx, 52h ; 'R'; void *
0x18019c062  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18019c067  nop
0x18019c068  lea     rcx, [rsp+238h+pbInput]
0x18019c06d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18019c072  nop
0x18019c073  lea     rcx, [rsp+238h+phProvider]
0x18019c078  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18019c07d  nop
0x18019c07e  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x18019c083  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c08b  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x18019c090  nop
0x18019c091  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c099  call    ??1AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator(void)
0x18019c09e  mov     eax, ebx
0x18019c0a0  jmp     loc_18019C703
0x18019c0a5  mov     r8, [rsp+238h+pbInput]; pbInput
0x18019c0aa  or      r9, 0FFFFFFFFFFFFFFFFh
0x18019c0ae  inc     r9
0x18019c0b1  cmp     [r8+r9*2], r12w
0x18019c0b6  jnz     short loc_18019C0AE
0x18019c0b8  add     r9d, r9d; cbInput
0x18019c0bb  mov     [rsp+238h+dwFlags], r12d; dwFlags
0x18019c0c0  lea     rdx, aPcpAlternateKe; "PCP_ALTERNATE_KEY_STORAGE_LOCATION"
0x18019c0c7  mov     rcx, [rsp+238h+phProvider]; hObject
0x18019c0cc  call    cs:__imp_NCryptSetProperty
0x18019c0d3  nop     dword ptr [rax+rax+00h]
0x18019c0d8  mov     ebx, eax
0x18019c0da  mov     r8d, eax; int
0x18019c0dd  lea     rdx, aWindowsAikLoca; "Windows AIK location"
0x18019c0e4  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c0ec  call    ?WindowsAikHresultStatus@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBGJ@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(ushort const *,long)
0x18019c0f1  test    ebx, ebx
0x18019c0f3  jns     short loc_18019C14B
0x18019c0f5  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x18019c0fc  jz      short loc_18019C10E
0x18019c0fe  mov     r8d, ebx
0x18019c101  lea     rdx, AutopilotManagerWindowsAikAltLocationFailed
0x18019c108  call    McTemplateU0q_EventWriteTransfer
0x18019c10d  nop
0x18019c10e  lea     rcx, [rsp+238h+pbInput]
0x18019c113  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18019c118  nop
0x18019c119  lea     rcx, [rsp+238h+phProvider]
0x18019c11e  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18019c123  nop
0x18019c124  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x18019c129  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c131  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x18019c136  nop
0x18019c137  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c13f  call    ??1AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator(void)
0x18019c144  mov     eax, ebx
0x18019c146  jmp     loc_18019C703
0x18019c14b  mov     dil, r12b
0x18019c14e  mov     [rsp+238h+ppEnumState], r12
0x18019c153  mov     [rsp+238h+var_48], r12
0x18019c15b  mov     ebx, r12d
0x18019c15e  cmp     ebx, 14h
0x18019c161  jge     loc_18019C22C
0x18019c167  mov     [rsp+238h+var_58], r12
0x18019c16f  lea     rax, [rsp+238h+var_58]
0x18019c177  mov     [rsp+238h+var_1D8], rax
0x18019c17c  mov     [rsp+238h+ppKeyName], r12
0x18019c181  mov     [rsp+238h+var_1C8], r13b
0x18019c186  mov     [rsp+238h+dwFlags], 60h ; '`'; int
0x18019c18e  lea     r9, [rsp+238h+ppEnumState]; ppEnumState
0x18019c193  lea     r8, [rsp+238h+ppKeyName]; ppKeyName
0x18019c198  xor     edx, edx; pszScope
0x18019c19a  mov     rcx, [rsp+238h+phProvider]; hProvider
0x18019c19f  call    cs:__imp_NCryptEnumKeys
0x18019c1a6  nop     dword ptr [rax+rax+00h]
0x18019c1ab  mov     esi, eax
0x18019c1ad  lea     rcx, [rsp+238h+var_1D8]
0x18019c1b2  call    ??1?$out_param_t@V?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>(void)
0x18019c1b7  cmp     esi, 8009002Ah
0x18019c1bd  jz      short loc_18019C21D
0x18019c1bf  test    esi, esi
0x18019c1c1  jnz     short loc_18019C201
0x18019c1c3  lea     rdx, pszKeyName; "Windows AIK"
0x18019c1ca  mov     rcx, [rsp+238h+var_58]
0x18019c1d2  mov     rcx, [rcx]
0x18019c1d5  call    cs:__imp__o__wcsicmp
0x18019c1dc  nop     dword ptr [rax+rax+00h]
0x18019c1e1  xor     edx, edx
0x18019c1e3  lea     rcx, [rsp+238h+var_58]
0x18019c1eb  test    eax, eax
0x18019c1ed  jz      short loc_18019C1FC
0x18019c1ef  add     ebx, r13d
0x18019c1f2  call    ?reset@?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@QEAAXPEAUNCryptKeyName@@@Z; wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>::reset(NCryptKeyName *)
0x18019c1f7  jmp     loc_18019C15E
0x18019c1fc  mov     dil, r13b
0x18019c1ff  jmp     short loc_18019C227
0x18019c201  mov     rcx, [rsp+238h]; this
0x18019c209  mov     r9d, esi; char *
0x18019c20c  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019c213  mov     edx, 80h; void *
0x18019c218  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18019c21d  lea     rcx, [rsp+238h+var_58]
0x18019c225  xor     edx, edx
0x18019c227  call    ?reset@?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@QEAAXPEAUNCryptKeyName@@@Z; wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>::reset(NCryptKeyName *)
0x18019c22c  movzx   r8d, dil; int
0x18019c230  lea     rdx, aWindowsAikKeyS; "Windows AIK key status"
0x18019c237  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c23f  call    ?WindowsAikHresultStatus@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBGJ@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(ushort const *,long)
0x18019c244  test    dil, dil
0x18019c247  jnz     short loc_18019C2AC
0x18019c249  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x18019c250  jz      short loc_18019C26F
0x18019c252  lea     rax, [rsp+238h+var_48]
0x18019c25a  mov     qword ptr [rsp+238h+dwFlags], rax
0x18019c25f  mov     r9d, r13d
0x18019c262  lea     rdx, AutopilotManagerWindowsAikKeyNotFoundByName
0x18019c269  call    McGenEventWrite_EventWriteTransfer
0x18019c26e  nop
0x18019c26f  lea     rcx, [rsp+238h+pbInput]
0x18019c274  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18019c279  nop
0x18019c27a  lea     rcx, [rsp+238h+phProvider]
0x18019c27f  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18019c284  nop
0x18019c285  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x18019c28a  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c292  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x18019c297  nop
0x18019c298  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c2a0  call    ??1AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator(void)
0x18019c2a5  xor     eax, eax
0x18019c2a7  jmp     loc_18019C703
0x18019c2ac  mov     [rsp+238h+phKey], r12
0x18019c2b1  mov     [rsp+238h+dwFlags], r12d; dwFlags
0x18019c2b6  xor     r9d, r9d; dwLegacyKeySpec
0x18019c2b9  lea     r8, pszKeyName; "Windows AIK"
0x18019c2c0  lea     rdx, [rsp+238h+phKey]; phKey
0x18019c2c5  mov     rcx, [rsp+238h+phProvider]; hProvider
0x18019c2ca  call    cs:__imp_NCryptOpenKey
0x18019c2d1  nop     dword ptr [rax+rax+00h]
0x18019c2d6  mov     ebx, eax
0x18019c2d8  mov     r8d, eax; int
0x18019c2db  lea     rdx, aWindowsAikKeyA; "Windows AIK key access"
0x18019c2e2  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c2ea  call    ?WindowsAikHresultStatus@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBGJ@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(ushort const *,long)
0x18019c2ef  test    ebx, ebx
0x18019c2f1  jns     loc_18019C387
0x18019c2f7  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, r13b
0x18019c2fe  jz      short loc_18019C310
0x18019c300  mov     r8d, ebx
0x18019c303  lea     rdx, AutopilotManagerWindowsAikKeyFailedOpen
0x18019c30a  call    McTemplateU0q_EventWriteTransfer
0x18019c30f  nop
0x18019c310  lea     rcx, [rsp+238h+phKey]
0x18019c315  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18019c31a  nop
0x18019c31b  lea     rcx, [rsp+238h+pbInput]
0x18019c320  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18019c325  nop
0x18019c326  lea     rcx, [rsp+238h+phProvider]
0x18019c32b  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18019c330  nop
0x18019c331  cmp     ebx, 80090011h
0x18019c337  jnz     short loc_18019C360
0x18019c339  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x18019c33e  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c346  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x18019c34b  nop
0x18019c34c  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c354  call    ??1AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator(void)
0x18019c359  xor     eax, eax
0x18019c35b  jmp     loc_18019C703
0x18019c360  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x18019c365  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c36d  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x18019c372  nop
0x18019c373  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c37b  call    ??1AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator(void)
0x18019c380  mov     eax, ebx
0x18019c382  jmp     loc_18019C703
0x18019c387  mov     [r15], r13b
0x18019c38a  movzx   r8d, byte ptr [r14]; int
0x18019c38e  mov     edx, r13d; int
0x18019c391  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c399  call    ?WindowsAikStatusChange@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXHH@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikStatusChange(int,int)
0x18019c39e  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x18019c3a5  jz      short loc_18019C3C3
0x18019c3a7  lea     rax, [rsp+238h+var_58]
0x18019c3af  mov     qword ptr [rsp+238h+dwFlags], rax
0x18019c3b4  mov     r9d, r13d
0x18019c3b7  lea     rdx, AutopilotManagerTpmAikKeyFound
0x18019c3be  call    McGenEventWrite_EventWriteTransfer
0x18019c3c3  mov     [rsp+238h+pcbResult], r12d
0x18019c3c8  mov     [rsp+238h+var_210], r12d; dwFlags
0x18019c3cd  lea     rax, [rsp+238h+pcbResult]
0x18019c3d2  mov     qword ptr [rsp+238h+dwFlags], rax; int
0x18019c3d7  xor     r9d, r9d; cbOutput
0x18019c3da  xor     r8d, r8d; pbOutput
0x18019c3dd  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x18019c3e4  mov     rcx, [rsp+238h+phKey]; hObject
0x18019c3e9  call    cs:__imp_NCryptGetProperty
0x18019c3f0  nop     dword ptr [rax+rax+00h]
0x18019c3f5  mov     ebx, eax
0x18019c3f7  mov     r8d, eax; int
0x18019c3fa  lea     rdx, aWindowsAikCert; "Windows AIK cert query status"
0x18019c401  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c409  call    ?WindowsAikHresultStatus@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBGJ@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(ushort const *,long)
0x18019c40e  test    ebx, ebx
0x18019c410  jns     loc_18019C4A6
0x18019c416  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, r13b
0x18019c41d  jz      short loc_18019C42F
0x18019c41f  mov     r8d, ebx
0x18019c422  lea     rdx, AutopilotManagerWindowsAikKeyFailedQueryCertificate
0x18019c429  call    McTemplateU0q_EventWriteTransfer
0x18019c42e  nop
0x18019c42f  lea     rcx, [rsp+238h+phKey]
0x18019c434  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18019c439  nop
0x18019c43a  lea     rcx, [rsp+238h+pbInput]
0x18019c43f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18019c444  nop
0x18019c445  lea     rcx, [rsp+238h+phProvider]
0x18019c44a  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18019c44f  nop
0x18019c450  cmp     ebx, 80090011h
0x18019c456  jnz     short loc_18019C47F
0x18019c458  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x18019c45d  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c465  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x18019c46a  nop
0x18019c46b  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c473  call    ??1AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator(void)
0x18019c478  xor     eax, eax
0x18019c47a  jmp     loc_18019C703
0x18019c47f  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x18019c484  lea     rcx, [rsp+238h+var_1A8]; this
0x18019c48c  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x18019c491  nop
0x18019c492  lea     rcx, [rsp+238h+var_1A8]; this
  ... truncated ...
```
