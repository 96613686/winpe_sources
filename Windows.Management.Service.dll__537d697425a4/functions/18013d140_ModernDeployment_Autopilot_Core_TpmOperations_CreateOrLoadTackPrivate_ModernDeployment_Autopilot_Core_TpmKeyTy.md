# ModernDeployment::Autopilot::Core::TpmOperations::CreateOrLoadTackPrivate(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType,bool &,ModernDeployment::Autopilot::Core::TpmKeyWrapper &)

- ea: `0x18013d140`
- end: `0x18013e0df`
- name: `?CreateOrLoadTackPrivate@TpmOperations@Core@Autopilot@ModernDeployment@@QEAAJW4IdkKeyType@TpmKeyTypes@234@AEA_NAEAVTpmKeyWrapper@234@@Z`
- size: `3999`
- prototype: `int __high(enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType, bool *, struct ModernDeployment::Autopilot::Core::TpmKeyWrapper *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18013cf84`

## callees

- `0x18000b8f0`
- `0x180067e34`
- `0x180067e54`
- `0x18006ee48`
- `0x180077c04`
- `0x180077de0`
- `0x180080bac`
- `0x180080c10`
- `0x180081f38`
- `0x18008aea8`
- `0x18008d290`
- `0x180094ce0`
- `0x18013a968`
- `0x18013a9e4`
- `0x18013aaec`
- `0x18013ac44`
- `0x18013d140`
- `0x18013ef70`
- `0x1801401f4`
- `0x1801404d0`
- `0x180140560`
- `0x1801407d8`
- `0x1801481a0`
- `0x1801482b4`
- `0x180148354`
- `0x1801483dc`
- `0x180162ac4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18013da38`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x18013da38`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18013dac7`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x18013dac7`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18013d9a1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18013d9a1`
- `ncrypt!NCryptOpenKey` at `0x18013d412`
- `ncrypt!NCryptOpenKey` at `0x18013d412`
- `ncrypt!NCryptSetProperty` at `0x18013d7ff`
- `ncrypt!NCryptSetProperty` at `0x18013d889`
- `ncrypt!NCryptSetProperty` at `0x18013daf9`
- `ncrypt!NCryptSetProperty` at `0x18013dc14`
- `ncrypt!NCryptSetProperty` at `0x18013ddb7`
- `ncrypt!NCryptSetProperty` at `0x18013d7ff`
- `ncrypt!NCryptSetProperty` at `0x18013d889`
- `ncrypt!NCryptSetProperty` at `0x18013daf9`
- `ncrypt!NCryptSetProperty` at `0x18013dc14`
- `ncrypt!NCryptSetProperty` at `0x18013ddb7`
- `ncrypt!NCryptCreatePersistedKey` at `0x18013d712`
- `ncrypt!NCryptCreatePersistedKey` at `0x18013d712`
- `ncrypt!NCryptFinalizeKey` at `0x18013de50`
- `ncrypt!NCryptFinalizeKey` at `0x18013de50`

## string_xrefs

