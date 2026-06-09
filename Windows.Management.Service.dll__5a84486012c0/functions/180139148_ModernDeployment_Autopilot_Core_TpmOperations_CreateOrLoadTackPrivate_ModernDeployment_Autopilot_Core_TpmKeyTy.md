# ModernDeployment::Autopilot::Core::TpmOperations::CreateOrLoadTackPrivate(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType,bool &,ModernDeployment::Autopilot::Core::TpmKeyWrapper &)

- ea: `0x180139148`
- end: `0x18013a0a5`
- name: `?CreateOrLoadTackPrivate@TpmOperations@Core@Autopilot@ModernDeployment@@QEAAJW4IdkKeyType@TpmKeyTypes@234@AEA_NAEAVTpmKeyWrapper@234@@Z`
- size: `3933`
- prototype: `int __high(enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType, bool *, struct ModernDeployment::Autopilot::Core::TpmKeyWrapper *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180138f8c`

## callees

- `0x18000b820`
- `0x180067a34`
- `0x180067a54`
- `0x18006e89c`
- `0x180077384`
- `0x18007755c`
- `0x18008019c`
- `0x1800801fc`
- `0x1800814a8`
- `0x180089ff4`
- `0x18008c244`
- `0x180093a28`
- `0x180136a00`
- `0x180136a7c`
- `0x180136b84`
- `0x180136cd4`
- `0x180139148`
- `0x18013af1c`
- `0x18013c178`
- `0x18013c450`
- `0x18013c4dc`
- `0x18013c750`
- `0x180144120`
- `0x180144234`
- `0x1801442d4`
- `0x18014435c`
- `0x18015e760`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180139a22`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180139a22`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180139aab`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorLength` at `0x180139aab`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180139991`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180139991`
- `ncrypt!NCryptOpenKey` at `0x18013941a`
- `ncrypt!NCryptOpenKey` at `0x18013941a`
- `ncrypt!NCryptSetProperty` at `0x1801397fb`
- `ncrypt!NCryptSetProperty` at `0x18013987f`
- `ncrypt!NCryptSetProperty` at `0x180139ad7`
- `ncrypt!NCryptSetProperty` at `0x180139bec`
- `ncrypt!NCryptSetProperty` at `0x180139d89`
- `ncrypt!NCryptSetProperty` at `0x1801397fb`
- `ncrypt!NCryptSetProperty` at `0x18013987f`
- `ncrypt!NCryptSetProperty` at `0x180139ad7`
- `ncrypt!NCryptSetProperty` at `0x180139bec`
- `ncrypt!NCryptSetProperty` at `0x180139d89`
- `ncrypt!NCryptCreatePersistedKey` at `0x180139714`
- `ncrypt!NCryptCreatePersistedKey` at `0x180139714`
- `ncrypt!NCryptFinalizeKey` at `0x180139e1c`
- `ncrypt!NCryptFinalizeKey` at `0x180139e1c`

## string_xrefs

