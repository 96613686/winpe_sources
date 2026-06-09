# Microsoft::Windows::Autopilot::AutopilotTpmValidator::TryQueryWindowsAikAvailable(bool &,bool &)

- ea: `0x180196d64`
- end: `0x180197547`
- name: `?TryQueryWindowsAikAvailable@AutopilotTpmValidator@Autopilot@Windows@Microsoft@@SAJAEA_N0@Z`
- size: `2019`
- prototype: `__int64 __fastcall(bool *, bool *)`
- caller_count: `2`
- callee_count: `17`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800d2eb4`
- `0x1800d47d0`

## callees

- `0x18000b820`
- `0x18000bd80`
- `0x180067a54`
- `0x1800730b4`
- `0x1800806b0`
- `0x180080708`
- `0x18008e328`
- `0x1800b0f3c`
- `0x1800b1850`
- `0x1800b2bb0`
- `0x1800cff04`
- `0x180120364`
- `0x180120840`
- `0x1801208a4`
- `0x180196d64`
- `0x1801978f0`
- `0x1801979dc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180196fe7`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180196fe7`
- `ncrypt!NCryptOpenKey` at `0x1801970f2`
- `ncrypt!NCryptOpenKey` at `0x1801970f2`
- `ncrypt!NCryptGetProperty` at `0x18019720b`
- `ncrypt!NCryptGetProperty` at `0x180197371`
- `ncrypt!NCryptGetProperty` at `0x18019720b`
- `ncrypt!NCryptGetProperty` at `0x180197371`
- `ncrypt!NCryptEnumKeys` at `0x180196fb7`
- `ncrypt!NCryptEnumKeys` at `0x180196fb7`
- `ncrypt!NCryptSetProperty` at `0x180196eea`
- `ncrypt!NCryptSetProperty` at `0x180196eea`
- `ncrypt!NCryptFreeBuffer` at `0x18019700d`
- `ncrypt!NCryptFreeBuffer` at `0x18019704e`
- `ncrypt!NCryptFreeBuffer` at `0x18019700d`
- `ncrypt!NCryptFreeBuffer` at `0x18019704e`
- `ncrypt!NCryptOpenStorageProvider` at `0x180196df9`
- `ncrypt!NCryptOpenStorageProvider` at `0x180196df9`

## string_xrefs

