# Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::AccessCheck(void)

- ea: `0x18006874c`
- end: `0x180069ca6`
- name: `?AccessCheck@CapabilityAccessManager@Private@CapabilityAccess@Internal@Windows@@QEAA?AW4AccessCheckStatus@2345@XZ`
- size: `5466`
- prototype: ``
- caller_count: `8`
- callee_count: `64`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18005e77c`
- `0x18006874c`
- `0x1800919c0`
- `0x1800b5054`
- `0x1800b50a4`
- `0x1800b56a0`
- `0x1800b5c30`
- `0x1800b5d70`

## callees

- `0x1800094c0`
- `0x180016490`
- `0x18001649c`
- `0x180016cb0`
- `0x180017bc4`
- `0x18001c3b4`
- `0x18001d00c`
- `0x18001e118`
- `0x18001e42c`
- `0x18002392c`
- `0x1800257a4`
- `0x180026fac`
- `0x18002735c`
- `0x180029304`
- `0x180029408`
- `0x18002c970`
- `0x18002e304`
- `0x18002f260`
- `0x18002f93c`
- `0x18002f978`
- `0x1800365c8`
- `0x180038894`
- `0x180039e9c`
- `0x18003ae98`
- `0x18003b2c0`
- `0x18003fe80`
- `0x180041e2c`
- `0x180041f2c`
- `0x180042fe8`
- `0x180043c44`
- `0x180043ebc`
- `0x180044664`
- `0x180045434`
- `0x18004657c`
- `0x180046610`
- `0x18005319c`
- `0x18005326c`
- `0x18005333c`
- `0x180053490`
- `0x1800572b4`
- `0x180057384`
- `0x1800579a4`
- `0x180057ab0`
- `0x1800581a8`
- `0x18005829c`
- `0x180058dfc`
- `0x18006632c`
- `0x180066fec`
- `0x180067158`
- `0x180067190`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x180068c22`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180069153`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x180069153`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180069485`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x180069485`
- `ntdll!RtlInitUnicodeString` at `0x180069467`
- `ntdll!RtlInitUnicodeString` at `0x180069467`
- `api-ms-win-appmodel-unlock-l1-1-0!IsDeveloperModeEnabled` at `0x180068921`
- `api-ms-win-appmodel-unlock-l1-1-0!IsDeveloperModeEnabled` at `0x180068921`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x180069161`
- `api-ms-win-core-kernel32-legacy-l1-1-0!WTSGetActiveConsoleSessionId` at `0x180069161`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1800694c7`
- `api-ms-win-appmodel-identity-l1-2-0!AppContainerDeriveSidFromMoniker` at `0x1800694c7`

## string_xrefs

- `0x180068fbf`: `Software\Microsoft\Windows\CurrentVersion\CapabilityAccessManager`
- `0x180069bb2`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x180069bc7`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x180069bdb`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x180069c43`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x180069c54`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x180069c6c`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x180069c81`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x180069c93`: `onecore\base\devices\cam\core\capabilityaccessmanager.cpp`
- `0x1800687c5`: `PID:%d, TID:%d, SID:%ws, Packaged:%d, PFN:%ws, Full Trust:%d, Interactive:%d, Capability:%ws`
- `0x1800689bb`: `Access is blocked due to blockAccess policy`
- `0x18006893e`: `Access is blocked due to requireDeveloperMode policy`
- `0x180068ab9`: `Access is Allowed - caller is an Agentic session, and capability is on the Always Allow list.`
- `0x180068a28`: `Access is blocked due to alwaysBlockNonPackaged policy`
- `0x180068c90`: `Access is blocked due to alwaysBlockAccess policy`
- `0x180068b0a`: `Access is blocked - caller is an Agentic session, and capability is not on the allow-list.`
- `0x180068e8b`: `Handler AccessCheck returned '%ws'`
- `0x180068d96`: `Access is blocked due to requireWindowsCert policy`
- `0x18006902d`: `Handler cancelled the access check. Returning 'Allowed'`
- `0x180068f34`: `Handler returned 'ForceAllow', stopping Access Check and returning 'Allowed'`
- `0x180069bec`: `Capability specifies requireActiveSessionForInteractiveUsers, but attempted to do an AccessCheck without process information`
- `0x180068fd6`: `'SkipCapabilityHandlerCancel' set in registry. Skipping cancel call to handler.`
- `0x180069525`: `App is in permissive learning mode. Log access check failure and grant access even though the app doesn't have required '%ws' capability.`
- `0x180069807`: `Service does not require consent, skipping consent check`
- `0x180069a3a`: `AccessCheck passed for base capability, but a required capability was not authorized. Returning %ws`
- `0x180069971`: `Access check returning with '%ws'`
- `0x180069abc`: `Access check passed. Returning 'Allowed'`

## pseudocode