- `0x1801391a5`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x1801391f5`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139225`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013927e`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x1801392d5`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x1801394b6`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139532`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x1801395ef`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013964d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013972b`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013978d`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139812`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139896`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139918`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x1801399a3`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139a34`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139aee`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139b79`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139c03`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139c88`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139d08`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139da0`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139e33`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139f06`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139f98`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x18013a060`: `onecoreuap\admin\moderndeployment\autopilot\service\tpmoperations\tpmoperations.cpp`
- `0x180139ad0`: `Security Descr`

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
0x180139148  mov     rax, rsp
0x18013914b  push    rbx
0x18013914c  push    rsi
0x18013914d  push    rdi
0x18013914e  push    r12
0x180139150  push    r13
0x180139152  push    r14
0x180139154  push    r15
0x180139156  sub     rsp, 200h
0x18013915d  movaps  xmmword ptr [rax-48h], xmm6
0x180139161  mov     rax, cs:__security_cookie
0x180139168  xor     rax, rsp
0x18013916b  mov     [rsp+238h+var_58], rax
0x180139173  mov     r14, r9
0x180139176  mov     r15, r8
0x180139179  mov     edi, edx
0x18013917b  mov     rsi, rcx
0x18013917e  mov     [rsp+238h+bSaclPresent], edx
0x180139182  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging> `wil::Feature<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::GetImpl(void)'::`2'::impl
0x180139189  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_AutopilotDeviceTagging@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AutopilotDeviceTagging>::__private_IsEnabled(void)
0x18013918e  xor     r12d, r12d
0x180139191  test    al, al
0x180139193  jnz     short loc_1801391BD
0x180139195  mov     rcx, [rsp+238h]; this
0x18013919d  mov     ebx, 80004001h
0x1801391a2  mov     r9d, ebx; char *
0x1801391a5  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801391ac  mov     edx, 0F7h; void *
0x1801391b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801391b6  mov     eax, ebx
0x1801391b8  jmp     loc_18013A079
0x1801391bd  mov     rax, [rsi+0F0h]
0x1801391c4  test    rax, rax
0x1801391c7  jz      loc_18013A050
0x1801391cd  cmp     [rax], r12
0x1801391d0  jz      loc_18013A050
0x1801391d6  test    edi, edi
0x1801391d8  jnz     short loc_18013923D
0x1801391da  lea     rcx, [rsp+238h+bSaclPresent]; enum ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType *
0x1801391df  call    ?GetTackKeyType@AutopilotConfig@Core@Autopilot@ModernDeployment@@SAJAEAW4IdkKeyType@TpmKeyTypes@234@@Z; ModernDeployment::Autopilot::Core::AutopilotConfig::GetTackKeyType(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType &)
0x1801391e4  mov     ebx, eax
0x1801391e6  test    eax, eax
0x1801391e8  jns     short loc_18013920D
0x1801391ea  mov     rcx, [rsp+238h]; this
0x1801391f2  mov     r9d, eax; char *
0x1801391f5  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801391fc  mov     edx, 0FDh; void *
0x180139201  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180139206  mov     eax, ebx
0x180139208  jmp     loc_18013A079
0x18013920d  mov     edi, [rsp+238h+bSaclPresent]
0x180139211  test    edi, edi
0x180139213  jnz     short loc_18013923D
0x180139215  mov     rcx, [rsp+238h]; this
0x18013921d  mov     ebx, 80070057h
0x180139222  mov     r9d, ebx; char *
0x180139225  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x18013922c  mov     edx, 0FFh; void *
0x180139231  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180139236  mov     eax, ebx
0x180139238  jmp     loc_18013A079
0x18013923d  xorps   xmm0, xmm0
0x180139240  movups  [rsp+238h+var_1E8], xmm0
0x180139245  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18013924d  movdqu  [rsp+238h+var_1D8], xmm6
0x180139253  mov     word ptr [rsp+238h+var_1E8], r12w
0x180139259  lea     r8, [rsp+238h+bSaclDefaulted]
0x18013925e  lea     rdx, [rsp+238h+var_1E8]
0x180139263  lea     rcx, [rsp+238h+bSaclPresent]
0x180139268  call    ?GetAlgorithmIdFromKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@SAJAEBW4IdkKeyType@1234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAK@Z; ModernDeployment::Autopilot::Core::TpmKeyTypes::GetAlgorithmIdFromKeyType(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType const &,std::wstring &,ulong &)
0x18013926d  mov     ebx, eax
0x18013926f  test    eax, eax
0x180139271  jns     short loc_1801392A1
0x180139273  mov     rcx, [rsp+238h]; this
0x18013927b  mov     r9d, eax; char *
0x18013927e  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x180139285  mov     edx, 103h; void *
0x18013928a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013928f  nop
0x180139290  lea     rcx, [rsp+238h+var_1E8]
0x180139295  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013929a  mov     eax, ebx
0x18013929c  jmp     loc_18013A079
0x1801392a1  xorps   xmm0, xmm0
0x1801392a4  movups  [rsp+238h+var_1C8], xmm0
0x1801392a9  movdqu  [rsp+238h+var_1B8], xmm6
0x1801392b2  mov     word ptr [rsp+238h+var_1C8], r12w
0x1801392b8  lea     rdx, [rsp+238h+var_1C8]
0x1801392bd  mov     ecx, edi
0x1801392bf  call    ?GetTackKeyName@TpmOperations@Core@Autopilot@ModernDeployment@@KAJW4IdkKeyType@TpmKeyTypes@234@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ModernDeployment::Autopilot::Core::TpmOperations::GetTackKeyName(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType,std::wstring &)
0x1801392c4  mov     ebx, eax
0x1801392c6  test    eax, eax
0x1801392c8  jns     short loc_180139303
0x1801392ca  mov     rcx, [rsp+238h]; this
0x1801392d2  mov     r9d, eax; char *
0x1801392d5  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801392dc  mov     edx, 106h; void *
0x1801392e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801392e6  nop
0x1801392e7  lea     rcx, [rsp+238h+var_1C8]
0x1801392ec  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801392f1  nop
0x1801392f2  lea     rcx, [rsp+238h+var_1E8]
0x1801392f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801392fc  mov     eax, ebx
0x1801392fe  jmp     loc_18013A079
0x180139303  lea     rcx, [rsp+238h+var_138]; this
0x18013930b  call    ??0NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::NcryptKeyData(void)
0x180139310  nop
0x180139311  lea     rdx, [rsp+238h+var_1E8]
0x180139316  lea     rcx, [rsp+238h+var_F8]
0x18013931e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180139323  mov     [rsp+238h+var_80], edi
0x18013932a  lea     rdx, aSha256_0; "SHA256"
0x180139331  lea     rcx, [rsp+238h+var_D8]
0x180139339  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::assign(ushort const * const)
0x18013933e  lea     rdx, [rsi+0F0h]
0x180139345  lea     rcx, [rsp+238h+pSacl]
0x18013934d  call    ??0?$shared_ptr@VAutoPilotManager@AutoPilot@Service@EnterpriseDeviceManagement@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager>(std::shared_ptr<EnterpriseDeviceManagement::Service::AutoPilot::AutoPilotManager> const &)
0x180139352  mov     rdx, [rax]
0x180139355  mov     rcx, [rsp+238h+var_138]
0x18013935d  mov     [rax], rcx
0x180139360  mov     [rsp+238h+var_138], rdx
0x180139368  mov     rdx, [rax+8]
0x18013936c  mov     rcx, [rsp+238h+var_130]
0x180139374  mov     [rax+8], rcx
0x180139378  mov     [rsp+238h+var_130], rdx
0x180139380  mov     rcx, [rsp+238h+pSacl+8]; this
0x180139388  test    rcx, rcx
0x18013938b  jz      short loc_180139392
0x18013938d  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180139392  lea     rdx, [rsp+238h+var_1C8]
0x180139397  lea     rcx, [rsp+238h+var_118]
0x18013939f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1801393a4  lea     rcx, [rsp+238h+var_118]
0x1801393ac  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801393b1  mov     rbx, rax
0x1801393b4  xorps   xmm0, xmm0
0x1801393b7  movdqu  xmmword ptr [rsp+238h+pSacl], xmm0
0x1801393c0  lea     rdx, [rsp+238h+pSacl]
0x1801393c8  lea     rcx, [rsp+238h+var_128]
0x1801393d0  call    ??4?$shared_ptr@VEtwProcessingDataEntry@Diagnostics@Autopilot@Windows@Microsoft@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry>::operator=(std::shared_ptr<Microsoft::Windows::Autopilot::Diagnostics::EtwProcessingDataEntry> &&)
0x1801393d5  mov     rcx, [rsp+238h+pSacl+8]; this
0x1801393dd  test    rcx, rcx
0x1801393e0  jz      short loc_1801393E7
0x1801393e2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1801393e7  lea     rcx, [rsp+238h+var_128]
0x1801393ef  call    ??$addressof@U?$integral_constant@_K$0A@@wistd@@$0A@@?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAAPEA_KXZ; wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>::addressof<wistd::integral_constant<unsigned __int64,0>,0>(void)
0x1801393f4  mov     rcx, [rsp+238h+var_138]
0x1801393fc  test    rcx, rcx
0x1801393ff  jz      short loc_180139406
0x180139401  mov     rcx, [rcx]
0x180139404  jmp     short loc_180139409
0x180139406  mov     rcx, r12; hProvider
0x180139409  mov     [rsp+238h+dwFlags], 40h ; '@'; int
0x180139411  xor     r9d, r9d; dwLegacyKeySpec
0x180139414  mov     r8, rbx; pszKeyName
0x180139417  mov     rdx, rax; phKey
0x18013941a  call    cs:__imp_NCryptOpenKey
0x180139420  mov     ebx, eax
0x180139422  test    eax, eax
0x180139424  jnz     loc_1801395D8
0x18013942a  mov     [r15], r12b
0x18013942d  xorps   xmm0, xmm0
0x180139430  movups  [rsp+238h+var_160], xmm0
0x180139438  movdqu  [rsp+238h+var_150], xmm6
0x180139441  mov     word ptr [rsp+238h+var_160], r12w
0x18013944a  movups  xmmword ptr [rsp+238h+pSacl], xmm0
0x180139452  movdqu  [rsp+238h+var_198], xmm6
0x18013945b  mov     word ptr [rsp+238h+pSacl], r12w
0x180139464  mov     [rsp+238h+bSaclDefaulted], r12d
0x180139469  lea     rax, [rsp+238h+bSaclDefaulted]
0x18013946e  mov     qword ptr [rsp+238h+var_210], rax
0x180139473  lea     rax, [rsp+238h+pSacl]
0x18013947b  mov     qword ptr [rsp+238h+dwFlags], rax; int
0x180139480  lea     r9, [rsp+238h+var_B8]
0x180139488  lea     r8, [rsp+238h+var_160]
0x180139490  lea     rdx, [rsp+238h+var_F8]
0x180139498  lea     rcx, [rsp+238h+var_128]
0x1801394a0  call    ?ExportTpmKeyBlobFromSrkBasedKey@CryptoWrappers@Core@Autopilot@ModernDeployment@@SAJAEBV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?NCryptFreeObject@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV78@AEAV?$vector@EV?$allocator@E@std@@@8@2AEAK@Z; ModernDeployment::Autopilot::Core::CryptoWrappers::ExportTpmKeyBlobFromSrkBasedKey(wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&NCryptFreeObject(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>>> const &,std::wstring const &,std::wstring &,std::vector<uchar> &,std::wstring &,ulong &)
0x1801394a5  mov     ebx, eax
0x1801394a7  test    eax, eax
0x1801394a9  jns     short loc_18013950E
0x1801394ab  mov     rcx, [rsp+238h]; this
0x1801394b3  mov     r9d, eax; char *
0x1801394b6  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801394bd  mov     edx, 126h; void *
0x1801394c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801394c7  nop
0x1801394c8  lea     rcx, [rsp+238h+pSacl]
0x1801394d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801394d5  nop
0x1801394d6  lea     rcx, [rsp+238h+var_160]
0x1801394de  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801394e3  nop
0x1801394e4  lea     rcx, [rsp+238h+var_138]; this
0x1801394ec  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x1801394f1  nop
0x1801394f2  lea     rcx, [rsp+238h+var_1C8]
0x1801394f7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801394fc  nop
0x1801394fd  lea     rcx, [rsp+238h+var_1E8]
0x180139502  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180139507  mov     eax, ebx
0x180139509  jmp     loc_18013A079
0x18013950e  mov     r9, r14; struct ModernDeployment::Autopilot::Core::TpmKeyWrapper *
0x180139511  xor     r8d, r8d; bool
0x180139514  lea     rcx, [rsp+238h+var_138]; struct ModernDeployment::Autopilot::Core::NcryptKeyData *
0x18013951c  call    ?CreateFromKeyData@TpmKeyWrapper@Core@Autopilot@ModernDeployment@@SAJAEBVNcryptKeyData@234@_N1AEAV1234@@Z; ModernDeployment::Autopilot::Core::TpmKeyWrapper::CreateFromKeyData(ModernDeployment::Autopilot::Core::NcryptKeyData const &,bool,bool,ModernDeployment::Autopilot::Core::TpmKeyWrapper &)
0x180139521  mov     ebx, eax
0x180139523  test    eax, eax
0x180139525  jns     short loc_18013958A
0x180139527  mov     rcx, [rsp+238h]; this
0x18013952f  mov     r9d, eax; char *
0x180139532  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x180139539  mov     edx, 128h; void *
0x18013953e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180139543  nop
0x180139544  lea     rcx, [rsp+238h+pSacl]
0x18013954c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180139551  nop
0x180139552  lea     rcx, [rsp+238h+var_160]
0x18013955a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013955f  nop
0x180139560  lea     rcx, [rsp+238h+var_138]; this
0x180139568  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x18013956d  nop
0x18013956e  lea     rcx, [rsp+238h+var_1C8]
0x180139573  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180139578  nop
0x180139579  lea     rcx, [rsp+238h+var_1E8]
0x18013957e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180139583  mov     eax, ebx
0x180139585  jmp     loc_18013A079
0x18013958a  mov     [rsp+238h+var_7C], 1
0x180139592  lea     rcx, [rsp+238h+pSacl]
0x18013959a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18013959f  nop
0x1801395a0  lea     rcx, [rsp+238h+var_160]
0x1801395a8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801395ad  nop
0x1801395ae  lea     rcx, [rsp+238h+var_138]; this
0x1801395b6  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x1801395bb  nop
0x1801395bc  lea     rcx, [rsp+238h+var_1C8]
0x1801395c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801395c6  nop
0x1801395c7  lea     rcx, [rsp+238h+var_1E8]
0x1801395cc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1801395d1  xor     eax, eax
0x1801395d3  jmp     loc_18013A079
0x1801395d8  cmp     ebx, 80090016h
0x1801395de  jz      short loc_18013962B
0x1801395e0  test    ebx, ebx
0x1801395e2  jns     short loc_180139601
0x1801395e4  mov     rcx, [rsp+238h]; this
0x1801395ec  mov     r9d, ebx; char *
0x1801395ef  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x1801395f6  mov     edx, 131h; void *
0x1801395fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180139600  nop
0x180139601  lea     rcx, [rsp+238h+var_138]; this
0x180139609  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x18013960e  nop
0x18013960f  lea     rcx, [rsp+238h+var_1C8]
0x180139614  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180139619  nop
0x18013961a  lea     rcx, [rsp+238h+var_1E8]
0x18013961f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180139624  mov     eax, ebx
0x180139626  jmp     loc_18013A079
0x18013962b  mov     [rsp+238h+var_208], r12b
0x180139630  lea     rdx, [rsp+238h+var_208]
0x180139635  mov     ecx, edi
0x180139637  call    ?IsEccKeyType@TpmKeyTypes@Core@Autopilot@ModernDeployment@@SAJW4IdkKeyType@1234@AEA_N@Z; ModernDeployment::Autopilot::Core::TpmKeyTypes::IsEccKeyType(ModernDeployment::Autopilot::Core::TpmKeyTypes::IdkKeyType,bool &)
0x18013963c  mov     ebx, eax
0x18013963e  test    eax, eax
0x180139640  jns     short loc_180139689
0x180139642  mov     rcx, [rsp+238h]; this
0x18013964a  mov     r9d, eax; char *
0x18013964d  lea     r8, aOnecoreuapAdmi_130; "onecoreuap\\admin\\moderndeployment\\au"...
0x180139654  mov     edx, 135h; void *
0x180139659  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18013965e  nop
0x18013965f  lea     rcx, [rsp+238h+var_138]; this
0x180139667  call    ??1NcryptKeyData@Core@Autopilot@ModernDeployment@@QEAA@XZ; ModernDeployment::Autopilot::Core::NcryptKeyData::~NcryptKeyData(void)
0x18013966c  nop
0x18013966d  lea     rcx, [rsp+238h+var_1C8]
0x180139672  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180139677  nop
0x180139678  lea     rcx, [rsp+238h+var_1E8]
0x18013967d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180139682  mov     eax, ebx
0x180139684  jmp     loc_18013A079
0x180139689  lea     rcx, [rsp+238h+var_118]
0x180139691  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180139696  mov     rbx, rax
0x180139699  lea     rcx, [rsp+238h+var_F8]
0x1801396a1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1801396a6  mov     rsi, rax
  ... truncated ...
```