- `0x18013d19d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013d1ed`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013d21d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013d276`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013d2cd`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013d4b4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013d530`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013d5ed`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013d64b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013d72f`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013d791`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013d81c`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013d8a6`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013d928`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013d9b9`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013da50`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013db16`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013dba1`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013dc31`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013dcb6`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013dd36`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013ddd4`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013de6d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013df40`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013dfd2`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013e09a`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013daf2`: `Security Descr`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall ModernDeployment::Autopilot::Core::TpmOperations::CreateOrLoadTackPrivate(
        __int64 a1,
        WINBOOL a2,
        _BYTE *a3,
        struct ModernDeployment::Autopilot::Core::TpmKeyWrapper *a4)
{
  unsigned int v6; // edi
  _QWORD *v9; // rax
  int TackKeyType; // eax
  unsigned int v11; // ebx
  __m128i si128; // xmm6
  int AlgorithmIdFromKeyType; // eax
  unsigned int v14; // ebx
  int TackKeyName; // eax
  unsigned int v16; // ebx
  NCRYPT_PROV_HANDLE **v17; // rax
  NCRYPT_PROV_HANDLE *v18; // rdx
  NCRYPT_PROV_HANDLE *v19; // rdx
  const WCHAR *v20; // rbx
  NCRYPT_KEY_HANDLE *v21; // rax
  NCRYPT_PROV_HANDLE v22; // rcx
  SECURITY_STATUS v23; // eax
  unsigned int v24; // ebx
  int v25; // eax
  bool v26; // dl
  unsigned int v27; // ebx
  int v28; // eax
  unsigned int v29; // ebx
  int IsEccKeyType; // eax
  unsigned int v31; // ebx
  const WCHAR *v32; // rbx
  const WCHAR *v33; // rsi
  NCRYPT_KEY_HANDLE *v34; // rax
  NCRYPT_PROV_HANDLE v35; // rcx
  SECURITY_STATUS PersistedKey; // eax
  unsigned int v37; // ebx
  int TackKeyUsage; // eax
  unsigned int v39; // ebx
  NCRYPT_HANDLE v40; // rcx
  SECURITY_STATUS v41; // eax
  unsigned int v42; // ebx
  NCRYPT_HANDLE v43; // rcx
  SECURITY_STATUS v44; // eax
  unsigned int v45; // ebx
  int TackSecurityDescriptor; // eax
  unsigned int v47; // ebx
  const WCHAR *v48; // rax
  const char *v49; // r9
  unsigned int LastError; // ebx
  const char *v51; // r9
  unsigned int v52; // ebx
  BYTE *v53; // rsi
  DWORD v54; // ebx
  DWORD SecurityDescriptorLength; // eax
  NCRYPT_HANDLE v56; // rcx
  SECURITY_STATUS v57; // eax
  unsigned int v58; // ebx
  int KeyLengthFromKeyType; // eax
  unsigned int v60; // ebx
  NCRYPT_HANDLE v61; // rcx
  SECURITY_STATUS v62; // eax
  unsigned int v63; // ebx
  int RsaSigningSchemeHashAlgorithm; // eax
  unsigned int v65; // ebx
  int HashAlgorithmIdFromAlgorithmName; // eax
  unsigned int v67; // ebx
  NCRYPT_HANDLE v68; // rcx
  SECURITY_STATUS v69; // eax
  unsigned int v70; // ebx
  NCRYPT_KEY_HANDLE v71; // rcx
  SECURITY_STATUS v72; // eax
  unsigned int v73; // ebx
  int v74; // eax
  bool v75; // dl
  unsigned int v76; // ebx
  int v77; // eax
  unsigned int v78; // ebx
  int dwFlags; // [rsp+20h] [rbp-218h]
  int dwFlagsa; // [rsp+20h] [rbp-218h]
  int dwFlagsb; // [rsp+20h] [rbp-218h]
  int dwFlagsc; // [rsp+20h] [rbp-218h]
  int dwFlagsd; // [rsp+20h] [rbp-218h]
  int dwFlagse; // [rsp+20h] [rbp-218h]
  int dwFlagsf; // [rsp+20h] [rbp-218h]
  int dwFlagsg; // [rsp+20h] [rbp-218h]
  char v87[8]; // [rsp+30h] [rbp-208h] BYREF
  WINBOOL bSaclPresent; // [rsp+38h] [rbp-200h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+40h] [rbp-1F8h] BYREF
  BYTE v90[4]; // [rsp+44h] [rbp-1F4h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-1F0h] BYREF
  _OWORD v92[2]; // [rsp+50h] [rbp-1E8h] BYREF
  _OWORD v93[2]; // [rsp+70h] [rbp-1C8h] BYREF
  PACL pSacl[2]; // [rsp+90h] [rbp-1A8h] BYREF
  __m128i v95; // [rsp+A0h] [rbp-198h]
  BYTE pbInput[4]; // [rsp+B0h] [rbp-188h] BYREF
  __int128 v97; // [rsp+B8h] [rbp-180h] BYREF
  __int64 v98; // [rsp+C8h] [rbp-170h]
  __int64 v99; // [rsp+D0h] [rbp-168h]
  __int128 v100; // [rsp+D8h] [rbp-160h] BYREF
  __m128i v101; // [rsp+E8h] [rbp-150h]
  NCRYPT_PROV_HANDLE *v102; // [rsp+100h] [rbp-138h] BYREF
  NCRYPT_PROV_HANDLE *v103; // [rsp+108h] [rbp-130h]
  _QWORD v104[2]; // [rsp+110h] [rbp-128h] BYREF
  _BYTE v105[32]; // [rsp+120h] [rbp-118h] BYREF
  _BYTE v106[32]; // [rsp+140h] [rbp-F8h] BYREF
  char v107[32]; // [rsp+160h] [rbp-D8h] BYREF
  _BYTE v108[56]; // [rsp+180h] [rbp-B8h] BYREF
  unsigned int v109; // [rsp+1B8h] [rbp-80h]
  char v110; // [rsp+1BCh] [rbp-7Ch]
  int v111[4]; // [rsp+1C0h] [rbp-78h] BYREF
  __m128i v112; // [rsp+1D0h] [rbp-68h]
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  v6 = a2;
  bSaclPresent = a2;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl'::`2'::impl) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF7,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
      (const char *)0x80004001LL,
      dwFlags);
    return 2147500033LL;
  }
  v9 = *(_QWORD **)(a1 + 240);
  if ( v9 && *v9 )
  {
    if ( !v6 )
    {
      TackKeyType = ModernDeployment::Autopilot::Core::AutopilotConfig::GetTackKeyType((enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType *)&bSaclPresent);
      v11 = TackKeyType;
      if ( TackKeyType < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFD,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
          (const char *)(unsigned int)TackKeyType,
          dwFlags);
        return v11;
      }
      v6 = bSaclPresent;
      if ( !bSaclPresent )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xFF,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
          (const char *)0x80070057LL,
          dwFlags);
        return 2147942487LL;
      }
    }
    v92[0] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    v92[1] = si128;
    LOWORD(v92[0]) = 0;
    AlgorithmIdFromKeyType = ModernDeployment::Autopilot::Core::TpmKeyTypes::GetAlgorithmIdFromKeyType(
                               &bSaclPresent,
                               v92,
                               &bSaclDefaulted);
    v14 = AlgorithmIdFromKeyType;
    if ( AlgorithmIdFromKeyType < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x103,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
        (const char *)(unsigned int)AlgorithmIdFromKeyType,
        dwFlags);
      std::wstring::_Tidy_deallocate(v92);
      return v14;
    }
    v93[0] = 0;
    v93[1] = si128;
    LOWORD(v93[0]) = 0;
    TackKeyName = ModernDeployment::Autopilot::Core::TpmOperations::GetTackKeyName(v6, v93);
    v16 = TackKeyName;
    if ( TackKeyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x106,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
        (const char *)(unsigned int)TackKeyName,
        dwFlags);
      std::wstring::_Tidy_deallocate(v93);
      std::wstring::_Tidy_deallocate(v92);
      return v16;
    }
    ModernDeployment::Autopilot::Core::NcryptKeyData::NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
    std::wstring::operator=(v106, v92);
    v109 = v6;
    std::wstring::assign(v107, L"SHA256");
    v17 = (NCRYPT_PROV_HANDLE **)std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(
                                   pSacl,
                                   a1 + 240);
    v18 = *v17;
    *v17 = v102;
    v102 = v18;
    v19 = v17[1];
    v17[1] = v103;
    v103 = v19;
    if ( pSacl[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)pSacl[1]);
    std::wstring::operator=(v105, v93);
    v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v105);
    *(_OWORD *)pSacl = 0;
    std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(v104, pSacl);
    if ( pSacl[1] )
      std::_Ref_count_base::_Decref((std::_Ref_count_base *)pSacl[1]);
    v21 = (NCRYPT_KEY_HANDLE *)wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(v104);
    if ( v102 )
      v22 = *v102;
    else
      v22 = 0;
    v23 = NCryptOpenKey(v22, v21, v20, 0, 0x40u);
    v24 = v23;
    if ( v23 )
    {
      if ( v23 == -2146893802 )
      {
        v87[0] = 0;
        IsEccKeyType = ModernDeployment::Autopilot::Core::TpmKeyTypes::IsEccKeyType(v6, v87);
        v31 = IsEccKeyType;
        if ( IsEccKeyType < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x135,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
            (const char *)(unsigned int)IsEccKeyType,
            dwFlagsa);
          ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
          std::wstring::_Tidy_deallocate(v93);
          std::wstring::_Tidy_deallocate(v92);
          return v31;
        }
        v32 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v105);
        v33 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v106);
        *(_OWORD *)pSacl = 0;
        std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(v104, pSacl);
        if ( pSacl[1] )
          std::_Ref_count_base::_Decref((std::_Ref_count_base *)pSacl[1]);
        v34 = (NCRYPT_KEY_HANDLE *)wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(v104);
        if ( v102 )
          v35 = *v102;
        else
          v35 = 0;
        PersistedKey = NCryptCreatePersistedKey(v35, v34, v33, v32, 0, 0xE0u);
        v37 = PersistedKey;
        if ( PersistedKey < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x13E,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
            (const char *)(unsigned int)PersistedKey,
            dwFlagsc);
          ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
          std::wstring::_Tidy_deallocate(v93);
          std::wstring::_Tidy_deallocate(v92);
          return v37;
        }
        *(_DWORD *)pbInput = 0;
        TackKeyUsage = ModernDeployment::Autopilot::Core::AutopilotConfig::GetTackKeyUsage((unsigned int *)pbInput);
        v39 = TackKeyUsage;
        if ( TackKeyUsage < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x141,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
            (const char *)(unsigned int)TackKeyUsage,
            dwFlagsc);
          ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
          std::wstring::_Tidy_deallocate(v93);
          std::wstring::_Tidy_deallocate(v92);
          return v39;
        }
        if ( v104[0] )
          v40 = *(_QWORD *)v104[0];
        else
          v40 = 0;
        v41 = NCryptSetProperty(v40, L"PCP_KEY_USAGE_POLICY", pbInput, 4u, 0);
        v42 = v41;
        if ( v41 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x14B,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
            (const char *)(unsigned int)v41,
            dwFlagsd);
          ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
          std::wstring::_Tidy_deallocate(v93);
          std::wstring::_Tidy_deallocate(v92);
          return v42;
        }
        *(_DWORD *)v90 = 0xFFFFFF;
        if ( v104[0] )
          v43 = *(_QWORD *)v104[0];
        else
          v43 = 0;
        v44 = NCryptSetProperty(v43, L"Key Usage", v90, 4u, 0);
        v45 = v44;
        if ( v44 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x154,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
            (const char *)(unsigned int)v44,
            dwFlagse);
          ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
          std::wstring::_Tidy_deallocate(v93);
          std::wstring::_Tidy_deallocate(v92);
          return v45;
        }
        v97 = 0;
        v98 = 0;
        v99 = 7;
        LOWORD(v97) = 0;
        TackSecurityDescriptor = ModernDeployment::Autopilot::Core::AutopilotConfig::GetTackSecurityDescriptor(&v97);
        v47 = TackSecurityDescriptor;
        if ( TackSecurityDescriptor < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x158,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
            (const char *)(unsigned int)TackSecurityDescriptor,
            dwFlagse);
          std::wstring::_Tidy_deallocate(&v97);
          ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
          std::wstring::_Tidy_deallocate(v93);
          std::wstring::_Tidy_deallocate(v92);
          return v47;
        }
        if ( v98 )
        {
          SecurityDescriptor = 0;
          v48 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v97);
          if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v48, 1u, &SecurityDescriptor, 0) )
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0x161,
                          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
                          v49);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&SecurityDescriptor);
            std::wstring::_Tidy_deallocate(&v97);
            ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
            std::wstring::_Tidy_deallocate(v93);
            std::wstring::_Tidy_deallocate(v92);
            return LastError;
          }
          pSacl[0] = 0;
          bSaclPresent = 0;
          bSaclDefaulted = 0;
          if ( !GetSecurityDescriptorSacl(SecurityDescriptor, &bSaclPresent, pSacl, &bSaclDefaulted) )
          {
            v52 = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x16A,
                    (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
                    v51);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&SecurityDescriptor);
            std::wstring::_Tidy_deallocate(&v97);
            ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
            std::wstring::_Tidy_deallocate(v93);
            std::wstring::_Tidy_deallocate(v92);
            return v52;
          }
          v53 = (BYTE *)SecurityDescriptor;
          if ( !bSaclPresent || (v54 = 12, !pSacl[0]) )
            v54 = 4;
          SecurityDescriptorLength = GetSecurityDescriptorLength(SecurityDescriptor);
          if ( v104[0] )
            v56 = *(_QWORD *)v104[0];
          else
            v56 = 0;
          v57 = NCryptSetProperty(v56, L"Security Descr", v53, SecurityDescriptorLength, v54);
          v58 = v57;
          if ( v57 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x180,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
              (const char *)(unsigned int)v57,
              dwFlagse);
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&SecurityDescriptor);
            std::wstring::_Tidy_deallocate(&v97);
            ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
            std::wstring::_Tidy_deallocate(v93);
            std::wstring::_Tidy_deallocate(v92);
            return v58;
          }
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&SecurityDescriptor);
        }
        if ( !v87[0] )
        {
          bSaclPresent = 0;
          KeyLengthFromKeyType = ModernDeployment::Autopilot::Core::TpmKeyTypes::GetKeyLengthFromKeyType(
                                   v6,
                                   &bSaclPresent);
          v60 = KeyLengthFromKeyType;
          if ( KeyLengthFromKeyType < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x187,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
              (const char *)(unsigned int)KeyLengthFromKeyType,
              dwFlagse);
            std::wstring::_Tidy_deallocate(&v97);
            ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
            std::wstring::_Tidy_deallocate(v93);
            std::wstring::_Tidy_deallocate(v92);
            return v60;
          }
          if ( v104[0] )
            v61 = *(_QWORD *)v104[0];
          else
            v61 = 0;
          v62 = NCryptSetProperty(v61, L"Length", (PBYTE)&bSaclPresent, 4u, 0);
          v63 = v62;
          if ( v62 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x18E,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
              (const char *)(unsigned int)v62,
              dwFlagsf);
            std::wstring::_Tidy_deallocate(&v97);
            ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
            std::wstring::_Tidy_deallocate(v93);
            std::wstring::_Tidy_deallocate(v92);
            return v63;
          }
          *(_OWORD *)pSacl = 0;
          v95 = si128;
          LOWORD(pSacl[0]) = 0;
          RsaSigningSchemeHashAlgorithm = ModernDeployment::Autopilot::Core::AutopilotConfig::GetRsaSigningSchemeHashAlgorithm(pSacl);
          v65 = RsaSigningSchemeHashAlgorithm;
          if ( RsaSigningSchemeHashAlgorithm < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x192,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
              (const char *)(unsigned int)RsaSigningSchemeHashAlgorithm,
              dwFlagsf);
            std::wstring::_Tidy_deallocate(pSacl);
            std::wstring::_Tidy_deallocate(&v97);
            ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
            std::wstring::_Tidy_deallocate(v93);
            std::wstring::_Tidy_deallocate(v92);
            return v65;
          }
          bSaclDefaulted = 0;
          HashAlgorithmIdFromAlgorithmName = ModernDeployment::Autopilot::Core::TpmKeyTypes::GetHashAlgorithmIdFromAlgorithmName(
                                               pSacl,
                                               &bSaclDefaulted);
          v67 = HashAlgorithmIdFromAlgorithmName;
          if ( HashAlgorithmIdFromAlgorithmName < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x195,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
              (const char *)(unsigned int)HashAlgorithmIdFromAlgorithmName,
              dwFlagsf);
            std::wstring::_Tidy_deallocate(pSacl);
            std::wstring::_Tidy_deallocate(&v97);
            ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
            std::wstring::_Tidy_deallocate(v93);
            std::wstring::_Tidy_deallocate(v92);
            return v67;
          }
          if ( v104[0] )
            v68 = *(_QWORD *)v104[0];
          else
            v68 = 0;
          v69 = NCryptSetProperty(v68, L"PCP_RSA_SCHEME_HASH_ALG", (PBYTE)&bSaclDefaulted, 4u, 0);
          v70 = v69;
          if ( v69 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x19C,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
              (const char *)(unsigned int)v69,
              dwFlagse);
            std::wstring::_Tidy_deallocate(pSacl);
            std::wstring::_Tidy_deallocate(&v97);
            ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
            std::wstring::_Tidy_deallocate(v93);
            std::wstring::_Tidy_deallocate(v92);
            return v70;
          }
          std::wstring::_Tidy_deallocate(pSacl);
        }
        if ( v104[0] )
          v71 = *(_QWORD *)v104[0];
        else
          v71 = 0;
        v72 = NCryptFinalizeKey(v71, 0);
        v73 = v72;
        if ( v72 >= 0 )
        {
          v100 = 0;
          v101 = si128;
          LOWORD(v100) = 0;
          *(_OWORD *)v111 = 0;
          v112 = si128;
          LOWORD(v111[0]) = 0;
          bSaclDefaulted = 0;
          v74 = ModernDeployment::Autopilot::Core::CryptoWrappers::ExportTpmKeyBlobFromSrkBasedKey(
                  (unsigned int)v104,
                  (unsigned int)v106,
                  (unsigned int)&v100,
                  (unsigned int)v108,
                  (__int64)v111,
                  (__int64)&bSaclDefaulted);
          v76 = v74;
          if ( v74 >= 0 )
          {
            v110 = 1;
            v77 = ModernDeployment::Autopilot::Core::TpmKeyWrapper::CreateFromKeyData(
                    (const struct ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102,
                    v75,
                    0,
                    a4);
            v78 = v77;
            if ( v77 >= 0 )
            {
              *a3 = 1;
              std::wstring::_Tidy_deallocate(v111);
              std::wstring::_Tidy_deallocate(&v100);
              std::wstring::_Tidy_deallocate(&v97);
              ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
              std::wstring::_Tidy_deallocate(v93);
              std::wstring::_Tidy_deallocate(v92);
              return 0;
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1AF,
                (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
                (const char *)(unsigned int)v77,
                dwFlagsg);
              std::wstring::_Tidy_deallocate(v111);
              std::wstring::_Tidy_deallocate(&v100);
              std::wstring::_Tidy_deallocate(&v97);
              ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
              std::wstring::_Tidy_deallocate(v93);
              std::wstring::_Tidy_deallocate(v92);
              return v78;
            }
          }
          else
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1AB,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
              (const char *)(unsigned int)v74,
              dwFlagsg);
            std::wstring::_Tidy_deallocate(v111);
            std::wstring::_Tidy_deallocate(&v100);
            std::wstring::_Tidy_deallocate(&v97);
            ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
            std::wstring::_Tidy_deallocate(v93);
            std::wstring::_Tidy_deallocate(v92);
            return v76;
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1A0,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
            (const char *)(unsigned int)v72,
            dwFlagse);
          std::wstring::_Tidy_deallocate(&v97);
          ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
          std::wstring::_Tidy_deallocate(v93);
          std::wstring::_Tidy_deallocate(v92);
          return v73;
        }
      }
      else
      {
        if ( v23 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x131,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
            (const char *)(unsigned int)v23,
            dwFlagsa);
        ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
        std::wstring::_Tidy_deallocate(v93);
        std::wstring::_Tidy_deallocate(v92);
        return v24;
      }
    }
    else
    {
      *a3 = 0;
      v100 = 0;
      v101 = si128;
      LOWORD(v100) = 0;
      *(_OWORD *)pSacl = 0;
      v95 = si128;
      LOWORD(pSacl[0]) = 0;
      bSaclDefaulted = 0;
      v25 = ModernDeployment::Autopilot::Core::CryptoWrappers::ExportTpmKeyBlobFromSrkBasedKey(
              (unsigned int)v104,
              (unsigned int)v106,
              (unsigned int)&v100,
              (unsigned int)v108,
              (__int64)pSacl,
              (__int64)&bSaclDefaulted);
      v27 = v25;
      if ( v25 >= 0 )
      {
        v28 = ModernDeployment::Autopilot::Core::TpmKeyWrapper::CreateFromKeyData(
                (const struct ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102,
                v26,
                0,
                a4);
        v29 = v28;
        if ( v28 >= 0 )
        {
          v110 = 1;
          std::wstring::_Tidy_deallocate(pSacl);
          std::wstring::_Tidy_deallocate(&v100);
          ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
          std::wstring::_Tidy_deallocate(v93);
          std::wstring::_Tidy_deallocate(v92);
          return 0;
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x128,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
            (const char *)(unsigned int)v28,
            dwFlagsb);
          std::wstring::_Tidy_deallocate(pSacl);
          std::wstring::_Tidy_deallocate(&v100);
          ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
          std::wstring::_Tidy_deallocate(v93);
          std::wstring::_Tidy_deallocate(v92);
          return v29;
        }
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x126,
          (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
          (const char *)(unsigned int)v25,
          dwFlagsb);
        std::wstring::_Tidy_deallocate(pSacl);
        std::wstring::_Tidy_deallocate(&v100);
        ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData((ModernDeployment::Autopilot::Core::NcryptKeyData *)&v102);
        std::wstring::_Tidy_deallocate(v93);
        std::wstring::_Tidy_deallocate(v92);
        return v27;
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\tpmoperations\\tpmoperations.cpp",
      (const char *)0x8103C006LL,
      dwFlags);
    return 2164506630LL;
  }
}