```c
// Hidden C++ exception states: #wind=47
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::AccessCheck(__int64 a1)
{
  int v2; // r14d
  char v3; // si
  __int64 v4; // rdx
  Windows::Internal::CapabilityAccess::Private *v5; // rcx
  __int64 v6; // rax
  __int64 result; // rax
  volatile signed __int32 *v8; // rdx
  volatile signed __int32 *v9; // rdi
  __int64 v10; // r13
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 ImageFullPathFromProcessId; // rax
  int v17; // eax
  __int64 SvchostPath; // rax
  __int64 v19; // rax
  wil::details::in1diag3 *v20; // rcx
  __int64 v21; // rdi
  __int64 v22; // rax
  char v23; // di
  char v24; // r15
  __int64 v25; // rdi
  __int64 v26; // rdx
  __int64 v27; // r11
  int v28; // eax
  int v29; // eax
  __int64 v30; // rax
  unsigned int v31; // edx
  DWORD v32; // ecx
  __int64 v33; // rdi
  __int64 ConsentIdFromObjectId; // rax
  const char *v35; // r9
  __int64 v36; // rsi
  __int64 v37; // rdi
  __int64 v38; // rax
  __int64 v39; // rdx
  __int64 v40; // r8
  const char *v41; // r9
  __int64 v42; // rax
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // r10
  __int64 *v46; // r8
  char HasCapability; // r12
  const WCHAR *v48; // rax
  int v49; // eax
  __int64 v50; // rax
  int v51; // eax
  int v52; // eax
  __int64 v53; // rdx
  __int64 v54; // rax
  __int64 v55; // r10
  __int64 v56; // rax
  __int64 v57; // rdi
  __int64 v58; // r13
  __int64 v59; // rax
  __int64 v60; // r10
  __int64 v61; // rax
  char v62; // r12
  __int64 v63; // rcx
  int v64; // r14d
  unsigned int v65; // esi
  Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager **v66; // rsi
  Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager **v67; // r12
  unsigned int v68; // r14d
  unsigned int v69; // eax
  __int64 v70; // rdi
  char v71; // r14
  __int64 v72; // rax
  int v73; // ebx
  wil *v74; // rcx
  int v75; // eax
  __int64 v76; // rdi
  char v77; // r14
  __int64 v78; // rax
  int v79; // ebx
  unsigned int v80; // eax
  const struct wil::FailureInfo *Failure; // rax
  __int64 v82; // rdx
  unsigned int v83; // r15d
  char *v84; // r12
  __int64 v85; // rbx
  char v86; // r13
  int v87; // r14d
  __int64 v88; // rax
  int v89; // esi
  __int64 v90; // rdi
  wil *v91; // rcx
  int v92; // eax
  const struct wil::FailureInfo *v93; // rax
  __int64 v94; // rdx
  unsigned int v95; // r15d
  char *v96; // r12
  __int64 v97; // rsi
  char v98; // r13
  int v99; // r14d
  __int64 v100; // rax
  int v101; // edi
  __int64 v102; // rbx
  unsigned int v103; // eax
  int v104; // [rsp+20h] [rbp-278h]
  int v105; // [rsp+20h] [rbp-278h]
  bool *v106; // [rsp+20h] [rbp-278h]
  int v107; // [rsp+40h] [rbp-258h] BYREF
  unsigned int v108; // [rsp+44h] [rbp-254h]
  LPVOID pv; // [rsp+48h] [rbp-250h] BYREF
  _BYTE v110[8]; // [rsp+50h] [rbp-248h] BYREF
  DWORD pSessionId[2]; // [rsp+58h] [rbp-240h] BYREF
  _QWORD v112[3]; // [rsp+60h] [rbp-238h] BYREF
  char v113; // [rsp+78h] [rbp-220h]
  PSID Sid[2]; // [rsp+80h] [rbp-218h] BYREF
  __int64 v115; // [rsp+90h] [rbp-208h]
  struct _UNICODE_STRING DestinationString; // [rsp+98h] [rbp-200h] BYREF
  _BYTE v117[224]; // [rsp+B0h] [rbp-1E8h] BYREF
  __int128 v118; // [rsp+190h] [rbp-108h] BYREF
  __int128 v119; // [rsp+1A0h] [rbp-F8h]
  _BYTE v120[32]; // [rsp+1B0h] [rbp-E8h] BYREF
  __int128 v121; // [rsp+1D0h] [rbp-C8h] BYREF
  __m128i si128; // [rsp+1E0h] [rbp-B8h]
  _BYTE v123[64]; // [rsp+1F0h] [rbp-A8h] BYREF
  _BYTE v124[48]; // [rsp+230h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+298h] [rbp+0h]

  v115 = a1;
  v2 = 0;
  v108 = 0;
  v3 = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids);
  }
  std::wstring::wstring(
    &v118,
    L"PID:%d, TID:%d, SID:%ws, Packaged:%d, PFN:%ws, Full Trust:%d, Interactive:%d, Capability:%ws");
  std::wstring::_Tidy_deallocate(&v118);
  wil::ThreadFailureCache::ThreadFailureCache((wil::ThreadFailureCache *)v117);
  try
  {
    v107 = 0;
    v6 = *(_QWORD *)(a1 + 128);
    if ( v6 && *(_BYTE *)(v6 + 42) && !Windows::Internal::CapabilityAccess::Private::GetOobeState(v5) )
    {
      wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v117);
      return 3;
    }
    pv = 0;
    LOBYTE(v4) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMBugBundle_Se>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CAMBugBundle_Se>::GetImpl'::`2'::impl,
      v4);
    v8 = *(volatile signed __int32 **)(tip2::start_and_watch_errors<tip2::tip_test<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>>((struct wil::details::IFailureCallback *)v123)
                                     + 56);
    pv = (LPVOID)v8;
    if ( v8 )
      _InterlockedAdd(v8 + 76, 1u);
    tip2::test_watcher<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>::~test_watcher<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>(v123);
    v9 = *(volatile signed __int32 **)tip2::tip_test<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>::ensure_data(&pv);
    Sid[0] = (PSID)v9;
    if ( v9 )
      _InterlockedAdd(v9 + 76, 1u);
    tip2::details::shared_data<1,0,0>::begin_update(v9 + 2);
    v10 = a1 + 296;
    std::wstring::operator=(v9 + 68, a1 + 296);
    tip2::test_data_control<tip2::details::merged_data<_tip_CAMConsentCheckTest,_tip_CAMConsentCheckTest>>::~test_data_control<tip2::details::merged_data<_tip_CAMConsentCheckTest,_tip_CAMConsentCheckTest>>(Sid);
    v112[0] = a1;
    v112[1] = &v107;
    v112[2] = &pv;
    v113 = 1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl'::`2'::impl) )
    {
      v11 = *(_QWORD *)(a1 + 128);
      if ( v11 )
      {
        if ( *(_BYTE *)(v11 + 513) )
        {
          pSessionId[0] = 0;
          v12 = IsDeveloperModeEnabled(pSessionId);
          if ( v12 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x3FE,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
              (const char *)(unsigned int)v12,
              (int)v106);
          if ( !pSessionId[0] )
          {
            std::wstring::wstring(&v118, L"Access is blocked due to requireDeveloperMode policy");
            std::wstring::_Tidy_deallocate(&v118);
            v107 = 0;
            v113 = 0;
            lambda_d8d162e6b268c4497ea9d6dd4f5c31b9_::operator()(v112);
            wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(&pv);
            wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v117);
            return 0;
          }
        }
      }
    }
    v13 = *(_QWORD *)(a1 + 128);
    if ( v13
      && *(_BYTE *)(v13 + 48)
      && !*(_BYTE *)(a1 + 34)
      && (unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::BlockAccessForApp(
                            v13,
                            a1 + 168) )
    {
      std::wstring::wstring(&v118, L"Access is blocked due to blockAccess policy");
      std::wstring::_Tidy_deallocate(&v118);
      v107 = 0;
      v113 = 0;
      lambda_d8d162e6b268c4497ea9d6dd4f5c31b9_::operator()(v112);
      wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(&pv);
      wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v117);
      return 0;
    }
    v14 = *(_QWORD *)(a1 + 128);
    if ( v14 && *(_BYTE *)(v14 + 46) && !*(_BYTE *)(a1 + 36) )
    {
      std::wstring::wstring(&v118, L"Access is blocked due to alwaysBlockNonPackaged policy");
      std::wstring::_Tidy_deallocate(&v118);
      v107 = 0;
      v113 = 0;
      lambda_d8d162e6b268c4497ea9d6dd4f5c31b9_::operator()(v112);
      wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(&pv);
      wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v117);
      return 0;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl'::`2'::impl) )
    {
      v15 = *(_QWORD *)(a1 + 128);
      if ( v15 )
      {
        if ( *(_BYTE *)(a1 + 40) )
        {
          if ( *(_BYTE *)(v15 + 43) )
          {
            std::wstring::wstring(
              &v118,
              L"Access is Allowed - caller is an Agentic session, and capability is on the Always Allow list.");
            std::wstring::_Tidy_deallocate(&v118);
            v107 = 3;
            v113 = 0;
            lambda_d8d162e6b268c4497ea9d6dd4f5c31b9_::operator()(v112);
            wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(&pv);
            wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v117);
            return 3;
          }
          else
          {
            std::wstring::wstring(
              &v118,
              L"Access is blocked - caller is an Agentic session, and capability is not on the allow-list.");
            std::wstring::_Tidy_deallocate(&v118);
            v107 = 0;
            v113 = 0;
            lambda_d8d162e6b268c4497ea9d6dd4f5c31b9_::operator()(v112);
            wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(&pv);
            wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v117);
            return 0;
          }
        }
      }
    }
    if ( !*(_QWORD *)(a1 + 128) )
      goto LABEL_46;
    v121 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v121) = 0;
    if ( !*(_BYTE *)(a1 + 36) )
    {
      ImageFullPathFromProcessId = Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(
                                     &v118,
                                     *(unsigned int *)(a1 + 48));
      std::wstring::operator=(&v121, ImageFullPathFromProcessId);
      std::wstring::_Tidy_deallocate(&v118);
      if ( !*(_BYTE *)(a1 + 36) )
        goto LABEL_255;
    }
    if ( (unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::AlwaysBlockAccessForApp(
                            *(_QWORD *)(a1 + 128),
                            a1 + 168) )
    {
LABEL_41:
      if ( *(_BYTE *)(a1 + 36)
        || (v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v121),
            std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
              (unsigned int)Sid,
              v17,
              v17 + 2 * si128.m128i_i32[0],
              v17,
              *(__int64 *)&_o_towlower),
            SvchostPath = Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::GetSvchostPath(),
            std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(SvchostPath),
            v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&v121),
            !(unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v19, si128.m128i_i64[0]))
        || (unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::AlwaysBlockAccessForServiceHost(
                              *(_QWORD *)(a1 + 128),
                              a1 + 448) )
      {
        std::wstring::wstring(&v118, L"Access is blocked due to alwaysBlockAccess policy");
        std::wstring::_Tidy_deallocate(&v118);
        v107 = 0;
        std::wstring::_Tidy_deallocate(&v121);
        v113 = 0;
        lambda_d8d162e6b268c4497ea9d6dd4f5c31b9_::operator()(v112);
        wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(&pv);
        wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v117);
        return 0;
      }
      goto LABEL_45;
    }
    if ( !*(_BYTE *)(a1 + 36) )
    {
LABEL_255:
      if ( (unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::AlwaysBlockAccessForBinaryFullPath(
                              *(_QWORD *)(a1 + 128),
                              &v121) )
        goto LABEL_41;
    }
LABEL_45:
    std::wstring::_Tidy_deallocate(&v121);
LABEL_46:
    v20 = *(wil::details::in1diag3 **)(a1 + 128);
    if ( !v20 || !*((_BYTE *)v20 + 60) || *(_BYTE *)(a1 + 28) )
      goto LABEL_59;
    if ( !*(_BYTE *)(a1 + 36) )
      goto LABEL_52;
    if ( (unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::RequireWindowsCertForApp(
                            v20,
                            a1 + 168) )
    {
LABEL_53:
      v23 = 1;
      goto LABEL_55;
    }
    if ( !*(_BYTE *)(a1 + 36) )
    {
LABEL_52:
      v21 = *(_QWORD *)(a1 + 128);
      v22 = Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(
              &v118,
              *(unsigned int *)(a1 + 48));
      v2 = 1;
      v108 = 1;
      if ( (unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::RequireWindowsCertForBinaryFullPath(
                              v21,
                              v22) )
        goto LABEL_53;
    }
    v23 = 0;
LABEL_55:
    if ( (v2 & 1) != 0 )
    {
      v2 &= ~1u;
      v108 = v2;
      std::wstring::_Tidy_deallocate(&v118);
    }
    if ( v23 )
    {
      std::wstring::wstring(&v118, L"Access is blocked due to requireWindowsCert policy");
      std::wstring::_Tidy_deallocate(&v118);
      v107 = 0;
      v113 = 0;
      lambda_d8d162e6b268c4497ea9d6dd4f5c31b9_::operator()(v112);
      wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(&pv);
      wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v117);
      return 0;
    }
LABEL_59:
    *(_QWORD *)&v121 = a1;
    *((_QWORD *)&v121 + 1) = &v107;
    v24 = 1;
    si128.m128i_i8[0] = 1;
    v25 = *(_QWORD *)(a1 + 64);
    if ( v25 )
    {
      pSessionId[0] = 1;
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 168);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 360);
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 296);
      v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 392);
      LODWORD(v106) = *(_DWORD *)(a1 + 48);
      v28 = (*(__int64 (__fastcall **)(__int64, __int64))(v27 + 32))(v25, v26);
      if ( v28 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x484,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
          (const char *)(unsigned int)v28,
          (int)v106);
      std::wstring::wstring(&v118, L"Handler AccessCheck returned '%ws'");
      std::wstring::_Tidy_deallocate(&v118);
      if ( !pSessionId[0] )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, &WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids);
        }
        v107 = 0;
        (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 64) + 40LL))(*(_QWORD *)(a1 + 64), 0);
        v113 = 0;
        lambda_d8d162e6b268c4497ea9d6dd4f5c31b9_::operator()(v112);
        wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(&pv);
        wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v117);
        return 0;
      }
      if ( pSessionId[0] == 2 )
      {
        std::wstring::wstring(&v118, L"Handler returned 'ForceAllow', stopping Access Check and returning 'Allowed'");
        std::wstring::_Tidy_deallocate(&v118);
        v107 = 3;
        (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 64) + 40LL))(*(_QWORD *)(a1 + 64), 1);
        v113 = 0;
        lambda_d8d162e6b268c4497ea9d6dd4f5c31b9_::operator()(v112);
        wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(&pv);
        wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v117);
        return 3;
      }
    }
    else
    {
      v24 = 0;
      si128.m128i_i8[0] = 0;
    }
    if ( *(_QWORD *)(a1 + 64) )
    {
      if ( Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
             (Windows::Internal::CapabilityAccess::Private *)0xFFFFFFFF80000002LL,
             (HKEY)L"Software\\Microsoft\\Windows\\CurrentVersion\\CapabilityAccessManager",
             L"SkipCapabilityHandlerCancel",
             0,
             v106) == 1 )
      {
        std::wstring::wstring(&v118, L"'SkipCapabilityHandlerCancel' set in registry. Skipping cancel call to handler.");
        std::wstring::_Tidy_deallocate(&v118);
      }
      else
      {
        v110[0] = 0;
        v29 = (*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 64) + 24LL))(*(_QWORD *)(a1 + 64), v110);
        v20 = retaddr;
        if ( v29 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x4A6,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
            (const char *)(unsigned int)v29,
            (int)v106);
        if ( v110[0] )
        {
          std::wstring::wstring(&v118, L"Handler cancelled the access check. Returning 'Allowed'");
          std::wstring::_Tidy_deallocate(&v118);
          v107 = 3;
          if ( v24 )
            (*(void (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(a1 + 64) + 40LL))(*(_QWORD *)(a1 + 64), 1);
          goto LABEL_179;
        }
      }
    }
    v30 = *(_QWORD *)(a1 + 128);
    if ( v30
      && *(_BYTE *)(v30 + 140)
      && !Windows::Internal::CapabilityAccess::Private::IsEnterpriseMultiSessionEnvironment(v20) )
    {
      v32 = *(_DWORD *)(a1 + 48);
      if ( !v32 )
      {
        std::wstring::wstring(
          &v118,
          L"Capability specifies requireActiveSessionForInteractiveUsers, but attempted to do an AccessCheck without process information");
        std::pair<std::wstring const,unsigned int>::~pair<std::wstring const,unsigned int>(&v118);
        std::wstring::wstring(&v118, L"Returning E_UNPEXPCTED. Process ID must be provided to evaluate this policy");
        std::pair<std::wstring const,unsigned int>::~pair<std::wstring const,unsigned int>(&v118);
        v69 = wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4BC,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
          (const char *)v69,
          (int)v106);
      }
      if ( !*(_BYTE *)(a1 + 41)
        || Windows::Internal::CapabilityAccess::Private::IsProcessRunningInRemoteSession(v32, v31) )
      {
        std::wstring::wstring(
          v120,
          L"Process is running in a remote session - bypassing requireActiveSessionForInteractiveUsers check");
        std::wstring::_Tidy_deallocate(v120);
      }
      else
      {
        v33 = *(_QWORD *)(a1 + 96);
        ConsentIdFromObjectId = Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::GetConsentIdFromObjectId(
                                  v33,
                                  &v118,
                                  a1 + 360);
        LOBYTE(v33) = Windows::Internal::CapabilityAccess::Private::CapabilityConsentManager::IsAppForceAllowedByPolicy(
                        v33,
                        a1 + 232,
                        ConsentIdFromObjectId,
                        a1 + 168);
        std::wstring::_Tidy_deallocate(&v118);
        if ( !(_BYTE)v33 )
        {
          pSessionId[0] = 0;
          if ( !ProcessIdToSessionId(*(_DWORD *)(a1 + 48), pSessionId) )
            wil::details::in1diag3::Throw_GetLastError(
              retaddr,
              (void *)0x4C7,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
              v35);
          if ( pSessionId[0] != WTSGetActiveConsoleSessionId() )
          {
            std::wstring::wstring(
              &v118,
              L"Capability provides RequireActiveSessionForInteractiveUsers and app is in an inactive session. Returning DeniedBySystem");
            std::wstring::_Tidy_deallocate(&v118);
            Sid[0] = &v118;
            v36 = std::wstring::wstring(&v118, a1 + 168);
            Sid[1] = v124;
            v37 = Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(
                    v124,
                    *(unsigned int *)(a1 + 48));
            v38 = std::wstring::wstring(v120, a1 + 296);
            LogAccessDeniedByActiveSessionPolicy(v38, v37, v36);
            v107 = 0;
            if ( v24 )
              (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 64) + 40LL))(*(_QWORD *)(a1 + 64), 0);
LABEL_89:
            v113 = 0;
            lambda_d8d162e6b268c4497ea9d6dd4f5c31b9_::operator()(v112);
            wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(&pv);
            wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v117);
            return 0;
          }
        }
      }
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl'::`2'::impl) )
    {
      v42 = *(_QWORD *)(a1 + 128);
      if ( v42 )
      {
        if ( *(_BYTE *)(v42 + 512) )
        {
          std::wstring::wstring(v120, L"Policy for %ws does not require capability checks. Skipping.");
          std::wstring::_Tidy_deallocate(v120);
          *(_BYTE *)(a1 + 31) = 0;
        }
      }
    }
    if ( *(_BYTE *)(a1 + 36) )
    {
      LOBYTE(v40) = 3;
      LOBYTE(v39) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl'::`2'::impl,
        v39,
        v40);
      v43 = *(_QWORD *)(a1 + 128);
      if ( v43 && *(_BYTE *)(v43 + 59) )
      {
        if ( !(unsigned __int8)Windows::Internal::CapabilityAccess::Private::IsCapabilityExplicitlyAuthorizedForPackage(
                                 a1 + 200,
                                 a1 + 296) )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v44 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 296);
            WPP_SF_S(*(_QWORD *)(v45 + 16), 16, &WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids, v44);
          }
          v107 = 4;
          if ( v24 )
            (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 64) + 40LL))(*(_QWORD *)(a1 + 64), 0);
