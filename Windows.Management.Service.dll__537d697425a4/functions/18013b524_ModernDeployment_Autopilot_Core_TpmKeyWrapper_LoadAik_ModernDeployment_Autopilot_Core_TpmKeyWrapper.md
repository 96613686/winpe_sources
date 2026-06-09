# ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik(ModernDeployment::Autopilot::Core::TpmKeyWrapper &)

- ea: `0x18013b524`
- end: `0x18013bef5`
- name: `?LoadAik@TpmKeyWrapper@Core@Autopilot@ModernDeployment@@SAJAEAV1234@@Z`
- size: `2513`
- prototype: `__int64 __fastcall(struct ModernDeployment::Autopilot::Core::TpmKeyWrapper *)`
- caller_count: `1`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180133578`

## callees

- `0x18000b8f0`
- `0x18000be44`
- `0x180067e54`
- `0x18006ee48`
- `0x180077c04`
- `0x180080c10`
- `0x1800810f0`
- `0x18008f458`
- `0x1800d238c`
- `0x180123edc`
- `0x1801243d0`
- `0x180126130`
- `0x18013a968`
- `0x18013a9e4`
- `0x18013aaec`
- `0x18013ab70`
- `0x18013ac44`
- `0x18013b524`
- `0x180160048`
- `0x1801a4a04`
- `0x1801a4b1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18013b8dc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18013b8dc`
- `ncrypt!NCryptOpenKey` at `0x18013b9a7`
- `ncrypt!NCryptOpenKey` at `0x18013b9a7`
- `ncrypt!NCryptGetProperty` at `0x18013ba6d`
- `ncrypt!NCryptGetProperty` at `0x18013bba2`
- `ncrypt!NCryptGetProperty` at `0x18013ba6d`
- `ncrypt!NCryptGetProperty` at `0x18013bba2`
- `ncrypt!NCryptEnumKeys` at `0x18013b836`
- `ncrypt!NCryptEnumKeys` at `0x18013b836`
- `ncrypt!NCryptSetProperty` at `0x18013b755`
- `ncrypt!NCryptSetProperty` at `0x18013b755`
- `ncrypt!NCryptOpenStorageProvider` at `0x18013b646`
- `ncrypt!NCryptOpenStorageProvider` at `0x18013b646`

## string_xrefs

- `0x18013b66a`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x18013b6ce`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x18013b779`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x18013b86b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x18013b9cb`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x18013ba91`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x18013bb02`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x18013bbbf`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x18013bc6e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x18013bcfd`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x18013bde0`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x18013be4d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x18013beb7`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmkeywrapper.cpp`
- `0x18013b5f3`: `OpenProviderForAik`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
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
  __int64 v13; // rcx
  __int64 v14; // r8
  unsigned int v15; // ebx
  int i; // esi
  NCRYPT_PROV_HANDLE v17; // rcx
  unsigned int v18; // r14d
  NCRYPT_KEY_HANDLE *v19; // rax
  NCRYPT_PROV_HANDLE v20; // rcx
  SECURITY_STATUS v21; // eax
  unsigned int v22; // edi
  NCRYPT_HANDLE *v23; // rdi
  NCRYPT_HANDLE v24; // rcx
  SECURITY_STATUS Property; // eax
  unsigned int v26; // esi
  std::_Ref_count_base *v27; // rax
  NCRYPT_HANDLE v28; // rcx
  SECURITY_STATUS v29; // eax
  unsigned int v30; // edi
  int v31; // eax
  bool v32; // dl
  unsigned int v33; // edi
  int v34; // eax
  unsigned int v35; // edi
  int dwFlags; // [rsp+20h] [rbp-2B8h]
  int dwFlagsa; // [rsp+20h] [rbp-2B8h]
  int dwFlagsb; // [rsp+20h] [rbp-2B8h]
  int dwFlagsc; // [rsp+20h] [rbp-2B8h]
  int dwFlagsd; // [rsp+20h] [rbp-2B8h]
  int dwFlagse; // [rsp+20h] [rbp-2B8h]
  PBYTE pbInput; // [rsp+30h] [rbp-2A8h] BYREF
  _QWORD v43[4]; // [rsp+38h] [rbp-2A0h] BYREF
  char v44; // [rsp+58h] [rbp-280h]
  std::_Ref_count_base *v45[2]; // [rsp+60h] [rbp-278h] BYREF
  std::_Ref_count_base **v46; // [rsp+70h] [rbp-268h] BYREF
  NCryptKeyName *ppKeyName; // [rsp+78h] [rbp-260h] BYREF
  char v48; // [rsp+80h] [rbp-258h]
  DWORD pcbResult; // [rsp+88h] [rbp-250h] BYREF
  const wchar_t *v50; // [rsp+90h] [rbp-248h] BYREF
  PVOID ppEnumState; // [rsp+98h] [rbp-240h] BYREF
  char v52; // [rsp+A0h] [rbp-238h] BYREF
  char v53; // [rsp+A1h] [rbp-237h] BYREF
  char *v54; // [rsp+A4h] [rbp-234h] BYREF
  _BYTE v55[80]; // [rsp+B0h] [rbp-228h] BYREF
  _QWORD v56[2]; // [rsp+100h] [rbp-1D8h] BYREF
  _QWORD v57[22]; // [rsp+110h] [rbp-1C8h] BYREF
  _BYTE v58[192]; // [rsp+1C0h] [rbp-118h] BYREF
  std::_Ref_count_base *v59[2]; // [rsp+280h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    ModernDeployment::Autopilot::Core::NcryptKeyData::NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v56);
    v53 = 0;
    v52 = 0;
    LODWORD(v54) = 0;
    Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(
      (Microsoft::Windows::Autopilot::ScopedTsmLogger *)v55,
      L"TpmKeyWrapper",
      L"LoadAik",
      (int *)&v54);
    v43[0] = &v54;
    v43[1] = &v50;
    v43[2] = &v53;
    v43[3] = &v52;
    v44 = 1;
    v50 = L"OpenProviderForAik";
    *(_OWORD *)v45 = 0;
    std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(v56, v45);
    if ( v45[1] )
      std::_Ref_count_base::_Decref(v45[1]);
    v2 = (NCRYPT_PROV_HANDLE *)wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(v56);
    v3 = NCryptOpenStorageProvider(v2, L"Microsoft Platform Crypto Provider", 0);
    v5 = v3;
    LODWORD(v54) = v3;
    if ( v3 >= 0 )
    {
      pbInput = 0;
      v7 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>,256>(
             v4,
             &pbInput);
      v8 = v7;
      if ( v7 >= 0 )
      {
        v9 = -1;
        do
          ++v9;
        while ( *(_WORD *)&pbInput[2 * v9] );
        v10 = (NCRYPT_PROV_HANDLE *)v56[0];
        if ( v56[0] )
          v11 = *(_QWORD *)v56[0];
        else
          v11 = 0;
        v12 = NCryptSetProperty(v11, L"PCP_ALTERNATE_KEY_STORAGE_LOCATION", pbInput, 2 * v9, 0);
        v15 = v12;
        LODWORD(v54) = v12;
        if ( v12 >= 0 )
        {
          ppEnumState = 0;
          v45[0] = 0;
          v50 = L"EnumeratePossibleKeys";
          for ( i = 0; i < 20; ++i )
          {
            v59[0] = 0;
            v46 = v59;
            ppKeyName = 0;
            v48 = 1;
            if ( v10 )
              v17 = *v10;
            else
              v17 = 0;
            LODWORD(v54) = NCryptEnumKeys(v17, 0, &ppKeyName, &ppEnumState, 0x60u);
            wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>>(&v46);
            v18 = (unsigned int)v54;
            if ( (int)v54 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xDF,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
                (const char *)(unsigned int)v54,
                dwFlagsb);
              wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>::reset(
                v59,
                0);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
              v44 = 0;
              ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v43);
              Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v55);
              ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v56);
              return v18;
            }
            if ( !(unsigned int)_o__wcsicmp(*(_QWORD *)v59[0], L"Windows AIK") )
            {
              wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>::reset(
                v59,
                0);
              goto LABEL_27;
            }
            wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&long NCryptFreeBuffer(void *)>>::reset(
              v59,
              0);
          }
          if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
            McGenEventWrite_EventWriteTransfer(v13, AutopilotMaaLoadAikKeyEnumFailed, v14, 1);
LABEL_27:
          v50 = L"LoadAIK";
          *(_OWORD *)v59 = 0;
          std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(v57, v59);
          if ( v59[1] )
            std::_Ref_count_base::_Decref(v59[1]);
          v19 = (NCRYPT_KEY_HANDLE *)wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(v57);
          if ( v56[0] )
            v20 = *(_QWORD *)v56[0];
          else
            v20 = 0;
          v21 = NCryptOpenKey(v20, v19, L"Windows AIK", 0, 0);
          v22 = v21;
          LODWORD(v54) = v21;
          if ( v21 >= 0 )
          {
            v53 = 1;
            v50 = L"ConfirmAikCert";
            pcbResult = 0;
            v23 = (NCRYPT_HANDLE *)v57[0];
            if ( v57[0] )
              v24 = *(_QWORD *)v57[0];
            else
              v24 = 0;
            Property = NCryptGetProperty(v24, L"SmartCardKeyCertificate", 0, 0, &pcbResult, 0);
            v26 = Property;
            LODWORD(v54) = Property;
            if ( Property >= 0 )
            {
              if ( pcbResult )
              {
                v27 = (std::_Ref_count_base *)operator new[](pcbResult, (const struct std::nothrow_t *)&std::nothrow);
                v59[0] = v27;
                if ( v27 )
                {
                  if ( v23 )
                    v28 = *v23;
                  else
                    v28 = 0;
                  v29 = NCryptGetProperty(v28, L"SmartCardKeyCertificate", (PBYTE)v27, pcbResult, &pcbResult, 0);
                  v30 = v29;
                  if ( v29 >= 0 )
                  {
                    if ( pcbResult )
                    {
                      v52 = 1;
                      ModernDeployment::Autopilot::Core::NcryptKeyData::NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v58);
                      v31 = ModernDeployment::Autopilot::Core::NcryptKeyData::CreateFromKeyHandle(v56, v57, v58);
                      v33 = v31;
                      if ( v31 >= 0 )
                      {
                        v34 = ModernDeployment::Autopilot::Core::TpmKeyWrapper::CreateFromKeyData(
                                (const struct ModernDeployment::Autopilot::Core::NcryptKeyData *)v58,
                                v32,
                                0,
                                a1);
                        v35 = v34;
                        if ( v34 >= 0 )
                        {
                          ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v58);
                          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v59);
                          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
                          v44 = 0;
                          ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v43);
                          Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v55);
                          ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v56);
                          return 0;
                        }
                        else
                        {
                          wil::details::in1diag3::Return_Hr(
                            retaddr,
                            (void *)0x122,
                            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
                            (const char *)(unsigned int)v34,
                            dwFlagse);
                          ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v58);
                          std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v59);
                          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
                          v44 = 0;
                          ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v43);
                          Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v55);
                          ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v56);
                          return v35;
                        }
                      }
                      else
                      {
                        wil::details::in1diag3::Return_Hr(
                          retaddr,
                          (void *)0x120,
                          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
                          (const char *)(unsigned int)v31,
                          dwFlagse);
                        ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v58);
                        std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v59);
                        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
                        v44 = 0;
                        ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v43);
                        Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v55);
                        ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v56);
                        return v33;
                      }
                    }
                    else
                    {
                      v52 = 0;
                      LODWORD(v54) = -2147023727;
                      wil::details::in1diag3::Return_Hr(
                        retaddr,
                        (void *)0x118,
                        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
                        (const char *)0x80070491LL,
                        dwFlagse);
                      std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v59);
                      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
                      v44 = 0;
                      ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v43);
                      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v55);
                      ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v56);
                      return 2147943569LL;
                    }
                  }
                  else
                  {
                    wil::details::in1diag3::Return_Hr(
                      retaddr,
                      (void *)0x113,
                      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
                      (const char *)(unsigned int)v29,
                      dwFlagse);
                    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v59);
                    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
                    v44 = 0;
                    ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v43);
                    Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v55);
                    ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v56);
                    return v30;
                  }
                }
                else
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x10B,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
                    (const char *)0x8007000ELL,
                    dwFlagsd);
                  std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v59);
                  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
                  v44 = 0;
                  ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v43);
                  Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v55);
                  ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v56);
                  return 2147942414LL;
                }
              }
              else
              {
                LODWORD(v54) = -2147023727;
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x106,
                  (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
                  (const char *)0x80070491LL,
                  dwFlagsd);
                wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
                v44 = 0;
                ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v43);
                Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v55);
                ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v56);
                return 2147943569LL;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x102,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
                (const char *)(unsigned int)Property,
                dwFlagsd);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
              v44 = 0;
              ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v43);
              Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v55);
              ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v56);
              return v26;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xF5,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
              (const char *)(unsigned int)v21,
              dwFlagsc);
            wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
            v44 = 0;
            ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v43);
            Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v55);
            ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v56);
            return v22;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xC4,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
            (const char *)(unsigned int)v12,
            dwFlagsa);
          wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
          v44 = 0;
          ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v43);
          Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v55);
          ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v56);
          return v15;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBB,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
          (const char *)(unsigned int)v7,
          dwFlags);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pbInput);
        v44 = 0;
        ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v43);
        Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v55);
        ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v56);
        return v8;
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xB7,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
        (const char *)(unsigned int)v3,
        dwFlags);
      v44 = 0;
      ModernDeployment::Autopilot::Core::TpmKeyWrapper::LoadAik_::_3_::_lambda_1_::operator()(v43);
      Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger((Microsoft::Windows::Autopilot::ScopedTsmLogger *)v55);
      ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)v56);
      return v5;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmkeywrapper.cpp",
      (const char *)0x80004001LL,
      dwFlags);
    return 2147500033LL;
  }
}

```