- `0x180196e10`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottpmvalidator.cpp`
- `0x180196e74`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottpmvalidator.cpp`
- `0x180197028`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottpmvalidator.cpp`
- `0x180197388`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottpmvalidator.cpp`
- `0x1801974b0`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilottpmvalidator.cpp`
- `0x1801970fd`: `Windows AIK key access`

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
  int v17; // eax
  PVOID v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // r8
  SECURITY_STATUS Property; // ebx
  __int64 v22; // rcx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rcx
  void *v26; // rax
  SECURITY_STATUS v27; // eax
  unsigned int v28; // ebx
  bool v29; // al
  __int64 v30; // rcx
  __int64 v31; // r8
  __int64 *v32; // rdx
  int dwFlags; // [rsp+20h] [rbp-218h]
  int dwFlagsa; // [rsp+20h] [rbp-218h]
  int dwFlagsb; // [rsp+20h] [rbp-218h]
  int dwFlagsc; // [rsp+20h] [rbp-218h]
  NCRYPT_PROV_HANDLE phProvider; // [rsp+30h] [rbp-208h] BYREF
  DWORD pcbResult; // [rsp+38h] [rbp-200h] BYREF
  unsigned __int16 *v39; // [rsp+40h] [rbp-1F8h] BYREF
  PBYTE pbInput; // [rsp+48h] [rbp-1F0h] BYREF
  NCRYPT_KEY_HANDLE phKey; // [rsp+50h] [rbp-1E8h] BYREF
  PVOID ppEnumState; // [rsp+58h] [rbp-1E0h] BYREF
  PVOID *v43; // [rsp+60h] [rbp-1D8h] BYREF
  NCryptKeyName *ppKeyName; // [rsp+68h] [rbp-1D0h] BYREF
  char v45; // [rsp+70h] [rbp-1C8h]
  _BYTE *v46; // [rsp+78h] [rbp-1C0h]
  unsigned __int16 **v47; // [rsp+80h] [rbp-1B8h]
  char v48; // [rsp+88h] [rbp-1B0h]
  _BYTE v49[336]; // [rsp+90h] [rbp-1A8h] BYREF
  PVOID pvInput[2]; // [rsp+1E0h] [rbp-58h] BYREF
  _QWORD v51[2]; // [rsp+1F0h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  *a1 = 0;
  *a2 = 0;
  v39 = L"TryQueryWindowsAikAvailable";
  ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Start<unsigned short const * const &>((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49);
  v46 = v49;
  v47 = &v39;
  v48 = 1;
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
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49,
        v39);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49);
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
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49,
        v39);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49);
      return v10;
    }
    v11 = -1;
    do
      ++v11;
    while ( *(_WORD *)&pbInput[2 * v11] );
    v12 = NCryptSetProperty(phProvider, L"PCP_ALTERNATE_KEY_STORAGE_LOCATION", pbInput, 2 * v11, 0);
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(
      (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49,
      L"Windows AIK location",
      v12);
    if ( v12 < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
        McTemplateU0q_EventWriteTransfer(v13, AutopilotManagerWindowsAikAltLocationFailed, (unsigned int)v12);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49,
        v39);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49);
      return (unsigned int)v12;
    }
    v14 = 0;
    ppEnumState = 0;
    v51[0] = 0;
    for ( i = 0; i < 20; ++i )
    {
      pvInput[0] = 0;
      v43 = pvInput;
      ppKeyName = 0;
      v45 = 1;
      v16 = NCryptEnumKeys(phProvider, 0, &ppKeyName, &ppEnumState, 0x60u);
      wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>(&v43);
      if ( v16 == -2146893782 )
        goto LABEL_21;
      if ( v16 )
      {
        wil::details::in1diag3::Log_Hr(
          retaddr,
          (void *)0x80,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottpmvalidator.cpp",
          (const char *)v16,
          dwFlagsa);
LABEL_21:
        v18 = pvInput[0];
        pvInput[0] = 0;
LABEL_22:
        if ( v18 )
          NCryptFreeBuffer(v18);
        break;
      }
      v17 = _o__wcsicmp(*(_QWORD *)pvInput[0], L"Windows AIK");
      v18 = pvInput[0];
      pvInput[0] = 0;
      if ( !v17 )
      {
        v14 = 1;
        goto LABEL_22;
      }
      if ( v18 )
        NCryptFreeBuffer(v18);
    }
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(
      (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49,
      L"Windows AIK key status",
      v14);
    if ( !v14 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
        McGenEventWrite_EventWriteTransfer(v19, AutopilotManagerWindowsAikKeyNotFoundByName, v20, 1, v51);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49,
        v39);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49);
      return 0;
    }
    phKey = 0;
    Property = NCryptOpenKey(phProvider, &phKey, L"Windows AIK", 0, 0);
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(
      (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49,
      L"Windows AIK key access",
      Property);
    if ( Property < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(v22, AutopilotManagerWindowsAikKeyFailedOpen, (unsigned int)Property);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      if ( Property == -2146893807 )
      {
LABEL_32:
        ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
          (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49,
          v39);
        ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49);
        return 0;
      }
LABEL_33:
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49,
        v39);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49);
      return (unsigned int)Property;
    }
    *a1 = 1;
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikStatusChange(
      (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49,
      1,
      *a2);
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v23, AutopilotManagerTpmAikKeyFound, v24, 1, pvInput);
    pcbResult = 0;
    Property = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", 0, 0, &pcbResult, 0);
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(
      (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49,
      L"Windows AIK cert query status",
      Property);
    if ( Property < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(
          v25,
          AutopilotManagerWindowsAikKeyFailedQueryCertificate,
          (unsigned int)Property);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      if ( Property == -2146893807 )
        goto LABEL_32;
      goto LABEL_33;
    }
    if ( !pcbResult )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer(v25, AutopilotManagerWindowsAikKeyFailedQueryCertificate, 2147943569LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49,
        v39);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49);
      return 0;
    }
    v26 = operator new[](pcbResult, (const struct std::nothrow_t *)&std::nothrow);
    pvInput[0] = v26;
    if ( !v26 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCC,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottpmvalidator.cpp",
        (const char *)0x8007000ELL,
        dwFlagsb);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(pvInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49,
        v39);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49);
      return 2147942414LL;
    }
    v27 = NCryptGetProperty(phKey, L"SmartCardKeyCertificate", (PBYTE)v26, pcbResult, &pcbResult, 0);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD4,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilottpmvalidator.cpp",
        (const char *)(unsigned int)v27,
        dwFlagsc);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(pvInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(
        (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49,
        v39);
      ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49);
      return v28;
    }
    v29 = pcbResult != 0;
    *a2 = pcbResult != 0;
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikStatusChange(
      (ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49,
      *a1,
      v29);
    if ( *a2 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
      {
        v32 = AutopilotManagerTpmAikCertFound;
LABEL_53:
        McGenEventWrite_EventWriteTransfer(v30, v32, v31, 1, v51);
      }
    }
    else if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 2) != 0 )
    {
      v32 = AutopilotManagerTpmAikCertNotFound;
      goto LABEL_53;
    }
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(pvInput);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phKey);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
    wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(&phProvider);
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49, v39);
    ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator((ZeroTouchProvCxhTelemetry::AutopilotTpmValidator *)v49);
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
0x180196d64  mov     [rsp+arg_10], rbx
0x180196d69  mov     [rsp+arg_18], rsi
0x180196d6e  push    rdi
0x180196d6f  push    r12
0x180196d71  push    r13
0x180196d73  push    r14
0x180196d75  push    r15
0x180196d77  sub     rsp, 210h
0x180196d7e  mov     rax, cs:__security_cookie
0x180196d85  xor     rax, rsp
0x180196d88  mov     [rsp+238h+var_38], rax
0x180196d90  mov     r14, rdx
0x180196d93  mov     r15, rcx
0x180196d96  xor     r12d, r12d
0x180196d99  mov     [rcx], r12b
0x180196d9c  mov     [rdx], r12b
0x180196d9f  lea     rax, aTryquerywindow; "TryQueryWindowsAikAvailable"
0x180196da6  mov     [rsp+238h+var_1F8], rax
0x180196dab  lea     rdx, [rsp+238h+var_1F8]
0x180196db0  lea     rcx, [rsp+238h+var_1A8]
0x180196db8  call    ??$Start@AEBQEBG@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@SA?AV01@AEBQEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Start<ushort const * const &>(ushort const * const &)
0x180196dbd  nop
0x180196dbe  lea     rax, [rsp+238h+var_1A8]
0x180196dc6  mov     [rsp+238h+var_1C0], rax
0x180196dcb  lea     rax, [rsp+238h+var_1F8]
0x180196dd0  mov     [rsp+238h+var_1B8], rax
0x180196dd8  lea     r13d, [r12+1]
0x180196ddd  mov     [rsp+238h+var_1B0], r13b
0x180196de5  mov     [rsp+238h+phProvider], r12
0x180196dea  xor     r8d, r8d; dwFlags
0x180196ded  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x180196df4  lea     rcx, [rsp+238h+phProvider]; phProvider
0x180196df9  call    cs:__imp_NCryptOpenStorageProvider
0x180196dff  mov     ebx, eax
0x180196e01  test    eax, eax
0x180196e03  jns     short loc_180196E54
0x180196e05  mov     rcx, [rsp+238h]; this
0x180196e0d  mov     r9d, eax; char *
0x180196e10  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x180196e17  lea     edx, [r12+4Eh]; void *
0x180196e1c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180196e21  nop
0x180196e22  lea     rcx, [rsp+238h+phProvider]
0x180196e27  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180196e2c  nop
0x180196e2d  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x180196e32  lea     rcx, [rsp+238h+var_1A8]; this
0x180196e3a  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x180196e3f  nop
0x180196e40  lea     rcx, [rsp+238h+var_1A8]; this
0x180196e48  call    ??1AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator(void)
0x180196e4d  mov     eax, ebx
0x180196e4f  jmp     loc_180197519
0x180196e54  mov     [rsp+238h+pbInput], r12
0x180196e59  lea     rdx, [rsp+238h+pbInput]
0x180196e5e  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x180196e63  mov     ebx, eax
0x180196e65  test    eax, eax
0x180196e67  jns     short loc_180196EC3
0x180196e69  mov     rcx, [rsp+238h]; this
0x180196e71  mov     r9d, eax; char *
0x180196e74  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x180196e7b  mov     edx, 52h ; 'R'; void *
0x180196e80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180196e85  nop
0x180196e86  lea     rcx, [rsp+238h+pbInput]
0x180196e8b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180196e90  nop
0x180196e91  lea     rcx, [rsp+238h+phProvider]
0x180196e96  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180196e9b  nop
0x180196e9c  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x180196ea1  lea     rcx, [rsp+238h+var_1A8]; this
0x180196ea9  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x180196eae  nop
0x180196eaf  lea     rcx, [rsp+238h+var_1A8]; this
0x180196eb7  call    ??1AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator(void)
0x180196ebc  mov     eax, ebx
0x180196ebe  jmp     loc_180197519
0x180196ec3  mov     r8, [rsp+238h+pbInput]; pbInput
0x180196ec8  or      r9, 0FFFFFFFFFFFFFFFFh
0x180196ecc  inc     r9
0x180196ecf  cmp     [r8+r9*2], r12w
0x180196ed4  jnz     short loc_180196ECC
0x180196ed6  add     r9d, r9d; cbInput
0x180196ed9  mov     [rsp+238h+dwFlags], r12d; dwFlags
0x180196ede  lea     rdx, aPcpAlternateKe; "PCP_ALTERNATE_KEY_STORAGE_LOCATION"
0x180196ee5  mov     rcx, [rsp+238h+phProvider]; hObject
0x180196eea  call    cs:__imp_NCryptSetProperty
0x180196ef0  mov     ebx, eax
0x180196ef2  mov     r8d, eax; int
0x180196ef5  lea     rdx, aWindowsAikLoca; "Windows AIK location"
0x180196efc  lea     rcx, [rsp+238h+var_1A8]; this
0x180196f04  call    ?WindowsAikHresultStatus@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBGJ@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(ushort const *,long)
0x180196f09  test    ebx, ebx
0x180196f0b  jns     short loc_180196F63
0x180196f0d  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180196f14  jz      short loc_180196F26
0x180196f16  mov     r8d, ebx
0x180196f19  lea     rdx, AutopilotManagerWindowsAikAltLocationFailed
0x180196f20  call    McTemplateU0q_EventWriteTransfer
0x180196f25  nop
0x180196f26  lea     rcx, [rsp+238h+pbInput]
0x180196f2b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180196f30  nop
0x180196f31  lea     rcx, [rsp+238h+phProvider]
0x180196f36  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180196f3b  nop
0x180196f3c  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x180196f41  lea     rcx, [rsp+238h+var_1A8]; this
0x180196f49  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x180196f4e  nop
0x180196f4f  lea     rcx, [rsp+238h+var_1A8]; this
0x180196f57  call    ??1AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator(void)
0x180196f5c  mov     eax, ebx
0x180196f5e  jmp     loc_180197519
0x180196f63  mov     dil, r12b
0x180196f66  mov     [rsp+238h+ppEnumState], r12
0x180196f6b  mov     [rsp+238h+var_48], r12
0x180196f73  mov     ebx, r12d
0x180196f76  cmp     ebx, 14h
0x180196f79  jge     loc_180197054
0x180196f7f  mov     [rsp+238h+pvInput], r12
0x180196f87  lea     rax, [rsp+238h+pvInput]
0x180196f8f  mov     [rsp+238h+var_1D8], rax
0x180196f94  mov     [rsp+238h+ppKeyName], r12
0x180196f99  mov     [rsp+238h+var_1C8], r13b
0x180196f9e  mov     [rsp+238h+dwFlags], 60h ; '`'; int
0x180196fa6  lea     r9, [rsp+238h+ppEnumState]; ppEnumState
0x180196fab  lea     r8, [rsp+238h+ppKeyName]; ppKeyName
0x180196fb0  xor     edx, edx; pszScope
0x180196fb2  mov     rcx, [rsp+238h+phProvider]; hProvider
0x180196fb7  call    cs:__imp_NCryptEnumKeys
0x180196fbd  mov     esi, eax
0x180196fbf  lea     rcx, [rsp+238h+var_1D8]
0x180196fc4  call    ??1?$out_param_t@V?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>(void)
0x180196fc9  cmp     esi, 8009002Ah
0x180196fcf  jz      short loc_180197039
0x180196fd1  test    esi, esi
0x180196fd3  jnz     short loc_18019701D
0x180196fd5  lea     rdx, pszKeyName; "Windows AIK"
0x180196fdc  mov     rcx, [rsp+238h+pvInput]
0x180196fe4  mov     rcx, [rcx]
0x180196fe7  call    cs:__imp__o__wcsicmp
0x180196fed  mov     rcx, [rsp+238h+pvInput]; pvInput
0x180196ff5  mov     [rsp+238h+pvInput], r12
0x180196ffd  test    eax, eax
0x180196fff  jz      short loc_180197018
0x180197001  add     ebx, r13d
0x180197004  test    rcx, rcx
0x180197007  jz      loc_180196F76
0x18019700d  call    cs:__imp_NCryptFreeBuffer
0x180197013  jmp     loc_180196F76
0x180197018  mov     dil, r13b
0x18019701b  jmp     short loc_180197049
0x18019701d  mov     rcx, [rsp+238h]; this
0x180197025  mov     r9d, esi; char *
0x180197028  lea     r8, aOnecoreuapAdmi_5; "onecoreuap\\admin\\moderndeployment\\au"...
0x18019702f  mov     edx, 80h; void *
0x180197034  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180197039  mov     rcx, [rsp+238h+pvInput]; pvInput
0x180197041  mov     [rsp+238h+pvInput], r12
0x180197049  test    rcx, rcx
0x18019704c  jz      short loc_180197054
0x18019704e  call    cs:__imp_NCryptFreeBuffer
0x180197054  movzx   r8d, dil; int
0x180197058  lea     rdx, aWindowsAikKeyS; "Windows AIK key status"
0x18019705f  lea     rcx, [rsp+238h+var_1A8]; this
0x180197067  call    ?WindowsAikHresultStatus@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBGJ@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(ushort const *,long)
0x18019706c  test    dil, dil
0x18019706f  jnz     short loc_1801970D4
0x180197071  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x180197078  jz      short loc_180197097
0x18019707a  lea     rax, [rsp+238h+var_48]
0x180197082  mov     qword ptr [rsp+238h+dwFlags], rax
0x180197087  mov     r9d, r13d
0x18019708a  lea     rdx, AutopilotManagerWindowsAikKeyNotFoundByName
0x180197091  call    McGenEventWrite_EventWriteTransfer
0x180197096  nop
0x180197097  lea     rcx, [rsp+238h+pbInput]
0x18019709c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1801970a1  nop
0x1801970a2  lea     rcx, [rsp+238h+phProvider]
0x1801970a7  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x1801970ac  nop
0x1801970ad  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x1801970b2  lea     rcx, [rsp+238h+var_1A8]; this
0x1801970ba  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x1801970bf  nop
0x1801970c0  lea     rcx, [rsp+238h+var_1A8]; this
0x1801970c8  call    ??1AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator(void)
0x1801970cd  xor     eax, eax
0x1801970cf  jmp     loc_180197519
0x1801970d4  mov     [rsp+238h+phKey], r12
0x1801970d9  mov     [rsp+238h+dwFlags], r12d; dwFlags
0x1801970de  xor     r9d, r9d; dwLegacyKeySpec
0x1801970e1  lea     r8, pszKeyName; "Windows AIK"
0x1801970e8  lea     rdx, [rsp+238h+phKey]; phKey
0x1801970ed  mov     rcx, [rsp+238h+phProvider]; hProvider
0x1801970f2  call    cs:__imp_NCryptOpenKey
0x1801970f8  mov     ebx, eax
0x1801970fa  mov     r8d, eax; int
0x1801970fd  lea     rdx, aWindowsAikKeyA; "Windows AIK key access"
0x180197104  lea     rcx, [rsp+238h+var_1A8]; this
0x18019710c  call    ?WindowsAikHresultStatus@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBGJ@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(ushort const *,long)
0x180197111  test    ebx, ebx
0x180197113  jns     loc_1801971A9
0x180197119  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, r13b
0x180197120  jz      short loc_180197132
0x180197122  mov     r8d, ebx
0x180197125  lea     rdx, AutopilotManagerWindowsAikKeyFailedOpen
0x18019712c  call    McTemplateU0q_EventWriteTransfer
0x180197131  nop
0x180197132  lea     rcx, [rsp+238h+phKey]
0x180197137  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18019713c  nop
0x18019713d  lea     rcx, [rsp+238h+pbInput]
0x180197142  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180197147  nop
0x180197148  lea     rcx, [rsp+238h+phProvider]
0x18019714d  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180197152  nop
0x180197153  cmp     ebx, 80090011h
0x180197159  jnz     short loc_180197182
0x18019715b  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x180197160  lea     rcx, [rsp+238h+var_1A8]; this
0x180197168  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x18019716d  nop
0x18019716e  lea     rcx, [rsp+238h+var_1A8]; this
0x180197176  call    ??1AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator(void)
0x18019717b  xor     eax, eax
0x18019717d  jmp     loc_180197519
0x180197182  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x180197187  lea     rcx, [rsp+238h+var_1A8]; this
0x18019718f  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x180197194  nop
0x180197195  lea     rcx, [rsp+238h+var_1A8]; this
0x18019719d  call    ??1AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator(void)
0x1801971a2  mov     eax, ebx
0x1801971a4  jmp     loc_180197519
0x1801971a9  mov     [r15], r13b
0x1801971ac  movzx   r8d, byte ptr [r14]; int
0x1801971b0  mov     edx, r13d; int
0x1801971b3  lea     rcx, [rsp+238h+var_1A8]; this
0x1801971bb  call    ?WindowsAikStatusChange@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXHH@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikStatusChange(int,int)
0x1801971c0  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 2
0x1801971c7  jz      short loc_1801971E5
0x1801971c9  lea     rax, [rsp+238h+pvInput]
0x1801971d1  mov     qword ptr [rsp+238h+dwFlags], rax
0x1801971d6  mov     r9d, r13d
0x1801971d9  lea     rdx, AutopilotManagerTpmAikKeyFound
0x1801971e0  call    McGenEventWrite_EventWriteTransfer
0x1801971e5  mov     [rsp+238h+pcbResult], r12d
0x1801971ea  mov     [rsp+238h+var_210], r12d; dwFlags
0x1801971ef  lea     rax, [rsp+238h+pcbResult]
0x1801971f4  mov     qword ptr [rsp+238h+dwFlags], rax; int
0x1801971f9  xor     r9d, r9d; cbOutput
0x1801971fc  xor     r8d, r8d; pbOutput
0x1801971ff  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180197206  mov     rcx, [rsp+238h+phKey]; hObject
0x18019720b  call    cs:__imp_NCryptGetProperty
0x180197211  mov     ebx, eax
0x180197213  mov     r8d, eax; int
0x180197216  lea     rdx, aWindowsAikCert; "Windows AIK cert query status"
0x18019721d  lea     rcx, [rsp+238h+var_1A8]; this
0x180197225  call    ?WindowsAikHresultStatus@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBGJ@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::WindowsAikHresultStatus(ushort const *,long)
0x18019722a  test    ebx, ebx
0x18019722c  jns     loc_1801972C2
0x180197232  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, r13b
0x180197239  jz      short loc_18019724B
0x18019723b  mov     r8d, ebx
0x18019723e  lea     rdx, AutopilotManagerWindowsAikKeyFailedQueryCertificate
0x180197245  call    McTemplateU0q_EventWriteTransfer
0x18019724a  nop
0x18019724b  lea     rcx, [rsp+238h+phKey]
0x180197250  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x180197255  nop
0x180197256  lea     rcx, [rsp+238h+pbInput]
0x18019725b  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180197260  nop
0x180197261  lea     rcx, [rsp+238h+phProvider]
0x180197266  call    ??1?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>(void)
0x18019726b  nop
0x18019726c  cmp     ebx, 80090011h
0x180197272  jnz     short loc_18019729B
0x180197274  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x180197279  lea     rcx, [rsp+238h+var_1A8]; this
0x180197281  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x180197286  nop
0x180197287  lea     rcx, [rsp+238h+var_1A8]; this
0x18019728f  call    ??1AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator(void)
0x180197294  xor     eax, eax
0x180197296  jmp     loc_180197519
0x18019729b  mov     rdx, [rsp+238h+var_1F8]; unsigned __int16 *
0x1801972a0  lea     rcx, [rsp+238h+var_1A8]; this
0x1801972a8  call    ?Stop@AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAAXPEBG@Z; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::Stop(ushort const *)
0x1801972ad  nop
0x1801972ae  lea     rcx, [rsp+238h+var_1A8]; this
0x1801972b6  call    ??1AutopilotTpmValidator@ZeroTouchProvCxhTelemetry@@QEAA@XZ; ZeroTouchProvCxhTelemetry::AutopilotTpmValidator::~AutopilotTpmValidator(void)
0x1801972bb  mov     eax, ebx
  ... truncated ...
```
