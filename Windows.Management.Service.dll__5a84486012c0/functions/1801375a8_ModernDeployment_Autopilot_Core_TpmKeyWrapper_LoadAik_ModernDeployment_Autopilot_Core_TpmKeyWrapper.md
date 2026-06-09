# ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik(ModernDeployment::Autopilot::Core::TpmKeyWrapper &)

- ea: `0x1801375a8`
- end: `0x180137f07`
- name: `?LoadAik@TpmKeyWrapper@Core@Autopilot@ModernDeployment@@SAJAEAV1234@@Z`
- size: `2399`
- prototype: `__int64 __fastcall(struct ModernDeployment::Autopilot::Core::TpmKeyWrapper *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18012f7f8`

## callees

- `0x18000b820`
- `0x18000bd80`
- `0x180067a54`
- `0x18006e89c`
- `0x180077384`
- `0x18007748c`
- `0x1800801fc`
- `0x1800806b0`
- `0x18008e328`
- `0x1800a8180`
- `0x1800cff04`
- `0x180120364`
- `0x180120840`
- `0x180136a00`
- `0x180136a7c`
- `0x180136b84`
- `0x180136c08`
- `0x180136cd4`
- `0x1801375a8`
- `0x180142f20`
- `0x18015bd64`
- `0x18019f59c`
- `0x18019f6b4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180137960`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180137960`
- `ncrypt!NCryptOpenKey` at `0x180137a3b`
- `ncrypt!NCryptOpenKey` at `0x180137a3b`
- `ncrypt!NCryptGetProperty` at `0x180137b2a`
- `ncrypt!NCryptGetProperty` at `0x180137ba1`
- `ncrypt!NCryptGetProperty` at `0x180137b2a`
- `ncrypt!NCryptGetProperty` at `0x180137ba1`
- `ncrypt!NCryptEnumKeys` at `0x1801378b4`
- `ncrypt!NCryptEnumKeys` at `0x1801378b4`
- `ncrypt!NCryptSetProperty` at `0x1801377d3`
- `ncrypt!NCryptSetProperty` at `0x1801377d3`
- `ncrypt!NCryptFreeBuffer` at `0x180137909`
- `ncrypt!NCryptFreeBuffer` at `0x18013797f`
- `ncrypt!NCryptFreeBuffer` at `0x180137992`
- `ncrypt!NCryptFreeBuffer` at `0x180137909`
- `ncrypt!NCryptFreeBuffer` at `0x18013797f`
- `ncrypt!NCryptFreeBuffer` at `0x180137992`
- `ncrypt!NCryptOpenStorageProvider` at `0x1801376ca`
- `ncrypt!NCryptOpenStorageProvider` at `0x1801376ca`

## string_xrefs

- `0x180137677`: `OpenProviderForAik`
- `0x1801376e8`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x18013774c`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x1801377f1`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x1801378e3`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x180137a59`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x180137ace`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x180137bb8`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x180137c3e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x180137cc2`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x180137d96`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x180137e17`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x180137ec9`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik(
        struct ModernDeployment::Autopilot::Core::TpmKeyWrapper *a1)
{
  NCRYPT_PROV_HANDLE *v2; // rax
  SECURITY_STATUS v3; // eax
  __int64 v4; // rcx
  unsigned int v5; // ebx
  int v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rax
  NCRYPT_PROV_HANDLE *v10; // rdi
  NCRYPT_HANDLE v11; // rcx
  SECURITY_STATUS v12; // eax
  PVOID v13; // rcx
  __int64 v14; // r8
  unsigned int v15; // ebx
  int i; // esi
  NCRYPT_PROV_HANDLE v17; // rcx
  unsigned int v18; // r14d
  PVOID v19; // rcx
  int v20; // eax
  NCRYPT_KEY_HANDLE *v21; // rax
  NCRYPT_PROV_HANDLE v22; // rcx
  SECURITY_STATUS v23; // eax
  unsigned int v24; // edi
  int AikCertRequiredOverride; // eax
  NCRYPT_HANDLE *v26; // rdi
  NCRYPT_HANDLE v27; // rcx
  int v28; // ecx
  SECURITY_STATUS Property; // r8d
  void *v30; // rax
  NCRYPT_HANDLE v31; // rcx
  SECURITY_STATUS v32; // eax
  unsigned int v33; // edi
  unsigned int v34; // edi
  int v35; // eax
  bool v36; // dl
  unsigned int v37; // edi
  int v38; // eax
  unsigned int v39; // edi
  int dwFlags; // [rsp+20h] [rbp-2B8h]
  int dwFlagsa; // [rsp+20h] [rbp-2B8h]
  int dwFlagsb; // [rsp+20h] [rbp-2B8h]
  int dwFlagsc; // [rsp+20h] [rbp-2B8h]
  int dwFlagsd; // [rsp+20h] [rbp-2B8h]
  bool v45; // [rsp+30h] [rbp-2A8h] BYREF
  PBYTE pbInput; // [rsp+38h] [rbp-2A0h] BYREF
  _QWORD v47[4]; // [rsp+40h] [rbp-298h] BYREF
  char v48; // [rsp+60h] [rbp-278h]
  std::_Ref_count_base *v49[2]; // [rsp+68h] [rbp-270h] BYREF
  PVOID *v50; // [rsp+78h] [rbp-260h] BYREF
  NCryptKeyName *ppKeyName; // [rsp+80h] [rbp-258h] BYREF
  char v52; // [rsp+88h] [rbp-250h]
  DWORD pcbResult; // [rsp+90h] [rbp-248h] BYREF
  const wchar_t *v54; // [rsp+98h] [rbp-240h] BYREF
  PVOID ppEnumState; // [rsp+A0h] [rbp-238h] BYREF
  char v56; // [rsp+A8h] [rbp-230h] BYREF
  char v57; // [rsp+A9h] [rbp-22Fh] BYREF
  SECURITY_STATUS v58; // [rsp+ACh] [rbp-22Ch] BYREF
  _BYTE v59[80]; // [rsp+B0h] [rbp-228h] BYREF
  _QWORD v60[2]; // [rsp+100h] [rbp-1D8h] BYREF
  _QWORD v61[22]; // [rsp+110h] [rbp-1C8h] BYREF
  _BYTE v62[192]; // [rsp+1C0h] [rbp-118h] BYREF
  PVOID pvInput[2]; // [rsp+280h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
      (const char *)0x80004001LL,
      dwFlags);
    return 2147500033LL;
  }
  ModernDeployment::Autopilot::Core::NcryptKeyData::NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v60);
  v57 = 0;
  v56 = 0;
  v58 = 0;
  Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(
    (Microsoft::Windows::Autopilot::ScopedTsmLogger *)v59,
    L"TpmKeyWrapper",
    L"LoadAik",
    &v58);
  v47[0] = &v58;
  v47[1] = &v54;
  v47[2] = &v57;
  v47[3] = &v56;
  v48 = 1;
  v54 = L"OpenProviderForAik";
  *(_OWORD *)v49 = 0;
  std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(v60, v49);
  if ( v49[1] )
    std::_Ref_count_base::_Decref(v49[1]);
  v2 = (NCRYPT_PROV_HANDLE *)wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(v60);
  v3 = NCryptOpenStorageProvider(v2, L"Microsoft Platform Crypto Provider", 0);
  v5 = v3;
  v58 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
      (const char *)(unsigned int)v3,
      dwFlags);
    v48 = 0;
    ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v47);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v59);
    ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v60);
    return v5;
  }
  pbInput = 0;
  v7 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
         v4,
         &pbInput);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
      (const char *)(unsigned int)v7,
      dwFlags);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
    v48 = 0;
    ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v47);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v59);
    ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v60);
    return v8;
  }
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)&pbInput[2 * v9] );
  v10 = (NCRYPT_PROV_HANDLE *)v60[0];
  if ( v60[0] )
    v11 = *(_QWORD *)v60[0];
  else
    v11 = 0;
  v12 = NCryptSetProperty(v11, L"PCP_ALTERNATE_KEY_STORAGE_LOCATION", pbInput, 2 * v9, 0);
  v15 = v12;
  v58 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
      (const char *)(unsigned int)v12,
      dwFlagsa);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
    v48 = 0;
    ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v47);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v59);
    ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v60);
    return v15;
  }
  ppEnumState = 0;
  v49[0] = 0;
  v54 = L"EnumeratePossibleKeys";
  for ( i = 0; i < 20; ++i )
  {
    pvInput[0] = 0;
    v50 = pvInput;
    ppKeyName = 0;
    v52 = 1;
    if ( v10 )
      v17 = *v10;
    else
      v17 = 0;
    v58 = NCryptEnumKeys(v17, 0, &ppKeyName, &ppEnumState, 0x60u);
    wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>(&v50);
    v18 = v58;
    if ( v58 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xDF,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
        (const char *)(unsigned int)v58,
        dwFlagsb);
      v19 = pvInput[0];
      pvInput[0] = 0;
      if ( v19 )
        NCryptFreeBuffer(v19);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      v48 = 0;
      ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v47);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v59);
      ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v60);
      return v18;
    }
    v20 = _o__wcsicmp(*(_QWORD *)pvInput[0], L"Windows AIK");
    v13 = pvInput[0];
    pvInput[0] = 0;
    if ( !v20 )
    {
      if ( v13 )
        NCryptFreeBuffer(v13);
      goto LABEL_31;
    }
    if ( v13 )
      NCryptFreeBuffer(v13);
  }
  if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(v13, AutopilotMaaLoadAikKeyEnumFailed, v14, 1, pvInput);
LABEL_31:
  v54 = L"LoadAIK";
  *(_OWORD *)pvInput = 0;
  std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(v61, pvInput);
  if ( pvInput[1] )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)pvInput[1]);
  v21 = (NCRYPT_KEY_HANDLE *)wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(v61);
  if ( v60[0] )
    v22 = *(_QWORD *)v60[0];
  else
    v22 = 0;
  v23 = NCryptOpenKey(v22, v21, L"Windows AIK", 0, 0);
  v24 = v23;
  v58 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF5,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
      (const char *)(unsigned int)v23,
      dwFlagsc);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
    v48 = 0;
    ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v47);
    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v59);
    ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v60);
    return v24;
  }
  v57 = 1;
  v45 = 1;
  AikCertRequiredOverride = ModernDeployment::Autopilot::Core::AutopilotConfig::GetAikCertRequiredOverride(&v45);
  if ( AikCertRequiredOverride < 0 )
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xFF,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
      (const char *)(unsigned int)AikCertRequiredOverride,
      dwFlagsc);
  v54 = L"ConfirmAikCert";
  pcbResult = 0;
  v26 = (NCRYPT_HANDLE *)v61[0];
  if ( v61[0] )
    v27 = *(_QWORD *)v61[0];
  else
    v27 = 0;
  Property = NCryptGetProperty(v27, L"SmartCardKeyCertificate", 0, 0, &pcbResult, 0);
  v58 = Property;
  if ( Property >= 0 && pcbResult )
  {
    v30 = operator new[](pcbResult, (const struct std::nothrow_t *)&std::nothrow);
    pvInput[0] = v30;
    if ( !v30 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x124,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
        (const char *)0x8007000ELL,
        dwFlagsd);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(pvInput);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      v48 = 0;
      ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v47);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v59);
      ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v60);
      return 2147942414LL;
    }
    if ( v26 )
      v31 = *v26;
    else
      v31 = 0;
    v32 = NCryptGetProperty(v31, L"SmartCardKeyCertificate", (PBYTE)v30, pcbResult, &pcbResult, 0);
    v33 = v32;
    if ( v32 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x12C,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
        (const char *)(unsigned int)v32,
        dwFlagsd);
      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(pvInput);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      v48 = 0;
      ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v47);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v59);
      ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v60);
      return v33;
    }
    v56 = 1;
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(pvInput);
    goto LABEL_63;
  }
  if ( !v45 )
  {
    v56 = 0;
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
    {
      if ( Property >= 0 )
        Property = -2147023727;
      McTemplateU0dzqq_EventWriteTransfer(
        v28,
        (unsigned int)AutopilotMaaLoadAikFailed,
        Property,
        (unsigned int)L"ConfirmAikCert_LogOnly",
        v57,
        0);
    }
    v58 = 0;
LABEL_63:
    ModernDeployment::Autopilot::Core::NcryptKeyData::NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v62);
    v35 = ModernDeployment::Autopilot::Core::NcryptKeyData::CreateFromKeyHandle(v60, v61, v62);
    v37 = v35;
    if ( v35 >= 0 )
    {
      v38 = ModernDeployment::Autopilot::Core::TpmKeyWrapper::CreateFromKeyData(
              (const struct ModernDeployment::Autopilot::Core::NcryptKeyData *)v62,
              v36,
              0,
              a1);
      v39 = v38;
      if ( v38 >= 0 )
      {
        ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v62);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
        v48 = 0;
        ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v47);
        Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v59);
        ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v60);
        return 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x138,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
          (const char *)(unsigned int)v38,
          dwFlagsd);
        ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v62);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
        v48 = 0;
        ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v47);
        Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v59);
        ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v60);
        return v39;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x136,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
        (const char *)(unsigned int)v35,
        dwFlagsd);
      ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v62);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
      v48 = 0;
      ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v47);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v59);
      ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v60);
      return v37;
    }
  }
  if ( Property < 0 )
  {
    v34 = Property;
  }
  else
  {
    v34 = -2147023727;
    v58 = -2147023727;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x114,
    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
    (const char *)v34,
    dwFlagsd);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
  v48 = 0;
  ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v47);
  Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v59);
  ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v60);
  return v34;
}

```