## disassembly

```asm
0x18013b524  push    rbx
0x18013b526  push    rsi
0x18013b527  push    rdi
0x18013b528  push    r12
0x18013b52a  push    r14
0x18013b52c  push    r15
0x18013b52e  sub     rsp, 2A8h
0x18013b535  mov     rax, cs:__security_cookie
0x18013b53c  xor     rax, rsp
0x18013b53f  mov     [rsp+2D8h+var_48], rax
0x18013b547  mov     r15, rcx
0x18013b54a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18013b551  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18013b556  xor     r12d, r12d
0x18013b559  test    al, al
0x18013b55b  jz      loc_18013BEA7
0x18013b561  lea     rcx, [rsp+2D8h+var_1D8]; this
0x18013b569  call    ??0NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::NcryptKeyData(void)
0x18013b56e  nop
0x18013b56f  mov     [rsp+2D8h+var_237], r12b
0x18013b577  mov     [rsp+2D8h+var_238], r12b
0x18013b57f  mov     dword ptr [rsp+2D8h+var_234], r12d
0x18013b587  lea     rax, sourceString
0x18013b58e  mov     [rsp+2D8h+var_248], rax
0x18013b596  lea     r9, [rsp+2D8h+var_234]; int *
0x18013b59e  lea     r8, aLoadaik; "LoadAik"
0x18013b5a5  lea     rdx, aTpmkeywrapper; "TpmKeyWrapper"
0x18013b5ac  lea     rcx, [rsp+2D8h+var_228]; this
0x18013b5b4  call    ??0ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@PEBG0AEAJ@Z; Microsoft::Windows::Autopilot::ScopedTsmLogger::ScopedTsmLogger(ushort const *,ushort const *,long &)
0x18013b5b9  nop
0x18013b5ba  lea     rax, [rsp+2D8h+var_234]
0x18013b5c2  mov     [rsp+2D8h+var_2A0], rax
0x18013b5c7  lea     rax, [rsp+2D8h+var_248]
0x18013b5cf  mov     [rsp+2D8h+var_298], rax
0x18013b5d4  lea     rax, [rsp+2D8h+var_237]
0x18013b5dc  mov     [rsp+2D8h+var_290], rax
0x18013b5e1  lea     rax, [rsp+2D8h+var_238]
0x18013b5e9  mov     [rsp+2D8h+var_288], rax
0x18013b5ee  mov     [rsp+2D8h+var_280], 1
0x18013b5f3  lea     rax, aOpenproviderfo; "OpenProviderForAik"
0x18013b5fa  mov     [rsp+2D8h+var_248], rax
0x18013b602  xorps   xmm0, xmm0
0x18013b605  movdqu  xmmword ptr [rsp+2D8h+var_278], xmm0
0x18013b60b  lea     rdx, [rsp+2D8h+var_278]
0x18013b610  lea     rcx, [rsp+2D8h+var_1D8]
0x18013b618  call    ??4?$shared_ptr@VEtwProcessingDataEntry@Diagnostics@Autopilot@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry> &&)
0x18013b61d  mov     rcx, [rsp+2D8h+var_278+8]; this
0x18013b622  test    rcx, rcx
0x18013b625  jz      short loc_18013B62C
0x18013b627  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18013b62c  lea     rcx, [rsp+2D8h+var_1D8]
0x18013b634  call    ??$addressof@U?$integral_constant@_K$0A@@wistd@@$0A@@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAPEA_KXZ; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(void)
0x18013b639  xor     r8d, r8d; dwFlags
0x18013b63c  lea     rdx, pszProviderName; "Microsoft Platform Crypto Provider"
0x18013b643  mov     rcx, rax; phProvider
0x18013b646  call    cs:__imp_NCryptOpenStorageProvider
0x18013b64d  nop     dword ptr [rax+rax+00h]
0x18013b652  mov     ebx, eax
0x18013b654  mov     dword ptr [rsp+2D8h+var_234], eax
0x18013b65b  test    eax, eax
0x18013b65d  jns     short loc_18013B6AE
0x18013b65f  mov     rcx, [rsp+2D8h]; this
0x18013b667  mov     r9d, eax; char *
0x18013b66a  lea     r8, aOnecoreuapAdmi_127; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013b671  mov     edx, 0B7h; void *
0x18013b676  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b67b  nop
0x18013b67c  mov     [rsp+2D8h+var_280], r12b
0x18013b681  lea     rcx, [rsp+2D8h+var_2A0]
0x18013b686  call    _ModernDeployment__Autopilot__Core__TpmKeyWrapper__LoadAik____3____lambda_1___operator__
0x18013b68b  nop
0x18013b68c  lea     rcx, [rsp+2D8h+var_228]; this
0x18013b694  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x18013b699  nop
0x18013b69a  lea     rcx, [rsp+2D8h+var_1D8]; this
0x18013b6a2  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x18013b6a7  mov     eax, ebx
0x18013b6a9  jmp     loc_18013BED3
0x18013b6ae  mov     [rsp+2D8h+pbInput], r12
0x18013b6b3  lea     rdx, [rsp+2D8h+pbInput]
0x18013b6b8  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18013b6bd  mov     ebx, eax
0x18013b6bf  test    eax, eax
0x18013b6c1  jns     short loc_18013B71D
0x18013b6c3  mov     rcx, [rsp+2D8h]; this
0x18013b6cb  mov     r9d, eax; char *
0x18013b6ce  lea     r8, aOnecoreuapAdmi_127; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013b6d5  mov     edx, 0BBh; void *
0x18013b6da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b6df  nop
0x18013b6e0  lea     rcx, [rsp+2D8h+pbInput]
0x18013b6e5  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18013b6ea  nop
0x18013b6eb  mov     [rsp+2D8h+var_280], r12b
0x18013b6f0  lea     rcx, [rsp+2D8h+var_2A0]
0x18013b6f5  call    _ModernDeployment__Autopilot__Core__TpmKeyWrapper__LoadAik____3____lambda_1___operator__
0x18013b6fa  nop
0x18013b6fb  lea     rcx, [rsp+2D8h+var_228]; this
0x18013b703  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x18013b708  nop
0x18013b709  lea     rcx, [rsp+2D8h+var_1D8]; this
0x18013b711  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x18013b716  mov     eax, ebx
0x18013b718  jmp     loc_18013BED3
0x18013b71d  mov     r8, [rsp+2D8h+pbInput]; pbInput
0x18013b722  or      rax, 0FFFFFFFFFFFFFFFFh
0x18013b726  inc     rax
0x18013b729  cmp     [r8+rax*2], r12w
0x18013b72e  jnz     short loc_18013B726
0x18013b730  lea     r9, [rax+rax]; cbInput
0x18013b734  mov     rdi, [rsp+2D8h+var_1D8]
0x18013b73c  test    rdi, rdi
0x18013b73f  jz      short loc_18013B746
0x18013b741  mov     rcx, [rdi]
0x18013b744  jmp     short loc_18013B749
0x18013b746  mov     rcx, r12; hObject
0x18013b749  mov     [rsp+2D8h+dwFlags], r12d; int
0x18013b74e  lea     rdx, aPcpAlternateKe; "PCP_ALTERNATE_KEY_STORAGE_LOCATION"
0x18013b755  call    cs:__imp_NCryptSetProperty
0x18013b75c  nop     dword ptr [rax+rax+00h]
0x18013b761  mov     ebx, eax
0x18013b763  mov     dword ptr [rsp+2D8h+var_234], eax
0x18013b76a  test    eax, eax
0x18013b76c  jns     short loc_18013B7C8
0x18013b76e  mov     rcx, [rsp+2D8h]; this
0x18013b776  mov     r9d, eax; char *
0x18013b779  lea     r8, aOnecoreuapAdmi_127; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013b780  mov     edx, 0C4h; void *
0x18013b785  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b78a  nop
0x18013b78b  lea     rcx, [rsp+2D8h+pbInput]
0x18013b790  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18013b795  nop
0x18013b796  mov     [rsp+2D8h+var_280], r12b
0x18013b79b  lea     rcx, [rsp+2D8h+var_2A0]
0x18013b7a0  call    _ModernDeployment__Autopilot__Core__TpmKeyWrapper__LoadAik____3____lambda_1___operator__
0x18013b7a5  nop
0x18013b7a6  lea     rcx, [rsp+2D8h+var_228]; this
0x18013b7ae  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x18013b7b3  nop
0x18013b7b4  lea     rcx, [rsp+2D8h+var_1D8]; this
0x18013b7bc  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x18013b7c1  mov     eax, ebx
0x18013b7c3  jmp     loc_18013BED3
0x18013b7c8  mov     [rsp+2D8h+ppEnumState], r12
0x18013b7d0  mov     [rsp+2D8h+var_278], r12
0x18013b7d5  lea     rax, aEnumeratepossi; "EnumeratePossibleKeys"
0x18013b7dc  mov     [rsp+2D8h+var_248], rax
0x18013b7e4  mov     esi, r12d
0x18013b7e7  cmp     esi, 14h
0x18013b7ea  jge     loc_18013B909
0x18013b7f0  mov     [rsp+2D8h+var_58], r12
0x18013b7f8  lea     rax, [rsp+2D8h+var_58]
0x18013b800  mov     [rsp+2D8h+var_268], rax
0x18013b805  mov     [rsp+2D8h+ppKeyName], r12
0x18013b80a  mov     [rsp+2D8h+var_258], 1
0x18013b812  test    rdi, rdi
0x18013b815  jz      short loc_18013B81C
0x18013b817  mov     rcx, [rdi]
0x18013b81a  jmp     short loc_18013B81F
0x18013b81c  mov     rcx, r12; hProvider
0x18013b81f  mov     [rsp+2D8h+dwFlags], 60h ; '`'; int
0x18013b827  lea     r9, [rsp+2D8h+ppEnumState]; ppEnumState
0x18013b82f  lea     r8, [rsp+2D8h+ppKeyName]; ppKeyName
0x18013b834  xor     edx, edx; pszScope
0x18013b836  call    cs:__imp_NCryptEnumKeys
0x18013b83d  nop     dword ptr [rax+rax+00h]
0x18013b842  mov     dword ptr [rsp+2D8h+var_234], eax
0x18013b849  lea     rcx, [rsp+2D8h+var_268]
0x18013b84e  call    ??1?$out_param_t@V?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>::~out_param_t<wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>>(void)
0x18013b853  mov     r14d, dword ptr [rsp+2D8h+var_234]
0x18013b85b  test    r14d, r14d
0x18013b85e  jns     short loc_18013B8CA
0x18013b860  mov     rcx, [rsp+2D8h]; this
0x18013b868  mov     r9d, r14d; char *
0x18013b86b  lea     r8, aOnecoreuapAdmi_127; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013b872  mov     edx, 0DFh; void *
0x18013b877  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b87c  xor     edx, edx
0x18013b87e  lea     rcx, [rsp+2D8h+var_58]
0x18013b886  call    ?reset@?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@QEAAXPEAUNCryptKeyName@@@Z; wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>::reset(NCryptKeyName *)
0x18013b88b  nop
0x18013b88c  lea     rcx, [rsp+2D8h+pbInput]
0x18013b891  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18013b896  nop
0x18013b897  mov     [rsp+2D8h+var_280], r12b
0x18013b89c  lea     rcx, [rsp+2D8h+var_2A0]
0x18013b8a1  call    _ModernDeployment__Autopilot__Core__TpmKeyWrapper__LoadAik____3____lambda_1___operator__
0x18013b8a6  nop
0x18013b8a7  lea     rcx, [rsp+2D8h+var_228]; this
0x18013b8af  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x18013b8b4  nop
0x18013b8b5  lea     rcx, [rsp+2D8h+var_1D8]; this
0x18013b8bd  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x18013b8c2  mov     eax, r14d
0x18013b8c5  jmp     loc_18013BED3
0x18013b8ca  lea     rdx, pszKeyName; "Windows AIK"
0x18013b8d1  mov     rcx, [rsp+2D8h+var_58]
0x18013b8d9  mov     rcx, [rcx]
0x18013b8dc  call    cs:__imp__o__wcsicmp
0x18013b8e3  nop     dword ptr [rax+rax+00h]
0x18013b8e8  xor     edx, edx
0x18013b8ea  lea     rcx, [rsp+2D8h+var_58]
0x18013b8f2  test    eax, eax
0x18013b8f4  jnz     short loc_18013B8FD
0x18013b8f6  call    ?reset@?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@QEAAXPEAUNCryptKeyName@@@Z; wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>::reset(NCryptKeyName *)
0x18013b8fb  jmp     short loc_18013B931
0x18013b8fd  inc     esi
0x18013b8ff  call    ?reset@?$unique_ptr@UNCryptKeyName@@U?$function_deleter@P6AJPEAX@Z$1?NCryptFreeBuffer@@YAJ0@Z@wil@@@wistd@@QEAAXPEAUNCryptKeyName@@@Z; wistd::unique_ptr<NCryptKeyName,wil::function_deleter<long (*)(void *),&NCryptFreeBuffer(void *)>>::reset(NCryptKeyName *)
0x18013b904  jmp     loc_18013B7E7
0x18013b909  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18013b910  jz      short loc_18013B931
0x18013b912  lea     rax, [rsp+2D8h+var_58]
0x18013b91a  mov     qword ptr [rsp+2D8h+dwFlags], rax
0x18013b91f  mov     r9d, 1
0x18013b925  lea     rdx, AutopilotMaaLoadAikKeyEnumFailed
0x18013b92c  call    McGenEventWrite_EventWriteTransfer
0x18013b931  lea     rax, aLoadaik_0; "LoadAIK"
0x18013b938  mov     [rsp+2D8h+var_248], rax
0x18013b940  xorps   xmm0, xmm0
0x18013b943  movdqu  xmmword ptr [rsp+2D8h+var_58], xmm0
0x18013b94c  lea     rdx, [rsp+2D8h+var_58]
0x18013b954  lea     rcx, [rsp+2D8h+var_1C8]
0x18013b95c  call    ??4?$shared_ptr@VEtwProcessingDataEntry@Diagnostics@Autopilot@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry> &&)
0x18013b961  mov     rcx, [rsp+2D8h+var_58+8]; this
0x18013b969  test    rcx, rcx
0x18013b96c  jz      short loc_18013B973
0x18013b96e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18013b973  lea     rcx, [rsp+2D8h+var_1C8]
0x18013b97b  call    ??$addressof@U?$integral_constant@_K$0A@@wistd@@$0A@@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAPEA_KXZ; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(void)
0x18013b980  mov     rcx, [rsp+2D8h+var_1D8]
0x18013b988  test    rcx, rcx
0x18013b98b  jz      short loc_18013B992
0x18013b98d  mov     rcx, [rcx]
0x18013b990  jmp     short loc_18013B995
0x18013b992  mov     rcx, r12; hProvider
0x18013b995  mov     [rsp+2D8h+dwFlags], r12d; int
0x18013b99a  xor     r9d, r9d; dwLegacyKeySpec
0x18013b99d  lea     r8, pszKeyName; "Windows AIK"
0x18013b9a4  mov     rdx, rax; phKey
0x18013b9a7  call    cs:__imp_NCryptOpenKey
0x18013b9ae  nop     dword ptr [rax+rax+00h]
0x18013b9b3  mov     edi, eax
0x18013b9b5  mov     dword ptr [rsp+2D8h+var_234], eax
0x18013b9bc  test    eax, eax
0x18013b9be  jns     short loc_18013BA1A
0x18013b9c0  mov     rcx, [rsp+2D8h]; this
0x18013b9c8  mov     r9d, eax; char *
0x18013b9cb  lea     r8, aOnecoreuapAdmi_127; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013b9d2  mov     edx, 0F5h; void *
0x18013b9d7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013b9dc  nop
0x18013b9dd  lea     rcx, [rsp+2D8h+pbInput]
0x18013b9e2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18013b9e7  nop
0x18013b9e8  mov     [rsp+2D8h+var_280], r12b
0x18013b9ed  lea     rcx, [rsp+2D8h+var_2A0]
0x18013b9f2  call    _ModernDeployment__Autopilot__Core__TpmKeyWrapper__LoadAik____3____lambda_1___operator__
0x18013b9f7  nop
0x18013b9f8  lea     rcx, [rsp+2D8h+var_228]; this
0x18013ba00  call    ??1ScopedTsmLogger@Autopilot@Windows@Microsoft@@QEAA@XZ; Microsoft::Windows::Autopilot::ScopedTsmLogger::~ScopedTsmLogger(void)
0x18013ba05  nop
0x18013ba06  lea     rcx, [rsp+2D8h+var_1D8]; this
0x18013ba0e  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x18013ba13  mov     eax, edi
0x18013ba15  jmp     loc_18013BED3
0x18013ba1a  mov     [rsp+2D8h+var_237], 1
0x18013ba22  lea     rax, aConfirmaikcert; "ConfirmAikCert"
0x18013ba29  mov     [rsp+2D8h+var_248], rax
0x18013ba31  mov     [rsp+2D8h+pcbResult], r12d
0x18013ba39  mov     rdi, [rsp+2D8h+var_1C8]
0x18013ba41  test    rdi, rdi
0x18013ba44  jz      short loc_18013BA4B
0x18013ba46  mov     rcx, [rdi]
0x18013ba49  jmp     short loc_18013BA4E
0x18013ba4b  mov     rcx, r12; hObject
0x18013ba4e  mov     [rsp+2D8h+var_2B0], r12d; dwFlags
0x18013ba53  lea     rax, [rsp+2D8h+pcbResult]
0x18013ba5b  mov     qword ptr [rsp+2D8h+dwFlags], rax; int
0x18013ba60  xor     r9d, r9d; cbOutput
0x18013ba63  xor     r8d, r8d; pbOutput
0x18013ba66  lea     rdx, aSmartcardkeyce; "SmartCardKeyCertificate"
0x18013ba6d  call    cs:__imp_NCryptGetProperty
0x18013ba74  nop     dword ptr [rax+rax+00h]
0x18013ba79  mov     esi, eax
0x18013ba7b  mov     dword ptr [rsp+2D8h+var_234], eax
0x18013ba82  test    eax, eax
0x18013ba84  jns     short loc_18013BAE0
0x18013ba86  mov     rcx, [rsp+2D8h]; this
0x18013ba8e  mov     r9d, eax; char *
0x18013ba91  lea     r8, aOnecoreuapAdmi_127; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013ba98  mov     edx, 102h; void *
0x18013ba9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013baa2  nop
0x18013baa3  lea     rcx, [rsp+2D8h+pbInput]
0x18013baa8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x18013baad  nop
0x18013baae  mov     [rsp+2D8h+var_280], r12b
0x18013bab3  lea     rcx, [rsp+2D8h+var_2A0]
0x18013bab8  call    _ModernDeployment__Autopilot__Core__TpmKeyWrapper__LoadAik____3____lambda_1___operator__
  ... truncated ...
```
