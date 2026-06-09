# Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadLegacyPolicyFromRegistry(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18002a438`
- end: `0x18002b8ba`
- name: `?ReadLegacyPolicyFromRegistry@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z`
- size: `5250`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `39`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18002b8c0`
- `0x180034c3c`

## callees

- `0x180003c80`
- `0x18000a248`
- `0x18000f9e4`
- `0x180014754`
- `0x18001b444`
- `0x18001c330`
- `0x1800207a4`
- `0x180020f7c`
- `0x180021204`
- `0x180021300`
- `0x180021550`
- `0x180021638`
- `0x18002392c`
- `0x180024358`
- `0x180024aa4`
- `0x180025080`
- `0x1800282e4`
- `0x180028414`
- `0x1800286e0`
- `0x180028c34`
- `0x180028ce8`
- `0x180028de8`
- `0x180029664`
- `0x1800296d8`
- `0x18002a1a8`
- `0x18002a1f4`
- `0x18002a438`
- `0x18002bb44`
- `0x18002bb68`
- `0x18002bc70`
- `0x18002bd90`
- `0x18002ca20`
- `0x18002ca5c`
- `0x18002cb24`
- `0x18002f41c`
- `0x18002f4c8`
- `0x18002f690`
- `0x18002f800`
- `0x18002f87c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18002b236`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18002b3f7`
- `api-ms-win-crt-private-l1-1-0!_o_towlower` at `0x18002b7ce`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002b658`
- `api-ms-win-core-registry-l1-1-0!RegEnumValueW` at `0x18002b658`

## string_xrefs

- `0x18002b69b`: `Services`
- `0x18002b6cf`: `Services`
- `0x18002aeeb`: `AccessChangeWnf`
- `0x18002ada1`: `AlwaysAllowInAgentSessions`
- `0x18002a8a9`: `ForegroundRequiredForAccess`
- `0x18002a855`: `FallbackTokenCapabilities`
- `0x18002a585`: `AlwaysAttemptPrompts`
- `0x18002a4ce`: `AccessDeniedToasts`
- `0x18002a5c2`: `AlwaysBlockAccess`
- `0x18002b18b`: `AlwaysBlockAccess`
- `0x18002b2fd`: `AlwaysBlockAccess`
- `0x18002b441`: `AlwaysBlockAccess`
- `0x18002b529`: `AlwaysBlockAccess`
- `0x18002b77e`: `AlwaysBlockAccess`
- `0x18002a739`: `BlockAccess`
- `0x18002b12d`: `BlockAccess`
- `0x18002abb6`: `TerminateAppOnAccessChange`
- `0x18002b071`: `TerminateAppOnAccessChange`
- `0x18002a6bc`: `AppLaunchAccessCheckRequired`
- `0x18002b042`: `AppLaunchAccessCheckRequired`

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
  __int64 v23; // r8
  __int64 v24; // r9
  unsigned __int64 v25; // rdx
  __int64 v26; // rax
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rax
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  int v36; // eax
  __int64 v37; // rdx
  __int64 v38; // r8
  __int64 v39; // r9
  __int64 v40; // rdi
  __int64 v41; // r13
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // r8
  __int64 v45; // r9
  __int64 v46; // rax
  __int64 v47; // rdx
  __int64 v48; // r8
  __int64 v49; // r9
  __int64 v50; // rax
  __int64 v51; // rdx
  __int64 v52; // r8
  __int64 v53; // r9
  __int64 v54; // rax
  DWORD i; // edx
  __int64 v56; // rdx
  __int64 v57; // r8
  __int64 v58; // r9
  int v59; // eax
  __int64 v60; // rax
  __int64 v61; // r8
  __int64 v62; // r9
  __int64 v63; // rdx
  __int64 v64; // rax
  __int64 v65; // rdx
  __int64 v66; // rdx
  __int64 v67; // r8
  __int64 v68; // r9
  int v69; // ebx
  __int64 v70; // rax
  __int64 v71; // rdx
  __int64 v72; // r8
  __int64 v73; // r9
  int v74; // ebx
  __int64 v75; // rax
  int v76; // ebx
  __int64 v77; // rax
  __int64 v78; // rdx
  __int64 v79; // rdx
  __int64 v80; // r8
  __int64 v81; // r9
  __int64 v82; // rax
  __int64 v83; // rdx
  __int64 v84; // r8
  __int64 v85; // r9
  __int64 v86; // rax
  LSTATUS v87; // eax
  __int64 v88; // rdi
  __int64 v89; // r15
  __int64 v90; // r8
  __int64 v91; // r9
  unsigned __int64 v92; // rdx
  __int64 v93; // rax
  __int64 v94; // rdx
  __int64 v95; // r8
  __int64 v96; // r9
  __int64 v97; // rax
  __int64 v98; // r8
  __int64 v99; // r9
  __int64 v100; // rdx
  __int64 v101; // r8
  __int64 v102; // r9
  int v103; // eax
  bool *lpReserved; // [rsp+20h] [rbp-E0h]
  bool *lpReserveda; // [rsp+20h] [rbp-E0h]
  bool *lpReservedb; // [rsp+20h] [rbp-E0h]
  bool *lpReservedc; // [rsp+20h] [rbp-E0h]
  Windows::Internal::CapabilityAccess::Private *v109; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v110; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v111; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[4]; // [rsp+58h] [rbp-A8h] BYREF
  DWORD Type; // [rsp+5Ch] [rbp-A4h] BYREF
  DWORD cbData; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  __int64 cchValueName; // [rsp+70h] [rbp-90h] BYREF
  HKEY v117; // [rsp+78h] [rbp-88h]
  char v118[8]; // [rsp+80h] [rbp-80h] BYREF
  std::_Ref_count_base *v119; // [rsp+88h] [rbp-78h]
  __int64 v120; // [rsp+98h] [rbp-68h] BYREF
  __int64 v121; // [rsp+A0h] [rbp-60h]
  _QWORD v122[2]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v123[3]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v124[16]; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v125; // [rsp+E8h] [rbp-18h]
  __int64 Src; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v127; // [rsp+100h] [rbp+0h]
  unsigned __int64 v128; // [rsp+108h] [rbp+8h]
  unsigned __int64 v129; // [rsp+110h] [rbp+10h]
  _BYTE v130[16]; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int64 v131; // [rsp+128h] [rbp+28h]
  unsigned __int64 v132; // [rsp+130h] [rbp+30h]
  void **v133; // [rsp+140h] [rbp+40h] BYREF
  __int128 v134; // [rsp+148h] [rbp+48h]
  __int128 v135; // [rsp+158h] [rbp+58h]
  __int64 v136; // [rsp+168h] [rbp+68h]
  void **v137; // [rsp+190h] [rbp+90h] BYREF
  __int128 v138; // [rsp+198h] [rbp+98h]
  __int128 v139; // [rsp+1A8h] [rbp+A8h]
  __int64 v140; // [rsp+1B8h] [rbp+B8h]
  WCHAR ValueName[264]; // [rsp+1E0h] [rbp+E0h] BYREF

  v4 = a2;
  v117 = a2;
  v5 = a1;
  hKey = a2;
  v6 = 0;
  v109 = 0;
  v111 = 0;
  v110 = 0;
  Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetAllVariantKeys(a1, a3, &v109, &v111, &v110);
  if ( v109 )
  {
    Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::Create(v122);
    v7 = v122[0];
    std::wstring::operator=(v122[0] + 8LL, a3);
    std::wstring::wstring((__int64)v124, (__int64)L"AccessDeniedToasts");
    *(_BYTE *)(v7 + 40) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"AllUsersConsentRequiredForMua");
    *(_BYTE *)(v7 + 41) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"AlwaysAllowBeforeOOBE");
    *(_BYTE *)(v7 + 42) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"AlwaysAttemptPrompts");
    *(_BYTE *)(v7 + 44) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"AlwaysBlockAccess");
    *(_BYTE *)(v7 + 45) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"AlwaysBlockNonPackaged");
    *(_BYTE *)(v7 + 46) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"AsyncPrompts");
    *(_BYTE *)(v7 + 152) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                             v5,
                             (unsigned int)&v109,
                             (unsigned int)&v111,
                             (unsigned int)&v110,
                             (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"AsyncPromptsDefault");
    *(_DWORD *)(v7 + 148) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyInt(
                              v5,
                              (unsigned int)&v109,
                              (unsigned int)&v111,
                              (unsigned int)&v110,
                              (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"AppLaunchAccessCheckRequired");
    *(_BYTE *)(v7 + 47) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"AuditBehaviorDefault");
    *(_DWORD *)(v7 + 136) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyInt(
                              v5,
                              (unsigned int)&v109,
                              (unsigned int)&v111,
                              (unsigned int)&v110,
                              (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"BlockAccess");
    *(_BYTE *)(v7 + 48) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"CapabilityForConsent");
    PolicyString = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyString(
                     (unsigned int)&v133,
                     (unsigned int)&v109,
                     (unsigned int)&v111,
                     (unsigned int)&v110,
                     (__int64)v124);
    std::wstring::operator=(v7 + 72, PolicyString);
    std::wstring::_Tidy_deallocate(&v133);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"CapabilityForPrompt");
    v9 = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyString(
           (unsigned int)&v133,
           (unsigned int)&v109,
           (unsigned int)&v111,
           (unsigned int)&v110,
           (__int64)v124);
    std::wstring::operator=(v7 + 104, v9);
    std::wstring::_Tidy_deallocate(&v133);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"CollapseRecentActivity");
    *(_BYTE *)(v7 + 49) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"FallbackTokenCapabilities");
    PolicyStringArray = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyStringArray(
                          (unsigned int)&Src,
                          (unsigned int)&v109,
                          (unsigned int)&v111,
                          (unsigned int)&v110,
                          (__int64)v124);
    std::vector<std::wstring>::operator=(v7 + 384, PolicyStringArray);
    std::vector<std::wstring>::_Tidy(&Src);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"ForegroundRequiredForAccess");
    *(_BYTE *)(v7 + 50) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"GlobalPrompts");
    *(_BYTE *)(v7 + 51) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"IncludedCapabilities");
    v11 = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyStringArray(
            (unsigned int)&Src,
            (unsigned int)&v109,
            (unsigned int)&v111,
            (unsigned int)&v110,
            (__int64)v124);
    std::vector<std::wstring>::operator=(v7 + 408, v11);
    std::vector<std::wstring>::_Tidy(&Src);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"InitAllAppsDeniedOrPrompt");
    *(_BYTE *)(v7 + 52) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"InitSystemGlobalConsentDenied");
    *(_BYTE *)(v7 + 53) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"InitUserAppConsentDenied");
    *(_BYTE *)(v7 + 54) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"InitUserGlobalConsentDenied");
    *(_BYTE *)(v7 + 55) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"MinimumSessionDuration");
    *(_BYTE *)(v7 + 56) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"RecordUsageData");
    *(_BYTE *)(v7 + 58) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"RequireActiveSessionForInteractiveUsers");
    *(_BYTE *)(v7 + 140) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                             v5,
                             (unsigned int)&v109,
                             (unsigned int)&v111,
                             (unsigned int)&v110,
                             (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"RequiredCapabilities");
    v12 = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyStringArray(
            (unsigned int)&Src,
            (unsigned int)&v109,
            (unsigned int)&v111,
            (unsigned int)&v110,
            (__int64)v124);
    std::vector<std::wstring>::operator=(v7 + 432, v12);
    std::vector<std::wstring>::_Tidy(&Src);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"RequireWindowsCert");
    *(_BYTE *)(v7 + 60) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"TerminateAppOnAccessChange");
    *(_BYTE *)(v7 + 62) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"ToastFrequencySeconds");
    *(_DWORD *)(v7 + 144) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyInt(
                              v5,
                              (unsigned int)&v109,
                              (unsigned int)&v111,
                              (unsigned int)&v110,
                              (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"UserConsentPromptRequired");
    *(_BYTE *)(v7 + 64) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    std::wstring::wstring((__int64)v124, (__int64)L"UserConsentRequired");
    *(_BYTE *)(v7 + 65) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID59213523>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID59213523>::GetImpl'::`2'::impl) )
    {
      std::wstring::wstring((__int64)v124, (__int64)L"RequireDeveloperMode");
      *(_BYTE *)(v7 + 513) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                               v5,
                               (unsigned int)&v109,
                               (unsigned int)&v111,
                               (unsigned int)&v110,
                               (__int64)v124);
      std::wstring::_Tidy_deallocate(v124);
      std::wstring::wstring((__int64)v124, (__int64)L"SkipCapabilityCheck");
      *(_BYTE *)(v7 + 512) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                               v5,
                               (unsigned int)&v109,
                               (unsigned int)&v111,
                               (unsigned int)&v110,
                               (__int64)v124);
      std::wstring::_Tidy_deallocate(v124);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59946133>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59946133>::GetImpl'::`2'::impl) )
    {
      std::wstring::wstring((__int64)v124, (__int64)L"HideUserGlobal");
      *(_BYTE *)(v7 + 514) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                               v5,
                               (unsigned int)&v109,
                               (unsigned int)&v111,
                               (unsigned int)&v110,
                               (__int64)v124);
      std::wstring::_Tidy_deallocate(v124);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CAM_AgenticSessionsBaseline>::GetImpl'::`2'::impl) )
    {
      std::wstring::wstring((__int64)v124, (__int64)L"AlwaysAllowInAgentSessions");
      *(_BYTE *)(v7 + 43) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                              v5,
                              (unsigned int)&v109,
                              (unsigned int)&v111,
                              (unsigned int)&v110,
                              (__int64)v124);
      std::wstring::_Tidy_deallocate(v124);
    }
    if ( !*(_BYTE *)(v7 + 56) )
    {
      std::wstring::wstring((__int64)v124, (__int64)L"ExtendUXLifetime");
      *(_BYTE *)(v7 + 56) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                              v5,
                              (unsigned int)&v109,
                              (unsigned int)&v111,
                              (unsigned int)&v110,
                              (__int64)v124);
      std::wstring::_Tidy_deallocate(v124);
    }
    LOBYTE(v14) = 3;
    LOBYTE(v13) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAM_CUASupport>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_CAM_CUASupport>::GetImpl'::`2'::impl,
      v13,
      v14);
    std::wstring::wstring((__int64)v124, (__int64)L"RequireExplicitDeclaration");
    *(_BYTE *)(v7 + 59) = Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(
                            v5,
                            (unsigned int)&v109,
                            (unsigned int)&v111,
                            (unsigned int)&v110,
                            (__int64)v124);
    std::wstring::_Tidy_deallocate(v124);
    StringValue = Windows::Internal::CapabilityAccess::Private::RegGetStringValue(
                    &v133,
                    v109,
                    0,
                    L"LegacyInterfaceClassGuid",
                    0);
    std::wstring::operator=(v7 + 456, StringValue);
    std::wstring::_Tidy_deallocate(&v133);
    *(_BYTE *)(v7 + 488) = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                             v109,
                             0,
                             L"NoClientContextForNotifications",
                             0,
                             lpReserved) == 1;
    *(_BYTE *)(v7 + 489) = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                             v109,
                             0,
                             L"PerAppConsentForFullTrustApps",
                             0,
                             lpReserveda) == 1;
    Uint64Value = Windows::Internal::CapabilityAccess::Private::RegGetUint64Value(
                    v109,
                    0,
                    L"AccessChangeWnf",
                    0,
                    lpReservedb);
    v17 = Windows::Internal::CapabilityAccess::Private::RegGetUint64Value(v109, 0, L"UsageChangeWnf", 0, lpReservedc);
    *(_QWORD *)(v7 + 156) = Uint64Value;
    *(_QWORD *)(v7 + 492) = v17;
    Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(v123, v109, L"CapabilityHandlers");
    v19 = v123[0];
    v20 = v123[1];
    while ( v19 != v20 )
    {
      Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadHandler(v18, v118, &v109, v19);
      std::upper_bound_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_std::shared_ptr_Windows::Internal::CapabilityAccess::Private::CapabilityHandler________std::shared_ptr_Windows::Internal::CapabilityAccess::Private::CapabilityHandler___lambda_f65c6354d7a69501a81a7d357b777466___(
        &hKey,
        *(_QWORD *)(v7 + 360),
        *(_QWORD *)(v7 + 368),
        v118);
      std::vector<std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler>>::emplace<std::shared_ptr<Windows::Internal::CapabilityAccess::Private::CapabilityHandler> const &>(
        (_QWORD *)(v7 + 360),
        &cchValueName,
        (__int64)hKey);
      v18 = v119;
      if ( v119 )
        std::_Ref_count_base::_Decref(v119);
      v19 += 32;
    }
    Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(&v120, v109, L"Apps");
    v21 = v120;
    v22 = v121;
    if ( v120 != v121 )
    {
      do
      {
        std::wstring::wstring((__int64)&Src, (__int64)L"Apps");
        v25 = v128;
        if ( v128 >= v129 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(&Src);
        }
        else
        {
          ++v128;
          v26 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(&Src, v25, v23, v24);
          *(_DWORD *)(v26 + 2 * v27) = 92;
        }
        v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v21, v27, v28, v29);
        std::wstring::_Append<unsigned short>(&Src, v30, *(_QWORD *)(v21 + 16));
        v133 = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
        v134 = 0;
        v135 = 0;
        v136 = 0;
        std::wstring::wstring((__int64)v124, (__int64)L"AppLaunchAccessCheckRequired");
        LODWORD(v134) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(
                          &v109,
                          &Src,
                          v124);
        std::wstring::_Tidy_deallocate(v124);
        std::wstring::wstring((__int64)v124, (__int64)L"TerminateAppOnAccessChange");
        DWORD1(v134) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v109, &Src, v124);
        std::wstring::_Tidy_deallocate(v124);
        std::wstring::wstring((__int64)v124, (__int64)L"UserConsentRequired");
        DWORD2(v134) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v109, &Src, v124);
        std::wstring::_Tidy_deallocate(v124);
        std::wstring::wstring((__int64)v124, (__int64)L"UserConsentPromptRequired");
        HIDWORD(v134) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(
                          &v109,
                          &Src,
                          v124);
        std::wstring::_Tidy_deallocate(v124);
        std::wstring::wstring((__int64)v124, (__int64)L"UserAppConsentRequired");
        LODWORD(v135) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(
                          &v109,
                          &Src,
                          v124);
        std::wstring::_Tidy_deallocate(v124);
        std::wstring::wstring((__int64)v124, (__int64)L"BlockAccess");
        DWORD1(v135) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v109, &Src, v124);
        std::wstring::_Tidy_deallocate(v124);
        std::wstring::wstring((__int64)v124, (__int64)L"InitUserAppConsentDenied");
        DWORD2(v135) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(&v109, &Src, v124);
        std::wstring::_Tidy_deallocate(v124);
        std::wstring::wstring((__int64)v124, (__int64)L"AlwaysBlockAccess");
        HIDWORD(v135) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(
                          &v109,
                          &Src,
                          v124);
        std::wstring::_Tidy_deallocate(v124);
        std::wstring::wstring((__int64)v124, (__int64)L"GlobalPrompts");
        LODWORD(v136) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(
                          &v109,
                          &Src,
                          v124);
        std::wstring::_Tidy_deallocate(v124);
        std::wstring::wstring((__int64)v124, (__int64)L"RequireWindowsCert");
        HIDWORD(v136) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(
                          &v109,
                          &Src,
                          v124);
        std::wstring::_Tidy_deallocate(v124);
        std::wstring::wstring((__int64)v130, v21, v31, v32);
        v36 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v130, v33, v34, v35);
        std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
          (unsigned int)&hKey,
          v36,
          v36 + 2 * v131,
          v36,
          _o_towlower);
        std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>(
          (__int64)&v137,
          (__int64)v130,
          &v133);
        std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::emplace<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>(
          (_QWORD *)(v7 + 168),
          (__int64)v118,
          &v137);
        *((_QWORD *)&v139 + 1) = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
        std::wstring::_Tidy_deallocate(&v137);
        std::wstring::_Tidy_deallocate(v130);
        std::wstring::_Tidy_deallocate(&Src);
        v21 += 32;
      }
      while ( v21 != v22 );
      v4 = v117;
    }
    std::vector<std::wstring>::_Tidy(&v120);
    Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(&Src, v109, L"Executables");
    v40 = Src;
    v41 = v127;
    if ( Src != v127 )
    {
      do
      {
        v42 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40, v37, v38, v39);
        if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v42, *(_QWORD *)(v40 + 16))
          || (v46 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40, v43, v44, v45),
              (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v46, *(_QWORD *)(v40 + 16)))
          || (v50 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40, v47, v48, v49),
              (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v50, *(_QWORD *)(v40 + 16))) )
        {
          std::wstring::wstring((__int64)v124, (__int64)L"Executables");
          std::wstring::_Append<unsigned short>(v124, L"\\", 1);
          v54 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40, v51, v52, v53);
          std::wstring::_Append<unsigned short>(v124, v54, *(_QWORD *)(v40 + 16));
          Windows::Internal::CapabilityAccess::Private::FullKeyByKeyAndSubPath(&hKey);
          for ( i = 0; ; i = v6 )
          {
            Type = 0;
            LODWORD(cchValueName) = 260;
            *(_DWORD *)Data = 0;
            cbData = 4;
            v87 = RegEnumValueW(hKey, i, ValueName, (LPDWORD)&cchValueName, 0, &Type, Data, &cbData);
            if ( v87 == 259 )
              break;
            if ( Type == 4 && !v87 )
            {
              std::wstring::wstring((__int64)v130, (__int64)ValueName);
              v59 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v130, v56, v57, v58);
              std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
                (unsigned int)v118,
                v59,
                v59 + 2 * v131,
                v59,
                _o_towlower);
              v60 = std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::count(
                      v7 + 296,
                      v130);
              v63 = *(_QWORD *)(v40 + 16);
              if ( v60 == 1 )
              {
                v64 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40, v63, v61, v62);
                if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v64, v65) )
                {
                  v69 = 2 - (*(_DWORD *)Data != 0);
                  *(_DWORD *)(std::unordered_map<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::at(
                                v7 + 296,
                                v130)
                            + 36) = v69;
                }
                else
                {
                  v70 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40, v66, v67, v68);
                  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v70, *(_QWORD *)(v40 + 16)) )
                  {
                    v74 = 2 - (*(_DWORD *)Data != 0);
                    *(_DWORD *)(std::unordered_map<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::at(
                                  v7 + 296,
                                  v130)
                              + 40) = v74;
                  }
                  else
                  {
                    v75 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40, v71, v72, v73);
                    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                            v75,
                                            *(_QWORD *)(v40 + 16)) )
                    {
                      v76 = 2 - (*(_DWORD *)Data != 0);
                      *(_DWORD *)(std::unordered_map<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::at(
                                    v7 + 296,
                                    v130)
                                + 44) = v76;
                    }
                  }
                }
              }
              else
              {
                v133 = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
                v134 = 0;
                v135 = 0;
                v136 = 0;
                v77 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40, v63, v61, v62);
                if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v77, v78) )
                {
                  HIDWORD(v135) = 2 - (*(_DWORD *)Data != 0);
                }
                else
                {
                  v82 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40, v79, v80, v81);
                  if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(v82, *(_QWORD *)(v40 + 16)) )
                  {
                    LODWORD(v136) = 2 - (*(_DWORD *)Data != 0);
                  }
                  else
                  {
                    v86 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v40, v83, v84, v85);
                    if ( (unsigned __int8)std::_Traits_equal<std::char_traits<unsigned short>>(
                                            v86,
                                            *(_QWORD *)(v40 + 16)) )
                      HIDWORD(v136) = 2 - (*(_DWORD *)Data != 0);
                  }
                }
                std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>(
                  (__int64)&v137,
                  (__int64)v130,
                  &v133);
                std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::emplace<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>(
                  (_QWORD *)(v7 + 296),
                  (__int64)&v120,
                  &v137);
                *((_QWORD *)&v139 + 1) = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
                std::wstring::_Tidy_deallocate(&v137);
              }
              std::wstring::_Tidy_deallocate(v130);
            }
            ++v6;
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          std::wstring::_Tidy_deallocate(v124);
          v6 = 0;
        }
        v40 += 32;
      }
      while ( v40 != v41 );
      v4 = v117;
    }
    std::vector<std::wstring>::_Tidy(&Src);
    Windows::Internal::CapabilityAccess::Private::RegGetKeyArray(&Src, v109, L"Services");
    v88 = Src;
    v89 = v127;
    if ( Src != v127 )
    {
      do
      {
        std::wstring::wstring((__int64)v130, (__int64)L"Services");
        v92 = v131;
        if ( v131 >= v132 )
        {
          std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(v130);
        }
        else
        {
          ++v131;
          v93 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v130, v92, v90, v91);
          *(_DWORD *)(v93 + 2 * v94) = 92;
        }
        v97 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v88, v94, v95, v96);
        std::wstring::_Append<unsigned short>(v130, v97, *(_QWORD *)(v88 + 16));
        v137 = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
        v138 = 0;
        v139 = 0;
        v140 = 0;
        std::wstring::wstring((__int64)&v133, (__int64)L"UserConsentRequired");
        DWORD2(v138) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(
                         &v109,
                         v130,
                         &v133);
        std::wstring::_Tidy_deallocate(&v133);
        std::wstring::wstring((__int64)&v133, (__int64)L"AlwaysBlockAccess");
        HIDWORD(v139) = Windows::Internal::CapabilityAccess::Private::ModernPolicy::ReadAppPolicyValue(
                          &v109,
                          v130,
                          &v133);
        std::wstring::_Tidy_deallocate(&v133);
        std::wstring::wstring((__int64)v124, v88, v98, v99);
        v103 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v124, v100, v101, v102);
        std::transform<std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,std::_String_iterator<std::_String_val<std::_Simple_types<unsigned short>>>,unsigned short (*)(unsigned short)>(
          (unsigned int)v118,
          v103,
          v103 + 2 * v125,
          v103,
          _o_towlower);
        std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>(
          (__int64)&v133,
          (__int64)v124,
          &v137);
        std::_Hash<std::_Umap_traits<std::wstring,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy,std::_Uhash_compare<std::wstring,std::hash<std::wstring>,std::equal_to<std::wstring>>,std::allocator<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>,0>>::emplace<std::pair<std::wstring const,Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy>>(
          (_QWORD *)(v7 + 232),
          (__int64)&v120,
          &v133);
        *((_QWORD *)&v135 + 1) = &Windows::Internal::CapabilityAccess::Private::CapabilityAppPolicy::`vftable';
        std::wstring::_Tidy_deallocate(&v133);
        std::wstring::_Tidy_deallocate(v124);
        std::wstring::_Tidy_deallocate(v130);
        v88 += 32;
      }
      while ( v88 != v89 );
      v4 = v117;
    }
    std::vector<std::wstring>::_Tidy(&Src);
    *v4 = v7;
    v4[1] = v122[1];
    std::vector<std::wstring>::_Tidy(v123);
  }
  else
  {
    *v4 = 0;
    v4[1] = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v110);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v111);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v109);
  return v4;
}

```