```

## disassembly

```asm
0x18013d140  mov     rax, rsp
0x18013d143  push    rbx
0x18013d144  push    rsi
0x18013d145  push    rdi
0x18013d146  push    r12
0x18013d148  push    r13
0x18013d14a  push    r14
0x18013d14c  push    r15
0x18013d14e  sub     rsp, 200h
0x18013d155  movaps  xmmword ptr [rax-48h], xmm6
0x18013d159  mov     rax, cs:__security_cookie
0x18013d160  xor     rax, rsp
0x18013d163  mov     [rsp+238h+var_58], rax
0x18013d16b  mov     r14, r9
0x18013d16e  mov     r15, r8
0x18013d171  mov     edi, edx
0x18013d173  mov     rsi, rcx
0x18013d176  mov     [rsp+238h+bSaclPresent], edx
0x18013d17a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x18013d181  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18013d186  xor     r12d, r12d
0x18013d189  test    al, al
0x18013d18b  jnz     short loc_18013D1B5
0x18013d18d  mov     rcx, [rsp+238h]; this
0x18013d195  mov     ebx, 80004001h
0x18013d19a  mov     r9d, ebx; char *
0x18013d19d  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d1a4  mov     edx, 0F7h; void *
0x18013d1a9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d1ae  mov     eax, ebx
0x18013d1b0  jmp     loc_18013E0B3
0x18013d1b5  mov     rax, [rsi+0F0h]
0x18013d1bc  test    rax, rax
0x18013d1bf  jz      loc_18013E08A
0x18013d1c5  cmp     [rax], r12
0x18013d1c8  jz      loc_18013E08A
0x18013d1ce  test    edi, edi
0x18013d1d0  jnz     short loc_18013D235
0x18013d1d2  lea     rcx, [rsp+238h+bSaclPresent]; enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType *
0x18013d1d7  call    ?GetTackKeyType@AutopilotConfig@Core@Autopilot@ModernDeployment@@SAJAEAW4IdkKeyType@TpmKeyTypes@234@@Z; ModernDeployment::Autopilot::Core::AutopilotConfig::GetTackKeyType(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType &)
0x18013d1dc  mov     ebx, eax
0x18013d1de  test    eax, eax
0x18013d1e0  jns     short loc_18013D205
0x18013d1e2  mov     rcx, [rsp+238h]; this
0x18013d1ea  mov     r9d, eax; char *
0x18013d1ed  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d1f4  mov     edx, 0FDh; void *
0x18013d1f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d1fe  mov     eax, ebx
0x18013d200  jmp     loc_18013E0B3
0x18013d205  mov     edi, [rsp+238h+bSaclPresent]
0x18013d209  test    edi, edi
0x18013d20b  jnz     short loc_18013D235
0x18013d20d  mov     rcx, [rsp+238h]; this
0x18013d215  mov     ebx, 80070057h
0x18013d21a  mov     r9d, ebx; char *
0x18013d21d  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d224  mov     edx, 0FFh; void *
0x18013d229  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d22e  mov     eax, ebx
0x18013d230  jmp     loc_18013E0B3
0x18013d235  xorps   xmm0, xmm0
0x18013d238  movups  [rsp+238h+var_1E8], xmm0
0x18013d23d  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18013d245  movdqu  [rsp+238h+var_1D8], xmm6
0x18013d24b  mov     word ptr [rsp+238h+var_1E8], r12w
0x18013d251  lea     r8, [rsp+238h+bSaclDefaulted]
0x18013d256  lea     rdx, [rsp+238h+var_1E8]
0x18013d25b  lea     rcx, [rsp+238h+bSaclPresent]
0x18013d260  call    ?GetAlgorithmIdFromKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@SAJAEBW4IdkKeyType@1234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK@Z; ModernDeployment::Autopilot::Core::TpmKeyTypes::GetAlgorithmIdFromKeyType(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType const &,std::wstring &,ulong &)
0x18013d265  mov     ebx, eax
0x18013d267  test    eax, eax
0x18013d269  jns     short loc_18013D299
0x18013d26b  mov     rcx, [rsp+238h]; this
0x18013d273  mov     r9d, eax; char *
0x18013d276  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d27d  mov     edx, 103h; void *
0x18013d282  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d287  nop
0x18013d288  lea     rcx, [rsp+238h+var_1E8]
0x18013d28d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d292  mov     eax, ebx
0x18013d294  jmp     loc_18013E0B3
0x18013d299  xorps   xmm0, xmm0
0x18013d29c  movups  [rsp+238h+var_1C8], xmm0
0x18013d2a1  movdqu  [rsp+238h+var_1B8], xmm6
0x18013d2aa  mov     word ptr [rsp+238h+var_1C8], r12w
0x18013d2b0  lea     rdx, [rsp+238h+var_1C8]
0x18013d2b5  mov     ecx, edi
0x18013d2b7  call    ?GetTackKeyName@TpmOperations@Core@Autopilot@ModernDeployment@@KAJW4IdkKeyType@TpmKeyTypes@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::TpmOperations::GetTackKeyName(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType,std::wstring &)
0x18013d2bc  mov     ebx, eax
0x18013d2be  test    eax, eax
0x18013d2c0  jns     short loc_18013D2FB
0x18013d2c2  mov     rcx, [rsp+238h]; this
0x18013d2ca  mov     r9d, eax; char *
0x18013d2cd  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d2d4  mov     edx, 106h; void *
0x18013d2d9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d2de  nop
0x18013d2df  lea     rcx, [rsp+238h+var_1C8]
0x18013d2e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d2e9  nop
0x18013d2ea  lea     rcx, [rsp+238h+var_1E8]
0x18013d2ef  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d2f4  mov     eax, ebx
0x18013d2f6  jmp     loc_18013E0B3
0x18013d2fb  lea     rcx, [rsp+238h+var_138]; this
0x18013d303  call    ??0NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::NcryptKeyData(void)
0x18013d308  nop
0x18013d309  lea     rdx, [rsp+238h+var_1E8]
0x18013d30e  lea     rcx, [rsp+238h+var_F8]
0x18013d316  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18013d31b  mov     [rsp+238h+var_80], edi
0x18013d322  lea     rdx, aSha256_0; "SHA256"
0x18013d329  lea     rcx, [rsp+238h+var_D8]
0x18013d331  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18013d336  lea     rdx, [rsi+0F0h]
0x18013d33d  lea     rcx, [rsp+238h+pSacl]
0x18013d345  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x18013d34a  mov     rdx, [rax]
0x18013d34d  mov     rcx, [rsp+238h+var_138]
0x18013d355  mov     [rax], rcx
0x18013d358  mov     [rsp+238h+var_138], rdx
0x18013d360  mov     rdx, [rax+8]
0x18013d364  mov     rcx, [rsp+238h+var_130]
0x18013d36c  mov     [rax+8], rcx
0x18013d370  mov     [rsp+238h+var_130], rdx
0x18013d378  mov     rcx, [rsp+238h+pSacl+8]; this
0x18013d380  test    rcx, rcx
0x18013d383  jz      short loc_18013D38A
0x18013d385  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18013d38a  lea     rdx, [rsp+238h+var_1C8]
0x18013d38f  lea     rcx, [rsp+238h+var_118]
0x18013d397  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18013d39c  lea     rcx, [rsp+238h+var_118]
0x18013d3a4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013d3a9  mov     rbx, rax
0x18013d3ac  xorps   xmm0, xmm0
0x18013d3af  movdqu  xmmword ptr [rsp+238h+pSacl], xmm0
0x18013d3b8  lea     rdx, [rsp+238h+pSacl]
0x18013d3c0  lea     rcx, [rsp+238h+var_128]
0x18013d3c8  call    ??4?$shared_ptr@VEtwProcessingDataEntry@Diagnostics@Autopilot@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry> &&)
0x18013d3cd  mov     rcx, [rsp+238h+pSacl+8]; this
0x18013d3d5  test    rcx, rcx
0x18013d3d8  jz      short loc_18013D3DF
0x18013d3da  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18013d3df  lea     rcx, [rsp+238h+var_128]
0x18013d3e7  call    ??$addressof@U?$integral_constant@_K$0A@@wistd@@$0A@@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAPEA_KXZ; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(void)
0x18013d3ec  mov     rcx, [rsp+238h+var_138]
0x18013d3f4  test    rcx, rcx
0x18013d3f7  jz      short loc_18013D3FE
0x18013d3f9  mov     rcx, [rcx]
0x18013d3fc  jmp     short loc_18013D401
0x18013d3fe  mov     rcx, r12; hProvider
0x18013d401  mov     [rsp+238h+dwFlags], 40h ; '@'; int
0x18013d409  xor     r9d, r9d; dwLegacyKeySpec
0x18013d40c  mov     r8, rbx; pszKeyName
0x18013d40f  mov     rdx, rax; phKey
0x18013d412  call    cs:__imp_NCryptOpenKey
0x18013d419  nop     dword ptr [rax+rax+00h]
0x18013d41e  mov     ebx, eax
0x18013d420  test    eax, eax
0x18013d422  jnz     loc_18013D5D6
0x18013d428  mov     [r15], r12b
0x18013d42b  xorps   xmm0, xmm0
0x18013d42e  movups  [rsp+238h+var_160], xmm0
0x18013d436  movdqu  [rsp+238h+var_150], xmm6
0x18013d43f  mov     word ptr [rsp+238h+var_160], r12w
0x18013d448  movups  xmmword ptr [rsp+238h+pSacl], xmm0
0x18013d450  movdqu  [rsp+238h+var_198], xmm6
0x18013d459  mov     word ptr [rsp+238h+pSacl], r12w
0x18013d462  mov     [rsp+238h+bSaclDefaulted], r12d
0x18013d467  lea     rax, [rsp+238h+bSaclDefaulted]
0x18013d46c  mov     qword ptr [rsp+238h+var_210], rax
0x18013d471  lea     rax, [rsp+238h+pSacl]
0x18013d479  mov     qword ptr [rsp+238h+dwFlags], rax; int
0x18013d47e  lea     r9, [rsp+238h+var_B8]
0x18013d486  lea     r8, [rsp+238h+var_160]
0x18013d48e  lea     rdx, [rsp+238h+var_F8]
0x18013d496  lea     rcx, [rsp+238h+var_128]
0x18013d49e  call    ?ExportTpmKeyBlobFromSrkBasedKey@CryptoWrappers@Core@Autopilot@ModernDeployment@@SAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV78@AEAV?$vector@EV?$allocator@E@std@@@8@2AEAK@Z; ModernDeployment::Autopilot::Core::CryptoWrappers::ExportTpmKeyBlobFromSrkBasedKey(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>> const &,std::wstring const &,std::wstring &,std::vector<uchar> &,std::wstring &,ulong &)
0x18013d4a3  mov     ebx, eax
0x18013d4a5  test    eax, eax
0x18013d4a7  jns     short loc_18013D50C
0x18013d4a9  mov     rcx, [rsp+238h]; this
0x18013d4b1  mov     r9d, eax; char *
0x18013d4b4  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d4bb  mov     edx, 126h; void *
0x18013d4c0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d4c5  nop
0x18013d4c6  lea     rcx, [rsp+238h+pSacl]
0x18013d4ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d4d3  nop
0x18013d4d4  lea     rcx, [rsp+238h+var_160]
0x18013d4dc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d4e1  nop
0x18013d4e2  lea     rcx, [rsp+238h+var_138]; this
0x18013d4ea  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x18013d4ef  nop
0x18013d4f0  lea     rcx, [rsp+238h+var_1C8]
0x18013d4f5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d4fa  nop
0x18013d4fb  lea     rcx, [rsp+238h+var_1E8]
0x18013d500  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d505  mov     eax, ebx
0x18013d507  jmp     loc_18013E0B3
0x18013d50c  mov     r9, r14; struct ModernDeployment::Autopilot::Core::TpmKeyWrapper *
0x18013d50f  xor     r8d, r8d; bool
0x18013d512  lea     rcx, [rsp+238h+var_138]; struct ModernDeployment::Autopilot::Core::NcryptKeyData *
0x18013d51a  call    ?CreateFromKeyData@TpmKeyWrapper@Core@Autopilot@ModernDeployment@@SAJAEBVNcryptKeyData@234@_N1AEAV1234@@Z; ModernDeployment::Autopilot::Core::TpmKeyWrapper::CreateFromKeyData(ModernDeployment::Autopilot::Core::NcryptKeyData const &,bool,bool,ModernDeployment::Autopilot::Core::TpmKeyWrapper &)
0x18013d51f  mov     ebx, eax
0x18013d521  test    eax, eax
0x18013d523  jns     short loc_18013D588
0x18013d525  mov     rcx, [rsp+238h]; this
0x18013d52d  mov     r9d, eax; char *
0x18013d530  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d537  mov     edx, 128h; void *
0x18013d53c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d541  nop
0x18013d542  lea     rcx, [rsp+238h+pSacl]
0x18013d54a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d54f  nop
0x18013d550  lea     rcx, [rsp+238h+var_160]
0x18013d558  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d55d  nop
0x18013d55e  lea     rcx, [rsp+238h+var_138]; this
0x18013d566  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x18013d56b  nop
0x18013d56c  lea     rcx, [rsp+238h+var_1C8]
0x18013d571  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d576  nop
0x18013d577  lea     rcx, [rsp+238h+var_1E8]
0x18013d57c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d581  mov     eax, ebx
0x18013d583  jmp     loc_18013E0B3
0x18013d588  mov     [rsp+238h+var_7C], 1
0x18013d590  lea     rcx, [rsp+238h+pSacl]
0x18013d598  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d59d  nop
0x18013d59e  lea     rcx, [rsp+238h+var_160]
0x18013d5a6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d5ab  nop
0x18013d5ac  lea     rcx, [rsp+238h+var_138]; this
0x18013d5b4  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x18013d5b9  nop
0x18013d5ba  lea     rcx, [rsp+238h+var_1C8]
0x18013d5bf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d5c4  nop
0x18013d5c5  lea     rcx, [rsp+238h+var_1E8]
0x18013d5ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d5cf  xor     eax, eax
0x18013d5d1  jmp     loc_18013E0B3
0x18013d5d6  cmp     ebx, 80090016h
0x18013d5dc  jz      short loc_18013D629
0x18013d5de  test    ebx, ebx
0x18013d5e0  jns     short loc_18013D5FF
0x18013d5e2  mov     rcx, [rsp+238h]; this
0x18013d5ea  mov     r9d, ebx; char *
0x18013d5ed  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d5f4  mov     edx, 131h; void *
0x18013d5f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d5fe  nop
0x18013d5ff  lea     rcx, [rsp+238h+var_138]; this
0x18013d607  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x18013d60c  nop
0x18013d60d  lea     rcx, [rsp+238h+var_1C8]
0x18013d612  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d617  nop
0x18013d618  lea     rcx, [rsp+238h+var_1E8]
0x18013d61d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d622  mov     eax, ebx
0x18013d624  jmp     loc_18013E0B3
0x18013d629  mov     [rsp+238h+var_208], r12b
0x18013d62e  lea     rdx, [rsp+238h+var_208]
0x18013d633  mov     ecx, edi
0x18013d635  call    ?IsEccKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@SAJW4IdkKeyType@1234@AEA_N@Z; ModernDeployment::Autopilot::Core::TpmKeyTypes::IsEccKeyType(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType,bool &)
0x18013d63a  mov     ebx, eax
0x18013d63c  test    eax, eax
0x18013d63e  jns     short loc_18013D687
0x18013d640  mov     rcx, [rsp+238h]; this
0x18013d648  mov     r9d, eax; char *
0x18013d64b  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013d652  mov     edx, 135h; void *
0x18013d657  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013d65c  nop
0x18013d65d  lea     rcx, [rsp+238h+var_138]; this
0x18013d665  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x18013d66a  nop
0x18013d66b  lea     rcx, [rsp+238h+var_1C8]
0x18013d670  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d675  nop
0x18013d676  lea     rcx, [rsp+238h+var_1E8]
0x18013d67b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013d680  mov     eax, ebx
0x18013d682  jmp     loc_18013E0B3
0x18013d687  lea     rcx, [rsp+238h+var_118]
0x18013d68f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18013d694  mov     rbx, rax
0x18013d697  lea     rcx, [rsp+238h+var_F8]
0x18013d69f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
  ... truncated ...
```
