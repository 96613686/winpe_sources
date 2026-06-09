# Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadLegacyPolicyFromRegistry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800553e8`
- end: `0x18005686a`
- name: `?ReadLegacyPolicyFromRegistry@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z`
- size: `5250`
- prototype: ``
- caller_count: `2`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180056870`
- `0x180085958`

## callees

- `0x1800094c0`
- `0x18001649c`
- `0x18001c3b4`
- `0x180020fcc`
- `0x1800257a4`
- `0x180029408`
- `0x18002a564`
- `0x18002c970`
- `0x18002e304`
- `0x18002f280`
- `0x18002f93c`
- `0x18002f978`
- `0x180038894`
- `0x18003afa0`
- `0x1800473fc`
- `0x180048444`
- `0x180052674`
- `0x1800529c4`
- `0x180052a78`
- `0x180052b74`
- `0x1800535b8`
- `0x18005371c`
- `0x180055158`
- `0x1800551a4`
- `0x1800553e8`
- `0x180056af4`
- `0x180056b18`
- `0x180056c20`
- `0x180056d40`
- `0x18005816c`
- `0x1800581a8`
- `0x18005829c`
- `0x180058318`
- `0x1800583e0`
- `0x1800588a4`
- `0x180058ac4`
- `0x180058c8c`
- `0x180058dfc`
- `0x180058e78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800561e6`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x1800563a7`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18005677e`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180056608`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x180056608`

## string_xrefs

- `0x18005664b`: `Services`
- `0x18005667f`: `Services`
- `0x180055e9b`: `AccessChangeWnf`
- `0x180055d51`: `AlwaysAllowInAgentSessions`
- `0x180055859`: `ForegroundRequiredForAccess`
- `0x180055805`: `FallbackTokenCapabilities`
- `0x180055535`: `AlwaysAttemptPrompts`
- `0x18005547e`: `AccessDeniedToasts`
- `0x180055572`: `AlwaysBlockAccess`
- `0x18005613b`: `AlwaysBlockAccess`
- `0x1800562ad`: `AlwaysBlockAccess`
- `0x1800563f1`: `AlwaysBlockAccess`
- `0x1800564d9`: `AlwaysBlockAccess`
- `0x18005672e`: `AlwaysBlockAccess`
- `0x1800556e9`: `BlockAccess`
- `0x1800560dd`: `BlockAccess`
- `0x180055b66`: `TerminateAppOnAccessChange`
- `0x180056021`: `TerminateAppOnAccessChange`
- `0x18005566c`: `AppLaunchAccessCheckRequired`
- `0x180055ff2`: `AppLaunchAccessCheckRequired`

## pseudocode

```c
// Hidden C++ exception states: #wind=26
_QWORD *__fastcall Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadLegacyPolicyFromRegistry(
        __int64 a1,
        HKEY a2,
        __int64 a3)
{
  _QWORD *v4; // r14
  int v5; // ebx
  DWORD v6; // r12d
  __int64 v7; // rsi
  __int64 PolicyString; // rax
  __int64 v9; // rax
  __int64 PolicyStringArray; // rax
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // r8
  __int64 StringValue; // rax
  unsigned __int64 Uint64Value; // rbx
  unsigned __int64 v17; // rax
  std::_Ref_count_base *v18; // rcx
  __int64 v19; // rdi
  __int64 v20; // r15
  __int64 v21; // rdi
  __int64 v22; // r15
  __int64 v23; // rax
  __int64 v24; // rdx
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rdi
  __int64 v28; // r13
  __int64 v29; // rax
  __int64 v30; // rax
  __int64 v31; // rax
  __int64 v32; // rax
  DWORD i; // edx
  int v34; // eax
  __int64 v35; // rax
  __int64 v36; // rdx
  int v37; // ebx
  __int64 v38; // rax
  int v39; // ebx
  __int64 v40; // rax
  int v41; // ebx
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rax
  __int64 v45; // rax
  LSTATUS v46; // eax
  __int64 v47; // rdi
  __int64 v48; // r15
  __int64 v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rax
  int v52; // eax
  bool *lpReserved; // [rsp+20h] [rbp-E0h]
  bool *lpReserveda; // [rsp+20h] [rbp-E0h]
  bool *lpReservedb; // [rsp+20h] [rbp-E0h]
  bool *lpReservedc; // [rsp+20h] [rbp-E0h]
  Windows::Internal::CapabilityAccess::Private *v58; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v59; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v60; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cchValueName; // [rsp+70h] [rbp-90h] BYREF
  HKEY v66; // [rsp+78h] [rbp-88h]
  _BYTE v67[8]; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v68; // [rsp+88h] [rbp-78h]
  __int64 v69; // [rsp+98h] [rbp-68h] BYREF
  __int64 v70; // [rsp+A0h] [rbp-60h]
  _QWORD v71[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v72[3]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v73[16]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v74; // [rsp+E8h] [rbp-18h]
  __int64 Src; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v76; // [rsp+100h] [rbp+0h]
  unsigned __int64 v77; // [rsp+108h] [rbp+8h]
  unsigned __int64 v78; // [rsp+110h] [rbp+10h]
  _BYTE v79[16]; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int64 v80; // [rsp+128h] [rbp+28h]
  unsigned __int64 v81; // [rsp+130h] [rbp+30h]
  void **v82; // [rsp+140h] [rbp+40h] BYREF
  __int128 v83; // [rsp+148h] [rbp+48h]
  __int128 v84; // [rsp+158h] [rbp+58h]
  __int64 v85; // [rsp+168h] [rbp+68h]
  void **v86; // [rsp+190h] [rbp+90h] BYREF
  __int128 v87; // [rsp+198h] [rbp+98h]
  __int128 v88; // [rsp+1A8h] [rbp+A8h]
  __int64 v89; // [rsp+1B8h] [rbp+B8h]
  WCHAR ValueName[264]; // [rsp+1E0h] [rbp+E0h] BYREF

  v4 = a2;
  v66 = a2;
  v5 = a1;
  hKey = a2;
  v6 = 0;
  v58 = 0;
  v60 = 0;
  v59 = 0;
  Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetAllVariantKeys(a1, a3, &v58, &v60, &v59);
  if ( v58 )
  {
    Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::Create(v71);
    v7 = v71[0];
    std::wstring::operator=(v71[0] + 8LL, a3);
    std::wstring::wstring(v73, L"AccessDeniedToasts");
    *(_BYTE *)(v7 + 40) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"AllUsersConsentRequiredForMua");
    *(_BYTE *)(v7 + 41) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"AlwaysAllowBeforeOOBE");
    *(_BYTE *)(v7 + 42) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"AlwaysAttemptPrompts");
    *(_BYTE *)(v7 + 44) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"AlwaysBlockAccess");
    *(_BYTE *)(v7 + 45) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"AlwaysBlockNonPackaged");
    *(_BYTE *)(v7 + 46) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"AsyncPrompts");
    *(_BYTE *)(v7 + 152) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                             v5,
                             (unsigned int)&v58,
                             (unsigned int)&v60,
                             (unsigned int)&v59,
                             (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"AsyncPromptsDefault");
    *(_DWORD *)(v7 + 148) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyInt(
                              v5,
                              (unsigned int)&v58,
                              (unsigned int)&v60,
                              (unsigned int)&v59,
                              (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"AppLaunchAccessCheckRequired");
    *(_BYTE *)(v7 + 47) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"AuditBehaviorDefault");
    *(_DWORD *)(v7 + 136) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyInt(
                              v5,
                              (unsigned int)&v58,
                              (unsigned int)&v60,
                              (unsigned int)&v59,
                              (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"BlockAccess");
    *(_BYTE *)(v7 + 48) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"CapabilityForConsent");
    PolicyString = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyString(
                     (unsigned int)&v82,
                     (unsigned int)&v58,
                     (unsigned int)&v60,
                     (unsigned int)&v59,
                     (__int64)v73);
    std::wstring::operator=(v7 + 72, PolicyString);
    std::wstring::_Tidy_deallocate(&v82);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"CapabilityForPrompt");
    v9 = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyString(
           (unsigned int)&v82,
           (unsigned int)&v58,
           (unsigned int)&v60,
           (unsigned int)&v59,
           (__int64)v73);
    std::wstring::operator=(v7 + 104, v9);
    std::wstring::_Tidy_deallocate(&v82);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"CollapseRecentActivity");
    *(_BYTE *)(v7 + 49) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"FallbackTokenCapabilities");
    PolicyStringArray = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyStringArray(
                          (unsigned int)&Src,
                          (unsigned int)&v58,
                          (unsigned int)&v60,
                          (unsigned int)&v59,
                          (__int64)v73);
    std::vector<std::wstring>::operator=(v7 + 384, PolicyStringArray);
    std::vector<std::wstring>::_Tidy(&Src);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"ForegroundRequiredForAccess");
    *(_BYTE *)(v7 + 50) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"GlobalPrompts");
    *(_BYTE *)(v7 + 51) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"IncludedCapabilities");
    v11 = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyStringArray(
            (unsigned int)&Src,
            (unsigned int)&v58,
            (unsigned int)&v60,
            (unsigned int)&v59,
            (__int64)v73);
    std::vector<std::wstring>::operator=(v7 + 408, v11);
    std::vector<std::wstring>::_Tidy(&Src);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"InitAllAppsDeniedOrPrompt");
    *(_BYTE *)(v7 + 52) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"InitSystemGlobalConsentDenied");
    *(_BYTE *)(v7 + 53) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"InitUserAppConsentDenied");
    *(_BYTE *)(v7 + 54) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"InitUserGlobalConsentDenied");
    *(_BYTE *)(v7 + 55) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"MinimumSessionDuration");
    *(_BYTE *)(v7 + 56) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"RecordUsageData");
    *(_BYTE *)(v7 + 58) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"RequireActiveSessionForInteractiveUsers");
    *(_BYTE *)(v7 + 140) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                             v5,
                             (unsigned int)&v58,
                             (unsigned int)&v60,
                             (unsigned int)&v59,
                             (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"RequiredCapabilities");
    v12 = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyStringArray(
            (unsigned int)&Src,
            (unsigned int)&v58,
            (unsigned int)&v60,
            (unsigned int)&v59,
            (__int64)v73);
    std::vector<std::wstring>::operator=(v7 + 432, v12);
    std::vector<std::wstring>::_Tidy(&Src);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"RequireWindowsCert");
    *(_BYTE *)(v7 + 60) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"TerminateAppOnAccessChange");
    *(_BYTE *)(v7 + 62) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"ToastFrequencySeconds");
    *(_DWORD *)(v7 + 144) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyInt(
                              v5,
                              (unsigned int)&v58,
                              (unsigned int)&v60,
                              (unsigned int)&v59,
                              (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"UserConsentPromptRequired");
    *(_BYTE *)(v7 + 64) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    std::wstring::wstring(v73, L"UserConsentRequired");
    *(_BYTE *)(v7 + 65) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl'::`2'::impl) )
    {
      std::wstring::wstring(v73, L"RequireDeveloperMode");
      *(_BYTE *)(v7 + 513) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                               v5,
                               (unsigned int)&v58,
                               (unsigned int)&v60,
                               (unsigned int)&v59,
                               (__int64)v73);
      std::wstring::_Tidy_deallocate(v73);
      std::wstring::wstring(v73, L"SkipCapabilityCheck");
      *(_BYTE *)(v7 + 512) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                               v5,
                               (unsigned int)&v58,
                               (unsigned int)&v60,
                               (unsigned int)&v59,
                               (__int64)v73);
      std::wstring::_Tidy_deallocate(v73);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59946133>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59946133>::GetImpl'::`2'::impl) )
    {
      std::wstring::wstring(v73, L"HideUserGlobal");
      *(_BYTE *)(v7 + 514) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                               v5,
                               (unsigned int)&v58,
                               (unsigned int)&v60,
                               (unsigned int)&v59,
                               (__int64)v73);
      std::wstring::_Tidy_deallocate(v73);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl'::`2'::impl) )
    {
      std::wstring::wstring(v73, L"AlwaysAllowInAgentSessions");
      *(_BYTE *)(v7 + 43) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                              v5,
                              (unsigned int)&v58,
                              (unsigned int)&v60,
                              (unsigned int)&v59,
                              (__int64)v73);
      std::wstring::_Tidy_deallocate(v73);
    }
    if ( !*(_BYTE *)(v7 + 56) )
    {
      std::wstring::wstring(v73, L"ExtendUXLifetime");
      *(_BYTE *)(v7 + 56) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                              v5,
                              (unsigned int)&v58,
                              (unsigned int)&v60,
                              (unsigned int)&v59,
                              (__int64)v73);
      std::wstring::_Tidy_deallocate(v73);
    }
    LOBYTE(v14) = 3;
    LOBYTE(v13) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl'::`2'::impl,
      v13,
      v14);
    std::wstring::wstring(v73, L"RequireExplicitDeclaration");
    *(_BYTE *)(v7 + 59) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v58,
                            (unsigned int)&v60,
                            (unsigned int)&v59,
                            (__int64)v73);
    std::wstring::_Tidy_deallocate(v73);
    StringValue = Windows::Internal::CapabilityAccess::Private::RegGetStringValue(
                    &v82,
                    v58,
                    0,
                    L"LegacyInterfaceClassGuid",
                    0);
    std::wstring::operator=(v7 + 456, StringValue);
    std::wstring::_Tidy_deallocate(&v82);
    *(_BYTE *)(v7 + 488) = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                             v58,
                             0,
                             L"NoClientContextForNotifications",
                             0,
                             lpReserved) == 1;
    *(_BYTE *)(v7 + 489) = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                             v58,
                             0,
                             L"PerAppConsentForFullTrustApps",
                             0,
                             lpReserveda) == 1;
    Uint64Value = Windows::Internal::CapabilityAccess::Private::RegGetUint64Value(
                    v58,
                    0,
                    L"AccessChangeWnf",
                    0,
                    lpReservedb);
    v17 = Windows::Internal::CapabilityAccess::Private::RegGetUint64Value(v58, 0, L"UsageChangeWnf", 0, lpReservedc);
    *(_QWORD *)(v7 + 156) = Uint64Value;
    *(_QWORD *)(v7 + 492) = v17;
    Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(v72, v58, L"CapabilityHandlers");
    v19 = v72[0];
    v20 = v72[1];
    while ( v19 != v20 )
    {
      Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadHandler(v18, v67, &v58, v19);
      std::upper_bound_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::shared_ptr_Windows::Internal::CapabilityAccess::Private::CapabilityHandler________std::shared_ptr_Windows::Internal::CapabilityAccess::Private::CapabilityHandler___lambda_f65c6354d7a69501a81a7d357b777466___(
        &hKey,
        *(_QWORD *)(v7 + 360),
        *(_QWORD *)(v7 + 368),
        v67);
      std::vector<std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>>::emplace<std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> const &>(
        v7 + 360,
        &cchValueName,
        hKey,
        v67);
      v18 = v68;
      if ( v68 )
        std::_Ref_count_base::_Decref(v68);
      v19 += 32;
    }
    Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(&v69, v58, L"Apps");
    v21 = v69;
    v22 = v70;
    if ( v69 != v70 )
    {
      do
      {
        std::wstring::wstring(&Src, L"Apps");
        if ( v77 >= v78 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&Src);
        }
        else
        {
          ++v77;
          v23 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Src);
          *(_DWORD *)(v23 + 2 * v24) = 92;
        }
        v25 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21);
        std::wstring::_Append<unsigned short>(&Src, v25);
        v82 = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
        v83 = 0;
        v84 = 0;
        v85 = 0;
        std::wstring::wstring(v73, L"AppLaunchAccessCheckRequired");
        LODWORD(v83) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v58, &Src, v73);
        std::wstring::_Tidy_deallocate(v73);
        std::wstring::wstring(v73, L"TerminateAppOnAccessChange");
        DWORD1(v83) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v58, &Src, v73);
        std::wstring::_Tidy_deallocate(v73);
        std::wstring::wstring(v73, L"UserConsentRequired");
        DWORD2(v83) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v58, &Src, v73);
        std::wstring::_Tidy_deallocate(v73);
        std::wstring::wstring(v73, L"UserConsentPromptRequired");
        HIDWORD(v83) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v58, &Src, v73);
        std::wstring::_Tidy_deallocate(v73);
        std::wstring::wstring(v73, L"UserAppConsentRequired");
        LODWORD(v84) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v58, &Src, v73);
        std::wstring::_Tidy_deallocate(v73);
        std::wstring::wstring(v73, L"BlockAccess");
        DWORD1(v84) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v58, &Src, v73);
        std::wstring::_Tidy_deallocate(v73);
        std::wstring::wstring(v73, L"InitUserAppConsentDenied");
        DWORD2(v84) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v58, &Src, v73);
        std::wstring::_Tidy_deallocate(v73);
        std::wstring::wstring(v73, L"AlwaysBlockAccess");
        HIDWORD(v84) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v58, &Src, v73);
        std::wstring::_Tidy_deallocate(v73);
        std::wstring::wstring(v73, L"GlobalPrompts");
        LODWORD(v85) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v58, &Src, v73);
        std::wstring::_Tidy_deallocate(v73);
        std::wstring::wstring(v73, L"RequireWindowsCert");
        HIDWORD(v85) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v58, &Src, v73);
        std::wstring::_Tidy_deallocate(v73);
        std::wstring::wstring(v79, v21);
        v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v79);
        std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
          (unsigned int)&hKey,
          v26,
          v26 + 2 * v80,
          v26,
          *(__int64 *)&_o_towlower);
        std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>(
          &v86,
          v79,
          &v82);
        std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::emplace<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>(
          v7 + 168,
          v67,
          &v86);
        *((_QWORD *)&v88 + 1) = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
        std::wstring::_Tidy_deallocate(&v86);
        std::wstring::_Tidy_deallocate(v79);
        std::wstring::_Tidy_deallocate(&Src);
        v21 += 32;
      }
      while ( v21 != v22 );
      v4 = v66;
    }
    std::vector<std::wstring>::_Tidy(&v69);
    Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(&Src, v58, L"Executables");
    v27 = Src;
    v28 = v76;
    if ( Src != v76 )
    {
      do
      {
        v29 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                v29,
                                *(_QWORD *)(v27 + 16),
                                L"AlwaysBlockAccess",
                                17)
          || (v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27),
              (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                 v30,
                                 *(_QWORD *)(v27 + 16),
                                 L"GlobalPrompts",
                                 13))
          || (v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27),
              (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                 v31,
                                 *(_QWORD *)(v27 + 16),
                                 L"RequireWindowsCert",
                                 18)) )
        {
          std::wstring::wstring(v73, L"Executables");
          std::wstring::_Append<unsigned short>(v73, L"\\");
          v32 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
          std::wstring::_Append<unsigned short>(v73, v32);
          Windows::Internal::CapabilityAccess::Private::FullKeyByKeyAndSubPath(&hKey);
          for ( i = 0; ; i = v6 )
          {
            Type = 0;
            cchValueName = 260;
            *(_DWORD *)Data = 0;
            cbData = 4;
            v46 = RegEnumValueW(hKey, i, ValueName, &cchValueName, 0, &Type, Data, &cbData);
            if ( v46 == 259 )
              break;
            if ( Type == 4 && !v46 )
            {
              std::wstring::wstring(v79, ValueName);
              v34 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v79);
              std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
                (unsigned int)v67,
                v34,
                v34 + 2 * v80,
                v34,
                *(__int64 *)&_o_towlower);
              if ( std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::count(
                     v7 + 296,
                     v79) == 1 )
              {
                v35 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
                if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                        v35,
                                        v36,
                                        L"AlwaysBlockAccess",
                                        17) )
                {
                  v37 = 2 - (*(_DWORD *)Data != 0);
                  *(_DWORD *)(std::unordered_map<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::at(
                                v7 + 296,
                                v79)
                            + 36) = v37;
                }
                else
                {
                  v38 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
                  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                          v38,
                                          *(_QWORD *)(v27 + 16),
                                          L"GlobalPrompts",
                                          13) )
                  {
                    v39 = 2 - (*(_DWORD *)Data != 0);
                    *(_DWORD *)(std::unordered_map<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::at(
                                  v7 + 296,
                                  v79)
                              + 40) = v39;
                  }
                  else
                  {
                    v40 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
                    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                            v40,
                                            *(_QWORD *)(v27 + 16),
                                            L"RequireWindowsCert",
                                            18) )
                    {
                      v41 = 2 - (*(_DWORD *)Data != 0);
                      *(_DWORD *)(std::unordered_map<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::at(
                                    v7 + 296,
                                    v79)
                                + 44) = v41;
                    }
                  }
                }
              }
              else
              {
                v82 = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
                v83 = 0;
                v84 = 0;
                v85 = 0;
                v42 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
                if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                        v42,
                                        v43,
                                        L"AlwaysBlockAccess",
                                        17) )
                {
                  HIDWORD(v84) = 2 - (*(_DWORD *)Data != 0);
                }
                else
                {
                  v44 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
                  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                          v44,
                                          *(_QWORD *)(v27 + 16),
                                          L"GlobalPrompts",
                                          13) )
                  {
                    LODWORD(v85) = 2 - (*(_DWORD *)Data != 0);
                  }
                  else
                  {
                    v45 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
                    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                            v45,
                                            *(_QWORD *)(v27 + 16),
                                            L"RequireWindowsCert",
                                            18) )
                      HIDWORD(v85) = 2 - (*(_DWORD *)Data != 0);
                  }
                }
                std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>(
                  &v86,
                  v79,
                  &v82);
                std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::emplace<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>(
                  v7 + 296,
                  &v69,
                  &v86);
                *((_QWORD *)&v88 + 1) = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
                std::wstring::_Tidy_deallocate(&v86);
              }
              std::wstring::_Tidy_deallocate(v79);
            }
            ++v6;
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          std::wstring::_Tidy_deallocate(v73);
          v6 = 0;
        }
        v27 += 32;
      }
      while ( v27 != v28 );
      v4 = v66;
    }
    std::vector<std::wstring>::_Tidy(&Src);
    Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(&Src, v58, L"Services");
    v47 = Src;
    v48 = v76;
    if ( Src != v76 )
    {
      do
      {
        std::wstring::wstring(v79, L"Services");
        if ( v80 >= v81 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v79);
        }
        else
        {
          ++v80;
          v49 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v79);
          *(_DWORD *)(v49 + 2 * v50) = 92;
        }
        v51 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
        std::wstring::_Append<unsigned short>(v79, v51);
        v86 = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
        v87 = 0;
        v88 = 0;
        v89 = 0;
        std::wstring::wstring(&v82, L"UserConsentRequired");
        DWORD2(v87) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v58, v79, &v82);
        std::wstring::_Tidy_deallocate(&v82);
        std::wstring::wstring(&v82, L"AlwaysBlockAccess");
        HIDWORD(v88) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v58, v79, &v82);
        std::wstring::_Tidy_deallocate(&v82);
        std::wstring::wstring(v73, v47);
        v52 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v73);
        std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
          (unsigned int)v67,
          v52,
          v52 + 2 * v74,
          v52,
          *(__int64 *)&_o_towlower);
        std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>(
          &v82,
          v73,
          &v86);
        std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::emplace<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>(
          v7 + 232,
          &v69,
          &v82);
        *((_QWORD *)&v84 + 1) = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
        std::wstring::_Tidy_deallocate(&v82);
        std::wstring::_Tidy_deallocate(v73);
        std::wstring::_Tidy_deallocate(v79);
        v47 += 32;
      }
      while ( v47 != v48 );
      v4 = v66;
    }
    std::vector<std::wstring>::_Tidy(&Src);
    *v4 = v7;
    v4[1] = v71[1];
    std::vector<std::wstring>::_Tidy(v72);
  }
  else
  {
    *v4 = 0;
    v4[1] = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v59);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v60);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v58);
  return v4;
}