LABEL_141:
          v113 = 0;
          lambda_d8d162e6b268c4497ea9d6dd4f5c31b9_::operator()(v112);
          wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(&pv);
          wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v117);
          return 4;
        }
      }
      else if ( *(_BYTE *)(a1 + 31) && !*(_BYTE *)(a1 + 34) && *(_BYTE *)(a1 + 41) )
      {
        v46 = (__int64 *)(v43 + 384);
        if ( !v43 )
          v46 = 0;
        if ( !Windows::Internal::CapabilityAccess::Private::PackageHasCapability((void *)(a1 + 200), a1 + 296, v46, 0) )
        {
          std::wstring::wstring(&v118, L"permissiveLearningMode");
          HasCapability = Windows::Internal::CapabilityAccess::Private::PackageHasCapability(
                            (void *)(a1 + 200),
                            (__int64)&v118,
                            0,
                            0);
          std::wstring::_Tidy_deallocate(&v118);
          if ( !HasCapability )
          {
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              v54 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 296);
              WPP_SF_S(*(_QWORD *)(v55 + 16), 17, &WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids, v54);
            }
            v107 = 4;
            if ( v24 )
              (*(void (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 64) + 40LL))(*(_QWORD *)(a1 + 64), 0);
            goto LABEL_141;
          }
          Windows::Internal::CapabilityAccess::Private::GetSidFromSidString(Sid);
          DestinationString = 0;
          v48 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 296);
          RtlInitUnicodeString(&DestinationString, v48);
          v49 = RtlDeriveCapabilitySidsFromName(&DestinationString, v123, v124);
          if ( v49 < 0 )
            wil::details::in1diag3::_Throw_NtStatus(
              retaddr,
              (void *)0x514,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
              (const char *)(unsigned int)v49,
              (int)v106);
          *(_QWORD *)pSessionId = 0;
          wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
            pSessionId,
            0);
          v50 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 168);
          v51 = AppContainerDeriveSidFromMoniker(v50, pSessionId);
          if ( v51 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x518,
              (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
              (const char *)(unsigned int)v51,
              (int)v106);
          if ( (Microsoft_Windows_Privacy_Auditing_PermissiveLearningModeEnableBits & 1) != 0 )
          {
            std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 168);
            v52 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 296);
            McTemplateU0kzkzk_EventWriteTransfer(
              pSessionId[0],
              v53,
              Sid[0],
              v52,
              (__int64)v124,
              v53,
              *(__int64 *)pSessionId);
          }
          std::wstring::wstring(
            v120,
            L"App is in permissive learning mode. Log access check failure and grant access even though the app doesn't ha"
             "ve required '%ws' capability.");
          std::wstring::_Tidy_deallocate(v120);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(pSessionId);
          wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(Sid);
        }
      }
    }
    else if ( *(_BYTE *)(a1 + 31) && !*(_BYTE *)(a1 + 34) )
    {
      if ( (unsigned __int64)(*(_QWORD *)(a1 + 448) - 1LL) > 0xFFFFFFFFFFFFFFFDuLL )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x557,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
          v41);
      if ( !(unsigned __int8)Windows::Internal::CapabilityAccess::Private::CheckTokenCapability(a1 + 448, a1 + 296) )
      {
        v56 = *(_QWORD *)(a1 + 128);
        if ( !v56 )
        {
LABEL_135:
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v59 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10);
            WPP_SF_S(*(_QWORD *)(v60 + 16), 19, &WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids, v59);
          }
          v107 = 4;
          if ( v24 )
            (*(void (__fastcall **)(_QWORD, bool))(**(_QWORD **)(a1 + 64) + 40LL))(*(_QWORD *)(a1 + 64), v107 == 3);
          goto LABEL_141;
        }
        v57 = *(_QWORD *)(v56 + 384);
        v58 = *(_QWORD *)(v56 + 392);
        while ( 1 )
        {
          if ( v57 == v58 )
          {
            v10 = a1 + 296;
            goto LABEL_135;
          }
          if ( (unsigned __int8)Windows::Internal::CapabilityAccess::Private::CheckTokenCapability(a1 + 448, v57) )
            break;
          v57 += 32;
        }
        v10 = a1 + 296;
      }
    }
    v61 = *(_QWORD *)(a1 + 128);
    if ( !v61 )
    {
      v107 = 3;
      if ( v24 )
        (*(void (__fastcall **)(_QWORD, bool))(**(_QWORD **)(a1 + 64) + 40LL))(*(_QWORD *)(a1 + 64), v107 == 3);
      goto LABEL_179;
    }
    if ( *(_BYTE *)(v61 + 50)
      && !Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::IsAppInForeground((Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager *)a1) )
    {
      v107 = 0;
      if ( v24 )
        (*(void (__fastcall **)(_QWORD, bool))(**(_QWORD **)(a1 + 64) + 40LL))(*(_QWORD *)(a1 + 64), v107 == 3);
      goto LABEL_89;
    }
    if ( *(_BYTE *)(a1 + 36) )
    {
      if ( !(unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::UserConsentRequiredForApp(
                               *(_QWORD *)(a1 + 128),
                               a1 + 168,
                               *(_QWORD *)(a1 + 432)) )
      {
        v3 = 0;
        std::wstring::wstring(v120, L"App does not require consent, skipping consent check");
        goto LABEL_155;
      }
      if ( *(_BYTE *)(a1 + 36) )
        goto LABEL_156;
    }
    if ( (unsigned __int8)Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::UserConsentRequiredForServiceHost(
                            *(_QWORD *)(a1 + 128),
                            a1 + 448) )
      goto LABEL_156;
    v3 = 0;
    std::wstring::wstring(v120, L"Service does not require consent, skipping consent check");
LABEL_155:
    std::wstring::_Tidy_deallocate(v120);
LABEL_156:
    std::wstring::wstring(v120, L"consentCheckRequired: %d");
    std::wstring::_Tidy_deallocate(v120);
    if ( v3 )
    {
      try
      {
        v107 = Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::ConsentCheck(a1);
        v62 = *(_BYTE *)(a1 + 29);
        if ( v62 )
        {
          *(_QWORD *)&DestinationString.Length = &v118;
          if ( *(_BYTE *)(a1 + 36) )
          {
            v63 = std::wstring::wstring(v123, a1 + 168);
            v64 = v2 | 2;
          }
          else
          {
            v63 = Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(
                    v124,
                    *(unsigned int *)(a1 + 48));
            v64 = v2 | 4;
          }
          v108 = v64;
          v118 = 0;
          v119 = 0u;
          v118 = *(_OWORD *)v63;
          v119 = *(_OWORD *)(v63 + 16);
          *(_QWORD *)(v63 + 16) = 0;
          *(_QWORD *)(v63 + 24) = 7;
          *(_WORD *)v63 = 0;
          std::wstring::wstring(v120, v10);
          LogConsentCheck(0, v62);
          if ( (v64 & 4) != 0 )
          {
            v64 &= ~4u;
            v108 = v64;
            std::wstring::_Tidy_deallocate(v124);
          }
          if ( (v64 & 2) != 0 )
          {
            v108 = v64 & 0xFFFFFFFD;
            std::wstring::_Tidy_deallocate(v123);
          }
        }
      }
      catch ( wil::ResultException )
      {
        v70 = v115;
        v71 = *(_BYTE *)(v115 + 29);
        *(_QWORD *)&DestinationString.Length = v123;
        if ( *(_BYTE *)(v115 + 36) )
        {
          v72 = std::wstring::wstring(&v118, v115 + 168);
          v73 = v108 | 8;
        }
        else
        {
          v72 = Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(
                  v124,
                  *(unsigned int *)(v115 + 48));
          v73 = v108 | 0x10;
        }
        v108 = v73;
        std::wstring::wstring(v123, v72);
        std::wstring::wstring(v120, v70 + 296);
        v75 = wil::ResultFromCaughtException(v74);
        LogConsentCheck(v75, v71);
        if ( (v73 & 0x10) != 0 )
        {
          v73 &= ~0x10u;
          v108 = v73;
          std::pair<std::wstring const,unsigned int>::~pair<std::wstring const,unsigned int>(v124);
        }
        if ( (v73 & 8) != 0 )
        {
          v108 = v73 & 0xFFFFFFF7;
          std::pair<std::wstring const,unsigned int>::~pair<std::wstring const,unsigned int>(&v118);
        }
        throw;
      }
      catch ( ... )
      {
        v76 = v115;
        v77 = *(_BYTE *)(v115 + 29);
        *(_QWORD *)&DestinationString.Length = v123;
        if ( *(_BYTE *)(v115 + 36) )
        {
          v78 = std::wstring::wstring(&v118, v115 + 168);
          v79 = v108 | 0x20;
        }
        else
        {
          v78 = Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(
                  v124,
                  *(unsigned int *)(v115 + 48));
          v79 = v108 | 0x40;
        }
        v108 = v79;
        std::wstring::wstring(v123, v78);
        std::wstring::wstring(v120, v76 + 296);
        LogConsentCheck(-2147418113, v77);
        if ( (v79 & 0x40) != 0 )
        {
          v79 &= ~0x40u;
          v108 = v79;
          std::pair<std::wstring const,unsigned int>::~pair<std::wstring const,unsigned int>(v124);
        }
        if ( (v79 & 0x20) != 0 )
        {
          v108 = v79 & 0xFFFFFFDF;
          std::pair<std::wstring const,unsigned int>::~pair<std::wstring const,unsigned int>(&v118);
        }
        v80 = wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5AF,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
          (const char *)v80,
          v105);
      }
      if ( v107 != 3 )
      {
        std::wstring::wstring(v123, L"Access check returning with '%ws'");
        std::wstring::_Tidy_deallocate(v123);
        v65 = v107;
        if ( v24 )
          (*(void (__fastcall **)(_QWORD, bool))(**(_QWORD **)(a1 + 64) + 40LL))(*(_QWORD *)(a1 + 64), v107 == 3);
        v113 = 0;
        lambda_d8d162e6b268c4497ea9d6dd4f5c31b9_::operator()(v112);
        wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(&pv);
        wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v117);
        return v65;
      }
    }
    v66 = *(Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager ***)(a1 + 144);
    v67 = *(Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager ***)(a1 + 152);
    while ( v66 != v67 )
    {
      Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::put_SuppressUserConsentPrompt(
        *v66,
        *(_BYTE *)(a1 + 37));
      Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::put_SuppressGlobalUserConsentPrompt(
        *v66,
        *(_BYTE *)(a1 + 39));
      Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::put_SuppressPerAppUserConsentPrompt(
        *v66,
        *(_BYTE *)(a1 + 38));
      Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::put_CapabilityRequiredInToken(
        *v66,
        *(_BYTE *)(a1 + 31));
      v68 = Windows::Internal::CapabilityAccess::Private::CapabilityAccessManager::AccessCheck(*v66);
      if ( v68 != 3 )
      {
        std::wstring::wstring(
          v123,
          L"AccessCheck passed for base capability, but a required capability was not authorized. Returning %ws");
        std::wstring::_Tidy_deallocate(v123);
        v107 = v68;
        if ( v24 )
          (*(void (__fastcall **)(_QWORD, bool))(**(_QWORD **)(a1 + 64) + 40LL))(*(_QWORD *)(a1 + 64), v107 == 3);
        v113 = 0;
        lambda_d8d162e6b268c4497ea9d6dd4f5c31b9_::operator()(v112);
        wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(&pv);
        wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v117);
        return v68;
      }
      v66 += 2;
    }
    std::wstring::wstring(v123, L"Access check passed. Returning 'Allowed'");
    std::wstring::_Tidy_deallocate(v123);
    v107 = 3;
    if ( v24 )
      (*(void (__fastcall **)(_QWORD, bool))(**(_QWORD **)(a1 + 64) + 40LL))(*(_QWORD *)(a1 + 64), v107 == 3);