## disassembly

```asm
0x18002a438  mov     [rsp-8+arg_18], rbx
0x18002a43d  push    rbp
0x18002a43e  push    rsi
0x18002a43f  push    rdi
0x18002a440  push    r12
0x18002a442  push    r13
0x18002a444  push    r14
0x18002a446  push    r15
0x18002a448  lea     rbp, [rsp-300h]
0x18002a450  sub     rsp, 400h
0x18002a457  mov     rax, cs:__security_cookie
0x18002a45e  xor     rax, rsp
0x18002a461  mov     [rbp+330h+var_40], rax
0x18002a468  mov     rdi, r8
0x18002a46b  mov     r14, rdx
0x18002a46e  mov     [rsp+430h+var_3B8], rdx
0x18002a473  mov     rbx, rcx
0x18002a476  mov     [rsp+430h+hKey], rdx
0x18002a47b  xor     r12d, r12d
0x18002a47e  mov     [rsp+430h+var_3F0], r12
0x18002a483  mov     [rsp+430h+var_3E0], r12
0x18002a488  mov     [rsp+430h+var_3E8], r12
0x18002a48d  lea     rax, [rsp+430h+var_3E8]
0x18002a492  mov     [rsp+430h+lpReserved], rax
0x18002a497  lea     r9, [rsp+430h+var_3E0]
0x18002a49c  lea     r8, [rsp+430h+var_3F0]
0x18002a4a1  mov     rdx, rdi
0x18002a4a4  call    ?GetAllVariantKeys@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@11@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::GetAllVariantKeys(std::wstring const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &)
0x18002a4a9  cmp     [rsp+430h+var_3F0], r12
0x18002a4ae  jz      loc_18002B866
0x18002a4b4  lea     rcx, [rbp+330h+var_380]
0x18002a4b8  call    ?Create@CapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::CapabilityPolicy::Create(void)
0x18002a4bd  nop
0x18002a4be  mov     rsi, [rbp+330h+var_380]
0x18002a4c2  lea     rcx, [rsi+8]
0x18002a4c6  mov     rdx, rdi
0x18002a4c9  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18002a4ce  lea     rdx, aAccessdeniedto; "AccessDeniedToasts"
0x18002a4d5  lea     rcx, [rbp+330h+var_358]
0x18002a4d9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a4de  nop
0x18002a4df  lea     rax, [rbp+330h+var_358]
0x18002a4e3  mov     [rsp+430h+lpReserved], rax
0x18002a4e8  lea     r9, [rsp+430h+var_3E8]
0x18002a4ed  lea     r8, [rsp+430h+var_3E0]
0x18002a4f2  lea     rdx, [rsp+430h+var_3F0]
0x18002a4f7  mov     rcx, rbx
0x18002a4fa  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a4ff  mov     [rsi+28h], al
0x18002a502  lea     rcx, [rbp+330h+var_358]
0x18002a506  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a50b  lea     rdx, aAllusersconsen; "AllUsersConsentRequiredForMua"
0x18002a512  lea     rcx, [rbp+330h+var_358]
0x18002a516  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a51b  nop
0x18002a51c  lea     rax, [rbp+330h+var_358]
0x18002a520  mov     [rsp+430h+lpReserved], rax
0x18002a525  lea     r9, [rsp+430h+var_3E8]
0x18002a52a  lea     r8, [rsp+430h+var_3E0]
0x18002a52f  lea     rdx, [rsp+430h+var_3F0]
0x18002a534  mov     rcx, rbx
0x18002a537  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a53c  mov     [rsi+29h], al
0x18002a53f  lea     rcx, [rbp+330h+var_358]
0x18002a543  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a548  lea     rdx, aAlwaysallowbef; "AlwaysAllowBeforeOOBE"
0x18002a54f  lea     rcx, [rbp+330h+var_358]
0x18002a553  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a558  nop
0x18002a559  lea     rax, [rbp+330h+var_358]
0x18002a55d  mov     [rsp+430h+lpReserved], rax
0x18002a562  lea     r9, [rsp+430h+var_3E8]
0x18002a567  lea     r8, [rsp+430h+var_3E0]
0x18002a56c  lea     rdx, [rsp+430h+var_3F0]
0x18002a571  mov     rcx, rbx
0x18002a574  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a579  mov     [rsi+2Ah], al
0x18002a57c  lea     rcx, [rbp+330h+var_358]
0x18002a580  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a585  lea     rdx, aAlwaysattemptp; "AlwaysAttemptPrompts"
0x18002a58c  lea     rcx, [rbp+330h+var_358]
0x18002a590  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a595  nop
0x18002a596  lea     rax, [rbp+330h+var_358]
0x18002a59a  mov     [rsp+430h+lpReserved], rax
0x18002a59f  lea     r9, [rsp+430h+var_3E8]
0x18002a5a4  lea     r8, [rsp+430h+var_3E0]
0x18002a5a9  lea     rdx, [rsp+430h+var_3F0]
0x18002a5ae  mov     rcx, rbx
0x18002a5b1  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a5b6  mov     [rsi+2Ch], al
0x18002a5b9  lea     rcx, [rbp+330h+var_358]
0x18002a5bd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a5c2  lea     rdx, aAlwaysblockacc; "AlwaysBlockAccess"
0x18002a5c9  lea     rcx, [rbp+330h+var_358]
0x18002a5cd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a5d2  nop
0x18002a5d3  lea     rax, [rbp+330h+var_358]
0x18002a5d7  mov     [rsp+430h+lpReserved], rax
0x18002a5dc  lea     r9, [rsp+430h+var_3E8]
0x18002a5e1  lea     r8, [rsp+430h+var_3E0]
0x18002a5e6  lea     rdx, [rsp+430h+var_3F0]
0x18002a5eb  mov     rcx, rbx
0x18002a5ee  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a5f3  mov     [rsi+2Dh], al
0x18002a5f6  lea     rcx, [rbp+330h+var_358]
0x18002a5fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a5ff  lea     rdx, aAlwaysblocknon; "AlwaysBlockNonPackaged"
0x18002a606  lea     rcx, [rbp+330h+var_358]
0x18002a60a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a60f  nop
0x18002a610  lea     rax, [rbp+330h+var_358]
0x18002a614  mov     [rsp+430h+lpReserved], rax
0x18002a619  lea     r9, [rsp+430h+var_3E8]
0x18002a61e  lea     r8, [rsp+430h+var_3E0]
0x18002a623  lea     rdx, [rsp+430h+var_3F0]
0x18002a628  mov     rcx, rbx
0x18002a62b  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a630  mov     [rsi+2Eh], al
0x18002a633  lea     rcx, [rbp+330h+var_358]
0x18002a637  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a63c  lea     rdx, aAsyncprompts; "AsyncPrompts"
0x18002a643  lea     rcx, [rbp+330h+var_358]
0x18002a647  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a64c  nop
0x18002a64d  lea     rax, [rbp+330h+var_358]
0x18002a651  mov     [rsp+430h+lpReserved], rax
0x18002a656  lea     r9, [rsp+430h+var_3E8]
0x18002a65b  lea     r8, [rsp+430h+var_3E0]
0x18002a660  lea     rdx, [rsp+430h+var_3F0]
0x18002a665  mov     rcx, rbx
0x18002a668  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a66d  mov     [rsi+98h], al
0x18002a673  lea     rcx, [rbp+330h+var_358]
0x18002a677  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a67c  lea     rdx, aAsyncpromptsde; "AsyncPromptsDefault"
0x18002a683  lea     rcx, [rbp+330h+var_358]
0x18002a687  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a68c  nop
0x18002a68d  lea     rax, [rbp+330h+var_358]
0x18002a691  mov     [rsp+430h+lpReserved], rax
0x18002a696  lea     r9, [rsp+430h+var_3E8]
0x18002a69b  lea     r8, [rsp+430h+var_3E0]
0x18002a6a0  lea     rdx, [rsp+430h+var_3F0]
0x18002a6a5  mov     rcx, rbx
0x18002a6a8  call    ?ReadPolicyInt@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBAIAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyInt(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a6ad  mov     [rsi+94h], eax
0x18002a6b3  lea     rcx, [rbp+330h+var_358]
0x18002a6b7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a6bc  lea     rdx, aApplaunchacces; "AppLaunchAccessCheckRequired"
0x18002a6c3  lea     rcx, [rbp+330h+var_358]
0x18002a6c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a6cc  nop
0x18002a6cd  lea     rax, [rbp+330h+var_358]
0x18002a6d1  mov     [rsp+430h+lpReserved], rax
0x18002a6d6  lea     r9, [rsp+430h+var_3E8]
0x18002a6db  lea     r8, [rsp+430h+var_3E0]
0x18002a6e0  lea     rdx, [rsp+430h+var_3F0]
0x18002a6e5  mov     rcx, rbx
0x18002a6e8  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a6ed  mov     [rsi+2Fh], al
0x18002a6f0  lea     rcx, [rbp+330h+var_358]
0x18002a6f4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a6f9  lea     rdx, aAuditbehaviord; "AuditBehaviorDefault"
0x18002a700  lea     rcx, [rbp+330h+var_358]
0x18002a704  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a709  nop
0x18002a70a  lea     rax, [rbp+330h+var_358]
0x18002a70e  mov     [rsp+430h+lpReserved], rax
0x18002a713  lea     r9, [rsp+430h+var_3E8]
0x18002a718  lea     r8, [rsp+430h+var_3E0]
0x18002a71d  lea     rdx, [rsp+430h+var_3F0]
0x18002a722  mov     rcx, rbx
0x18002a725  call    ?ReadPolicyInt@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBAIAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyInt(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a72a  mov     [rsi+88h], eax
0x18002a730  lea     rcx, [rbp+330h+var_358]
0x18002a734  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a739  lea     rdx, aBlockaccess; "BlockAccess"
0x18002a740  lea     rcx, [rbp+330h+var_358]
0x18002a744  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a749  nop
0x18002a74a  lea     rax, [rbp+330h+var_358]
0x18002a74e  mov     [rsp+430h+lpReserved], rax
0x18002a753  lea     r9, [rsp+430h+var_3E8]
0x18002a758  lea     r8, [rsp+430h+var_3E0]
0x18002a75d  lea     rdx, [rsp+430h+var_3F0]
0x18002a762  mov     rcx, rbx
0x18002a765  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a76a  mov     [rsi+30h], al
0x18002a76d  lea     rcx, [rbp+330h+var_358]
0x18002a771  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a776  lea     rdx, aCapabilityforc; "CapabilityForConsent"
0x18002a77d  lea     rcx, [rbp+330h+var_358]
0x18002a781  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a786  nop
0x18002a787  lea     rax, [rbp+330h+var_358]
0x18002a78b  mov     [rsp+430h+lpReserved], rax
0x18002a790  lea     r9, [rsp+430h+var_3E8]
0x18002a795  lea     r8, [rsp+430h+var_3E0]
0x18002a79a  lea     rdx, [rsp+430h+var_3F0]
0x18002a79f  lea     rcx, [rbp+330h+var_2F0]
0x18002a7a3  call    ?ReadPolicyString@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@KA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV67@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a7a8  lea     rcx, [rsi+48h]
0x18002a7ac  mov     rdx, rax
0x18002a7af  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002a7b4  lea     rcx, [rbp+330h+var_2F0]
0x18002a7b8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a7bd  nop
0x18002a7be  lea     rcx, [rbp+330h+var_358]
0x18002a7c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a7c7  lea     rdx, aCapabilityforp_0; "CapabilityForPrompt"
0x18002a7ce  lea     rcx, [rbp+330h+var_358]
0x18002a7d2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a7d7  nop
0x18002a7d8  lea     rax, [rbp+330h+var_358]
0x18002a7dc  mov     [rsp+430h+lpReserved], rax
0x18002a7e1  lea     r9, [rsp+430h+var_3E8]
0x18002a7e6  lea     r8, [rsp+430h+var_3E0]
0x18002a7eb  lea     rdx, [rsp+430h+var_3F0]
0x18002a7f0  lea     rcx, [rbp+330h+var_2F0]
0x18002a7f4  call    ?ReadPolicyString@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@KA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV67@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a7f9  lea     rcx, [rsi+68h]
0x18002a7fd  mov     rdx, rax
0x18002a800  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18002a805  lea     rcx, [rbp+330h+var_2F0]
0x18002a809  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a80e  nop
0x18002a80f  lea     rcx, [rbp+330h+var_358]
0x18002a813  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a818  lea     rdx, aCollapserecent; "CollapseRecentActivity"
0x18002a81f  lea     rcx, [rbp+330h+var_358]
0x18002a823  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a828  nop
0x18002a829  lea     rax, [rbp+330h+var_358]
0x18002a82d  mov     [rsp+430h+lpReserved], rax
0x18002a832  lea     r9, [rsp+430h+var_3E8]
0x18002a837  lea     r8, [rsp+430h+var_3E0]
0x18002a83c  lea     rdx, [rsp+430h+var_3F0]
0x18002a841  mov     rcx, rbx
0x18002a844  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a849  mov     [rsi+31h], al
0x18002a84c  lea     rcx, [rbp+330h+var_358]
0x18002a850  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a855  lea     rdx, aFallbacktokenc; "FallbackTokenCapabilities"
0x18002a85c  lea     rcx, [rbp+330h+var_358]
0x18002a860  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a865  nop
0x18002a866  lea     rax, [rbp+330h+var_358]
0x18002a86a  mov     [rsp+430h+lpReserved], rax
0x18002a86f  lea     r9, [rsp+430h+var_3E8]
0x18002a874  lea     r8, [rsp+430h+var_3E0]
0x18002a879  lea     rdx, [rsp+430h+var_3F0]
0x18002a87e  lea     rcx, [rbp+330h+Src]
0x18002a882  call    ?ReadPolicyStringArray@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@KA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyStringArray(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a887  lea     rcx, [rsi+180h]
0x18002a88e  mov     rdx, rax
0x18002a891  call    ??4?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::vector<std::wstring>::operator=(std::vector<std::wstring> &&)
0x18002a896  lea     rcx, [rbp+330h+Src]
0x18002a89a  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002a89f  nop
0x18002a8a0  lea     rcx, [rbp+330h+var_358]
0x18002a8a4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a8a9  lea     rdx, aForegroundrequ; "ForegroundRequiredForAccess"
0x18002a8b0  lea     rcx, [rbp+330h+var_358]
0x18002a8b4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a8b9  nop
0x18002a8ba  lea     rax, [rbp+330h+var_358]
0x18002a8be  mov     [rsp+430h+lpReserved], rax
0x18002a8c3  lea     r9, [rsp+430h+var_3E8]
0x18002a8c8  lea     r8, [rsp+430h+var_3E0]
0x18002a8cd  lea     rdx, [rsp+430h+var_3F0]
0x18002a8d2  mov     rcx, rbx
0x18002a8d5  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a8da  mov     [rsi+32h], al
0x18002a8dd  lea     rcx, [rbp+330h+var_358]
0x18002a8e1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a8e6  lea     rdx, aGlobalprompts; "GlobalPrompts"
0x18002a8ed  lea     rcx, [rbp+330h+var_358]
0x18002a8f1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a8f6  nop
0x18002a8f7  lea     rax, [rbp+330h+var_358]
0x18002a8fb  mov     [rsp+430h+lpReserved], rax
0x18002a900  lea     r9, [rsp+430h+var_3E8]
0x18002a905  lea     r8, [rsp+430h+var_3E0]
0x18002a90a  lea     rdx, [rsp+430h+var_3F0]
0x18002a90f  mov     rcx, rbx
0x18002a912  call    ?ReadPolicyBool@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@IEBA_NAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@00AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicyBool(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &)
0x18002a917  mov     [rsi+33h], al
0x18002a91a  lea     rcx, [rbp+330h+var_358]
0x18002a91e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18002a923  lea     rdx, aIncludedcapabi; "IncludedCapabilities"
0x18002a92a  lea     rcx, [rbp+330h+var_358]
0x18002a92e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002a933  nop
0x18002a934  lea     rax, [rbp+330h+var_358]
0x18002a938  mov     [rsp+430h+lpReserved], rax
0x18002a93d  lea     r9, [rsp+430h+var_3E8]
0x18002a942  lea     r8, [rsp+430h+var_3E0]
0x18002a947  lea     rdx, [rsp+430h+var_3F0]
0x18002a94c  lea     rcx, [rbp+330h+Src]
  ... truncated ...
```