```

## disassembly

```asm
0x1800553e8  mov     [rsp-8+arg_18], rbx
0x1800553ed  push    rbp
0x1800553ee  push    rsi
0x1800553ef  push    rdi
0x1800553f0  push    r12
0x1800553f2  push    r13
0x1800553f4  push    r14
0x1800553f6  push    r15
0x1800553f8  lea     rbp, [rsp-300h]
0x180055400  sub     rsp, 400h
0x180055407  mov     rax, cs:__security_cookie
0x18005540e  xor     rax, rsp
0x180055411  mov     [rbp+330h+var_40], rax
0x180055418  mov     rdi, r8
0x18005541b  mov     r14, rdx
0x18005541e  mov     [rsp+430h+var_3B8], rdx
0x180055423  mov     rbx, rcx
0x180055426  mov     [rsp+430h+hKey], rdx
0x18005542b  xor     r12d, r12d
0x18005542e  mov     [rsp+430h+var_3F0], r12
0x180055433  mov     [rsp+430h+var_3E0], r12
0x180055438  mov     [rsp+430h+var_3E8], r12
0x18005543d  lea     rax, [rsp+430h+var_3E8]
0x180055442  mov     [rsp+430h+lpReserved], rax
0x180055447  lea     r9, [rsp+430h+var_3E0]
0x18005544c  lea     r8, [rsp+430h+var_3F0]
0x180055451  mov     rdx, rdi
0x180055454  call    ?GetAllVariantKeys@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@11@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetAllVariantKeys(std::wstring const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x180055459  cmp     [rsp+430h+var_3F0], r12
0x18005545e  jz      loc_180056816
0x180055464  lea     rcx, [rbp+330h+var_380]
0x180055468  call    ?Create@CapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::Create(void)
0x18005546d  nop
0x18005546e  mov     rsi, [rbp+330h+var_380]
0x180055472  lea     rcx, [rsi+8]
0x180055476  mov     rdx, rdi
0x180055479  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18005547e  lea     rdx, aAccessdeniedto; "AccessDeniedToasts"
0x180055485  lea     rcx, [rbp+330h+var_358]
0x180055489  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005548e  nop
0x18005548f  lea     rax, [rbp+330h+var_358]
0x180055493  mov     [rsp+430h+lpReserved], rax
0x180055498  lea     r9, [rsp+430h+var_3E8]
0x18005549d  lea     r8, [rsp+430h+var_3E0]
0x1800554a2  lea     rdx, [rsp+430h+var_3F0]
0x1800554a7  mov     rcx, rbx
0x1800554aa  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x1800554af  mov     [rsi+28h], al
0x1800554b2  lea     rcx, [rbp+330h+var_358]
0x1800554b6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800554bb  lea     rdx, aAllusersconsen; "AllUsersConsentRequiredForMua"
0x1800554c2  lea     rcx, [rbp+330h+var_358]
0x1800554c6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800554cb  nop
0x1800554cc  lea     rax, [rbp+330h+var_358]
0x1800554d0  mov     [rsp+430h+lpReserved], rax
0x1800554d5  lea     r9, [rsp+430h+var_3E8]
0x1800554da  lea     r8, [rsp+430h+var_3E0]
0x1800554df  lea     rdx, [rsp+430h+var_3F0]
0x1800554e4  mov     rcx, rbx
0x1800554e7  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x1800554ec  mov     [rsi+29h], al
0x1800554ef  lea     rcx, [rbp+330h+var_358]
0x1800554f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800554f8  lea     rdx, aAlwaysallowbef; "AlwaysAllowBeforeOOBE"
0x1800554ff  lea     rcx, [rbp+330h+var_358]
0x180055503  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180055508  nop
0x180055509  lea     rax, [rbp+330h+var_358]
0x18005550d  mov     [rsp+430h+lpReserved], rax
0x180055512  lea     r9, [rsp+430h+var_3E8]
0x180055517  lea     r8, [rsp+430h+var_3E0]
0x18005551c  lea     rdx, [rsp+430h+var_3F0]
0x180055521  mov     rcx, rbx
0x180055524  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x180055529  mov     [rsi+2Ah], al
0x18005552c  lea     rcx, [rbp+330h+var_358]
0x180055530  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180055535  lea     rdx, aAlwaysattemptp; "AlwaysAttemptPrompts"
0x18005553c  lea     rcx, [rbp+330h+var_358]
0x180055540  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180055545  nop
0x180055546  lea     rax, [rbp+330h+var_358]
0x18005554a  mov     [rsp+430h+lpReserved], rax
0x18005554f  lea     r9, [rsp+430h+var_3E8]
0x180055554  lea     r8, [rsp+430h+var_3E0]
0x180055559  lea     rdx, [rsp+430h+var_3F0]
0x18005555e  mov     rcx, rbx
0x180055561  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x180055566  mov     [rsi+2Ch], al
0x180055569  lea     rcx, [rbp+330h+var_358]
0x18005556d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180055572  lea     rdx, aAlwaysblockacc; "AlwaysBlockAccess"
0x180055579  lea     rcx, [rbp+330h+var_358]
0x18005557d  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180055582  nop
0x180055583  lea     rax, [rbp+330h+var_358]
0x180055587  mov     [rsp+430h+lpReserved], rax
0x18005558c  lea     r9, [rsp+430h+var_3E8]
0x180055591  lea     r8, [rsp+430h+var_3E0]
0x180055596  lea     rdx, [rsp+430h+var_3F0]
0x18005559b  mov     rcx, rbx
0x18005559e  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x1800555a3  mov     [rsi+2Dh], al
0x1800555a6  lea     rcx, [rbp+330h+var_358]
0x1800555aa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800555af  lea     rdx, aAlwaysblocknon; "AlwaysBlockNonPackaged"
0x1800555b6  lea     rcx, [rbp+330h+var_358]
0x1800555ba  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800555bf  nop
0x1800555c0  lea     rax, [rbp+330h+var_358]
0x1800555c4  mov     [rsp+430h+lpReserved], rax
0x1800555c9  lea     r9, [rsp+430h+var_3E8]
0x1800555ce  lea     r8, [rsp+430h+var_3E0]
0x1800555d3  lea     rdx, [rsp+430h+var_3F0]
0x1800555d8  mov     rcx, rbx
0x1800555db  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x1800555e0  mov     [rsi+2Eh], al
0x1800555e3  lea     rcx, [rbp+330h+var_358]
0x1800555e7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800555ec  lea     rdx, aAsyncprompts; "AsyncPrompts"
0x1800555f3  lea     rcx, [rbp+330h+var_358]
0x1800555f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800555fc  nop
0x1800555fd  lea     rax, [rbp+330h+var_358]
0x180055601  mov     [rsp+430h+lpReserved], rax
0x180055606  lea     r9, [rsp+430h+var_3E8]
0x18005560b  lea     r8, [rsp+430h+var_3E0]
0x180055610  lea     rdx, [rsp+430h+var_3F0]
0x180055615  mov     rcx, rbx
0x180055618  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18005561d  mov     [rsi+98h], al
0x180055623  lea     rcx, [rbp+330h+var_358]
0x180055627  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005562c  lea     rdx, aAsyncpromptsde; "AsyncPromptsDefault"
0x180055633  lea     rcx, [rbp+330h+var_358]
0x180055637  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005563c  nop
0x18005563d  lea     rax, [rbp+330h+var_358]
0x180055641  mov     [rsp+430h+lpReserved], rax
0x180055646  lea     r9, [rsp+430h+var_3E8]
0x18005564b  lea     r8, [rsp+430h+var_3E0]
0x180055650  lea     rdx, [rsp+430h+var_3F0]
0x180055655  mov     rcx, rbx
0x180055658  call    ?ReadPolicyInt@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBAIAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyInt(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18005565d  mov     [rsi+94h], eax
0x180055663  lea     rcx, [rbp+330h+var_358]
0x180055667  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005566c  lea     rdx, aApplaunchacces; "AppLaunchAccessCheckRequired"
0x180055673  lea     rcx, [rbp+330h+var_358]
0x180055677  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005567c  nop
0x18005567d  lea     rax, [rbp+330h+var_358]
0x180055681  mov     [rsp+430h+lpReserved], rax
0x180055686  lea     r9, [rsp+430h+var_3E8]
0x18005568b  lea     r8, [rsp+430h+var_3E0]
0x180055690  lea     rdx, [rsp+430h+var_3F0]
0x180055695  mov     rcx, rbx
0x180055698  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18005569d  mov     [rsi+2Fh], al
0x1800556a0  lea     rcx, [rbp+330h+var_358]
0x1800556a4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800556a9  lea     rdx, aAuditbehaviord; "AuditBehaviorDefault"
0x1800556b0  lea     rcx, [rbp+330h+var_358]
0x1800556b4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800556b9  nop
0x1800556ba  lea     rax, [rbp+330h+var_358]
0x1800556be  mov     [rsp+430h+lpReserved], rax
0x1800556c3  lea     r9, [rsp+430h+var_3E8]
0x1800556c8  lea     r8, [rsp+430h+var_3E0]
0x1800556cd  lea     rdx, [rsp+430h+var_3F0]
0x1800556d2  mov     rcx, rbx
0x1800556d5  call    ?ReadPolicyInt@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBAIAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyInt(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x1800556da  mov     [rsi+88h], eax
0x1800556e0  lea     rcx, [rbp+330h+var_358]
0x1800556e4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800556e9  lea     rdx, aBlockaccess; "BlockAccess"
0x1800556f0  lea     rcx, [rbp+330h+var_358]
0x1800556f4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800556f9  nop
0x1800556fa  lea     rax, [rbp+330h+var_358]
0x1800556fe  mov     [rsp+430h+lpReserved], rax
0x180055703  lea     r9, [rsp+430h+var_3E8]
0x180055708  lea     r8, [rsp+430h+var_3E0]
0x18005570d  lea     rdx, [rsp+430h+var_3F0]
0x180055712  mov     rcx, rbx
0x180055715  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18005571a  mov     [rsi+30h], al
0x18005571d  lea     rcx, [rbp+330h+var_358]
0x180055721  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180055726  lea     rdx, aCapabilityforc; "CapabilityForConsent"
0x18005572d  lea     rcx, [rbp+330h+var_358]
0x180055731  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180055736  nop
0x180055737  lea     rax, [rbp+330h+var_358]
0x18005573b  mov     [rsp+430h+lpReserved], rax
0x180055740  lea     r9, [rsp+430h+var_3E8]
0x180055745  lea     r8, [rsp+430h+var_3E0]
0x18005574a  lea     rdx, [rsp+430h+var_3F0]
0x18005574f  lea     rcx, [rbp+330h+var_2F0]
0x180055753  call    ?ReadPolicyString@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@KA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV67@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x180055758  lea     rcx, [rsi+48h]
0x18005575c  mov     rdx, rax
0x18005575f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180055764  lea     rcx, [rbp+330h+var_2F0]
0x180055768  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005576d  nop
0x18005576e  lea     rcx, [rbp+330h+var_358]
0x180055772  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180055777  lea     rdx, aCapabilityforp_0; "CapabilityForPrompt"
0x18005577e  lea     rcx, [rbp+330h+var_358]
0x180055782  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180055787  nop
0x180055788  lea     rax, [rbp+330h+var_358]
0x18005578c  mov     [rsp+430h+lpReserved], rax
0x180055791  lea     r9, [rsp+430h+var_3E8]
0x180055796  lea     r8, [rsp+430h+var_3E0]
0x18005579b  lea     rdx, [rsp+430h+var_3F0]
0x1800557a0  lea     rcx, [rbp+330h+var_2F0]
0x1800557a4  call    ?ReadPolicyString@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@KA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV67@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x1800557a9  lea     rcx, [rsi+68h]
0x1800557ad  mov     rdx, rax
0x1800557b0  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800557b5  lea     rcx, [rbp+330h+var_2F0]
0x1800557b9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800557be  nop
0x1800557bf  lea     rcx, [rbp+330h+var_358]
0x1800557c3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800557c8  lea     rdx, aCollapserecent; "CollapseRecentActivity"
0x1800557cf  lea     rcx, [rbp+330h+var_358]
0x1800557d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800557d8  nop
0x1800557d9  lea     rax, [rbp+330h+var_358]
0x1800557dd  mov     [rsp+430h+lpReserved], rax
0x1800557e2  lea     r9, [rsp+430h+var_3E8]
0x1800557e7  lea     r8, [rsp+430h+var_3E0]
0x1800557ec  lea     rdx, [rsp+430h+var_3F0]
0x1800557f1  mov     rcx, rbx
0x1800557f4  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x1800557f9  mov     [rsi+31h], al
0x1800557fc  lea     rcx, [rbp+330h+var_358]
0x180055800  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180055805  lea     rdx, aFallbacktokenc; "FallbackTokenCapabilities"
0x18005580c  lea     rcx, [rbp+330h+var_358]
0x180055810  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180055815  nop
0x180055816  lea     rax, [rbp+330h+var_358]
0x18005581a  mov     [rsp+430h+lpReserved], rax
0x18005581f  lea     r9, [rsp+430h+var_3E8]
0x180055824  lea     r8, [rsp+430h+var_3E0]
0x180055829  lea     rdx, [rsp+430h+var_3F0]
0x18005582e  lea     rcx, [rbp+330h+Src]
0x180055832  call    ?ReadPolicyStringArray@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@KA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyStringArray(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x180055837  lea     rcx, [rsi+180h]
0x18005583e  mov     rdx, rax
0x180055841  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> &&)
0x180055846  lea     rcx, [rbp+330h+Src]
0x18005584a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18005584f  nop
0x180055850  lea     rcx, [rbp+330h+var_358]
0x180055854  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180055859  lea     rdx, aForegroundrequ; "ForegroundRequiredForAccess"
0x180055860  lea     rcx, [rbp+330h+var_358]
0x180055864  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180055869  nop
0x18005586a  lea     rax, [rbp+330h+var_358]
0x18005586e  mov     [rsp+430h+lpReserved], rax
0x180055873  lea     r9, [rsp+430h+var_3E8]
0x180055878  lea     r8, [rsp+430h+var_3E0]
0x18005587d  lea     rdx, [rsp+430h+var_3F0]
0x180055882  mov     rcx, rbx
0x180055885  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18005588a  mov     [rsi+32h], al
0x18005588d  lea     rcx, [rbp+330h+var_358]
0x180055891  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180055896  lea     rdx, aGlobalprompts; "GlobalPrompts"
0x18005589d  lea     rcx, [rbp+330h+var_358]
0x1800558a1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800558a6  nop
0x1800558a7  lea     rax, [rbp+330h+var_358]
0x1800558ab  mov     [rsp+430h+lpReserved], rax
0x1800558b0  lea     r9, [rsp+430h+var_3E8]
0x1800558b5  lea     r8, [rsp+430h+var_3E0]
0x1800558ba  lea     rdx, [rsp+430h+var_3F0]
0x1800558bf  mov     rcx, rbx
0x1800558c2  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x1800558c7  mov     [rsi+33h], al
0x1800558ca  lea     rcx, [rbp+330h+var_358]
0x1800558ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800558d3  lea     rdx, aIncludedcapabi; "IncludedCapabilities"
0x1800558da  lea     rcx, [rbp+330h+var_358]
0x1800558de  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800558e3  nop
0x1800558e4  lea     rax, [rbp+330h+var_358]
0x1800558e8  mov     [rsp+430h+lpReserved], rax
0x1800558ed  lea     r9, [rsp+430h+var_3E8]
0x1800558f2  lea     r8, [rsp+430h+var_3E0]
0x1800558f7  lea     rdx, [rsp+430h+var_3F0]
0x1800558fc  lea     rcx, [rbp+330h+Src]
  ... truncated ...
```