LABEL_179:
    v113 = 0;
    lambda_d8d162e6b268c4497ea9d6dd4f5c31b9_::operator()(v112);
    wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(&pv);
    wil::ThreadFailureCache::~ThreadFailureCache((wil::ThreadFailureCache *)v117);
    result = 3;
  }
  catch ( wil::ResultException )
  {
    Failure = wil::ThreadFailureCache::GetFailure((wil::ThreadFailureCache *)v117);
    if ( Failure )
      v83 = *((_DWORD *)Failure + 16);
    else
      v83 = 0;
    if ( Failure )
      v84 = (char *)*((_QWORD *)Failure + 7);
    else
      v84 = (char *)qword_1800D35C0;
    LOBYTE(v82) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMBugBundle_Se>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CAMBugBundle_Se>::GetImpl'::`2'::impl,
      v82);
    tip2::tip_test<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>::tip_test<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>(&pv);
    if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>::open(&pv) )
      tip2::tip_test<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>::complete(&pv);
    tip2::tip_test<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>::~tip_test<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>(&pv);
    v85 = v115;
    v86 = *(_BYTE *)(v115 + 29);
    v87 = 2 - (*(_BYTE *)(v115 + 36) != 0);
    *(_QWORD *)&DestinationString.Length = v123;
    if ( *(_BYTE *)(v115 + 36) )
    {
      v88 = std::wstring::wstring(&v118, v115 + 168);
      v89 = v108 | 0x80;
    }
    else
    {
      v88 = Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(
              v124,
              *(unsigned int *)(v115 + 48));
      v89 = v108 | 0x100;
    }
    v108 = v89;
    v90 = std::wstring::wstring(v123, v88);
    std::wstring::wstring(v120, v85 + 296);
    v92 = wil::ResultFromCaughtException(v91);
    LogAccessCheck(v92, v83, v84, v90, v87, v86, -1);
    if ( (v89 & 0x100) != 0 )
      std::pair<std::wstring const,unsigned int>::~pair<std::wstring const,unsigned int>(v124);
    if ( (v89 & 0x80u) != 0 )
      std::pair<std::wstring const,unsigned int>::~pair<std::wstring const,unsigned int>(&v118);
    throw;
  }
  catch ( ... )
  {
    v93 = wil::ThreadFailureCache::GetFailure((wil::ThreadFailureCache *)v117);
    if ( v93 )
      v95 = *((_DWORD *)v93 + 16);
    else
      v95 = 0;
    if ( v93 )
      v96 = (char *)*((_QWORD *)v93 + 7);
    else
      v96 = (char *)qword_1800D35C0;
    LOBYTE(v94) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMBugBundle_Se>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CAMBugBundle_Se>::GetImpl'::`2'::impl,
      v94);
    tip2::tip_test<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>::tip_test<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>(&pv);
    if ( (unsigned __int8)tip2::tip_test<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>::open(&pv) )
      tip2::tip_test<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>::complete(&pv);
    tip2::tip_test<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>::~tip_test<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>(&pv);
    v97 = v115;
    v98 = *(_BYTE *)(v115 + 29);
    v99 = 2 - (*(_BYTE *)(v115 + 36) != 0);
    *(_QWORD *)&DestinationString.Length = v123;
    if ( *(_BYTE *)(v115 + 36) )
    {
      v100 = std::wstring::wstring(&v118, v115 + 168);
      v101 = v108 | 0x200;
    }
    else
    {
      v100 = Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(
               v124,
               *(unsigned int *)(v115 + 48));
      v101 = v108 | 0x400;
    }
    v108 = v101;
    v102 = std::wstring::wstring(v123, v100);
    std::wstring::wstring(v120, v97 + 296);
    LogAccessCheck(-2147418113, v95, v96, v102, v99, v98, -1);
    if ( (v101 & 0x400) != 0 )
    {
      LOWORD(v101) = v101 & 0xFBFF;
      std::pair<std::wstring const,unsigned int>::~pair<std::wstring const,unsigned int>(v124);
    }
    if ( (v101 & 0x200) != 0 )
      std::pair<std::wstring const,unsigned int>::~pair<std::wstring const,unsigned int>(&v118);
    v103 = wil::verify_hresult<long>(2147549183LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x5F8,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityaccessmanager.cpp",
      (const char *)v103,
      v104);
  }
  return result;
}