## disassembly

```asm
0x1801375a8  push    rbx
0x1801375aa  push    rsi
0x1801375ab  push    rdi
0x1801375ac  push    r12
0x1801375ae  push    r14
0x1801375b0  push    r15
0x1801375b2  sub     rsp, 2A8h
0x1801375b9  mov     rax, cs:__security_cookie
0x1801375c0  xor     rax, rsp
0x1801375c3  mov     [rsp+2D8h+var_48], rax
0x1801375cb  mov     r15, rcx
0x1801375ce  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x1801375d5  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x1801375da  xor     r12d, r12d
0x1801375dd  test    al, al
0x1801375df  jz      loc_180137EB9
0x1801375e5  lea     rcx, [rsp+2D8h+var_1D8]; this
0x1801375ed  call    ??0NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::NcryptKeyData(void)
0x1801375f2  nop
0x1801375f3  mov     [rsp+2D8h+var_22F], r12b
0x1801375fb  mov     [rsp+2D8h+var_230], r12b
0x180137603  mov     dword ptr [rsp+2D8h+var_22C], r12d
0x18013760b  lea     rax, sourceString
0x180137612  mov     [rsp+2D8h+var_240], rax
0x18013761a  lea     r9, [rsp+2D8h+var_22C]; int *
0x180137622  lea     r8, aLoadaik; "LoadAik"
0x180137629  lea     rdx, aTpmkeywrapper; "TpmKeyWrapper"
0x180137630  lea     rcx, [rsp+2D8h+var_22C+4]; this
0x180137638  call    ??0ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@PEBG0AEAJ@Z; Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(ushort const *,ushort const *,long &)
0x18013763d  nop
0x18013763e  lea     rax, [rsp+2D8h+var_22C]
0x180137646  mov     [rsp+2D8h+var_298], rax
0x18013764b  lea     rax, [rsp+2D8h+var_240]
0x180137653  mov     [rsp+2D8h+var_290], rax
0x180137658  lea     rax, [rsp+2D8h+var_22F]
0x180137660  mov     [rsp+2D8h+var_288], rax
0x180137665  lea     rax, [rsp+2D8h+var_230]
0x18013766d  mov     [rsp+2D8h+var_280], rax
0x180137672  mov     [rsp+2D8h+var_278], 1
0x180137677  lea     rax, aOpenproviderfo; "OpenProviderForAik"
0x18013767e  mov     [rsp+2D8h+var_240], rax
0x180137686  xorps   xmm0, xmm0
0x180137689  movdqu  xmmword ptr [rsp+2D8h+var_270], xmm0
0x18013768f  lea     rdx, [rsp+2D8h+var_270]
0x180137694  lea     rcx, [rsp+2D8h+var_1D8]
0x18013769c  call    ??4?$shared_ptr@VEtwProcessingDataEntry@Diagnostics@Autopilot@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry> &&)
0x1801376a1  mov     rcx, [rsp+2D8h+var_270+8]; this
0x1801376a6  test    rcx, rcx
0x1801376a9  jz      short loc_1801376B0
0x1801376ab  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801376b0  lea     rcx, [rsp+2D8h+var_1D8]
0x1801376b8  call    ??$addressof@U?$integral_constant@_K$0A@@wistd@@$0A@@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAPEA_KXZ; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(void)
0x1801376bd  xor     r8d, r8d; dwFlags
0x1801376c0  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x1801376c7  mov     rcx, rax; phProvider
0x1801376ca  call    cs:__imp_NCryptOpenStorageProvider
0x1801376d0  mov     ebx, eax
0x1801376d2  mov     dword ptr [rsp+2D8h+var_22C], eax
0x1801376d9  test    eax, eax
0x1801376db  jns     short loc_18013772C
0x1801376dd  mov     rcx, [rsp+2D8h]; this
0x1801376e5  mov     r9d, eax; char *
0x1801376e8  lea     r8, aOnecoreuapAdmi_127; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801376ef  mov     edx, 0B7h; void *
0x1801376f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801376f9  nop
0x1801376fa  mov     [rsp+2D8h+var_278], r12b
0x1801376ff  lea     rcx, [rsp+2D8h+var_298]
0x180137704  call    _ModernDeployment__Autopilot__Core__TpmKeyWrapper__LoadAik____3____lambda_1___operator__
0x180137709  nop
0x18013770a  lea     rcx, [rsp+2D8h+var_22C+4]; this
0x180137712  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180137717  nop
0x180137718  lea     rcx, [rsp+2D8h+var_1D8]; this
0x180137720  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x180137725  mov     eax, ebx
0x180137727  jmp     loc_180137EE5
0x18013772c  mov     [rsp+2D8h+pbInput], r12
0x180137731  lea     rdx, [rsp+2D8h+pbInput]
0x180137736  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18013773b  mov     ebx, eax
0x18013773d  test    eax, eax
0x18013773f  jns     short loc_18013779B
0x180137741  mov     rcx, [rsp+2D8h]; this
0x180137749  mov     r9d, eax; char *
0x18013774c  lea     r8, aOnecoreuapAdmi_127; "onecoreuap\\admin\\moderndeployment\\au"...
0x180137753  mov     edx, 0BBh; void *
0x180137758  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013775d  nop
0x18013775e  lea     rcx, [rsp+2D8h+pbInput]
0x180137763  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180137768  nop
0x180137769  mov     [rsp+2D8h+var_278], r12b
0x18013776e  lea     rcx, [rsp+2D8h+var_298]
0x180137773  call    _ModernDeployment__Autopilot__Core__TpmKeyWrapper__LoadAik____3____lambda_1___operator__
0x180137778  nop
0x180137779  lea     rcx, [rsp+2D8h+var_22C+4]; this
0x180137781  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180137786  nop
0x180137787  lea     rcx, [rsp+2D8h+var_1D8]; this
0x18013778f  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x180137794  mov     eax, ebx
0x180137796  jmp     loc_180137EE5
0x18013779b  mov     r8, [rsp+2D8h+pbInput]; pbInput
0x1801377a0  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801377a4  inc     rax
0x1801377a7  cmp     [r8+rax*2], r12w
0x1801377ac  jnz     short loc_1801377A4
0x1801377ae  lea     r9, [rax+rax]; cbInput
0x1801377b2  mov     rdi, [rsp+2D8h+var_1D8]
0x1801377ba  test    rdi, rdi
0x1801377bd  jz      short loc_1801377C4
0x1801377bf  mov     rcx, [rdi]
0x1801377c2  jmp     short loc_1801377C7
0x1801377c4  mov     rcx, r12; hObject
0x1801377c7  mov     [rsp+2D8h+dwFlags], r12d; int
0x1801377cc  lea     rdx, aPcpAlternateKe; "PCP_ALTERNATE_KEY_STORAGE_LOCATION"
0x1801377d3  call    cs:__imp_NCryptSetProperty
0x1801377d9  mov     ebx, eax
0x1801377db  mov     dword ptr [rsp+2D8h+var_22C], eax
0x1801377e2  test    eax, eax
0x1801377e4  jns     short loc_180137840
0x1801377e6  mov     rcx, [rsp+2D8h]; this
0x1801377ee  mov     r9d, eax; char *
0x1801377f1  lea     r8, aOnecoreuapAdmi_127; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801377f8  mov     edx, 0C4h; void *
0x1801377fd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137802  nop
0x180137803  lea     rcx, [rsp+2D8h+pbInput]
0x180137808  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18013780d  nop
0x18013780e  mov     [rsp+2D8h+var_278], r12b
0x180137813  lea     rcx, [rsp+2D8h+var_298]
0x180137818  call    _ModernDeployment__Autopilot__Core__TpmKeyWrapper__LoadAik____3____lambda_1___operator__
0x18013781d  nop
0x18013781e  lea     rcx, [rsp+2D8h+var_22C+4]; this
0x180137826  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x18013782b  nop
0x18013782c  lea     rcx, [rsp+2D8h+var_1D8]; this
0x180137834  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x180137839  mov     eax, ebx
0x18013783b  jmp     loc_180137EE5
0x180137840  mov     [rsp+2D8h+ppEnumState], r12
0x180137848  mov     [rsp+2D8h+var_270], r12
0x18013784d  lea     rax, aEnumeratepossi; "EnumeratePossibleKeys"
0x180137854  mov     [rsp+2D8h+var_240], rax
0x18013785c  mov     esi, r12d
0x18013785f  cmp     esi, 14h
0x180137862  jge     loc_18013799D
0x180137868  mov     [rsp+2D8h+pvInput], r12
0x180137870  lea     rax, [rsp+2D8h+pvInput]
0x180137878  mov     [rsp+2D8h+var_260], rax
0x18013787d  mov     [rsp+2D8h+ppKeyName], r12
0x180137885  mov     [rsp+2D8h+var_250], 1
0x18013788d  test    rdi, rdi
0x180137890  jz      short loc_180137897
0x180137892  mov     rcx, [rdi]
0x180137895  jmp     short loc_18013789A
0x180137897  mov     rcx, r12; hProvider
0x18013789a  mov     [rsp+2D8h+dwFlags], 60h ; '`'; int
0x1801378a2  lea     r9, [rsp+2D8h+ppEnumState]; ppEnumState
0x1801378aa  lea     r8, [rsp+2D8h+ppKeyName]; ppKeyName
0x1801378b2  xor     edx, edx; pszScope
0x1801378b4  call    cs:__imp_NCryptEnumKeys
0x1801378ba  mov     dword ptr [rsp+2D8h+var_22C], eax
0x1801378c1  lea     rcx, [rsp+2D8h+var_260]
0x1801378c6  call    ??1?$out_param_t@V?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>(void)
0x1801378cb  mov     r14d, dword ptr [rsp+2D8h+var_22C]
0x1801378d3  test    r14d, r14d
0x1801378d6  jns     short loc_18013794E
0x1801378d8  mov     rcx, [rsp+2D8h]; this
0x1801378e0  mov     r9d, r14d; char *
0x1801378e3  lea     r8, aOnecoreuapAdmi_127; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801378ea  mov     edx, 0DFh; void *
0x1801378ef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801378f4  mov     rcx, [rsp+2D8h+pvInput]; pvInput
0x1801378fc  mov     [rsp+2D8h+pvInput], r12
0x180137904  test    rcx, rcx
0x180137907  jz      short loc_180137910
0x180137909  call    cs:__imp_NCryptFreeBuffer
0x18013790f  nop
0x180137910  lea     rcx, [rsp+2D8h+pbInput]
0x180137915  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18013791a  nop
0x18013791b  mov     [rsp+2D8h+var_278], r12b
0x180137920  lea     rcx, [rsp+2D8h+var_298]
0x180137925  call    _ModernDeployment__Autopilot__Core__TpmKeyWrapper__LoadAik____3____lambda_1___operator__
0x18013792a  nop
0x18013792b  lea     rcx, [rsp+2D8h+var_22C+4]; this
0x180137933  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180137938  nop
0x180137939  lea     rcx, [rsp+2D8h+var_1D8]; this
0x180137941  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x180137946  mov     eax, r14d
0x180137949  jmp     loc_180137EE5
0x18013794e  lea     rdx, pszKeyName; "Windows AIK"
0x180137955  mov     rcx, [rsp+2D8h+pvInput]
0x18013795d  mov     rcx, [rcx]
0x180137960  call    cs:__imp__o__wcsicmp
0x180137966  mov     rcx, [rsp+2D8h+pvInput]; pvInput
0x18013796e  mov     [rsp+2D8h+pvInput], r12
0x180137976  test    eax, eax
0x180137978  jnz     short loc_180137987
0x18013797a  test    rcx, rcx
0x18013797d  jz      short loc_1801379C5
0x18013797f  call    cs:__imp_NCryptFreeBuffer
0x180137985  jmp     short loc_1801379C5
0x180137987  inc     esi
0x180137989  test    rcx, rcx
0x18013798c  jz      loc_18013785F
0x180137992  call    cs:__imp_NCryptFreeBuffer
0x180137998  jmp     loc_18013785F
0x18013799d  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x1801379a4  jz      short loc_1801379C5
0x1801379a6  lea     rax, [rsp+2D8h+pvInput]
0x1801379ae  mov     qword ptr [rsp+2D8h+dwFlags], rax
0x1801379b3  mov     r9d, 1
0x1801379b9  lea     rdx, AutopilotMaaLoadAikKeyEnumFailed
0x1801379c0  call    McGenEventWrite_EventWriteTransfer
0x1801379c5  lea     rax, aLoadaik_0; "LoadAIK"
0x1801379cc  mov     [rsp+2D8h+var_240], rax
0x1801379d4  xorps   xmm0, xmm0
0x1801379d7  movdqu  xmmword ptr [rsp+2D8h+pvInput], xmm0
0x1801379e0  lea     rdx, [rsp+2D8h+pvInput]
0x1801379e8  lea     rcx, [rsp+2D8h+var_1C8]
0x1801379f0  call    ??4?$shared_ptr@VEtwProcessingDataEntry@Diagnostics@Autopilot@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry> &&)
0x1801379f5  mov     rcx, [rsp+2D8h+pvInput+8]; this
0x1801379fd  test    rcx, rcx
0x180137a00  jz      short loc_180137A07
0x180137a02  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180137a07  lea     rcx, [rsp+2D8h+var_1C8]
0x180137a0f  call    ??$addressof@U?$integral_constant@_K$0A@@wistd@@$0A@@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAPEA_KXZ; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(void)
0x180137a14  mov     rcx, [rsp+2D8h+var_1D8]
0x180137a1c  test    rcx, rcx
0x180137a1f  jz      short loc_180137A26
0x180137a21  mov     rcx, [rcx]
0x180137a24  jmp     short loc_180137A29
0x180137a26  mov     rcx, r12; hProvider
0x180137a29  mov     [rsp+2D8h+dwFlags], r12d; int
0x180137a2e  xor     r9d, r9d; dwLegacyKeySpec
0x180137a31  lea     r8, pszKeyName; "Windows AIK"
0x180137a38  mov     rdx, rax; phKey
0x180137a3b  call    cs:__imp_NCryptOpenKey
0x180137a41  mov     edi, eax
0x180137a43  mov     dword ptr [rsp+2D8h+var_22C], eax
0x180137a4a  test    eax, eax
0x180137a4c  jns     short loc_180137AA8
0x180137a4e  mov     rcx, [rsp+2D8h]; this
0x180137a56  mov     r9d, eax; char *
0x180137a59  lea     r8, aOnecoreuapAdmi_127; "onecoreuap\\admin\\moderndeployment\\au"...
0x180137a60  mov     edx, 0F5h; void *
0x180137a65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180137a6a  nop
0x180137a6b  lea     rcx, [rsp+2D8h+pbInput]
0x180137a70  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180137a75  nop
0x180137a76  mov     [rsp+2D8h+var_278], r12b
0x180137a7b  lea     rcx, [rsp+2D8h+var_298]
0x180137a80  call    _ModernDeployment__Autopilot__Core__TpmKeyWrapper__LoadAik____3____lambda_1___operator__
0x180137a85  nop
0x180137a86  lea     rcx, [rsp+2D8h+var_22C+4]; this
0x180137a8e  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x180137a93  nop
0x180137a94  lea     rcx, [rsp+2D8h+var_1D8]; this
0x180137a9c  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x180137aa1  mov     eax, edi
0x180137aa3  jmp     loc_180137EE5
0x180137aa8  mov     [rsp+2D8h+var_22F], 1
0x180137ab0  mov     [rsp+2D8h+var_2A8], 1
0x180137ab5  lea     rcx, [rsp+2D8h+var_2A8]; bool *
0x180137aba  call    ?GetAikCertRequiredOverride@AutopilotConfig@Core@Autopilot@ModernDeployment@@SAJAEA_N@Z; ModernDeployment::Autopilot::Core::AutopilotConfig::GetAikCertRequiredOverride(bool &)
0x180137abf  mov     rcx, [rsp+2D8h]; this
0x180137ac7  test    eax, eax
0x180137ac9  jns     short loc_180137ADF
0x180137acb  mov     r9d, eax; char *
0x180137ace  lea     r8, aOnecoreuapAdmi_127; "onecoreuap\\admin\\moderndeployment\\au"...
0x180137ad5  mov     edx, 0FFh; void *
0x180137ada  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180137adf  lea     rax, aConfirmaikcert_0; "ConfirmAikCert"
0x180137ae6  mov     [rsp+2D8h+var_240], rax
0x180137aee  mov     [rsp+2D8h+pcbResult], r12d
0x180137af6  mov     rdi, [rsp+2D8h+var_1C8]
0x180137afe  test    rdi, rdi
0x180137b01  jz      short loc_180137B08
0x180137b03  mov     rcx, [rdi]
0x180137b06  jmp     short loc_180137B0B
0x180137b08  mov     rcx, r12; hObject
0x180137b0b  mov     [rsp+2D8h+var_2B0], r12d; dwFlags
0x180137b10  lea     rax, [rsp+2D8h+pcbResult]
0x180137b18  mov     qword ptr [rsp+2D8h+dwFlags], rax; int
0x180137b1d  xor     r9d, r9d; cbOutput
0x180137b20  xor     r8d, r8d; pbOutput
0x180137b23  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x180137b2a  call    cs:__imp_NCryptGetProperty
0x180137b30  mov     r8d, eax
0x180137b33  mov     dword ptr [rsp+2D8h+var_22C], eax
0x180137b3a  test    eax, eax
0x180137b3c  js      loc_180137C9A
0x180137b42  mov     eax, [rsp+2D8h+pcbResult]
0x180137b49  test    eax, eax
  ... truncated ...
```
