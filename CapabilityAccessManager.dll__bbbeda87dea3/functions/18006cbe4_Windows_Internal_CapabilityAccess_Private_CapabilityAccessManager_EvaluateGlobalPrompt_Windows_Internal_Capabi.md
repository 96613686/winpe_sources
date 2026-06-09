# Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::EvaluateGlobalPrompt(Windows::Internal::CapabilityAccess::Private::GlobalPrompt,Windows::Internal::CapabilityAccess::Private::UserConsentSwitch)

- ea: `0x18006cbe4`
- end: `0x18006de0f`
- name: `?EvaluateGlobalPrompt@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@AEAA?AW4AccessCheckStatus@2345@W4GlobalPrompt@2345@W4UserConsentSwitch@2345@@Z`
- size: `4651`
- prototype: ``
- caller_count: `1`
- callee_count: `59`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006a080`

## callees

- `0x1800094c0`
- `0x18000a0bc`
- `0x18001649c`
- `0x18001c3b4`
- `0x18001e118`
- `0x18001e32c`
- `0x18001e42c`
- `0x180020fcc`
- `0x1800211d4`
- `0x18002392c`
- `0x1800257a4`
- `0x180025b6c`
- `0x180027ed0`
- `0x180027f94`
- `0x180029408`
- `0x18002949c`
- `0x18002e304`
- `0x18002f93c`
- `0x18002f978`
- `0x180036f0c`
- `0x1800389b8`
- `0x180039e9c`
- `0x18003a264`
- `0x18003b518`
- `0x18003b54c`
- `0x1800417e0`
- `0x1800418e8`
- `0x180041e2c`
- `0x1800429ac`
- `0x180045a8c`
- `0x1800463e4`
- `0x1800465b0`
- `0x18004b7c8`
- `0x1800518c0`
- `0x180051af0`
- `0x180057454`
- `0x180057524`
- `0x180057784`
- `0x1800579a4`
- `0x18005c834`
- `0x18006517c`
- `0x1800651fc`
- `0x1800666f0`
- `0x180066890`
- `0x180066e70`
- `0x180066eb8`
- `0x180069cac`
- `0x180069d00`
- `0x18006a080`
- `0x18006c2bc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18006d360`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18006d3a9`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18006d4d4`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006d2db`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006d2db`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18006d2f4`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x18006d2f4`

## string_xrefs

- `0x18006dde3`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x18006ddfd`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=64
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::EvaluateGlobalPrompt(
        std::_Ref_count_base *a1,
        int a2,
        __int64 a3)
{
  unsigned int v3; // r13d
  std::_Ref_count_base *v4; // rsi
  __int64 ImageFullPathFromProcessId; // rax
  int v7; // r14d
  __int64 v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rax
  __int64 v11; // rcx
  unsigned int v12; // ebx
  __int64 v13; // rdx
  Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore *v14; // rcx
  __int64 *v15; // rcx
  __m128i v16; // xmm6
  Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore *v17; // rcx
  const char *v18; // r9
  const char *v19; // r9
  int v20; // edx
  unsigned __int64 v21; // rax
  int v22; // eax
  int v23; // r8d
  __int128 *v24; // rcx
  int *v25; // rcx
  int v26; // eax
  int v27; // r8d
  __int64 last_of; // rax
  int v29; // r12d
  __int64 v30; // rax
  char *v31; // rcx
  __int64 FriendlyNameFromImageFullPath; // rax
  const char *v33; // r9
  __int64 v34; // rax
  int GlobalPrompt; // eax
  unsigned int v36; // ebx
  const unsigned __int16 *v37; // rax
  __int64 v38; // rax
  wil *v39; // rcx
  int v40; // r15d
  __int64 v41; // rbx
  __int64 ConsentIdFromObjectId; // rax
  __int64 v43; // rbx
  int v44; // eax
  __int64 v45; // rbx
  int v46; // r9d
  int v47; // r14d
  std::_Ref_count_base **UserAppConsent; // rax
  char v49; // r14
  std::_Ref_count_base *v50; // rbx
  const unsigned __int16 *v51; // rax
  const unsigned __int16 *v52; // r9
  const unsigned __int16 *v53; // r10
  const unsigned __int16 *v54; // r11
  _DWORD *v55; // rbx
  __int64 v56; // rdx
  __int64 v57; // rdx
  const unsigned __int16 *v58; // rax
  int v59; // r8d
  const unsigned __int16 *v60; // r9
  const unsigned __int16 *v61; // r10
  const unsigned __int16 *v62; // r11
  const struct wil::FailureInfo *Failure; // rbx
  wil *v64; // rcx
  unsigned int v65; // eax
  const unsigned __int16 *v66; // rax
  int v67; // edx
  int v68; // [rsp+20h] [rbp-818h]
  char v69; // [rsp+70h] [rbp-7C8h] BYREF
  int v70; // [rsp+74h] [rbp-7C4h]
  int v71; // [rsp+78h] [rbp-7C0h] BYREF
  int v72; // [rsp+80h] [rbp-7B8h]
  std::_Ref_count_base *v73; // [rsp+88h] [rbp-7B0h] BYREF
  char v74[8]; // [rsp+90h] [rbp-7A8h] BYREF
  std::_Ref_count_base *v75; // [rsp+98h] [rbp-7A0h]
  unsigned int v76; // [rsp+A0h] [rbp-798h]
  __int64 v77; // [rsp+A8h] [rbp-790h] BYREF
  __int64 v78; // [rsp+B0h] [rbp-788h] BYREF
  std::_Ref_count_base *v79; // [rsp+B8h] [rbp-780h]
  std::_Ref_count_base *v80; // [rsp+C0h] [rbp-778h] BYREF
  std::_Ref_count_base *v81; // [rsp+C8h] [rbp-770h]
  char v82; // [rsp+D0h] [rbp-768h]
  __int64 v83; // [rsp+D8h] [rbp-760h] BYREF
  std::_Ref_count_base *v84; // [rsp+E0h] [rbp-758h]
  __int64 v85; // [rsp+E8h] [rbp-750h] BYREF
  std::_Ref_count_base *v86; // [rsp+F0h] [rbp-748h]
  int v87[4]; // [rsp+F8h] [rbp-740h] BYREF
  __int128 v88; // [rsp+108h] [rbp-730h]
  __int64 v89[2]; // [rsp+118h] [rbp-720h] BYREF
  __m128i v90; // [rsp+128h] [rbp-710h]
  __int64 v91[2]; // [rsp+138h] [rbp-700h] BYREF
  __m128i v92; // [rsp+148h] [rbp-6F0h]
  __int128 v93; // [rsp+158h] [rbp-6E0h] BYREF
  __m128i si128; // [rsp+168h] [rbp-6D0h]
  __int128 v95; // [rsp+178h] [rbp-6C0h] BYREF
  __m128i v96; // [rsp+188h] [rbp-6B0h]
  _BYTE v97[32]; // [rsp+198h] [rbp-6A0h] BYREF
  _BYTE v98[16]; // [rsp+1B8h] [rbp-680h] BYREF
  __int64 v99; // [rsp+1C8h] [rbp-670h]
  int v100[4]; // [rsp+1D8h] [rbp-660h] BYREF
  __int64 v101; // [rsp+1E8h] [rbp-650h]
  __int64 v102; // [rsp+1F0h] [rbp-648h]
  _BYTE v103[16]; // [rsp+1F8h] [rbp-640h] BYREF
  unsigned __int64 v104; // [rsp+208h] [rbp-630h]
  _BYTE v105[32]; // [rsp+218h] [rbp-620h] BYREF
  _BYTE v106[32]; // [rsp+238h] [rbp-600h] BYREF
  char v107[8]; // [rsp+258h] [rbp-5E0h] BYREF
  std::_Ref_count_base *v108; // [rsp+260h] [rbp-5D8h]
  _BYTE v109[32]; // [rsp+278h] [rbp-5C0h] BYREF
  _BYTE v110[32]; // [rsp+298h] [rbp-5A0h] BYREF
  _BYTE v111[40]; // [rsp+2B8h] [rbp-580h] BYREF
  char v112[8]; // [rsp+2E0h] [rbp-558h] BYREF
  _DWORD v113[54]; // [rsp+2E8h] [rbp-550h] BYREF
  WCHAR Buffer[264]; // [rsp+3C0h] [rbp-478h] BYREF
  WCHAR v115[264]; // [rsp+5D0h] [rbp-268h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+838h] [rbp+0h]

  v3 = a3;
  v72 = a2;
  v4 = a1;
  v73 = a1;
  v71 = a2;
  v76 = a3;
  v70 = 0;
  if ( !Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x1E3,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
      (const char *)0x8000FFFFLL,
      v68);
  _acquire___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
    &Windows::Internal::CapabilityAccess::Private::Globals::SemaphoreManager::m_globalPromptSemaphore,
    &v77,
    a3,
    0);
  if ( !v77 )
  {
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v77);
    return 2;
  }
  if ( *((_BYTE *)v4 + 36) )
  {
    ImageFullPathFromProcessId = std::wstring::wstring(v105, (char *)v4 + 168);
    v7 = 4;
  }
  else
  {
    ImageFullPathFromProcessId = Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(
                                   v97,
                                   *((unsigned int *)v4 + 12));
    v7 = 8;
  }
  v70 = v7;
  *(_OWORD *)v87 = 0;
  v88 = 0;
  *(_OWORD *)v87 = *(_OWORD *)ImageFullPathFromProcessId;
  v88 = *(_OWORD *)(ImageFullPathFromProcessId + 16);
  *(_QWORD *)(ImageFullPathFromProcessId + 16) = 0;
  *(_QWORD *)(ImageFullPathFromProcessId + 24) = 7;
  *(_WORD *)ImageFullPathFromProcessId = 0;
  if ( (v7 & 8) != 0 )
  {
    v7 &= ~8u;
    v70 = v7;
    std::wstring::_Tidy_deallocate(v97);
  }
  if ( (v7 & 4) != 0 )
  {
    v7 &= ~4u;
    v70 = v7;
    std::wstring::_Tidy_deallocate(v105);
  }
  if ( !*(_BYTE *)(*((_QWORD *)v4 + 16) + 51LL) || !*((_BYTE *)v4 + 41) )
    goto LABEL_52;
  Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore>>::Instance(v74);
  if ( !*((_BYTE *)v4 + 36) )
    goto LABEL_149;
  if ( (unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::UserShownGlobalPromptForPackage(
                          v8,
                          v87,
                          (char *)v4 + 392,
                          (char *)v4 + 296) )
    goto LABEL_17;
  if ( !*((_BYTE *)v4 + 36) )
  {
LABEL_149:
    if ( (unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::UserShownGlobalPromptForBinaryFullPath(
                            v8,
                            v87,
                            (char *)v4 + 392,
                            (char *)v4 + 296) )
    {
LABEL_17:
      if ( !*((_BYTE *)v4 + 36) )
      {
        if ( !Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1EB,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\synchronizationhelpers.cpp",
            (const char *)0x8000FFFFLL,
            v68);
        _acquire___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAA_AV__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil___2_PEAKKH_Z(
          &Windows::Internal::CapabilityAccess::Private::Globals::SemaphoreManager::m_globalPromptCompatIDRecordingSemaphore,
          &v73,
          v9,
          0);
        if ( v73 )
        {
          std::enable_shared_from_this<Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager>::shared_from_this(
            (char *)v4 + 8,
            &v80);
          v10 = lambda_588d46ef73bdd48b5ef5b5308c2d69e6_::_lambda_588d46ef73bdd48b5ef5b5308c2d69e6_(
                  (unsigned int)v112,
                  (unsigned int)&v73,
                  (unsigned int)v87,
                  (unsigned int)&v80,
                  (__int64)v4 + 392,
                  (__int64)v4 + 296,
                  (__int64)v4,
                  (__int64)&v71);
          std::thread::thread__lambda_588d46ef73bdd48b5ef5b5308c2d69e6__0_(&v78, v10);
          lambda_588d46ef73bdd48b5ef5b5308c2d69e6_::__lambda_588d46ef73bdd48b5ef5b5308c2d69e6_(v112);
          std::thread::detach((std::thread *)&v78);
          std::thread::~thread((std::thread *)&v78);
          if ( v81 )
            std::_Ref_count_base::_Decref(v81);
        }
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v73);
      }
      goto LABEL_50;
    }
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CM_OneClick>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CM_OneClick>::GetImpl'::`2'::impl) )
  {
    v12 = 3;
    if ( v3 != 3
      && !(unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetShowGlobalPrompts(
                             v11,
                             (char *)v4 + 392,
                             (char *)v4 + 296) )
    {
      goto LABEL_50;
    }
  }
  else
  {
    if ( !(unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetShowGlobalPrompts(
                             v11,
                             (char *)v4 + 392,
                             (char *)v4 + 296) )
      goto LABEL_50;
    v12 = 3;
  }
  if ( *((_BYTE *)v4 + 37) || *((_BYTE *)v4 + 39) )
    goto LABEL_85;
  if ( !*((_BYTE *)v4 + 36) )
    goto LABEL_150;
  if ( !(unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::ShowGlobalPromptForApp(
                           *((_QWORD *)v4 + 16),
                           v87) )
    goto LABEL_38;
  if ( !*((_BYTE *)v4 + 36) )
  {
LABEL_150:
    if ( (unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::ShowGlobalPromptForBinaryFullPath(
                            *((_QWORD *)v4 + 16),
                            v87) )
      goto LABEL_35;
LABEL_38:
    v93 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v93) = 0;
    v95 = 0;
    v96 = si128;
    LOWORD(v95) = 0;
    Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GlobalPromptEvaluated(
      (_DWORD)v4,
      (unsigned int)v87,
      (unsigned int)&v95,
      (unsigned int)&v93);
    std::wstring::_Tidy_deallocate(&v95);
    v15 = (__int64 *)&v93;
LABEL_49:
    std::wstring::_Tidy_deallocate(v15);
LABEL_50:
    if ( v75 )
      std::_Ref_count_base::_Decref(v75);
LABEL_52:
    std::wstring::_Tidy_deallocate(v87);
    __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v77);
    return 1;
  }
LABEL_35:
  LOBYTE(v13) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_HideSystemPackages>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_HideSystemPackages>::GetImpl'::`2'::impl,
    v13);
  if ( *((_BYTE *)v4 + 36)
    && (!(unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::UserAppConsentRequiredForApp(
                            *((_QWORD *)v4 + 16),
                            v87,
                            (char *)v4 + 392)
     || !(unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::UserConsentRequiredForApp(
                            *((_QWORD *)v4 + 16),
                            v87,
                            *((_QWORD *)v4 + 54))) )
  {
    goto LABEL_38;
  }
  *(_OWORD *)v91 = 0;
  v16 = _mm_load_si128((const __m128i *)&_xmm);
  v92 = v16;
  LOWORD(v91[0]) = 0;
  *(_OWORD *)v89 = 0;
  v90 = v16;
  LOWORD(v89[0]) = 0;
  if ( !*((_BYTE *)v4 + 36) )
    Windows::Internal::CapabilityAccess::Private::GetFileProgramIDByBinaryFullPath(v87, v91, v89);
  if ( !*((_QWORD *)v4 + 14) )
    goto LABEL_53;
  if ( !Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore::IsAutoAcceptConsentPromptsEnabled(v14) )
  {
    if ( *((_QWORD *)v4 + 14)
      && Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore::IsAutoDenyConsentPromptsEnabled(v17) )
    {
      std::wstring::wstring(v97, L"Test AutoDeny key is set - skipping showing Global Prompt");
      std::wstring::_Tidy_deallocate(v97);
      Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GlobalPromptEvaluated(
        (_DWORD)v4,
        (unsigned int)v87,
        (unsigned int)v91,
        (unsigned int)v89);
      std::wstring::_Tidy_deallocate(v89);
      v15 = v91;
      goto LABEL_49;
    }
LABEL_53:
    if ( *((_BYTE *)v4 + 36) )
    {
      v31 = (char *)v4 + 232;
      if ( !*((_QWORD *)v4 + 31) )
        v31 = (char *)v4 + 392;
      if ( (unsigned int)Windows::Internal::CapabilityAccess::Private::GetPackageOriginFromFamilyNameAndUser(
                           v31,
                           (char *)v4 + 168) == 2 )
      {
        Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GlobalPromptEvaluated(
          (_DWORD)v4,
          (unsigned int)v87,
          (unsigned int)v91,
          (unsigned int)v89);
        goto LABEL_61;
      }
      v29 = -1;
    }
    else
    {
      memset_0(Buffer, 0, 0x208u);
      memset_0(v115, 0, 0x208u);
      if ( !GetSystemDirectoryW(Buffer, 0x104u) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xD86,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
          v18);
      if ( !GetSystemWow64DirectoryW(v115, 0x104u) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0xD8B,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
          v19);
      std::wstring::wstring(&v93, Buffer);
      std::wstring::wstring(v103, v115);
      std::wstring::wstring(v98, v87);
      v20 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v98);
      std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
        (unsigned int)&v78,
        v20,
        v20 + 2 * v99,
        v20,
        *(__int64 *)&_o_towlower);
      v21 = v88;
      if ( (unsigned __int64)v88 >= si128.m128i_i64[0] )
      {
        v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v93);
        std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
          (unsigned int)&v78,
          v22,
          v22 + 2 * v23,
          v22,
          *(__int64 *)&_o_towlower);
        std::wstring::substr(v98, v109, 0, si128.m128i_i64[0]);
        if ( !(unsigned int)std::wstring::compare(v109, &v93) )
        {
          Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GlobalPromptEvaluated(
            (_DWORD)v4,
            (unsigned int)v87,
            (unsigned int)v91,
            (unsigned int)v89);
          v24 = (__int128 *)v109;
LABEL_59:
          std::wstring::_Tidy_deallocate(v24);
          std::wstring::_Tidy_deallocate(v98);
          std::wstring::_Tidy_deallocate(v103);
          v25 = (int *)&v93;
LABEL_60:
          std::wstring::_Tidy_deallocate(v25);
LABEL_61:
          std::wstring::_Tidy_deallocate(v89);
          std::wstring::_Tidy_deallocate(v91);
          if ( v75 )
            std::_Ref_count_base::_Decref(v75);
          v12 = 1;
          goto LABEL_88;
        }
        std::wstring::_Tidy_deallocate(v109);
        v21 = v88;
      }
      if ( v21 >= v104 )
      {
        v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v103);
        std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
          (unsigned int)&v78,
          v26,
          v26 + 2 * v27,
          v26,
          *(__int64 *)&_o_towlower);
        std::wstring::substr(v98, v105, 0, v104);
        if ( !(unsigned int)std::wstring::compare(v105, v103) )
        {
          Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GlobalPromptEvaluated(
            (_DWORD)v4,
            (unsigned int)v87,
            (unsigned int)v91,
            (unsigned int)v89);
          v24 = (__int128 *)v105;
          goto LABEL_59;
        }
        std::wstring::_Tidy_deallocate(v105);
      }
      last_of = std::wstring::find_last_of(v98);
      v95 = 0;
      v96 = v16;
      LOWORD(v95) = 0;
      v29 = -1;
      if ( last_of == -1 )
      {
        std::wstring::operator=(&v95, v98);
      }
      else
      {
        v30 = std::wstring::substr(v98, v97, last_of + 1, -1);
        std::wstring::operator=(&v95, v30);
        std::wstring::_Tidy_deallocate(v97);
      }
      if ( !(unsigned int)std::wstring::compare(&v95, L"msedgewebview2.exe")
        || (unsigned __int8)Windows::Internal::CapabilityAccess::Private::SQL::UserShownGlobalPromptForFileIDOrProgramID(
                              (unsigned int)v91,
                              (unsigned int)v89,
                              (int)v4 + 392,
                              (int)v4 + 296,
                              0) )
      {
        Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GlobalPromptEvaluated(
          (_DWORD)v4,
          (unsigned int)v87,
          (unsigned int)v91,
          (unsigned int)v89);
        v24 = &v95;
        goto LABEL_59;
      }
      std::wstring::_Tidy_deallocate(&v95);
      std::wstring::_Tidy_deallocate(v98);
      std::wstring::_Tidy_deallocate(v103);
      std::wstring::_Tidy_deallocate(&v93);
    }
    *(_OWORD *)v100 = 0;
    v101 = 0;
    v102 = 7;
    LOWORD(v100[0]) = 0;
    if ( *((_BYTE *)v4 + 36) )
      goto LABEL_89;
    try
    {
      FriendlyNameFromImageFullPath = Windows::Internal::CapabilityAccess::Private::GetFriendlyNameFromImageFullPath(
                                        v97,
                                        v87);
      std::wstring::operator=(v100, FriendlyNameFromImageFullPath);
      std::wstring::_Tidy_deallocate(v97);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0xDE7,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
        v33);
      v29 = -1;
      v7 = v70;
      v4 = v73;
      v72 = v71;
      v3 = v76;
    }
    if ( v101 )
    {
LABEL_89:
      if ( v72 != 3 )
      {
        std::wstring::wstring(v97, L"Preparing to show One Click Prompt. AppID: %ws, Capability: %ws");
        std::wstring::_Tidy_deallocate(v97);
        v71 = 0;
        GlobalPrompt = Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::CreateGlobalPrompt(
                         (int)v4,
                         v72,
                         (int)v100,
                         (int)v87,
                         (__int64)v91,
                         (__int64)v89,
                         (Windows::Internal::CapabilityAccess::Private *)&v71);
        v36 = v71;
        if ( GlobalPrompt >= 0 && v71 != 6 )
          Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GlobalPromptEvaluated(
            (_DWORD)v4,
            (unsigned int)v87,
            (unsigned int)v91,
            (unsigned int)v89);
        if ( v36 == 1 )
        {
          wil::ThreadFailureCache::ThreadFailureCache((wil::ThreadFailureCache *)v112);
          v72 = 0;
          try
          {
            Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::AdjustConsentToAllowed(v4, v3);
            v37 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v4 + 296);
            LogOneClickPromptAccepted(v37, 0, 0, 0, 0);
          }
          catch ( wil::ResultException )
          {
            Failure = wil::ThreadFailureCache::GetFailure((wil::ThreadFailureCache *)v112);
            v65 = wil::ResultFromCaughtException(v64);
            v66 = (const unsigned __int16 *)std::wstring::c_str((char *)v73 + 296, v65);
            LogOneClickPromptAccepted(
              v66,
              *((const char **)Failure + 7),
              *((_DWORD *)Failure + 16),
              *((const unsigned __int16 **)Failure + 3),
              v67);
            throw;
          }
          v69 = *((_BYTE *)v4 + 37);
          *((_BYTE *)v4 + 37) = 1;
          v80 = v4;
          v81 = (std::_Ref_count_base *)&v69;
          v82 = 1;
          std::wstring::wstring(v106, v87);
          if ( !*((_BYTE *)v4 + 36) )
          {
            v38 = Windows::Internal::CapabilityAccess::Private::SanitizeBinaryFullPath(v97, v87);
            std::wstring::operator=(v106, v38);
            std::wstring::_Tidy_deallocate(v97);
          }
          try
          {
            v40 = Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::ConsentCheck(v4);
            v72 = v40;
          }
          catch ( wil::ResultException )
          {
            v55 = v113;
            if ( v113[2] >= 0 )
              v55 = 0;
            wil::ResultFromCaughtException(v39);
            std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v73 + 232);
            std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v56 + 392);
            std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v57 + 296);
            v58 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v106);
            LogOneClickPromptFollowupAccessCheck(
              v61,
              v58,
              v76,
              v60,
              v62,
              -1,
              -1,
              -1,
              -1,
              -1,
              *((const char **)v55 + 7),
              v55[16],
              *((const unsigned __int16 **)v55 + 3),
              v59);
            v29 = -1;
            v40 = v72;
            v7 = v70;
            v4 = v73;
            v3 = v76;
          }
          Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::GetSystemGlobalConsent(
            *((_QWORD *)v4 + 12),
            &v85);
          v41 = *((_QWORD *)v4 + 12);
          ConsentIdFromObjectId = Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::GetConsentIdFromObjectId(
                                    v41,
                                    v107,
                                    (char *)v4 + 360);
          Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::GetUserGlobalConsent(
            v41,
            &v83,
            (char *)v4 + 392,
            ConsentIdFromObjectId);
          std::wstring::_Tidy_deallocate(v107);
          v43 = *((_QWORD *)v4 + 12);
          std::wstring::wstring(v97, L"NonPackaged");
          v44 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::GetConsentIdFromObjectId(
                  *((_QWORD *)v4 + 12),
                  v110,
                  (char *)v4 + 360);
          Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::GetUserAppConsent(
            v43,
            (unsigned int)&v78,
            (_DWORD)v4 + 392,
            v44,
            (__int64)v97,
            0);
          std::wstring::_Tidy_deallocate(v110);
          std::wstring::_Tidy_deallocate(v97);
          if ( *((_BYTE *)v4 + 36) )
          {
            v45 = *((_QWORD *)v4 + 12);
            v46 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::GetConsentIdFromObjectId(
                    v45,
                    v111,
                    (char *)v4 + 360);
            v47 = v7 | 0x10;
            v70 = v47;
            UserAppConsent = (std::_Ref_count_base **)Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::GetUserAppConsent(
                                                        v45,
                                                        (unsigned int)v107,
                                                        (int)v4 + 392,
                                                        v46,
                                                        (__int64)v4 + 168,
                                                        0);
            v49 = v47 | 0x20;
            v50 = *UserAppConsent;
          }
          else
          {
            v81 = 0;
            UserAppConsent = &v80;
            v49 = v7 | 0x40;
            v50 = 0;
          }
          v73 = UserAppConsent[1];
          *UserAppConsent = 0;
          UserAppConsent[1] = 0;
          if ( (v49 & 0x40) != 0 )
          {
            v49 &= ~0x40u;
            if ( v81 )
              std::_Ref_count_base::_Decref(v81);
          }
          if ( (v49 & 0x20) != 0 )
          {
            v49 &= ~0x20u;
            if ( v108 )
              std::_Ref_count_base::_Decref(v108);
          }
          if ( (v49 & 0x10) != 0 )
            std::wstring::_Tidy_deallocate(v111);
          if ( v50 )
            v29 = *((_DWORD *)v50 + 48);
          std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v4 + 232);
          std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v4 + 392);
          std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v4 + 296);
          v51 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v106);
          LogOneClickPromptFollowupAccessCheck(
            v53,
            v51,
            v3,
            v52,
            v54,
            v40,
            *(_DWORD *)(v85 + 192),
            *(_DWORD *)(v83 + 192),
            *(_DWORD *)(v78 + 192),
            v29,
            0,
            0,
            0,
            0);
          if ( v73 )
            std::_Ref_count_base::_Decref(v73);
          if ( v79 )
            std::_Ref_count_base::_Decref(v79);
          if ( v84 )
            std::_Ref_count_base::_Decref(v84);
          if ( v86 )
            std::_Ref_count_base::_Decref(v86);
          std::wstring::_Tidy_deallocate(v106);
          *((_BYTE *)v4 + 37) = v69;
          wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v112);
          std::wstring::_Tidy_deallocate(v100);
          std::wstring::_Tidy_deallocate(v89);
          std::wstring::_Tidy_deallocate(v91);
          if ( v75 )
            std::_Ref_count_base::_Decref(v75);
          v12 = 3;
          goto LABEL_88;
        }
        v12 = Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::AccessCheckStatusFromCapabilityConsentValue(v36);
        std::wstring::_Tidy_deallocate(v100);
        goto LABEL_44;
      }
      std::enable_shared_from_this<Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager>::shared_from_this(
        (char *)v4 + 8,
        &v78);
      std::wstring::wstring(v97, L"Preparing to show Global Prompt. AppID: %ws, Capability: %ws");
      std::wstring::_Tidy_deallocate(v97);
      v34 = lambda_9943b74eda4322ef4fce8fea90f98e64_::_lambda_9943b74eda4322ef4fce8fea90f98e64__0(
              (unsigned int)v112,
              (unsigned int)&v77,
              (unsigned int)v87,
              (unsigned int)&v78,
              (__int64)v4,
              (__int64)&v71,
              (__int64)v100,
              (__int64)v91,
              (__int64)v89);
      std::thread::thread__lambda_9943b74eda4322ef4fce8fea90f98e64__0_(&v80, v34);
      lambda_9943b74eda4322ef4fce8fea90f98e64_::__lambda_9943b74eda4322ef4fce8fea90f98e64_(v112);
      std::thread::detach((std::thread *)&v80);
      std::thread::~thread((std::thread *)&v80);
      if ( v79 )
        std::_Ref_count_base::_Decref(v79);
      v25 = v100;
      goto LABEL_60;
    }
    std::wstring::_Tidy_deallocate(v100);
    std::wstring::_Tidy_deallocate(v89);
    std::wstring::_Tidy_deallocate(v91);