```

## disassembly

```asm
0x18006874c  mov     [rsp+arg_8], rbx
0x180068751  mov     [rsp+arg_10], rsi
0x180068756  push    rdi
0x180068757  push    r12
0x180068759  push    r13
0x18006875b  push    r14
0x18006875d  push    r15
0x18006875f  sub     rsp, 270h
0x180068766  mov     rax, cs:__security_cookie
0x18006876d  xor     rax, rsp
0x180068770  mov     [rsp+298h+var_38], rax
0x180068778  mov     rbx, rcx
0x18006877b  mov     [rsp+298h+var_208], rcx
0x180068783  xor     r12d, r12d
0x180068786  mov     r14d, r12d
0x180068789  mov     [rsp+298h+var_254], r12d
0x18006878e  lea     rax, WPP_GLOBAL_Control
0x180068795  mov     rcx, cs:WPP_GLOBAL_Control
0x18006879c  lea     esi, [r12+1]
0x1800687a1  cmp     rcx, rax
0x1800687a4  jz      short loc_1800687C5
0x1800687a6  test    [rcx+1Ch], sil
0x1800687aa  jz      short loc_1800687C5
0x1800687ac  cmp     byte ptr [rcx+19h], 5
0x1800687b0  jb      short loc_1800687C5
0x1800687b2  lea     edx, [rsi+0Dh]
0x1800687b5  lea     r8, WPP_5da0b0c25a7f3c0e58e9dfe16e60c1dc_Traceguids
0x1800687bc  mov     rcx, [rcx+10h]
0x1800687c0  call    WPP_SF_
0x1800687c5  lea     rdx, aPidDTidDSidWsP; "PID:%d, TID:%d, SID:%ws, Packaged:%d, P"...
0x1800687cc  lea     rcx, [rsp+298h+var_108]
0x1800687d4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800687d9  lea     rcx, [rsp+298h+var_108]
0x1800687e1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800687e6  lea     rcx, [rsp+298h+var_1E8]; this
0x1800687ee  call    ??0ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::ThreadFailureCache(void)
0x1800687f3  nop
0x1800687f4  mov     [rsp+298h+var_258], r12d
0x1800687f9  mov     rax, [rbx+80h]
0x180068800  test    rax, rax
0x180068803  jz      short loc_18006882B
0x180068805  cmp     [rax+2Ah], r12b
0x180068809  jz      short loc_18006882B
0x18006880b  call    ?GetOobeState@Private@CapabilityAccess@Internal@Windows@@YAIXZ; Windows::Internal::CapabilityAccess::Private::GetOobeState(void)
0x180068810  test    eax, eax
0x180068812  jnz     short loc_18006882B
0x180068814  lea     rcx, [rsp+298h+var_1E8]; this
0x18006881c  call    ??1ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::~ThreadFailureCache(void)
0x180068821  mov     eax, 3
0x180068826  jmp     loc_180069B82
0x18006882b  mov     [rsp+298h+pv], r12
0x180068830  mov     dl, sil
0x180068833  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAMBugBundle_Se@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAMBugBundle_Se@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMBugBundle_Se> `wil::Feature<__WilFeatureTraits_Feature_CAMBugBundle_Se>::GetImpl(void)'::`2'::impl
0x18006883a  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAMBugBundle_Se@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMBugBundle_Se>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18006883f  lea     rcx, [rsp+298h+var_A8]; struct wil::details::IFailureCallback *
0x180068847  call    ??$start_and_watch_errors@V?$tip_test@V?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@@tip2@@@tip2@@YA?A_PXZ
0x18006884c  mov     rdx, [rax+38h]
0x180068850  mov     rcx, [rsp+298h+pv]; pv
0x180068855  mov     [rsp+298h+pv], rdx
0x18006885a  test    rdx, rdx
0x18006885d  jz      short loc_180068866
0x18006885f  lock add [rdx+130h], esi
0x180068866  test    rcx, rcx
0x180068869  jz      short loc_180068870
0x18006886b  call    ?Release@?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@AEAAKXZ; tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>::Release(void)
0x180068870  lea     rcx, [rsp+298h+var_A8]
0x180068878  call    ??1?$test_watcher@V?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_watcher<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>::~test_watcher<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>(void)
0x18006887d  lea     rcx, [rsp+298h+pv]
0x180068882  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>>::ensure_data(void)
0x180068887  mov     rdi, [rax]
0x18006888a  mov     [rsp+298h+Sid], rdi
0x180068892  test    rdi, rdi
0x180068895  jz      short loc_18006889E
0x180068897  lock add [rdi+130h], esi
0x18006889e  lea     rcx, [rdi+8]
0x1800688a2  call    ?begin_update@?$shared_data@$00$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<1,0,0>::begin_update(void)
0x1800688a7  nop
0x1800688a8  lea     r13, [rbx+128h]
0x1800688af  lea     rcx, [rdi+110h]
0x1800688b6  mov     rdx, r13
0x1800688b9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x1800688be  nop
0x1800688bf  lea     rcx, [rsp+298h+Sid]
0x1800688c7  call    ??1?$test_data_control@V?$merged_data@U_tip_CAMConsentCheckTest@@U1@@details@tip2@@@tip2@@QEAA@XZ; tip2::test_data_control<tip2::details::merged_data<_tip_CAMConsentCheckTest,_tip_CAMConsentCheckTest>>::~test_data_control<tip2::details::merged_data<_tip_CAMConsentCheckTest,_tip_CAMConsentCheckTest>>(void)
0x1800688cc  mov     [rsp+298h+var_238], rbx
0x1800688d1  lea     rax, [rsp+298h+var_258]
0x1800688d6  mov     [rsp+298h+var_230], rax
0x1800688db  lea     rax, [rsp+298h+pv]
0x1800688e0  mov     [rsp+298h+var_228], rax
0x1800688e5  mov     [rsp+298h+var_220], sil
0x1800688ea  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID59213523@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523> `wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl(void)'::`2'::impl
0x1800688f1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID59213523@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(void)
0x1800688f6  test    al, al
0x1800688f8  jz      loc_180068993
0x1800688fe  mov     rax, [rbx+80h]
0x180068905  test    rax, rax
0x180068908  jz      loc_180068993
0x18006890e  cmp     [rax+201h], r12b
0x180068915  jz      short loc_180068993
0x180068917  mov     [rsp+298h+pSessionId], r12d
0x18006891c  lea     rcx, [rsp+298h+pSessionId]
0x180068921  call    cs:__imp_IsDeveloperModeEnabled
0x180068927  mov     rcx, [rsp+298h]; this
0x18006892f  test    eax, eax
0x180068931  js      loc_180069BAF
0x180068937  cmp     [rsp+298h+pSessionId], r12d
0x18006893c  jnz     short loc_180068993
0x18006893e  lea     rdx, aAccessIsBlocke_4; "Access is blocked due to requireDevelop"...
0x180068945  lea     rcx, [rsp+298h+var_108]
0x18006894d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180068952  lea     rcx, [rsp+298h+var_108]
0x18006895a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18006895f  mov     [rsp+298h+var_258], r12d
0x180068964  mov     [rsp+298h+var_220], r12b
0x180068969  lea     rcx, [rsp+298h+var_238]
0x18006896e  call    _lambda_d8d162e6b268c4497ea9d6dd4f5c31b9___operator__
0x180068973  nop
0x180068974  lea     rcx, [rsp+298h+pv]
0x180068979  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(void)
0x18006897e  nop
0x18006897f  lea     rcx, [rsp+298h+var_1E8]; this
0x180068987  call    ??1ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::~ThreadFailureCache(void)
0x18006898c  xor     eax, eax
0x18006898e  jmp     loc_180069B82
0x180068993  mov     rcx, [rbx+80h]
0x18006899a  test    rcx, rcx
0x18006899d  jz      short loc_180068A10
0x18006899f  cmp     [rcx+30h], r12b
0x1800689a3  jz      short loc_180068A10
0x1800689a5  cmp     [rbx+22h], r12b
0x1800689a9  jnz     short loc_180068A10
0x1800689ab  lea     rdx, [rbx+0A8h]
0x1800689b2  call    ?BlockAccessForApp@CapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::BlockAccessForApp(std::wstring const &)
0x1800689b7  test    al, al
0x1800689b9  jz      short loc_180068A10
0x1800689bb  lea     rdx, aAccessIsBlocke; "Access is blocked due to blockAccess po"...
0x1800689c2  lea     rcx, [rsp+298h+var_108]
0x1800689ca  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800689cf  lea     rcx, [rsp+298h+var_108]
0x1800689d7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800689dc  mov     [rsp+298h+var_258], r12d
0x1800689e1  mov     [rsp+298h+var_220], r12b
0x1800689e6  lea     rcx, [rsp+298h+var_238]
0x1800689eb  call    _lambda_d8d162e6b268c4497ea9d6dd4f5c31b9___operator__
0x1800689f0  nop
0x1800689f1  lea     rcx, [rsp+298h+pv]
0x1800689f6  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(void)
0x1800689fb  nop
0x1800689fc  lea     rcx, [rsp+298h+var_1E8]; this
0x180068a04  call    ??1ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::~ThreadFailureCache(void)
0x180068a09  xor     eax, eax
0x180068a0b  jmp     loc_180069B82
0x180068a10  mov     rax, [rbx+80h]
0x180068a17  test    rax, rax
0x180068a1a  jz      short loc_180068A7D
0x180068a1c  cmp     [rax+2Eh], r12b
0x180068a20  jz      short loc_180068A7D
0x180068a22  cmp     [rbx+24h], r12b
0x180068a26  jnz     short loc_180068A7D
0x180068a28  lea     rdx, aAccessIsBlocke_0; "Access is blocked due to alwaysBlockNon"...
0x180068a2f  lea     rcx, [rsp+298h+var_108]
0x180068a37  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180068a3c  lea     rcx, [rsp+298h+var_108]
0x180068a44  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180068a49  mov     [rsp+298h+var_258], r12d
0x180068a4e  mov     [rsp+298h+var_220], r12b
0x180068a53  lea     rcx, [rsp+298h+var_238]
0x180068a58  call    _lambda_d8d162e6b268c4497ea9d6dd4f5c31b9___operator__
0x180068a5d  nop
0x180068a5e  lea     rcx, [rsp+298h+pv]
0x180068a63  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(void)
0x180068a68  nop
0x180068a69  lea     rcx, [rsp+298h+var_1E8]; this
0x180068a71  call    ??1ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::~ThreadFailureCache(void)
0x180068a76  xor     eax, eax
0x180068a78  jmp     loc_180069B82
0x180068a7d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline> `wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl(void)'::`2'::impl
0x180068a84  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(void)
0x180068a89  test    al, al
0x180068a8b  jz      loc_180068B57
0x180068a91  mov     rax, [rbx+80h]
0x180068a98  test    rax, rax
0x180068a9b  jz      loc_180068B57
0x180068aa1  cmp     [rbx+28h], r12b
0x180068aa5  jz      loc_180068B57
0x180068aab  lea     rcx, [rsp+298h+var_108]
0x180068ab3  cmp     [rax+2Bh], r12b
0x180068ab7  jz      short loc_180068B0A
0x180068ab9  lea     rdx, aAccessIsAllowe; "Access is Allowed - caller is an Agenti"...
0x180068ac0  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180068ac5  lea     rcx, [rsp+298h+var_108]
0x180068acd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180068ad2  mov     edi, 3
0x180068ad7  mov     [rsp+298h+var_258], edi
0x180068adb  mov     [rsp+298h+var_220], r12b
0x180068ae0  lea     rcx, [rsp+298h+var_238]
0x180068ae5  call    _lambda_d8d162e6b268c4497ea9d6dd4f5c31b9___operator__
0x180068aea  nop
0x180068aeb  lea     rcx, [rsp+298h+pv]
0x180068af0  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(void)
0x180068af5  nop
0x180068af6  lea     rcx, [rsp+298h+var_1E8]; this
0x180068afe  call    ??1ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::~ThreadFailureCache(void)
0x180068b03  mov     eax, edi
0x180068b05  jmp     loc_180069B82
0x180068b0a  lea     rdx, aAccessIsBlocke_2; "Access is blocked - caller is an Agenti"...
0x180068b11  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180068b16  lea     rcx, [rsp+298h+var_108]
0x180068b1e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180068b23  mov     [rsp+298h+var_258], r12d
0x180068b28  mov     [rsp+298h+var_220], r12b
0x180068b2d  lea     rcx, [rsp+298h+var_238]
0x180068b32  call    _lambda_d8d162e6b268c4497ea9d6dd4f5c31b9___operator__
0x180068b37  nop
0x180068b38  lea     rcx, [rsp+298h+pv]
0x180068b3d  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(void)
0x180068b42  nop
0x180068b43  lea     rcx, [rsp+298h+var_1E8]; this
0x180068b4b  call    ??1ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::~ThreadFailureCache(void)
0x180068b50  xor     eax, eax
0x180068b52  jmp     loc_180069B82
0x180068b57  cmp     [rbx+80h], r12
0x180068b5e  jz      loc_180068D00
0x180068b64  xorps   xmm0, xmm0
0x180068b67  movups  [rsp+298h+var_C8], xmm0
0x180068b6f  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180068b77  movdqu  [rsp+298h+var_B8], xmm1
0x180068b80  mov     word ptr [rsp+298h+var_C8], r12w
0x180068b89  cmp     [rbx+24h], r12b
0x180068b8d  jnz     short loc_180068BC2
0x180068b8f  mov     edx, [rbx+30h]
0x180068b92  lea     rcx, [rsp+298h+var_108]
0x180068b9a  call    ?GetImageFullPathFromProcessId@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::GetImageFullPathFromProcessId(ulong)
0x180068b9f  mov     rdx, rax
0x180068ba2  lea     rcx, [rsp+298h+var_C8]
0x180068baa  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180068baf  lea     rcx, [rsp+298h+var_108]
0x180068bb7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180068bbc  cmp     [rbx+24h], r12b
0x180068bc0  jz      short loc_180068BE3
0x180068bc2  lea     rdx, [rbx+0A8h]
0x180068bc9  mov     rcx, [rbx+80h]
0x180068bd0  call    ?AlwaysBlockAccessForApp@CapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::AlwaysBlockAccessForApp(std::wstring const &)
0x180068bd5  test    al, al
0x180068bd7  jnz     short loc_180068BFF
0x180068bd9  cmp     [rbx+24h], r12b
0x180068bdd  jnz     loc_180068CF3
0x180068be3  lea     rdx, [rsp+298h+var_C8]
0x180068beb  mov     rcx, [rbx+80h]
0x180068bf2  call    ?AlwaysBlockAccessForBinaryFullPath@CapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@QEBA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::AlwaysBlockAccessForBinaryFullPath(std::wstring const &)
0x180068bf7  test    al, al
0x180068bf9  jz      loc_180068CF3
0x180068bff  cmp     [rbx+24h], r12b
0x180068c03  jnz     loc_180068C90
0x180068c09  lea     rcx, [rsp+298h+var_C8]
0x180068c11  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180068c16  mov     rcx, qword ptr [rsp+298h+var_B8]
0x180068c1e  lea     r8, [rax+rcx*2]
0x180068c22  mov     rcx, cs:__imp__o_towlower
0x180068c29  mov     qword ptr [rsp+298h+var_278], rcx
0x180068c2e  mov     r9, rax
0x180068c31  mov     rdx, rax
0x180068c34  lea     rcx, [rsp+298h+Sid]
0x180068c3c  call    ??$transform@V?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@std@@V12@P6AGG@Z@std@@YA?AV?$_String_iterator@V?$_String_val@U?$_Simple_types@G@std@@@std@@@0@V10@0V10@P6AGG@Z@Z; std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort)>(std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,std::_String_iterator<std::_String_val<std::_Simple_types<ushort>>>,ushort (*)(ushort))
0x180068c41  call    ?GetSvchostPath@FilePathCache@Globals@Private@CapabilityAccess@Internal@Windows@@SAAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Windows::Internal::CapabilityAccess::Private::Globals::FilePathCache::GetSvchostPath(void)
0x180068c46  mov     r9, rax
0x180068c49  mov     rcx, rax
0x180068c4c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180068c51  mov     r8, rax
0x180068c54  lea     rcx, [rsp+298h+var_C8]
0x180068c5c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180068c61  mov     rcx, rax
0x180068c64  mov     r9, [r9+10h]
0x180068c68  mov     rdx, qword ptr [rsp+298h+var_B8]
0x180068c70  call    ??$_Traits_equal@U?$char_traits@G@std@@@std@@YA_NQEBG_K01@Z; std::_Traits_equal<std::char_traits<ushort>>(ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180068c75  test    al, al
0x180068c77  jz      short loc_180068C90
0x180068c79  lea     rdx, [rbx+1C0h]
0x180068c80  mov     rcx, [rbx+80h]
0x180068c87  call    ?AlwaysBlockAccessForServiceHost@CapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@QEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::AlwaysBlockAccessForServiceHost(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> const &)
0x180068c8c  test    al, al
0x180068c8e  jz      short loc_180068CF3
0x180068c90  lea     rdx, aAccessIsBlocke_3; "Access is blocked due to alwaysBlockAcc"...
0x180068c97  lea     rcx, [rsp+298h+var_108]
0x180068c9f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180068ca4  lea     rcx, [rsp+298h+var_108]
0x180068cac  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180068cb1  mov     [rsp+298h+var_258], r12d
0x180068cb6  lea     rcx, [rsp+298h+var_C8]
0x180068cbe  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180068cc3  nop
0x180068cc4  mov     [rsp+298h+var_220], r12b
0x180068cc9  lea     rcx, [rsp+298h+var_238]
0x180068cce  call    _lambda_d8d162e6b268c4497ea9d6dd4f5c31b9___operator__
0x180068cd3  nop
0x180068cd4  lea     rcx, [rsp+298h+pv]
0x180068cd9  call    ??1?$com_ptr_t@V?$merged_data@U_tip_CAMAccessCheckTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>::~com_ptr_t<tip2::details::merged_data<_tip_CAMAccessCheckTest,_tip_CAMAccessCheckTest>,wil::err_returncode_policy>(void)
0x180068cde  nop
0x180068cdf  lea     rcx, [rsp+298h+var_1E8]; this
0x180068ce7  call    ??1ThreadFailureCache@wil@@QEAA@XZ; wil::ThreadFailureCache::~ThreadFailureCache(void)
  ... truncated ...
```
