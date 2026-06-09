# _lambda_5510f613d0fabd5671f0c5a9aef1d6be_::operator()_wpc::Sync::Internal::SyncLogger::SyncForUser_

- ea: `0x180071fc8`
- end: `0x180073142`
- name: `_lambda_5510f613d0fabd5671f0c5a9aef1d6be_::operator()_wpc::Sync::Internal::SyncLogger::SyncForUser_`
- size: `4474`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `63`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180076f00`

## callees

- `0x1800060a0`
- `0x180006ed4`
- `0x18000819c`
- `0x1800082bc`
- `0x180008cd8`
- `0x180008d50`
- `0x1800093ac`
- `0x180009a18`
- `0x180009a80`
- `0x180009de0`
- `0x18000bba8`
- `0x18000ce6c`
- `0x18000e8b0`
- `0x18000edec`
- `0x180014928`
- `0x18001f65c`
- `0x18001fb38`
- `0x180020720`
- `0x180021090`
- `0x180023638`
- `0x180035240`
- `0x180035340`
- `0x1800356c8`
- `0x180040888`
- `0x1800409b4`
- `0x18004ff40`
- `0x1800548b0`
- `0x180054934`
- `0x1800623f0`
- `0x1800717b8`
- `0x180071e94`
- `0x180071fc8`
- `0x1800733a0`
- `0x180073484`
- `0x1800736a0`
- `0x180073a88`
- `0x180073b98`
- `0x180073eac`
- `0x180073f70`
- `0x180074088`
- `0x180074164`
- `0x1800745c0`
- `0x180074828`
- `0x180074958`
- `0x180074cd4`
- `0x1800753d4`
- `0x180075458`
- `0x180075728`
- `0x180075998`
- `0x180075c08`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180073002`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180073002`

## string_xrefs

- `0x1800722ed`: `SettingsServiceServer`
- `0x1800722d6`: `public.settings.family.microsoft.com`
- `0x180072acd`: `Run Monitor Flag is %d, Run Monitor Service Flag is %d`
- `0x180072e12`: `*** MONITOR SERVICE SYNC: LastSyncTime updated for user `
- `0x180072dc7`: `MonitorService_SyncCheck`
- `0x180072cf5`: `Updated lastSyncTime for user `

## pseudocode

```c
void __fastcall lambda_5510f613d0fabd5671f0c5a9aef1d6be_::operator()_wpc::Sync::Internal::SyncLogger::SyncForUser_(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rdi
  int SettingsServiceAuthTarget; // r14d
  __int64 v7; // rbx
  char v8; // r15
  Private::Format *v9; // rbx
  Private::Format *v10; // rax
  Private::Format *v11; // rax
  Private::Format *v12; // rbx
  _QWORD *v13; // rdx
  const unsigned __int16 *p_Src; // rdx
  __int64 v15; // rbx
  char *v16; // rdi
  __int64 v17; // rbx
  wpc::Policy::SettingsData *v18; // rcx
  const struct Sid *v19; // rdx
  __int64 v20; // rdi
  int FamilyServiceAuthTarget; // r14d
  __int64 v22; // rbx
  Private::Format *v23; // rbx
  Private::Format *v24; // rax
  Private::Format *v25; // rbx
  _QWORD *v26; // rdx
  const unsigned __int16 *v27; // rdx
  __int64 v28; // rbx
  _QWORD *v29; // rdx
  __int64 v30; // rcx
  __int64 v31; // rdi
  char *v32; // rbx
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rbx
  __int64 v36; // rax
  __int64 v37; // rcx
  unsigned int v38; // r8d
  __int64 v39; // rdi
  __int64 v40; // rbx
  int v41; // eax
  __int64 v42; // rax
  unsigned int v43; // r8d
  __int64 v44; // rdi
  __int64 v45; // rbx
  int EnforcementFrontDoorServiceServer; // eax
  __int64 v47; // rax
  __int64 v48; // rdi
  char *v49; // rbx
  __int64 v50; // rax
  struct wpc::Policy::AppTimeLimitsSettings *v51; // rbx
  __int64 v52; // rax
  __int64 v53; // rax
  struct wpc::Policy::AppTimeLimitsSettings *v54; // rbx
  const struct wpc::Policy::SettingsData *v55; // rax
  __int64 Current; // rax
  __int64 v57; // rax
  __int64 v58; // rcx
  __int64 v59; // rax
  __int64 v60; // rax
  __int64 v61; // rax
  const wchar_t *v62; // rcx
  __int64 v63; // rax
  __int64 v64; // rcx
  __int64 v65; // rax
  __int64 v66; // rax
  __int64 v67; // rax
  _DWORD *v68; // rbx
  int SettingsFileAndMergeChangesWithMonitoringFlags; // eax
  __int64 v70; // rax
  Private::Format *v71; // rbx
  __int64 v72; // r8
  const unsigned __int16 *v73; // rdx
  _QWORD *v74; // rdx
  const unsigned __int16 *v75; // rdx
  struct wpc::Policy::AppTimeLimitsSettings *v76; // rbx
  struct Sync::SyncErrorContainer *v77; // [rsp+20h] [rbp-E0h]
  struct Sync::SyncErrorContainer *v78; // [rsp+20h] [rbp-E0h]
  struct Sync::SyncErrorContainer *v79; // [rsp+20h] [rbp-E0h]
  __int64 v80; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v81; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v82[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int128 Src; // [rsp+68h] [rbp-98h] BYREF
  __int128 v84; // [rsp+78h] [rbp-88h]
  int v85; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v86[32]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v87; // [rsp+B0h] [rbp-50h]
  __int64 v88; // [rsp+C0h] [rbp-40h]
  _BYTE v89[40]; // [rsp+C8h] [rbp-38h] BYREF
  unsigned __int16 *v90[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int128 v91; // [rsp+100h] [rbp+0h]
  __int64 v92; // [rsp+128h] [rbp+28h]
  __int64 v93[4]; // [rsp+150h] [rbp+50h] BYREF
  unsigned __int16 *v94[2]; // [rsp+170h] [rbp+70h] BYREF
  __int128 v95; // [rsp+180h] [rbp+80h]
  int v96; // [rsp+190h] [rbp+90h] BYREF
  char v97[32]; // [rsp+198h] [rbp+98h] BYREF
  _BYTE v98[40]; // [rsp+1B8h] [rbp+B8h] BYREF
  char v99[8]; // [rsp+1E0h] [rbp+E0h] BYREF
  char v100[48]; // [rsp+1E8h] [rbp+E8h] BYREF
  struct wpc::Policy::AppTimeLimitsSettings *v101; // [rsp+218h] [rbp+118h]
  int v102; // [rsp+220h] [rbp+120h] BYREF
  char v103[40]; // [rsp+228h] [rbp+128h] BYREF
  _QWORD v104[7]; // [rsp+250h] [rbp+150h] BYREF
  _QWORD *v105; // [rsp+288h] [rbp+188h]
  int v106[4]; // [rsp+290h] [rbp+190h] BYREF
  __int128 v107; // [rsp+2A0h] [rbp+1A0h]
  _OWORD v108[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  struct wpc::Policy::AppTimeLimitsSettings *v109; // [rsp+2D0h] [rbp+1D0h]
  char v110[32]; // [rsp+2D8h] [rbp+1D8h] BYREF
  _BYTE v111[32]; // [rsp+2F8h] [rbp+1F8h] BYREF
  char v112; // [rsp+318h] [rbp+218h]
  _BYTE v113[88]; // [rsp+410h] [rbp+310h] BYREF
  __int64 v114; // [rsp+468h] [rbp+368h]
  _BYTE v115[32]; // [rsp+470h] [rbp+370h] BYREF
  _OWORD v116[4]; // [rsp+490h] [rbp+390h] BYREF
  int v117; // [rsp+4D0h] [rbp+3D0h]
  char v118[32]; // [rsp+4D8h] [rbp+3D8h] BYREF
  _BYTE v119[32]; // [rsp+4F8h] [rbp+3F8h] BYREF
  char v120; // [rsp+518h] [rbp+418h]
  wpc::Policy::SettingsData *v121; // [rsp+618h] [rbp+518h]
  _BYTE v122[384]; // [rsp+628h] [rbp+528h] BYREF
  wpc::Policy::SettingsData *v123; // [rsp+7A8h] [rbp+6A8h]
  int v124; // [rsp+7B0h] [rbp+6B0h] BYREF
  wpc::Policy::SettingsData *v125; // [rsp+938h] [rbp+838h]

  v4 = *(_QWORD **)a1;
  if ( *(_QWORD *)(*(_QWORD *)a1 + 24LL) > 7u )
    v4 = (_QWORD *)*v4;
  v80 = (__int64)v4;
  wpc::Sync::Internal::SyncLogger::SyncForUser::Sid<unsigned short const *>(a2, &v80);
  v123 = 0;
  v114 = 0;
  v101 = 0;
  LOWORD(v81) = 0;
  v5 = *(_QWORD *)(a1 + 16);
  *(_OWORD *)v90 = 0;
  v91 = 0;
  std::wstring::_Construct<1,unsigned short const *>(v90, L"Settings::GetTicketsFailure_", 28);
  SettingsServiceAuthTarget = RegistryHelper::GetSettingsServiceAuthTarget(v98);
  v82[0] = v106;
  v7 = *(_QWORD *)(a1 + 8);
  *(_OWORD *)v106 = *(_OWORD *)v7;
  v107 = *(_OWORD *)(v7 + 16);
  v108[0] = *(_OWORD *)(v7 + 32);
  v108[1] = *(_OWORD *)(v7 + 48);
  LODWORD(v109) = *(_DWORD *)(v7 + 64);
  std::wstring::wstring(v110, v7 + 72);
  v80 = (__int64)v111;
  v112 = 0;
  if ( *(_BYTE *)(v7 + 136) )
  {
    std::wstring::wstring(v111, v7 + 104);
    v112 = 1;
  }
  RefreshTask::Private::GetTicketContainer(
    (unsigned int)&v102,
    (unsigned int)v106,
    SettingsServiceAuthTarget,
    (unsigned int)v90,
    v5);
  std::wstring::~wstring(v98);
  std::wstring::~wstring(v90);
  v8 = *(_BYTE *)(*(_QWORD *)(a1 + 16) + 44LL);
  Src = 0;
  v84 = 0u;
  std::wstring::_Construct<1,unsigned short const *>(
    &Src,
    L"{0}: Get ticket for settings: Ticket valid: {1}, has msa: {2}, cV: {3}",
    70);
  v9 = (Private::Format *)StringAlgo::FormatString(&v85, &Src);
  Sid::AbbrevString(*(_QWORD *)(a1 + 24), v89);
  v10 = (Private::Format *)Private::Format::operator%<std::wstring>(v9);
  v11 = (Private::Format *)Private::Format::operator%<bool>(v10);
  v12 = (Private::Format *)Private::Format::operator%<bool>(v11);
  v13 = *(_QWORD **)(a1 + 32);
  if ( v13[3] > 0xFu )
    v13 = (_QWORD *)*v13;
  StringAlgo::ToUnicode(&Src, v13);
  p_Src = (const unsigned __int16 *)&Src;
  if ( *((_QWORD *)&v84 + 1) > 7u )
    p_Src = (const unsigned __int16 *)Src;
  Private::Format::Replace(v12, p_Src);
  std::wstring::~wstring(&Src);
  LODWORD(v80) = 2;
  wpc::Sync::Internal::SyncLogger::LogMessage(&v80, v12);
  std::wstring::~wstring(v89);
  std::wstring::~wstring(&v85);
  if ( v8 )
  {
    wpc::Policy::SettingsData::SettingsData((wpc::Policy::SettingsData *)v116);
    LOBYTE(v116[0]) = 0;
    v82[0] = v116;
    if ( v123 )
    {
      wpc::Policy::SettingsData::~SettingsData(v123);
      v123 = 0;
    }
    v123 = (wpc::Policy::SettingsData *)wpc::Policy::SettingsData::SettingsData(v122);
    wpc::Policy::SettingsData::~SettingsData((wpc::Policy::SettingsData *)v116);
  }
  else if ( v102 == 1 )
  {
    **(_DWORD **)(a1 + 48) = 0;
  }
  else
  {
    RefreshTask::Private::RegisterForSettingsChanges(
      *(RefreshTask::Private **)(a1 + 24),
      (const struct Sid *)&v102,
      *(struct Sync::TicketContainer **)(a1 + 40),
      *(struct wpc::InstrumentationV2::SmartCV **)(a1 + 16),
      v77);
    v15 = *(_QWORD *)(a1 + 16);
    v16 = (char *)wpc::InstrumentationV2::SmartCV::Step(*(_QWORD *)(a1 + 40), v94);
    Src = 0;
    v84 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&Src, L"public.settings.family.microsoft.com", 36);
    RegistryHelper::ReadRegOrDefault(v93, L"SettingsServiceServer", &Src);
    std::wstring::~wstring(&Src);
    std::wstring::wstring(v89, *(_QWORD *)(a1 + 24) + 72LL);
    Settings::GetSettings(v116, v89);
    std::wstring::~wstring(v89);
    if ( v121 )
    {
      v87 = std::wstring::wstring(v86, (char *)v121 + 8);
      if ( v121 )
        wpc::Policy::SettingsData::~SettingsData(v121);
    }
    else
    {
      v87 = 0;
    }
    v17 = Sync::SyncSettings((int)&v124, *(_QWORD *)(a1 + 24), (int)&v102, (int)&v85, (__int64)v93, v16, v15);
    if ( v123 )
    {
      wpc::Policy::SettingsData::~SettingsData(v123);
      v123 = 0;
    }
    if ( *(_QWORD *)(v17 + 392) )
    {
      v123 = (wpc::Policy::SettingsData *)wpc::Policy::SettingsData::SettingsData(v122);
      v18 = *(wpc::Policy::SettingsData **)(v17 + 392);
      if ( v18 )
      {
        wpc::Policy::SettingsData::~SettingsData(v18);
        *(_QWORD *)(v17 + 392) = 0;
      }
    }
    if ( v125 )
    {
      wpc::Policy::SettingsData::~SettingsData(v125);
      v125 = 0;
    }
    if ( v87 )
    {
      std::wstring::~wstring(v87);
      v87 = 0;
    }
    std::wstring::~wstring(v93);
    std::string::~string(v94);
    **(_DWORD **)(a1 + 48) = 1;
    RefreshTask::Private::CacheUserRegion(*(RefreshTask::Private **)(a1 + 24), v19);
  }
  v20 = *(_QWORD *)(a1 + 16);
  *(_OWORD *)v94 = 0;
  v95 = 0;
  std::wstring::_Construct<1,unsigned short const *>(v94, L"AppTimeLimits::GetTicketsFailure_", 33);
  FamilyServiceAuthTarget = RegistryHelper::GetFamilyServiceAuthTarget(v115);
  v82[0] = v116;
  v22 = *(_QWORD *)(a1 + 8);
  v116[0] = *(_OWORD *)v22;
  v116[1] = *(_OWORD *)(v22 + 16);
  v116[2] = *(_OWORD *)(v22 + 32);
  v116[3] = *(_OWORD *)(v22 + 48);
  v117 = *(_DWORD *)(v22 + 64);
  std::wstring::wstring(v118, v22 + 72);
  v80 = (__int64)v119;
  v120 = 0;
  if ( *(_BYTE *)(v22 + 136) )
  {
    std::wstring::wstring(v119, v22 + 104);
    v120 = 1;
  }
  RefreshTask::Private::GetTicketContainer(
    (unsigned int)&v96,
    (unsigned int)v116,
    FamilyServiceAuthTarget,
    (unsigned int)v94,
    v20);
  std::wstring::~wstring(v115);
  std::wstring::~wstring(v94);
  Src = 0;
  v84 = 0u;
  std::wstring::_Construct<1,unsigned short const *>(
    &Src,
    L"{0}: Get ticket for appTimeLimits: Ticket valid: {1}, cV: {2}",
    61);
  v23 = (Private::Format *)StringAlgo::FormatString(&v85, &Src);
  Sid::AbbrevString(*(_QWORD *)(a1 + 24), v89);
  v24 = (Private::Format *)Private::Format::operator%<std::wstring>(v23);
  v25 = (Private::Format *)Private::Format::operator%<bool>(v24);
  v26 = *(_QWORD **)(a1 + 32);
  if ( v26[3] > 0xFu )
    v26 = (_QWORD *)*v26;
  StringAlgo::ToUnicode(v90, v26);
  v27 = (const unsigned __int16 *)v90;
  if ( *((_QWORD *)&v91 + 1) > 7u )
    v27 = v90[0];
  Private::Format::Replace(v25, v27);
  std::wstring::~wstring(v90);
  LODWORD(v80) = 2;
  wpc::Sync::Internal::SyncLogger::LogMessage(&v80, v25);
  std::wstring::~wstring(v89);
  std::wstring::~wstring(&v85);
  if ( v96 != 1 )
  {
    v28 = *(_QWORD *)(a1 + 24);
    v104[0] = &std::_Func_impl_no_alloc<_lambda_9ffc2c24446efac412092c7e47a9c464_,void,>::`vftable';
    v104[1] = v28;
    v104[2] = &v96;
    v104[3] = *(_QWORD *)(a1 + 40);
    v105 = v104;
    v80 = 864000000000LL;
    *(_OWORD *)v90 = 0;
    v91 = 0;
    std::wstring::_Construct<1,unsigned short const *>(v90, L"RegisterChildDeviceInfo", 23);
    RegHelpers::LimitFrequencyForUser(v90, v28, &v80, v104);
    std::wstring::~wstring(v90);
    if ( v105 )
    {
      v29 = v104;
      LOBYTE(v29) = v105 != v104;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v105 + 32LL))(v105, v29);
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59121731>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59121731>::GetImpl'::`2'::impl) )
    {
      v43 = *(_DWORD *)Feature_FamilySafetyRemoteLock__descriptor;
      if ( (*(_DWORD *)Feature_FamilySafetyRemoteLock__descriptor & 4) == 0 )
      {
        v82[0] = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FamilySafetyRemoteLock>::GetCachedFeatureEnabledState(
                              v30,
                              v82);
        v43 = v82[0];
      }
      LODWORD(v80) = 0;
      WORD2(v80) = 3;
      wil::details::ReportUsageToService(&qword_180109418, 32425780, (v43 >> 10) & 1, (v43 >> 11) & 1);
      RefreshTask::Private::RegisterForScreenTimeLimitsChanges(
        *(RefreshTask::Private **)(a1 + 24),
        (const struct Sid *)&v96,
        *(struct Sync::TicketContainer **)(a1 + 40),
        *(struct wpc::InstrumentationV2::SmartCV **)(a1 + 16),
        (struct Sync::SyncErrorContainer *)&v80);
      v44 = *(_QWORD *)(a1 + 16);
      v45 = wpc::InstrumentationV2::SmartCV::Step(*(_QWORD *)(a1 + 40), v93);
      EnforcementFrontDoorServiceServer = RegistryHelper::GetEnforcementFrontDoorServiceServer(v89);
      v87 = 0;
      v47 = Sync::SyncScreenTimeLimits(
              (unsigned int)v90,
              (unsigned int)&v96,
              (unsigned int)&v85,
              EnforcementFrontDoorServiceServer,
              v45,
              v44);
      Optional<wpc::Policy::TimeRestrictionsSettings>::operator=(v113, v47);
      Optional<wpc::Policy::TimeRestrictionsSettings>::~Optional<wpc::Policy::TimeRestrictionsSettings>(v90);
      if ( v87 )
      {
        std::wstring::~wstring(v87);
        v87 = 0;
      }
      std::wstring::~wstring(v89);
      std::string::~string(v93);
      RefreshTask::Private::RegisterForAppTimeLimitsChanges(
        *(RefreshTask::Private **)(a1 + 24),
        (const struct Sid *)&v96,
        *(struct Sync::TicketContainer **)(a1 + 40),
        *(struct wpc::InstrumentationV2::SmartCV **)(a1 + 16),
        v79);
      v48 = *(_QWORD *)(a1 + 16);
      v49 = (char *)wpc::InstrumentationV2::SmartCV::Step(*(_QWORD *)(a1 + 40), v93);
      v50 = RegistryHelper::GetEnforcementFrontDoorServiceServer(v89);
      v87 = 0;
      Sync::SyncAppTimeLimitsWithMonitoringFlags((int)v106, *(_QWORD *)(a1 + 24), (int)&v96, (int)&v85, v50, v49, v48);
      if ( v87 )
      {
        std::wstring::~wstring(v87);
        v87 = 0;
      }
      std::wstring::~wstring(v89);
      std::string::~string(v93);
      v51 = v101;
      if ( v101 )
      {
        std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::Policy::TimeLimitsRule,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>,0>>::~_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::Policy::TimeLimitsRule,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>,0>>((char *)v101 + 32);
        if ( *((_QWORD *)v51 + 3) )
          *((_QWORD *)v51 + 3) = 0;
        v101 = 0;
      }
      if ( v109 )
        v101 = (struct wpc::Policy::AppTimeLimitsSettings *)wpc::Policy::AppTimeLimitsSettings::AppTimeLimitsSettings(
                                                              (wpc::Policy::AppTimeLimitsSettings *)v100,
                                                              v109);
      LOWORD(v81) = v106[0];
      v52 = StringAlgo::Format(
              v90,
              L"Run Monitor Flag is %d, Run Monitor Service Flag is %d",
              HIBYTE(LOWORD(v106[0])),
              LOBYTE(v106[0]));
      LODWORD(v80) = 2;
      wpc::Sync::Internal::SyncLogger::LogMessage(&v80, v52);
      std::wstring::~wstring(v90);
      if ( v101 )
        v53 = wpc::Policy::AppTimeLimitsSettings::AppTimeLimitsSettings(
                (wpc::Policy::AppTimeLimitsSettings *)&v90[1],
                v101);
      else
        v53 = 0;
      v92 = v53;
      SyncEngineHelper::MergeAppLimitsSettingsChanges(*(_QWORD *)(a1 + 24), v90);
      v54 = v109;
      if ( v109 )
      {
        std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::Policy::TimeLimitsRule,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>,0>>::~_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::Policy::TimeLimitsRule,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>,0>>((char *)v109 + 32);
        if ( *((_QWORD *)v54 + 3) )
          *((_QWORD *)v54 + 3) = 0;
      }
    }
    else
    {
      RefreshTask::Private::RegisterForAppTimeLimitsChanges(
        *(RefreshTask::Private **)(a1 + 24),
        (const struct Sid *)&v96,
        *(struct Sync::TicketContainer **)(a1 + 40),
        *(struct wpc::InstrumentationV2::SmartCV **)(a1 + 16),
        v78);
      v31 = *(_QWORD *)(a1 + 16);
      v32 = (char *)wpc::InstrumentationV2::SmartCV::Step(*(_QWORD *)(a1 + 40), v93);
      v33 = RegistryHelper::GetEnforcementFrontDoorServiceServer(v89);
      v87 = 0;
      v34 = Sync::SyncAppTimeLimits((int)v90, *(_QWORD *)(a1 + 24), (int)&v96, (int)&v85, v33, v32, v31);
      Optional<wpc::Policy::AppTimeLimitsSettings>::operator=(v99, v34);
      v35 = v92;
      if ( v92 )
      {
        std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::Policy::TimeLimitsRule,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>,0>>::~_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::Policy::TimeLimitsRule,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>,0>>(v92 + 32);
        if ( *(_QWORD *)(v35 + 24) )
          *(_QWORD *)(v35 + 24) = 0;
        v92 = 0;
      }
      if ( v87 )
      {
        std::wstring::~wstring(v87);
        v87 = 0;
      }
      std::wstring::~wstring(v89);
      std::string::~string(v93);
      if ( v101 )
        v36 = wpc::Policy::AppTimeLimitsSettings::AppTimeLimitsSettings((wpc::Policy::AppTimeLimitsSettings *)v86, v101);
      else
        v36 = 0;
      v88 = v36;
      SyncEngineHelper::MergeAppLimitsSettingsChanges(*(_QWORD *)(a1 + 24), &v85);
      v38 = *(_DWORD *)Feature_FamilySafetyRemoteLock__descriptor;
      if ( (*(_DWORD *)Feature_FamilySafetyRemoteLock__descriptor & 4) == 0 )
      {
        v82[0] = *(_QWORD *)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FamilySafetyRemoteLock>::GetCachedFeatureEnabledState(
                              v37,
                              v82);
        v38 = v82[0];
      }
      LODWORD(v80) = 0;
      WORD2(v80) = 3;
      wil::details::ReportUsageToService(&qword_180109418, 32425780, (v38 >> 10) & 1, (v38 >> 11) & 1);
      RefreshTask::Private::RegisterForScreenTimeLimitsChanges(
        *(RefreshTask::Private **)(a1 + 24),
        (const struct Sid *)&v96,
        *(struct Sync::TicketContainer **)(a1 + 40),
        *(struct wpc::InstrumentationV2::SmartCV **)(a1 + 16),
        (struct Sync::SyncErrorContainer *)&v80);
      v39 = *(_QWORD *)(a1 + 16);
      v40 = wpc::InstrumentationV2::SmartCV::Step(*(_QWORD *)(a1 + 40), v93);
      v41 = RegistryHelper::GetEnforcementFrontDoorServiceServer(v89);
      v87 = 0;
      v42 = Sync::SyncScreenTimeLimits((unsigned int)v106, (unsigned int)&v96, (unsigned int)&v85, v41, v40, v39);
      Optional<wpc::Policy::TimeRestrictionsSettings>::operator=(v113, v42);
      Optional<wpc::Policy::TimeRestrictionsSettings>::~Optional<wpc::Policy::TimeRestrictionsSettings>(v106);
      if ( v87 )
      {
        std::wstring::~wstring(v87);
        v87 = 0;
      }
      std::wstring::~wstring(v89);
      std::string::~string(v93);
    }
  }
  if ( v123 || v114 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59121731>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59121731>::GetImpl'::`2'::impl) )
    {
      if ( v101 )
        v70 = wpc::Policy::AppTimeLimitsSettings::AppTimeLimitsSettings((wpc::Policy::AppTimeLimitsSettings *)v86, v101);
      else
        v70 = 0;
      v88 = v70;
      v68 = *(_DWORD **)(a1 + 48);
      SettingsFileAndMergeChangesWithMonitoringFlags = SyncEngineHelper::ReadSettingsFileAndMergeChangesWithMonitoringFlags(
                                                         *(SyncEngineHelper **)(a1 + 24),
                                                         (__int64)&v81);
    }
    else
    {
      v68 = *(_DWORD **)(a1 + 48);
      SettingsFileAndMergeChangesWithMonitoringFlags = SyncEngineHelper::ReadSettingsFileAndMergeChanges(*(SyncEngineHelper **)(a1 + 24));
    }
    *v68 = SettingsFileAndMergeChangesWithMonitoringFlags;
  }
  else if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58247009>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58247009>::GetImpl'::`2'::impl)
         && v102 != 1
         && !v8 )
  {
    *(_OWORD *)v90 = 0;
    v91 = 0;
    std::wstring::_Construct<1,unsigned short const *>(
      v90,
      L"No new policy fetched, but valid ticket - updating lastSyncTime",
      63);
    LODWORD(v80) = 2;
    wpc::Sync::Internal::SyncLogger::LogMessage(&v80, v90);
    std::wstring::~wstring(v90);
    Settings::LoadSettings(v98);
    std::wstring::wstring(v89, *(_QWORD *)(a1 + 24) + 72LL);
    Sid::AbbrevString(*(_QWORD *)(a1 + 24), v93);
    v55 = (const struct wpc::Policy::SettingsData *)stdext::lookup<std::wstring,std::map<std::wstring,wpc::Policy::SettingsData>>(
                                                      v98,
                                                      v89);
    if ( v55 && *(_BYTE *)v55 )
    {
      wpc::Policy::SettingsData::SettingsData((wpc::Policy::SettingsData *)v106, v55);
      Current = DateTime::GetCurrent(v82);
      DateTime::ToDebugString(Current, v90, 0);
      std::wstring::operator=((char *)v108 + 8, v90);
      std::wstring::~wstring(v90);
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_59121731>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_59121731>::GetImpl'::`2'::impl)
        && v101 )
      {
        LOBYTE(v106[1]) = BYTE1(v81);
        BYTE1(v106[1]) = v81;
      }
      v57 = std::map<std::wstring,wpc::Policy::SettingsData>::operator[](v98, v89);
      wpc::Policy::SettingsData::operator=(v57, v106);
      Settings::SaveSettings(v98);
      Src = 0;
      v84 = 0;
      v80 = 31;
      v59 = std::wstring::_Allocate_for_capacity<0>(v58, &v80);
      *(_QWORD *)&Src = v59;
      *(_QWORD *)&v84 = 30;
      *((_QWORD *)&v84 + 1) = v80;
      *(_OWORD *)v59 = *(_OWORD *)L"Updated lastSyncTime for user ";
      *(_OWORD *)(v59 + 16) = *(_OWORD *)L"lastSyncTime for user ";
      *(_OWORD *)(v59 + 32) = *(_OWORD *)L"Time for user ";
      *(_OWORD *)(v59 + 44) = *(_OWORD *)L"or user ";
      *(_WORD *)(v59 + 60) = 0;
      v60 = std::wstring::append(&Src);
      *(_OWORD *)v90 = 0;
      v91 = 0;
      *(_OWORD *)v90 = *(_OWORD *)v60;
      v91 = *(_OWORD *)(v60 + 16);
      *(_QWORD *)(v60 + 16) = 0;
      *(_QWORD *)(v60 + 24) = 7;
      *(_WORD *)v60 = 0;
      v61 = std::operator+<unsigned short>(&v85, v90, L" (no policy changes)");
      LODWORD(v80) = 2;
      wpc::Sync::Internal::SyncLogger::LogMessage(&v80, v61);
      std::wstring::~wstring(&v85);
      std::wstring::~wstring(v90);
      std::wstring::~wstring(&Src);
      v62 = *(const wchar_t **)(a1 + 56);
      v63 = *((_QWORD *)v62 + 2);
      if ( *((_QWORD *)v62 + 3) > 7u )
        v62 = *(const wchar_t **)v62;
      if ( v63 == 24 && !wmemcmp(v62, L"MonitorService_SyncCheck", 0x18u) )
      {
        Src = 0;
        v84 = 0;
        v80 = 63;
        v65 = std::wstring::_Allocate_for_capacity<0>(v64, &v80);
        *(_QWORD *)&Src = v65;
        *(_QWORD *)&v84 = 56;
        *((_QWORD *)&v84 + 1) = v80;
        *(_OWORD *)v65 = *(_OWORD *)L"*** MONITOR SERVICE SYNC: LastSyncTime updated for user ";
        *(_OWORD *)(v65 + 16) = *(_OWORD *)L"TOR SERVICE SYNC: LastSyncTime updated for user ";
        *(_OWORD *)(v65 + 32) = *(_OWORD *)L"ICE SYNC: LastSyncTime updated for user ";
        *(_OWORD *)(v65 + 48) = *(_OWORD *)L": LastSyncTime updated for user ";
        *(_OWORD *)(v65 + 64) = *(_OWORD *)L"ncTime updated for user ";
        *(_OWORD *)(v65 + 80) = *(_OWORD *)L"pdated for user ";
        *(_OWORD *)(v65 + 96) = *(_OWORD *)L"or user ";
        *(_WORD *)(v65 + 112) = 0;
        v66 = std::wstring::append(&Src);
        *(_OWORD *)v90 = 0;
        v91 = 0;
        *(_OWORD *)v90 = *(_OWORD *)v66;
        v91 = *(_OWORD *)(v66 + 16);
        *(_QWORD *)(v66 + 16) = 0;
        *(_QWORD *)(v66 + 24) = 7;
        *(_WORD *)v66 = 0;
        v67 = std::operator+<unsigned short>(&v85, v90, L" ***");
        LODWORD(v80) = 2;
        wpc::Sync::Internal::SyncLogger::LogMessage(&v80, v67);
        std::wstring::~wstring(&v85);
        std::wstring::~wstring(v90);
        std::wstring::~wstring(&Src);
      }
      wpc::Policy::SettingsData::~SettingsData((wpc::Policy::SettingsData *)v106);
    }
    std::wstring::~wstring(v93);
    std::wstring::~wstring(v89);
    std::_Tree<std::_Tmap_traits<std::wstring,wpc::Policy::SettingsData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wpc::Policy::SettingsData>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,wpc::Policy::SettingsData,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,wpc::Policy::SettingsData>>,0>>(v98);
  }
  LODWORD(v80) = **(_DWORD **)(a1 + 48);
  wpc::Sync::Internal::SyncLogger::SyncForUser::SettingsMergeResult<unsigned int>(a2, &v80);
  *(_OWORD *)v90 = 0;
  v91 = 0u;
  std::wstring::_Construct<1,unsigned short const *>(v90, L"Settings merge result: {0}, cV: {1}", 35);
  v71 = (Private::Format *)StringAlgo::FormatString(&v85, v90);
  memset_0(v106, 0, 0x82u);
  _o__ui64tow_s(**(int **)(a1 + 48), v106, 65);
  Src = 0;
  v84 = 0;
  v72 = -1;
  do
    ++v72;
  while ( *((_WORD *)v106 + v72) );
  std::wstring::_Construct<1,unsigned short const *>(&Src, v106, v72);
  v73 = (const unsigned __int16 *)&Src;
  if ( *((_QWORD *)&v84 + 1) > 7u )
    v73 = (const unsigned __int16 *)Src;
  Private::Format::Replace(v71, v73);
  std::wstring::~wstring(&Src);
  v74 = *(_QWORD **)(a1 + 32);
  if ( v74[3] > 0xFu )
    v74 = (_QWORD *)*v74;
  StringAlgo::ToUnicode(v94, v74);
  v75 = (const unsigned __int16 *)v94;
  if ( *((_QWORD *)&v95 + 1) > 7u )
    v75 = v94[0];
  Private::Format::Replace(v71, v75);
  std::wstring::~wstring(v94);
  LODWORD(v80) = 2;
  wpc::Sync::Internal::SyncLogger::LogMessage(&v80, v71);
  std::wstring::~wstring(&v85);
  std::wstring::~wstring(v97);
  std::wstring::~wstring(v103);
  v76 = v101;
  if ( v101 )
  {
    std::_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::Policy::TimeLimitsRule,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>,0>>::~_Tree<std::_Tmap_traits<appids::AnyRuntimeApp,wpc::Policy::TimeLimitsRule,std::less<appids::AnyRuntimeApp>,std::allocator<std::pair<appids::AnyRuntimeApp const,wpc::Policy::TimeLimitsRule>>,0>>((char *)v101 + 32);
    if ( *((_QWORD *)v76 + 3) )
      *((_QWORD *)v76 + 3) = 0;
    v101 = 0;
  }
  Optional<wpc::Policy::TimeRestrictionsSettings>::~Optional<wpc::Policy::TimeRestrictionsSettings>(v113);
  if ( v123 )
    wpc::Policy::SettingsData::~SettingsData(v123);
}