LABEL_85:
    if ( v75 )
      std::_Ref_count_base::_Decref(v75);
    v12 = 2;
    goto LABEL_88;
  }
  std::wstring::wstring(v97, L"Test AutoAccept key is set - skipping showing Global Prompt");
  std::wstring::_Tidy_deallocate(v97);
  Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::AdjustConsentToAllowed(v4, v3);
  Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GlobalPromptEvaluated(
    (_DWORD)v4,
    (unsigned int)v87,
    (unsigned int)v91,
    (unsigned int)v89);
LABEL_44:
  std::wstring::_Tidy_deallocate(v89);
  std::wstring::_Tidy_deallocate(v91);
  if ( v75 )
    std::_Ref_count_base::_Decref(v75);
LABEL_88:
  std::wstring::_Tidy_deallocate(v87);
  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_ReleaseSemaphore_details_wil__YAX0_ZU__integral_constant__K_01_wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v77);
  return v12;
}

```

## disassembly

```asm
0x18006cbe4  mov     rax, rsp
0x18006cbe7  push    rbx
0x18006cbe8  push    rsi
0x18006cbe9  push    rdi
0x18006cbea  push    r12
0x18006cbec  push    r13
0x18006cbee  push    r14
0x18006cbf0  push    r15
0x18006cbf2  sub     rsp, 800h
0x18006cbf9  movaps  xmmword ptr [rax-48h], xmm6
0x18006cbfd  mov     rax, cs:__security_cookie
0x18006cc04  xor     rax, rsp
0x18006cc07  mov     [rsp+838h+var_58], rax
0x18006cc0f  mov     r13d, r8d
0x18006cc12  mov     [rsp+838h+var_7B8], edx
0x18006cc19  mov     rsi, rcx
0x18006cc1c  mov     [rsp+838h+var_7B0], rcx
0x18006cc24  mov     [rsp+838h+var_7C0], edx
0x18006cc28  mov     [rsp+838h+var_798], r8d
0x18006cc30  xor     edi, edi
0x18006cc32  mov     [rsp+838h+var_7C4], edi
0x18006cc36  mov     eax, cs:?m_initializationState@GlobalManager@Globals@Private@CapabilityAccess@Internal@Windows@@0U?$atomic@K@std@@A; std::atomic<ulong> Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState
0x18006cc3c  nop
0x18006cc3d  mov     rcx, [rsp+838h]; this
0x18006cc45  lea     r15d, [rdi+1]
0x18006cc49  cmp     eax, r15d
0x18006cc4c  jb      loc_18006DDAB
0x18006cc52  xor     r9d, r9d
0x18006cc55  lea     rdx, [rsp+838h+var_790]
0x18006cc5d  lea     rcx, ?m_globalPromptSemaphore@SemaphoreManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A
0x18006cc64  call    ?acquire@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18006cc69  nop
0x18006cc6a  cmp     [rsp+838h+var_790], rdi
0x18006cc72  jnz     short loc_18006CC8B
0x18006cc74  lea     rcx, [rsp+838h+var_790]
0x18006cc7c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006cc81  mov     eax, 2
0x18006cc86  jmp     loc_18006D26B
0x18006cc8b  cmp     [rsi+24h], dil
0x18006cc8f  jz      short loc_18006CCAE
0x18006cc91  lea     rdx, [rsi+0A8h]
0x18006cc98  lea     rcx, [rsp+838h+var_620]
0x18006cca0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18006cca5  nop
0x18006cca6  mov     r14d, 4
0x18006ccac  jmp     short loc_18006CCC4
0x18006ccae  mov     edx, [rsi+30h]
0x18006ccb1  lea     rcx, [rsp+838h+var_6A0]
0x18006ccb9  call    ?GetImageFullPathFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(ulong)
0x18006ccbe  mov     r14d, 8
0x18006ccc4  mov     [rsp+838h+var_7C4], r14d
0x18006ccc9  xorps   xmm0, xmm0
0x18006cccc  movups  xmmword ptr [rsp+838h+var_740], xmm0
0x18006ccd4  xorps   xmm1, xmm1
0x18006ccd7  movdqu  [rsp+838h+var_730], xmm1
0x18006cce0  movups  xmm0, xmmword ptr [rax]
0x18006cce3  movups  xmmword ptr [rsp+838h+var_740], xmm0
0x18006cceb  movups  xmm1, xmmword ptr [rax+10h]
0x18006ccef  movups  [rsp+838h+var_730], xmm1
0x18006ccf7  mov     [rax+10h], rdi
0x18006ccfb  mov     r12d, 7
0x18006cd01  mov     [rax+18h], r12
0x18006cd05  mov     [rax], di
0x18006cd08  test    r14b, 8
0x18006cd0c  jz      short loc_18006CD25
0x18006cd0e  and     r14d, 0FFFFFFF7h
0x18006cd12  mov     [rsp+838h+var_7C4], r14d
0x18006cd17  lea     rcx, [rsp+838h+var_6A0]
0x18006cd1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006cd24  nop
0x18006cd25  test    r14b, 4
0x18006cd29  jz      short loc_18006CD41
0x18006cd2b  and     r14d, 0FFFFFFFBh
0x18006cd2f  mov     [rsp+838h+var_7C4], r14d
0x18006cd34  lea     rcx, [rsp+838h+var_620]
0x18006cd3c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006cd41  mov     rax, [rsi+80h]
0x18006cd48  cmp     [rax+33h], dil
0x18006cd4c  jz      loc_18006D24D
0x18006cd52  cmp     [rsi+29h], dil
0x18006cd56  jz      loc_18006D24D
0x18006cd5c  lea     rcx, [rsp+838h+var_7A8]
0x18006cd64  call    ?Instance@?$SingletonWithFactory@VCapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore>>::Instance(void)
0x18006cd69  nop
0x18006cd6a  cmp     [rsi+24h], dil
0x18006cd6e  jz      short loc_18006CD99
0x18006cd70  lea     r9, [rsi+128h]
0x18006cd77  lea     r8, [rsi+188h]
0x18006cd7e  lea     rdx, [rsp+838h+var_740]
0x18006cd86  call    ?UserShownGlobalPromptForPackage@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::UserShownGlobalPromptForPackage(std::wstring const &,std::wstring const &,std::wstring const &)
0x18006cd8b  test    al, al
0x18006cd8d  jnz     short loc_18006CDBC
0x18006cd8f  cmp     [rsi+24h], dil
0x18006cd93  jnz     loc_18006CEC2
0x18006cd99  lea     r9, [rsi+128h]
0x18006cda0  lea     r8, [rsi+188h]
0x18006cda7  lea     rdx, [rsp+838h+var_740]
0x18006cdaf  call    ?UserShownGlobalPromptForBinaryFullPath@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::UserShownGlobalPromptForBinaryFullPath(std::wstring const &,std::wstring const &,std::wstring const &)
0x18006cdb4  test    al, al
0x18006cdb6  jz      loc_18006CEC2
0x18006cdbc  cmp     [rsi+24h], dil
0x18006cdc0  jnz     loc_18006D23A
0x18006cdc6  mov     eax, cs:?m_initializationState@GlobalManager@Globals@Private@CapabilityAccess@Internal@Windows@@0U?$atomic@K@std@@A; std::atomic<ulong> Windows::Internal::CapabilityAccess::Private::Globals::GlobalManager::m_initializationState
0x18006cdcc  nop
0x18006cdcd  mov     rcx, [rsp+838h]; this
0x18006cdd5  cmp     eax, r15d
0x18006cdd8  jb      loc_18006DDC3
0x18006cdde  xor     r9d, r9d
0x18006cde1  lea     rdx, [rsp+838h+var_7B0]
0x18006cde9  lea     rcx, ?m_globalPromptCompatIDRecordingSemaphore@SemaphoreManager@Globals@Private@CapabilityAccess@Internal@Windows@@0V?$unique_any_t@V?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@@wil@@A
0x18006cdf0  call    ?acquire@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@2@PEAKKH@Z
0x18006cdf5  nop
0x18006cdf6  cmp     [rsp+838h+var_7B0], rdi
0x18006cdfe  jz      loc_18006CEB0
0x18006ce04  lea     rcx, [rsi+8]
0x18006ce08  lea     rdx, [rsp+838h+var_778]
0x18006ce10  call    ?shared_from_this@?$enable_shared_from_this@VCapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@@std@@QEAA?AV?$shared_ptr@VCapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@@2@XZ; std::enable_shared_from_this<Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager>::shared_from_this(void)
0x18006ce15  nop
0x18006ce16  lea     rax, [rsi+128h]
0x18006ce1d  lea     rcx, [rsi+188h]
0x18006ce24  lea     rdx, [rsp+838h+var_7C0]
0x18006ce29  mov     qword ptr [rsp+838h+var_800], rdx
0x18006ce2e  mov     [rsp+838h+var_808], rsi
0x18006ce33  mov     [rsp+838h+var_810], rax
0x18006ce38  mov     [rsp+838h+var_818], rcx
0x18006ce3d  lea     r9, [rsp+838h+var_778]
0x18006ce45  lea     r8, [rsp+838h+var_740]
0x18006ce4d  lea     rdx, [rsp+838h+var_7B0]
0x18006ce55  lea     rcx, [rsp+838h+var_558]
0x18006ce5d  call    _lambda_588d46ef73bdd48b5ef5b5308c2d69e6____lambda_588d46ef73bdd48b5ef5b5308c2d69e6_
0x18006ce62  nop
0x18006ce63  mov     rdx, rax
0x18006ce66  lea     rcx, [rsp+838h+var_788]
0x18006ce6e  call    std__thread__thread__lambda_588d46ef73bdd48b5ef5b5308c2d69e6__0_
0x18006ce73  nop
0x18006ce74  lea     rcx, [rsp+838h+var_558]
0x18006ce7c  call    _lambda_588d46ef73bdd48b5ef5b5308c2d69e6_____lambda_588d46ef73bdd48b5ef5b5308c2d69e6_
0x18006ce81  lea     rcx, [rsp+838h+var_788]; this
0x18006ce89  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x18006ce8e  nop
0x18006ce8f  lea     rcx, [rsp+838h+var_788]; this
0x18006ce97  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18006ce9c  nop
0x18006ce9d  mov     rcx, [rsp+838h+var_770]; this
0x18006cea5  test    rcx, rcx
0x18006cea8  jz      short loc_18006CEB0
0x18006ceaa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006ceaf  nop
0x18006ceb0  lea     rcx, [rsp+838h+var_7B0]
0x18006ceb8  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?ReleaseSemaphore@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18006cebd  jmp     loc_18006D23A
0x18006cec2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CM_OneClick@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CM_OneClick@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CM_OneClick> `wil::Feature<__WilFeatureTraits_Feature_CM_OneClick>::GetImpl(void)'::`2'::impl
0x18006cec9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CM_OneClick@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CM_OneClick>::__private_IsEnabled(void)
0x18006cece  test    al, al
0x18006ced0  jz      short loc_18006CEF8
0x18006ced2  mov     ebx, 3
0x18006ced7  cmp     r13d, ebx
0x18006ceda  jz      short loc_18006CF18
0x18006cedc  lea     r8, [rsi+128h]
0x18006cee3  lea     rdx, [rsi+188h]
0x18006ceea  call    ?GetShowGlobalPrompts@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetShowGlobalPrompts(std::wstring const &,std::wstring const &)
0x18006ceef  test    al, al
0x18006cef1  jnz     short loc_18006CF18
0x18006cef3  jmp     loc_18006D23A
0x18006cef8  lea     r8, [rsi+128h]
0x18006ceff  lea     rdx, [rsi+188h]
0x18006cf06  call    ?GetShowGlobalPrompts@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetShowGlobalPrompts(std::wstring const &,std::wstring const &)
0x18006cf0b  test    al, al
0x18006cf0d  jz      loc_18006D23A
0x18006cf13  mov     ebx, 3
0x18006cf18  cmp     [rsi+25h], dil
0x18006cf1c  jnz     loc_18006D7C5
0x18006cf22  cmp     [rsi+27h], dil
0x18006cf26  jnz     loc_18006D7C5
0x18006cf2c  cmp     [rsi+24h], dil
0x18006cf30  jz      short loc_18006CF54
0x18006cf32  lea     rdx, [rsp+838h+var_740]
0x18006cf3a  mov     rcx, [rsi+80h]
0x18006cf41  call    ?ShowGlobalPromptForApp@CapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::ShowGlobalPromptForApp(std::wstring const &)
0x18006cf46  test    al, al
0x18006cf48  jz      short loc_18006CF6C
0x18006cf4a  cmp     [rsi+24h], dil
0x18006cf4e  jnz     loc_18006CFE2
0x18006cf54  lea     rdx, [rsp+838h+var_740]
0x18006cf5c  mov     rcx, [rsi+80h]
0x18006cf63  call    ?ShowGlobalPromptForBinaryFullPath@CapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::ShowGlobalPromptForBinaryFullPath(std::wstring const &)
0x18006cf68  test    al, al
0x18006cf6a  jnz     short loc_18006CFE2
0x18006cf6c  xorps   xmm0, xmm0
0x18006cf6f  movups  [rsp+838h+var_6E0], xmm0
0x18006cf77  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18006cf7f  movdqu  [rsp+838h+var_6D0], xmm1
0x18006cf88  mov     word ptr [rsp+838h+var_6E0], di
0x18006cf90  movups  [rsp+838h+var_6C0], xmm0
0x18006cf98  movdqu  [rsp+838h+var_6B0], xmm1
0x18006cfa1  mov     word ptr [rsp+838h+var_6C0], di
0x18006cfa9  mov     dword ptr [rsp+838h+var_810], r15d
0x18006cfae  lea     r9, [rsp+838h+var_6E0]
0x18006cfb6  lea     r8, [rsp+838h+var_6C0]
0x18006cfbe  lea     rdx, [rsp+838h+var_740]
0x18006cfc6  mov     rcx, rsi
0x18006cfc9  call    ?GlobalPromptEvaluated@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4GlobalPrompt@2345@W4GlobalPromptSkippedJustification@2345@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GlobalPromptEvaluated(std::wstring const &,std::wstring const &,std::wstring const &,Windows::Internal::CapabilityAccess::Private::GlobalPrompt,Windows::Internal::CapabilityAccess::Private::GlobalPromptSkippedJustification)
0x18006cfce  nop
0x18006cfcf  lea     rcx, [rsp+838h+var_6C0]
0x18006cfd7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006cfdc  nop
0x18006cfdd  jmp     loc_18006D0B1
0x18006cfe2  mov     dl, r15b
0x18006cfe5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_HideSystemPackages@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_HideSystemPackages@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HideSystemPackages> `wil::Feature<__WilFeatureTraits_Feature_HideSystemPackages>::GetImpl(void)'::`2'::impl
0x18006cfec  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_HideSystemPackages@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HideSystemPackages>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18006cff1  cmp     [rsi+24h], dil
0x18006cff5  jz      loc_18006D0BE
0x18006cffb  lea     r8, [rsi+188h]
0x18006d002  lea     rdx, [rsp+838h+var_740]
0x18006d00a  mov     rcx, [rsi+80h]
0x18006d011  call    ?UserAppConsentRequiredForApp@CapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::UserAppConsentRequiredForApp(std::wstring const &,std::wstring const &)
0x18006d016  test    al, al
0x18006d018  jz      short loc_18006D03D
0x18006d01a  mov     r8, [rsi+1B0h]
0x18006d021  lea     rdx, [rsp+838h+var_740]
0x18006d029  mov     rcx, [rsi+80h]
0x18006d030  call    ?UserConsentRequiredForApp@CapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::UserConsentRequiredForApp(std::wstring const &,unsigned __int64)
0x18006d035  test    al, al
0x18006d037  jnz     loc_18006D0BE
0x18006d03d  xorps   xmm0, xmm0
0x18006d040  movups  [rsp+838h+var_6E0], xmm0
0x18006d048  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18006d050  movdqu  [rsp+838h+var_6D0], xmm1
0x18006d059  mov     word ptr [rsp+838h+var_6E0], di
0x18006d061  movups  [rsp+838h+var_6C0], xmm0
0x18006d069  movdqu  [rsp+838h+var_6B0], xmm1
0x18006d072  mov     word ptr [rsp+838h+var_6C0], di
0x18006d07a  mov     dword ptr [rsp+838h+var_810], 0Ah
0x18006d082  lea     r9, [rsp+838h+var_6E0]
0x18006d08a  lea     r8, [rsp+838h+var_6C0]
0x18006d092  lea     rdx, [rsp+838h+var_740]
0x18006d09a  mov     rcx, rsi
0x18006d09d  call    ?GlobalPromptEvaluated@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4GlobalPrompt@2345@W4GlobalPromptSkippedJustification@2345@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GlobalPromptEvaluated(std::wstring const &,std::wstring const &,std::wstring const &,Windows::Internal::CapabilityAccess::Private::GlobalPrompt,Windows::Internal::CapabilityAccess::Private::GlobalPromptSkippedJustification)
0x18006d0a2  nop
0x18006d0a3  lea     rcx, [rsp+838h+var_6C0]
0x18006d0ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d0b0  nop
0x18006d0b1  lea     rcx, [rsp+838h+var_6E0]
0x18006d0b9  jmp     loc_18006D234
0x18006d0be  xorps   xmm0, xmm0
0x18006d0c1  movups  xmmword ptr [rsp+838h+var_700], xmm0
0x18006d0c9  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18006d0d1  movdqu  [rsp+838h+var_6F0], xmm6
0x18006d0da  mov     word ptr [rsp+838h+var_700], di
0x18006d0e2  movups  xmmword ptr [rsp+838h+var_720], xmm0
0x18006d0ea  movdqu  [rsp+838h+var_710], xmm6
0x18006d0f3  mov     word ptr [rsp+838h+var_720], di
0x18006d0fb  cmp     [rsi+24h], dil
0x18006d0ff  jnz     short loc_18006D11E
0x18006d101  lea     r8, [rsp+838h+var_720]
0x18006d109  lea     rdx, [rsp+838h+var_700]
0x18006d111  lea     rcx, [rsp+838h+var_740]
0x18006d119  call    ?GetFileProgramIDByBinaryFullPath@Private@CapabilityAccess@Internal@Windows@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV56@1@Z; Windows::Internal::CapabilityAccess::Private::GetFileProgramIDByBinaryFullPath(std::wstring const &,std::wstring &,std::wstring &)
0x18006d11e  cmp     [rsi+70h], rdi
0x18006d122  jz      loc_18006D296
0x18006d128  call    ?IsAutoAcceptConsentPromptsEnabled@CapabilityConsentPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA_NXZ; Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore::IsAutoAcceptConsentPromptsEnabled(void)
0x18006d12d  test    al, al
0x18006d12f  jz      loc_18006D1C1
0x18006d135  lea     rdx, aTestAutoaccept; "Test AutoAccept key is set - skipping s"...
0x18006d13c  lea     rcx, [rsp+838h+var_6A0]
0x18006d144  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006d149  lea     rcx, [rsp+838h+var_6A0]
0x18006d151  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d156  mov     edx, r13d
0x18006d159  mov     rcx, rsi
0x18006d15c  call    ?AdjustConsentToAllowed@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@AEAAXW4UserConsentSwitch@2345@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::AdjustConsentToAllowed(Windows::Internal::CapabilityAccess::Private::UserConsentSwitch)
0x18006d161  mov     dword ptr [rsp+838h+var_810], 2
0x18006d169  lea     r9, [rsp+838h+var_720]
0x18006d171  lea     r8, [rsp+838h+var_700]
0x18006d179  lea     rdx, [rsp+838h+var_740]
0x18006d181  mov     rcx, rsi
0x18006d184  call    ?GlobalPromptEvaluated@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4GlobalPrompt@2345@W4GlobalPromptSkippedJustification@2345@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::GlobalPromptEvaluated(std::wstring const &,std::wstring const &,std::wstring const &,Windows::Internal::CapabilityAccess::Private::GlobalPrompt,Windows::Internal::CapabilityAccess::Private::GlobalPromptSkippedJustification)
0x18006d189  nop
0x18006d18a  lea     rcx, [rsp+838h+var_720]
0x18006d192  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d197  nop
0x18006d198  lea     rcx, [rsp+838h+var_700]
0x18006d1a0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d1a5  nop
0x18006d1a6  mov     rcx, [rsp+838h+var_7A0]; this
0x18006d1ae  test    rcx, rcx
0x18006d1b1  jz      loc_18006D7DC
0x18006d1b7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18006d1bc  jmp     loc_18006D7DC
0x18006d1c1  cmp     [rsi+70h], rdi
0x18006d1c5  jz      loc_18006D296
0x18006d1cb  call    ?IsAutoDenyConsentPromptsEnabled@CapabilityConsentPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA_NXZ; Windows::Internal::CapabilityAccess::Private::CapabilityConsentPolicyStore::IsAutoDenyConsentPromptsEnabled(void)
0x18006d1d0  test    al, al
0x18006d1d2  jz      loc_18006D296
0x18006d1d8  lea     rdx, aTestAutodenyKe; "Test AutoDeny key is set - skipping sho"...
0x18006d1df  lea     rcx, [rsp+838h+var_6A0]
0x18006d1e7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18006d1ec  lea     rcx, [rsp+838h+var_6A0]
0x18006d1f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006d1f9  mov     dword ptr [rsp+838h+var_810], ebx
  ... truncated ...
```