```

## disassembly

```asm
0x180071fc8  mov     [rsp-8+arg_10], rbx
0x180071fcd  push    rbp
0x180071fce  push    rsi
0x180071fcf  push    rdi
0x180071fd0  push    r12
0x180071fd2  push    r13
0x180071fd4  push    r14
0x180071fd6  push    r15
0x180071fd8  lea     rbp, [rsp-850h]
0x180071fe0  sub     rsp, 950h
0x180071fe7  mov     rax, cs:__security_cookie
0x180071fee  xor     rax, rsp
0x180071ff1  mov     [rbp+880h+var_40], rax
0x180071ff8  mov     r12, rdx
0x180071ffb  mov     rsi, rcx
0x180071ffe  xor     r13d, r13d
0x180072001  mov     rax, [rcx]
0x180072004  cmp     qword ptr [rax+18h], 7
0x180072009  jbe     short loc_18007200E
0x18007200b  mov     rax, [rax]
0x18007200e  mov     [rsp+980h+var_938], rax
0x180072013  lea     rdx, [rsp+980h+var_938]
0x180072018  mov     rcx, r12
0x18007201b  call    ??$Sid@PEBG@SyncForUser@SyncLogger@Internal@Sync@wpc@@QEAAX$$QEAPEBG@Z; wpc::Sync::Internal::SyncLogger::SyncForUser::Sid<ushort const *>(ushort const * &&)
0x180072020  mov     [rbp+880h+var_1D8], r13
0x180072027  mov     [rbp+880h+var_518], r13
0x18007202e  mov     [rbp+880h+var_768], r13
0x180072035  mov     word ptr [rsp+980h+var_930], r13w
0x18007203b  mov     rdi, [rsi+10h]
0x18007203f  xorps   xmm0, xmm0
0x180072042  movups  xmmword ptr [rbp+880h+var_890], xmm0
0x180072046  xorps   xmm1, xmm1
0x180072049  movdqu  [rbp+880h+var_880], xmm1
0x18007204e  mov     r8d, 1Ch
0x180072054  lea     rdx, aSettingsGettic; "Settings::GetTicketsFailure_"
0x18007205b  lea     rcx, [rbp+880h+var_890]
0x18007205f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180072064  nop
0x180072065  lea     rcx, [rbp+880h+var_7C8]
0x18007206c  call    ?GetSettingsServiceAuthTarget@RegistryHelper@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; RegistryHelper::GetSettingsServiceAuthTarget(void)
0x180072071  mov     r14, rax
0x180072074  lea     rax, [rbp+880h+var_6F0]
0x18007207b  mov     [rsp+980h+var_928], rax
0x180072080  mov     rbx, [rsi+8]
0x180072084  movups  xmm0, xmmword ptr [rbx]
0x180072087  movups  xmmword ptr [rbp+880h+var_6F0], xmm0
0x18007208e  movups  xmm1, xmmword ptr [rbx+10h]
0x180072092  movups  [rbp+880h+var_6E0], xmm1
0x180072099  movups  xmm0, xmmword ptr [rbx+20h]
0x18007209d  movups  [rbp+880h+var_6D0], xmm0
0x1800720a4  movups  xmm1, xmmword ptr [rbx+30h]
0x1800720a8  movups  [rbp+880h+var_6C0], xmm1
0x1800720af  mov     eax, [rbx+40h]
0x1800720b2  mov     dword ptr [rbp+880h+var_6B0], eax
0x1800720b8  lea     rdx, [rbx+48h]
0x1800720bc  lea     rcx, [rbp+880h+var_6A8]
0x1800720c3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800720c8  nop
0x1800720c9  lea     rax, [rbp+880h+var_688]
0x1800720d0  mov     [rsp+980h+var_938], rax
0x1800720d5  lea     rdx, [rbx+68h]
0x1800720d9  mov     [rbp+880h+var_668], r13b
0x1800720e0  cmp     [rdx+20h], r13b
0x1800720e4  jz      short loc_1800720F9
0x1800720e6  lea     rcx, [rbp+880h+var_688]
0x1800720ed  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800720f2  mov     [rbp+880h+var_668], 1
0x1800720f9  mov     [rsp+980h+var_960], rdi; struct Sync::SyncErrorContainer *
0x1800720fe  lea     r9, [rbp+880h+var_890]
0x180072102  mov     r8, r14
0x180072105  lea     rdx, [rbp+880h+var_6F0]
0x18007210c  lea     rcx, [rbp+880h+var_760]
0x180072113  call    ?GetTicketContainer@Private@RefreshTask@@YA?AVTicketContainer@Sync@@U?$pair@VSid@@V?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@6@1AEAVSyncErrorContainer@4@@Z; RefreshTask::Private::GetTicketContainer(std::pair<Sid,std::optional<std::wstring>>,std::wstring const &,std::wstring const &,Sync::SyncErrorContainer &)
0x180072118  nop
0x180072119  lea     rcx, [rbp+880h+var_7C8]
0x180072120  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180072125  nop
0x180072126  lea     rcx, [rbp+880h+var_890]
0x18007212a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007212f  mov     rax, [rsi+10h]
0x180072133  mov     r15b, [rax+2Ch]
0x180072137  xorps   xmm0, xmm0
0x18007213a  movups  [rsp+980h+Src], xmm0
0x18007213f  mov     qword ptr [rsp+980h+var_908], r13
0x180072144  mov     qword ptr [rbp+880h+var_908+8], r13
0x180072148  mov     r8d, 46h ; 'F'
0x18007214e  lea     rdx, a0GetTicketForS; "{0}: Get ticket for settings: Ticket va"...
0x180072155  lea     rcx, [rsp+980h+Src]
0x18007215a  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007215f  lea     rdx, [rsp+980h+Src]
0x180072164  lea     rcx, [rbp+880h+var_8F8]
0x180072168  call    ?FormatString@StringAlgo@@YA?AVFormat@Private@@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; StringAlgo::FormatString(std::wstring)
0x18007216d  mov     rbx, rax
0x180072170  lea     rdx, [rbp+880h+var_8B8]
0x180072174  mov     rcx, [rsi+18h]
0x180072178  call    ?AbbrevString@Sid@@QEBA?BV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; Sid::AbbrevString(void)
0x18007217d  nop
0x18007217e  mov     rdx, rax
0x180072181  mov     rcx, rbx; this
0x180072184  call    ??$?LV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Format@Private@@QEAAAEAV01@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Private::Format::operator%<std::wstring>(std::wstring const &)
0x180072189  cmp     [rbp+880h+var_760], 1
0x180072190  setnz   [rsp+980h+var_940]
0x180072195  lea     rdx, [rsp+980h+var_940]
0x18007219a  mov     rcx, rax; this
0x18007219d  call    ??$?L_N@Format@Private@@QEAAAEAV01@AEB_N@Z; Private::Format::operator%<bool>(bool const &)
0x1800721a2  test    r15b, r15b
0x1800721a5  setz    [rsp+980h+var_940]
0x1800721aa  lea     rdx, [rsp+980h+var_940]
0x1800721af  mov     rcx, rax; this
0x1800721b2  call    ??$?L_N@Format@Private@@QEAAAEAV01@AEB_N@Z; Private::Format::operator%<bool>(bool const &)
0x1800721b7  mov     rbx, rax
0x1800721ba  mov     rdx, [rsi+20h]
0x1800721be  cmp     qword ptr [rdx+18h], 0Fh
0x1800721c3  jbe     short loc_1800721C8
0x1800721c5  mov     rdx, [rdx]
0x1800721c8  lea     rcx, [rsp+980h+Src]
0x1800721cd  call    ?ToUnicode@StringAlgo@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; StringAlgo::ToUnicode(char const *)
0x1800721d2  nop
0x1800721d3  lea     rdx, [rsp+980h+Src]
0x1800721d8  cmp     qword ptr [rbp+880h+var_908+8], 7
0x1800721dd  cmova   rdx, qword ptr [rsp+980h+Src]; unsigned __int16 *
0x1800721e3  mov     rcx, rbx; this
0x1800721e6  call    ?Replace@Format@Private@@AEAAXPEBG@Z; Private::Format::Replace(ushort const *)
0x1800721eb  nop
0x1800721ec  lea     rcx, [rsp+980h+Src]
0x1800721f1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800721f6  mov     dword ptr [rsp+980h+var_938], 2
0x1800721fe  mov     rdx, rbx
0x180072201  lea     rcx, [rsp+980h+var_938]
0x180072206  call    ?LogMessage@SyncLogger@Internal@Sync@wpc@@SAXAEBW4LogLevel@Logging@4@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::Sync::Internal::SyncLogger::LogMessage(wpc::Logging::LogLevel const &,std::wstring const &)
0x18007220b  nop
0x18007220c  lea     rcx, [rbp+880h+var_8B8]
0x180072210  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180072215  nop
0x180072216  lea     rcx, [rbp+880h+var_8F8]
0x18007221a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007221f  test    r15b, r15b
0x180072222  jz      short loc_180072286
0x180072224  lea     rcx, [rbp+880h+var_4F0]; this
0x18007222b  call    ??0SettingsData@Policy@wpc@@QEAA@XZ; wpc::Policy::SettingsData::SettingsData(void)
0x180072230  mov     byte ptr [rbp+880h+var_4F0], r13b
0x180072237  lea     rax, [rbp+880h+var_4F0]
0x18007223e  mov     [rsp+980h+var_928], rax
0x180072243  mov     rcx, [rbp+880h+var_1D8]; this
0x18007224a  test    rcx, rcx
0x18007224d  jz      short loc_18007225B
0x18007224f  call    ??1SettingsData@Policy@wpc@@QEAA@XZ; wpc::Policy::SettingsData::~SettingsData(void)
0x180072254  mov     [rbp+880h+var_1D8], r13
0x18007225b  lea     rdx, [rbp+880h+var_4F0]
0x180072262  lea     rcx, [rbp+880h+var_358]
0x180072269  call    ??0SettingsData@Policy@wpc@@QEAA@$$QEAV012@@Z; wpc::Policy::SettingsData::SettingsData(wpc::Policy::SettingsData &&)
0x18007226e  mov     [rbp+880h+var_1D8], rax
0x180072275  lea     rcx, [rbp+880h+var_4F0]; this
0x18007227c  call    ??1SettingsData@Policy@wpc@@QEAA@XZ; wpc::Policy::SettingsData::~SettingsData(void)
0x180072281  jmp     loc_180072442
0x180072286  cmp     [rbp+880h+var_760], 1
0x18007228d  jz      loc_18007243B
0x180072293  mov     r9, [rsi+10h]; struct wpc::InstrumentationV2::SmartCV *
0x180072297  mov     r8, [rsi+28h]; struct Sync::TicketContainer *
0x18007229b  lea     rdx, [rbp+880h+var_760]; struct Sid *
0x1800722a2  mov     rcx, [rsi+18h]; this
0x1800722a6  call    ?RegisterForSettingsChanges@Private@RefreshTask@@YAXAEBVSid@@AEAVTicketContainer@Sync@@AEAVSmartCV@InstrumentationV2@wpc@@AEAVSyncErrorContainer@5@@Z; RefreshTask::Private::RegisterForSettingsChanges(Sid const &,Sync::TicketContainer &,wpc::InstrumentationV2::SmartCV &,Sync::SyncErrorContainer &)
0x1800722ab  mov     rbx, [rsi+10h]
0x1800722af  lea     rdx, [rbp+880h+var_810]
0x1800722b3  mov     rcx, [rsi+28h]
0x1800722b7  call    ?Step@SmartCV@InstrumentationV2@wpc@@QEAA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; wpc::InstrumentationV2::SmartCV::Step(void)
0x1800722bc  mov     rdi, rax
0x1800722bf  xorps   xmm0, xmm0
0x1800722c2  movups  [rsp+980h+Src], xmm0
0x1800722c7  xorps   xmm1, xmm1
0x1800722ca  movdqu  [rsp+980h+var_908], xmm1
0x1800722d0  mov     r8d, 24h ; '$'
0x1800722d6  lea     rdx, aPublicSettings; "public.settings.family.microsoft.com"
0x1800722dd  lea     rcx, [rsp+980h+Src]
0x1800722e2  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x1800722e7  nop
0x1800722e8  lea     r8, [rsp+980h+Src]
0x1800722ed  lea     rdx, aSettingsservic; "SettingsServiceServer"
0x1800722f4  lea     rcx, [rbp+880h+var_830]
0x1800722f8  call    ?ReadRegOrDefault@RegistryHelper@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBGAEBV23@@Z; RegistryHelper::ReadRegOrDefault(ushort const *,std::wstring const &)
0x1800722fd  nop
0x1800722fe  lea     rcx, [rsp+980h+Src]
0x180072303  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180072308  nop
0x180072309  mov     rdx, [rsi+18h]
0x18007230d  add     rdx, 48h ; 'H'
0x180072311  lea     rcx, [rbp+880h+var_8B8]
0x180072315  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18007231a  nop
0x18007231b  lea     rdx, [rbp+880h+var_8B8]
0x18007231f  lea     rcx, [rbp+880h+var_4F0]
0x180072326  call    ?GetSettings@Settings@@YA?AV?$Optional@VSettingsData@Policy@wpc@@@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Settings::GetSettings(std::wstring const &)
0x18007232b  nop
0x18007232c  lea     rcx, [rbp+880h+var_8B8]
0x180072330  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180072335  mov     rdx, [rbp+880h+var_368]
0x18007233c  test    rdx, rdx
0x18007233f  jz      short loc_180072365
0x180072341  add     rdx, 8
0x180072345  lea     rcx, [rbp+880h+var_8F0]
0x180072349  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18007234e  mov     [rbp+880h+var_8D0], rax
0x180072352  mov     rcx, [rbp+880h+var_368]; this
0x180072359  test    rcx, rcx
0x18007235c  jz      short loc_180072369
0x18007235e  call    ??1SettingsData@Policy@wpc@@QEAA@XZ; wpc::Policy::SettingsData::~SettingsData(void)
0x180072363  jmp     short loc_180072369
0x180072365  mov     [rbp+880h+var_8D0], r13
0x180072369  mov     [rsp+980h+var_950], rbx; __int64
0x18007236e  mov     [rsp+980h+var_958], rdi; char *
0x180072373  lea     rax, [rbp+880h+var_830]
0x180072377  mov     [rsp+980h+var_960], rax; __int64
0x18007237c  lea     r9, [rbp+880h+var_8F8]; int
0x180072380  lea     r8, [rbp+880h+var_760]; int
0x180072387  mov     rdx, [rsi+18h]; int
0x18007238b  lea     rcx, [rbp+880h+var_1D0]; int
0x180072392  call    ?SyncSettings@Sync@@YA?AV?$Optional@VSettingsData@Policy@wpc@@@@AEBVSid@@AEAVTicketContainer@1@AEBV?$Optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@7@AEAVSyncErrorContainer@1@@Z; Sync::SyncSettings(Sid const &,Sync::TicketContainer &,Optional<std::wstring> const &,std::wstring const &,std::string const &,Sync::SyncErrorContainer &)
0x180072397  mov     rbx, rax
0x18007239a  mov     rcx, [rbp+880h+var_1D8]; this
0x1800723a1  test    rcx, rcx
0x1800723a4  jz      short loc_1800723B2
0x1800723a6  call    ??1SettingsData@Policy@wpc@@QEAA@XZ; wpc::Policy::SettingsData::~SettingsData(void)
0x1800723ab  mov     [rbp+880h+var_1D8], r13
0x1800723b2  mov     rdx, [rbx+188h]
0x1800723b9  test    rdx, rdx
0x1800723bc  jz      short loc_1800723E9
0x1800723be  lea     rcx, [rbp+880h+var_358]
0x1800723c5  call    ??0SettingsData@Policy@wpc@@QEAA@$$QEAV012@@Z; wpc::Policy::SettingsData::SettingsData(wpc::Policy::SettingsData &&)
0x1800723ca  mov     [rbp+880h+var_1D8], rax
0x1800723d1  mov     rcx, [rbx+188h]; this
0x1800723d8  test    rcx, rcx
0x1800723db  jz      short loc_1800723E9
0x1800723dd  call    ??1SettingsData@Policy@wpc@@QEAA@XZ; wpc::Policy::SettingsData::~SettingsData(void)
0x1800723e2  mov     [rbx+188h], r13
0x1800723e9  mov     rcx, [rbp+880h+var_48]; this
0x1800723f0  test    rcx, rcx
0x1800723f3  jz      short loc_180072401
0x1800723f5  call    ??1SettingsData@Policy@wpc@@QEAA@XZ; wpc::Policy::SettingsData::~SettingsData(void)
0x1800723fa  mov     [rbp+880h+var_48], r13
0x180072401  mov     rcx, [rbp+880h+var_8D0]
0x180072405  test    rcx, rcx
0x180072408  jz      short loc_180072413
0x18007240a  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007240f  mov     [rbp+880h+var_8D0], r13
0x180072413  lea     rcx, [rbp+880h+var_830]
0x180072417  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18007241c  nop
0x18007241d  lea     rcx, [rbp+880h+var_810]
0x180072421  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180072426  mov     rax, [rsi+30h]
0x18007242a  mov     dword ptr [rax], 1
0x180072430  mov     rcx, [rsi+18h]; this
0x180072434  call    ?CacheUserRegion@Private@RefreshTask@@YAXAEBVSid@@@Z; RefreshTask::Private::CacheUserRegion(Sid const &)
0x180072439  jmp     short loc_180072442
0x18007243b  mov     rax, [rsi+30h]
0x18007243f  mov     [rax], r13d
0x180072442  mov     rdi, [rsi+10h]
0x180072446  xorps   xmm0, xmm0
0x180072449  movups  xmmword ptr [rbp+880h+var_810], xmm0
0x18007244d  xorps   xmm1, xmm1
0x180072450  movdqu  [rbp+880h+var_800], xmm1
0x180072458  mov     r8d, 21h ; '!'
0x18007245e  lea     rdx, aApptimelimitsG; "AppTimeLimits::GetTicketsFailure_"
0x180072465  lea     rcx, [rbp+880h+var_810]
0x180072469  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18007246e  nop
0x18007246f  lea     rcx, [rbp+880h+var_510]
0x180072476  call    ?GetFamilyServiceAuthTarget@RegistryHelper@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; RegistryHelper::GetFamilyServiceAuthTarget(void)
0x18007247b  mov     r14, rax
0x18007247e  lea     rax, [rbp+880h+var_4F0]
0x180072485  mov     [rsp+980h+var_928], rax
0x18007248a  mov     rbx, [rsi+8]
0x18007248e  movups  xmm0, xmmword ptr [rbx]
0x180072491  movups  [rbp+880h+var_4F0], xmm0
0x180072498  movups  xmm1, xmmword ptr [rbx+10h]
0x18007249c  movups  [rbp+880h+var_4E0], xmm1
0x1800724a3  movups  xmm0, xmmword ptr [rbx+20h]
0x1800724a7  movups  [rbp+880h+var_4D0], xmm0
0x1800724ae  movups  xmm1, xmmword ptr [rbx+30h]
0x1800724b2  movups  [rbp+880h+var_4C0], xmm1
0x1800724b9  mov     eax, [rbx+40h]
0x1800724bc  mov     [rbp+880h+var_4B0], eax
0x1800724c2  lea     rdx, [rbx+48h]
0x1800724c6  lea     rcx, [rbp+880h+var_4A8]
0x1800724cd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800724d2  nop
0x1800724d3  lea     rax, [rbp+880h+var_488]
0x1800724da  mov     [rsp+980h+var_938], rax
0x1800724df  lea     rdx, [rbx+68h]
0x1800724e3  mov     [rbp+880h+var_468], r13b
0x1800724ea  cmp     [rdx+20h], r13b
0x1800724ee  jz      short loc_180072503
0x1800724f0  lea     rcx, [rbp+880h+var_488]
0x1800724f7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800724fc  mov     [rbp+880h+var_468], 1
0x180072503  mov     [rsp+980h+var_960], rdi; struct Sync::SyncErrorContainer *
0x180072508  lea     r9, [rbp+880h+var_810]
0x18007250c  mov     r8, r14
0x18007250f  lea     rdx, [rbp+880h+var_4F0]
0x180072516  lea     rcx, [rbp+880h+var_7F0]
  ... truncated ...
```
