# WinREAgent::Executor::ScheduleExecution(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,WinREAgent::TelemetrySession *)

- ea: `0x18000f254`
- end: `0x18000feb5`
- name: `?ScheduleExecution@Executor@WinREAgent@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVTelemetrySession@2@@Z`
- size: `3169`
- prototype: ``
- caller_count: `4`
- callee_count: `37`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180017b90`
- `0x180017f20`
- `0x18001bf30`
- `0x18001c3a0`

## callees

- `0x180003d30`
- `0x180003d64`
- `0x180003e28`
- `0x180003ee4`
- `0x180003f4c`
- `0x1800047f8`
- `0x1800049a4`
- `0x180004af8`
- `0x1800050bc`
- `0x180005c00`
- `0x180005c70`
- `0x1800064a0`
- `0x1800074b8`
- `0x18000d394`
- `0x18000d5c0`
- `0x18000d620`
- `0x18000d92c`
- `0x18000d9ec`
- `0x18000f254`
- `0x1800119dc`
- `0x180011ef4`
- `0x180012f70`
- `0x18001e51c`
- `0x18001f228`
- `0x18001faf4`
- `0x1800201f8`
- `0x180020358`
- `0x1800203e4`
- `0x180023764`
- `0x18002dee0`
- `0x18002e06c`
- `0x18002e1f8`
- `0x18002f85c`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18006f010`

## string_xrefs

- `0x18000f376`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000fe78`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000fe64`: `Execution was already scheduled`
- `0x18000f37d`: `WinREAgent::Executor::ScheduleExecution`
- `0x18000fe7f`: `WinREAgent::Executor::ScheduleExecution`
- `0x18000f361`: `Attempt to Register WinRE to Recovery BCD`
- `0x18000f3e6`: `Failed to create execution context`
- `0x18000f447`: `Failed to get WinREAgent root directory`
- `0x18000f4a6`: `Failed to create Rollback Helper`
- `0x18000f640`: `update.wim`
- `0x18000f67e`: `Failed to build path to scratch to copy winre`
- `0x18000f706`: `Failed to allocate opCopyWinRE`
- `0x18000f85a`: `InstalledPackagesSize`
- `0x18000f935`: `Failed to add package [%u], path [%s]`
- `0x18000f9a9`: `Failed to add source path [%u], path [%s]`
- `0x18000f9e8`: `Failed to add reference wim path`
- `0x18000fad2`: `Failed to add manifest root path`
- `0x18000fb4b`: `Failed to add manifest root path`
- `0x18000fba7`: `Failed to add manifest root path`
- `0x18000fb72`: `\windows\winsxs\manifests`
- `0x18000fca2`: `Failed to add source paths`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall WinREAgent::Executor::ScheduleExecution(__int64 a1, _QWORD *a2, WinREAgent::TelemetrySession *a3)
{
  int *v6; // rcx
  int *v7; // rsi
  __int64 v8; // rbx
  signed int v9; // ebx
  __int64 v10; // r13
  int ExecutionContext; // ebx
  __int64 v13; // rax
  __int64 v14; // rdx
  int v15; // eax
  int v16; // r12d
  ATL::CStringData *v17; // rcx
  ATL::CStringData *v18; // rcx
  WinREAgent::CopyWinRE *v19; // rax
  unsigned __int16 *v20; // rbx
  WinREAgent::PrepareWinRE *v21; // rax
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // r8
  unsigned __int64 v25; // r9
  unsigned __int64 v26; // rcx
  unsigned __int64 v27; // r10
  __int64 v28; // r13
  WinREAgent::PrepareWinRE *v29; // rdi
  __int64 v30; // r8
  const struct PACKAGE_INFO **v31; // rax
  __int64 v32; // r13
  WinREAgent::PrepareWinRE *v33; // rdi
  __int64 v34; // r8
  const unsigned __int16 **v35; // rax
  __int64 v36; // rax
  int v37; // edi
  __int64 v38; // r8
  __int64 v39; // rdi
  __int64 v40; // r8
  __int64 v41; // rdi
  __int64 v42; // r8
  __int64 v43; // rdi
  __int64 v44; // r13
  WinREAgent::PrepareWinRE *v45; // rdi
  __int64 v46; // r8
  const unsigned __int16 **v47; // rax
  void **v48; // rdi
  WinREAgent::Operation *v49; // rax
  void **v50; // rdi
  __int64 v51; // rax
  int v52; // [rsp+30h] [rbp-89h]
  int v53; // [rsp+30h] [rbp-89h]
  __int64 v54; // [rsp+38h] [rbp-81h]
  __int64 v55; // [rsp+38h] [rbp-81h]
  __int64 v56; // [rsp+40h] [rbp-79h] BYREF
  void **v57; // [rsp+48h] [rbp-71h] BYREF
  __int64 v58; // [rsp+50h] [rbp-69h]
  void **v59; // [rsp+58h] [rbp-61h] BYREF
  __int64 v60; // [rsp+60h] [rbp-59h]
  void **v61; // [rsp+68h] [rbp-51h] BYREF
  WinREAgent::Operation *v62; // [rsp+70h] [rbp-49h]
  void **v63; // [rsp+78h] [rbp-41h] BYREF
  __int64 v64; // [rsp+80h] [rbp-39h]
  unsigned __int16 *v65; // [rsp+88h] [rbp-31h] BYREF
  __int64 v66; // [rsp+90h] [rbp-29h] BYREF
  __int64 v67; // [rsp+98h] [rbp-21h] BYREF
  unsigned __int64 v68; // [rsp+A0h] [rbp-19h]
  __int64 v69; // [rsp+A8h] [rbp-11h]
  int v70; // [rsp+B0h] [rbp-9h]
  _BYTE v71[8]; // [rsp+B8h] [rbp-1h] BYREF
  __int64 (__fastcall *v72)(); // [rsp+C0h] [rbp+7h]
  WinREAgent::TelemetrySession *v73; // [rsp+C8h] [rbp+Fh]
  __int64 *v74; // [rsp+D0h] [rbp+17h]
  char *v75; // [rsp+D8h] [rbp+1Fh]
  char v76; // [rsp+120h] [rbp+67h] BYREF
  __int64 v77; // [rsp+138h] [rbp+7Fh] BYREF

  if ( *(_QWORD *)(a1 + 40) || *(_QWORD *)(a1 + 72) || *(_BYTE *)(a1 + 272) || *(_BYTE *)(a1 + 304) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147943647LL,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      369,
      L"Execution was already scheduled");
    return 2147943647LL;
  }
  PushButtonReset::Logging::Trace(0, L"Schedule WinRE Servicing execution");
  if ( a3 )
    WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"Goal", L"WinREServicing");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v77,
    (__int64)L"FailToSchedule");
  v76 = 1;
  v71[0] = 0;
  v72 = TraceCanExecuteReason;
  v73 = a3;
  v74 = &v77;
  v75 = &v76;
  v6 = (int *)(*a2 - 24LL);
  v7 = (int *)(*(_QWORD *)(a1 + 368) - 24LL);
  if ( v6 != v7 )
  {
    if ( v7[4] >= 0 && *(_QWORD *)v6 == *(_QWORD *)v7 )
    {
      v8 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v6);
      ATL::CStringData::Release((ATL::CStringData *)v7);
      *(_QWORD *)(a1 + 368) = v8 + 24;
    }
    else
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(a1 + 368, *a2, *(unsigned int *)(*a2 - 16LL));
    }
  }
  PushButtonReset::Logging::Trace(0, L"Attempt to Register WinRE to Recovery BCD");
  v9 = RegisterToRecoveryBCD();
  if ( v9 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      1,
      (unsigned int)v9,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      393,
      L"Failed to Register WinRE to Recovery BCD");
    if ( a3 )
      WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"RegisterRecoveryBCDFailed", v9);
  }
  v10 = a1 + 408;
  ExecutionContext = WinREAgent::CreateExecutionContext(a1 + 368, 0, a1 + 408);
  if ( ExecutionContext < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)ExecutionContext,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      404,
      L"Failed to create execution context");
LABEL_17:
    ScopeGuardImplBase::SafeExecute<ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,bool *>>((__int64)v71);
    ATL::CStringData::Release((ATL::CStringData *)(v77 - 24));
    return (unsigned int)ExecutionContext;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v66);
  ExecutionContext = WinREAgent::WorkDir::GetRootDir(a1 + 368, (__int64)&v66);
  if ( ExecutionContext < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)ExecutionContext,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      409,
      L"Failed to get WinREAgent root directory");
LABEL_20:
    ATL::CStringData::Release((ATL::CStringData *)(v66 - 24));
    goto LABEL_17;
  }
  v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 416) + 8LL))(a1 + 416);
  ExecutionContext = WinREAgent::RollbackHelper::CreateRollbackHelper(&v66, v13);
  if ( ExecutionContext < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)ExecutionContext,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      412,
      L"Failed to create Rollback Helper");
    goto LABEL_20;
  }
  *(_QWORD *)(*(_QWORD *)v10 + 448LL) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 416) + 32LL))(a1 + 416);
  if ( !*(_BYTE *)(*(_QWORD *)v10 + 152LL) )
  {
    ATL::CSimpleStringT<unsigned short,0>::SetString(&v77, L"NoRecoveryEnvironment", 21);
    PushButtonReset::Logging::TraceErr(
      2,
      2147500037LL,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      420,
      L"WinRE is not available");
    ExecutionContext = -2147467259;
    goto LABEL_20;
  }
  LOBYTE(v14) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::GetImpl'::`2'::impl,
    v14);
  PushButtonReset::Logging::Trace(0, L"Trace partition info");
  v15 = TracePartitionInfo(a3);
  if ( v15 < 0 )
    PushButtonReset::Logging::TraceErr(
      1,
      (unsigned int)v15,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      429,
      L"Failed to trace partition info");
  v58 = 0;
  v57 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
  v62 = PbrNew<WinREAgent::CleanupScratch,>();
  v61 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
  if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v61) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      438,
      L"Failed to allocate opCleanupScratch");
    v61 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v61);
    v57 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
LABEL_77:
    RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v57);
    ExecutionContext = -2147024882;
    goto LABEL_20;
  }
  *(_BYTE *)(((__int64 (__fastcall *)(void ***))v61[3])(&v61) + 144) = 1;
  v56 = ((__int64 (__fastcall *)(void ***))v61[4])(&v61);
  ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
    (_QWORD *)(a1 + 32),
    &v56);
  v62 = 0;
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v65);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v56,
    (__int64)L"update.wim");
  v16 = PushButtonReset::Path::Combine(*(_QWORD *)v10 + 184LL, &v56, &v65);
  ATL::CStringData::Release((ATL::CStringData *)(v56 - 24));
  if ( v16 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v16,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      448,
      L"Failed to build path to scratch to copy winre");
    v17 = (ATL::CStringData *)(v65 - 12);
LABEL_31:
    ATL::CStringData::Release(v17);
    v61 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v61);
    v57 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v57);
    ExecutionContext = v16;
    goto LABEL_20;
  }
  v64 = PbrNew<WinREAgent::CopyWinRE,>();
  v63 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
  if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v63) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      451,
      L"Failed to allocate opCopyWinRE");
    v63 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v63);
    v18 = (ATL::CStringData *)(v65 - 12);
LABEL_76:
    ATL::CStringData::Release(v18);
    v61 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v61);
    v57 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
    goto LABEL_77;
  }
  v19 = (WinREAgent::CopyWinRE *)((__int64 (__fastcall *)(void ***))v63[3])(&v63);
  v20 = v65;
  WinREAgent::CopyWinRE::SetPath(v19, *(const unsigned __int16 **)(*(_QWORD *)v10 + 120LL), v65);
  v56 = ((__int64 (__fastcall *)(void ***))v63[4])(&v63);
  ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
    (_QWORD *)(a1 + 32),
    &v56);
  v64 = 0;
  v60 = PbrNew<WinREAgent::PrepareWinRE,>();
  v59 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
  if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v59) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      460,
      L"Failed to allocate prepareWinRE");
LABEL_75:
    v59 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v59);
    v63 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v63);
    v18 = (ATL::CStringData *)(v20 - 12);
    goto LABEL_76;
  }
  v21 = (WinREAgent::PrepareWinRE *)((__int64 (__fastcall *)(void ***))v59[3])(&v59);
  WinREAgent::PrepareWinRE::SetWimPath(v21, *(const unsigned __int16 **)(*(_QWORD *)v10 + 120LL));
  if ( !*(_DWORD *)(*(_QWORD *)(a1 + 400) - 16LL) )
  {
    LOBYTE(v22) = 1;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::ReportUsage(
      `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::GetImpl'::`2'::impl,
      v22);
    v56 = a1 + 96;
    v25 = 0;
    v26 = 0;
    v27 = *(_QWORD *)(a1 + 104);
    if ( v27 )
    {
      do
      {
        v24 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 8 * v26);
        if ( v24 )
          v25 += *(_QWORD *)(v24 + 16);
        ++v26;
      }
      while ( v26 < v27 );
      v20 = v65;
    }
    if ( a3 )
      WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"InstalledPackagesSize", v25);
    v28 = 0;
    if ( *(_QWORD *)(a1 + 104) )
    {
      while ( 1 )
      {
        v29 = (WinREAgent::PrepareWinRE *)((__int64 (__fastcall *)(void ***, __int64, __int64, unsigned __int64))v59[3])(
                                            &v59,
                                            v23,
                                            v24,
                                            v25);
        v31 = (const struct PACKAGE_INFO **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                              a1 + 96,
                                              v28,
                                              v30);
        v16 = WinREAgent::PrepareWinRE::AddPackage(v29, *v31);
        if ( v16 < 0 )
          break;
        if ( (unsigned __int64)++v28 >= *(_QWORD *)(a1 + 104) )
          goto LABEL_47;
      }
      v54 = **(_QWORD **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                           v56,
                           v28,
                           v24);
      v52 = v28;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v16,
        "WinREAgent::Executor::ScheduleExecution",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        484,
        L"Failed to add package [%u], path [%s]",
        v52,
        v54);
      goto LABEL_53;
    }
LABEL_47:
    v32 = 0;
    if ( *(_QWORD *)(a1 + 224) )
    {
      v56 = a1 + 216;
      while ( 1 )
      {
        v33 = (WinREAgent::PrepareWinRE *)((__int64 (__fastcall *)(void ***, __int64, __int64, unsigned __int64))v59[3])(
                                            &v59,
                                            v23,
                                            v24,
                                            v25);
        v35 = (const unsigned __int16 **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                           a1 + 216,
                                           v32,
                                           v34);
        v16 = WinREAgent::PrepareWinRE::AddSourcePath(v33, *v35);
        if ( v16 < 0 )
          break;
        if ( (unsigned __int64)++v32 >= *(_QWORD *)(a1 + 224) )
          goto LABEL_70;
      }
      v55 = *(_QWORD *)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                         v56,
                         v32,
                         v24);
      v53 = v32;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v16,
        "WinREAgent::Executor::ScheduleExecution",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        495,
        L"Failed to add source path [%u], path [%s]",
        v53,
        v55);
      goto LABEL_53;
    }
    goto LABEL_70;
  }
  v36 = ((__int64 (__fastcall *)(void ***))v59[3])(&v59);
  v37 = WinREAgent::PrepareWinRE::AddReferenceImagePath(v36, a1 + 400);
  if ( v37 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v37,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      502,
      L"Failed to add reference wim path");
LABEL_57:
    v59 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v59);
    v63 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v63);
    ATL::CStringData::Release((ATL::CStringData *)(v20 - 12));
    v61 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v61);
    v57 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v57);
    ExecutionContext = v37;
    goto LABEL_20;
  }
  v67 = 0;
  v68 = 0;
  v69 = 0;
  v70 = 0;
  ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::SetCount(
    &v67,
    3);
  v39 = ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
          &v67,
          0,
          v38);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v56,
    (__int64)L"\\windows\\servicing\\packages");
  v37 = PushButtonReset::Path::Combine(a1 + 400, &v56, v39);
  ATL::CStringData::Release((ATL::CStringData *)(v56 - 24));
  if ( v37 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v37,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      508,
      L"Failed to add manifest root path");
LABEL_60:
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v67);
    goto LABEL_57;
  }
  v41 = ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
          &v67,
          1,
          v40);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v56,
    (__int64)L"\\windows\\winsxs");
  v37 = PushButtonReset::Path::Combine(a1 + 400, &v56, v41);
  ATL::CStringData::Release((ATL::CStringData *)(v56 - 24));
  if ( v37 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v37,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      511,
      L"Failed to add manifest root path");
    goto LABEL_60;
  }
  v43 = ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
          &v67,
          2,
          v42);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v56,
    (__int64)L"\\windows\\winsxs\\manifests");
  v16 = PushButtonReset::Path::Combine(a1 + 400, &v56, v43);
  ATL::CStringData::Release((ATL::CStringData *)(v56 - 24));
  if ( v16 < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v16,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      514,
      L"Failed to add manifest root path");
LABEL_65:
    ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v67);
LABEL_53:
    v59 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v59);
    v63 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v63);
    v17 = (ATL::CStringData *)(v20 - 12);
    goto LABEL_31;
  }
  v44 = 0;
  if ( v68 )
  {
    while ( 1 )
    {
      v45 = (WinREAgent::PrepareWinRE *)((__int64 (__fastcall *)(void ***))v59[3])(&v59);
      v47 = (const unsigned __int16 **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                         &v67,
                                         v44,
                                         v46);
      v16 = WinREAgent::PrepareWinRE::AddSourcePath(v45, *v47);
      if ( v16 < 0 )
        break;
      if ( ++v44 >= v68 )
        goto LABEL_69;
    }
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)v16,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      519,
      L"Failed to add source paths");
    goto LABEL_65;
  }
LABEL_69:
  ATL::CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>::~CAtlArray<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>,ATL::CElementTraits<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>>((__int64)&v67);
LABEL_70:
  v56 = ((__int64 (__fastcall *)(void ***, __int64, __int64, unsigned __int64))v59[4])(&v59, v23, v24, v25);
  ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
    (_QWORD *)(a1 + 32),
    &v56);
  v60 = 0;
  v48 = v57;
  v49 = PbrNew<WinREAgent::SaveWinREHash,>();
  ((void (__fastcall *)(void ***, WinREAgent::Operation *))v48[6])(&v57, v49);
  if ( ((unsigned __int8 (__fastcall *)(void ***))v57[9])(&v57) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      530,
      L"Failed to allocate operation");
    goto LABEL_75;
  }
  v56 = ((__int64 (__fastcall *)(void ***))v57[4])(&v57);
  ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
    (_QWORD *)(a1 + 32),
    &v56);
  v58 = 0;
  v50 = v57;
  v51 = PbrNew<WinREAgent::BackupWinRE,>();
  ((void (__fastcall *)(void ***, __int64))v50[6])(&v57, v51);
  if ( ((unsigned __int8 (__fastcall *)(void ***))v57[9])(&v57) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942414LL,
      "WinREAgent::Executor::ScheduleExecution",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      537,
      L"Failed to allocate operation");
    goto LABEL_75;
  }
  v56 = ((__int64 (__fastcall *)(void ***))v57[4])(&v57);
  ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
    (_QWORD *)(a1 + 32),
    &v56);
  v58 = 0;
  *(_BYTE *)(a1 + 272) = 1;
  v76 = 0;
  v59 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
  RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v59);
  v63 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
  RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v63);
  ATL::CStringData::Release((ATL::CStringData *)(v20 - 12));
  v61 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
  RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v61);
  v57 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
  RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v57);
  ATL::CStringData::Release((ATL::CStringData *)(v66 - 24));
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,bool *>>((__int64)v71);
  ATL::CStringData::Release((ATL::CStringData *)(v77 - 24));
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x18000f254  mov     [rsp-8+arg_8], rbx
0x18000f259  push    rbp
0x18000f25a  push    rsi
0x18000f25b  push    rdi
0x18000f25c  push    r12
0x18000f25e  push    r13
0x18000f260  push    r14
0x18000f262  push    r15
0x18000f264  lea     rbp, [rsp-27h]
0x18000f269  sub     rsp, 0E0h
0x18000f270  mov     rdi, r8
0x18000f273  mov     rbx, rdx
0x18000f276  mov     r15, rcx
0x18000f279  xor     r13d, r13d
0x18000f27c  cmp     [rcx+28h], r13
0x18000f280  jnz     loc_18000FE64
0x18000f286  cmp     [rcx+48h], r13
0x18000f28a  jnz     loc_18000FE64
0x18000f290  cmp     [rcx+110h], r13b
0x18000f297  jnz     loc_18000FE64
0x18000f29d  cmp     [rcx+130h], r13b
0x18000f2a4  jnz     loc_18000FE64
0x18000f2aa  lea     rdx, aScheduleWinreS_2; "Schedule WinRE Servicing execution"
0x18000f2b1  xor     ecx, ecx
0x18000f2b3  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18000f2b8  test    rdi, rdi
0x18000f2bb  jz      short loc_18000F2DA
0x18000f2bd  lea     r9, aWinreservicing; "WinREServicing"
0x18000f2c4  lea     r8, aGoal; "Goal"
0x18000f2cb  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x18000f2d2  mov     rcx, rdi; this
0x18000f2d5  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x18000f2da  lea     rdx, aFailtoschedule; "FailToSchedule"
0x18000f2e1  lea     rcx, [rbp+57h+arg_18]
0x18000f2e5  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000f2ea  nop
0x18000f2eb  mov     [rbp+57h+arg_0], 1
0x18000f2ef  mov     [rbp+57h+var_58], r13b
0x18000f2f3  lea     rax, TraceCanExecuteReason
0x18000f2fa  mov     [rbp+57h+var_50], rax
0x18000f2fe  mov     [rbp+57h+var_48], rdi
0x18000f302  lea     rax, [rbp+57h+arg_18]
0x18000f306  mov     [rbp+57h+var_40], rax
0x18000f30a  lea     rax, [rbp+57h+arg_0]
0x18000f30e  mov     [rbp+57h+var_38], rax
0x18000f312  lea     r12, [r15+170h]
0x18000f319  mov     rdx, [rbx]
0x18000f31c  lea     rcx, [rdx-18h]
0x18000f320  mov     rsi, [r12]
0x18000f324  add     rsi, 0FFFFFFFFFFFFFFE8h
0x18000f328  cmp     rcx, rsi
0x18000f32b  jz      short loc_18000F361
0x18000f32d  cmp     [rsi+10h], r13d
0x18000f331  jl      short loc_18000F355
0x18000f333  mov     rax, [rsi]
0x18000f336  cmp     [rcx], rax
0x18000f339  jnz     short loc_18000F355
0x18000f33b  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000f340  mov     rbx, rax
0x18000f343  mov     rcx, rsi; this
0x18000f346  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f34b  lea     rax, [rbx+18h]
0x18000f34f  mov     [r12], rax
0x18000f353  jmp     short loc_18000F361
0x18000f355  mov     r8d, [rdx-10h]
0x18000f359  mov     rcx, r12
0x18000f35c  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000f361  lea     rdx, aAttemptToRegis; "Attempt to Register WinRE to Recovery B"...
0x18000f368  xor     ecx, ecx
0x18000f36a  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18000f36f  call    ?RegisterToRecoveryBCD@@YAJXZ; RegisterToRecoveryBCD(void)
0x18000f374  mov     ebx, eax
0x18000f376  lea     rsi, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000f37d  lea     r14, aWinreagentExec_16; "WinREAgent::Executor::ScheduleExecution"
0x18000f384  test    eax, eax
0x18000f386  jns     short loc_18000F3CC
0x18000f388  lea     rax, aFailedToRegist; "Failed to Register WinRE to Recovery BC"...
0x18000f38f  mov     [rsp+110h+var_E8], rax
0x18000f394  mov     [rsp+110h+var_F0], 189h
0x18000f39c  mov     r9, rsi
0x18000f39f  mov     r8, r14
0x18000f3a2  mov     edx, ebx
0x18000f3a4  mov     ecx, 1
0x18000f3a9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000f3ae  test    rdi, rdi
0x18000f3b1  jz      short loc_18000F3CC
0x18000f3b3  mov     r9d, ebx; unsigned int
0x18000f3b6  lea     r8, aRegisterrecove; "RegisterRecoveryBCDFailed"
0x18000f3bd  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x18000f3c4  mov     rcx, rdi; this
0x18000f3c7  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ulong)
0x18000f3cc  lea     r13, [r15+198h]
0x18000f3d3  mov     r8, r13
0x18000f3d6  xor     edx, edx
0x18000f3d8  mov     rcx, r12
0x18000f3db  call    ?CreateExecutionContext@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAPEAVExecutionContext@1@@Z; WinREAgent::CreateExecutionContext(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *,WinREAgent::ExecutionContext * *)
0x18000f3e0  mov     ebx, eax
0x18000f3e2  test    eax, eax
0x18000f3e4  jns     short loc_18000F42B
0x18000f3e6  lea     rax, aFailedToCreate_6; "Failed to create execution context"
0x18000f3ed  mov     [rsp+110h+var_E8], rax
0x18000f3f2  mov     [rsp+110h+var_F0], 194h
0x18000f3fa  mov     r9, rsi
0x18000f3fd  mov     r8, r14
0x18000f400  mov     edx, ebx
0x18000f402  mov     ecx, 2
0x18000f407  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000f40c  nop
0x18000f40d  lea     rcx, [rbp+57h+var_58]
0x18000f411  call    ??$SafeExecute@V?$ScopeGuardImpl3@P6AXPEBVTelemetrySession@WinREAgent@@PEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@ZPEAV12@PEAV34@PEA_N@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl3@P6AXPEBVTelemetrySession@WinREAgent@@PEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@ZPEAV12@PEAV34@PEA_N@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,bool *>>(ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,bool *> &)
0x18000f416  nop
0x18000f417  mov     rcx, [rbp+57h+arg_18]
0x18000f41b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000f41f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f424  mov     eax, ebx
0x18000f426  jmp     loc_18000FE9A
0x18000f42b  lea     rcx, [rbp+57h+var_80]
0x18000f42f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000f434  nop
0x18000f435  lea     rdx, [rbp+57h+var_80]
0x18000f439  mov     rcx, r12
0x18000f43c  call    ?GetRootDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetRootDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18000f441  mov     ebx, eax
0x18000f443  test    eax, eax
0x18000f445  jns     short loc_18000F47D
0x18000f447  lea     rax, aFailedToGetWin; "Failed to get WinREAgent root directory"
0x18000f44e  mov     [rsp+110h+var_E8], rax
0x18000f453  mov     [rsp+110h+var_F0], 199h
0x18000f45b  mov     r9, rsi
0x18000f45e  mov     r8, r14
0x18000f461  mov     edx, ebx
0x18000f463  mov     ecx, 2
0x18000f468  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000f46d  nop
0x18000f46e  mov     rcx, [rbp+57h+var_80]
0x18000f472  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000f476  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f47b  jmp     short loc_18000F40D
0x18000f47d  lea     r12, [r15+1A0h]
0x18000f484  mov     rax, [r12]
0x18000f488  mov     rcx, r12
0x18000f48b  mov     rax, [rax+8]
0x18000f48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f494  mov     rdx, rax
0x18000f497  lea     rcx, [rbp+57h+var_80]
0x18000f49b  call    ?CreateRollbackHelper@RollbackHelper@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; WinREAgent::RollbackHelper::CreateRollbackHelper(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,WinREAgent::RollbackHelper * *)
0x18000f4a0  mov     ebx, eax
0x18000f4a2  test    eax, eax
0x18000f4a4  jns     short loc_18000F4BC
0x18000f4a6  lea     rax, aFailedToCreate_2; "Failed to create Rollback Helper"
0x18000f4ad  mov     [rsp+110h+var_E8], rax
0x18000f4b2  mov     [rsp+110h+var_F0], 19Ch
0x18000f4ba  jmp     short loc_18000F45B
0x18000f4bc  mov     rax, [r12]
0x18000f4c0  mov     rcx, r12
0x18000f4c3  mov     rax, [rax+20h]
0x18000f4c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4cc  mov     rcx, [r13+0]
0x18000f4d0  mov     [rcx+1C0h], rax
0x18000f4d7  mov     rax, [r13+0]
0x18000f4db  xor     ebx, ebx
0x18000f4dd  cmp     [rax+98h], bl
0x18000f4e3  jnz     short loc_18000F52A
0x18000f4e5  lea     r8d, [rbx+15h]
0x18000f4e9  lea     rdx, aNorecoveryenvi; "NoRecoveryEnvironment"
0x18000f4f0  lea     rcx, [rbp+57h+arg_18]
0x18000f4f4  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000f4f9  lea     rax, aWinreIsNotAvai; "WinRE is not available"
0x18000f500  mov     [rsp+110h+var_E8], rax
0x18000f505  mov     [rsp+110h+var_F0], 1A4h
0x18000f50d  mov     r9, rsi
0x18000f510  mov     r8, r14
0x18000f513  mov     edx, 80004005h
0x18000f518  lea     ecx, [rbx+2]
0x18000f51b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000f520  mov     ebx, 80004005h
0x18000f525  jmp     loc_18000F46E
0x18000f52a  mov     dl, 1
0x18000f52c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing> `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::GetImpl(void)'::`2'::impl
0x18000f533  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000f538  lea     rdx, aTracePartition; "Trace partition info"
0x18000f53f  xor     ecx, ecx
0x18000f541  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18000f546  mov     rdx, [r13+0]
0x18000f54a  add     rdx, 78h ; 'x'
0x18000f54e  mov     rcx, rdi; this
0x18000f551  call    ?TracePartitionInfo@@YAJPEAVTelemetrySession@WinREAgent@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; TracePartitionInfo(WinREAgent::TelemetrySession *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000f556  test    eax, eax
0x18000f558  jns     short loc_18000F580
0x18000f55a  lea     rcx, aFailedToTraceP; "Failed to trace partition info"
0x18000f561  mov     [rsp+110h+var_E8], rcx
0x18000f566  mov     [rsp+110h+var_F0], 1ADh
0x18000f56e  mov     r9, rsi
0x18000f571  mov     r8, r14
0x18000f574  mov     edx, eax
0x18000f576  mov     ecx, 1
0x18000f57b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000f580  mov     [rbp+57h+var_C0], rbx
0x18000f584  lea     r12, ??_7?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable'
0x18000f58b  mov     [rbp+57h+var_C8], r12
0x18000f58f  call    ??$PbrNew@VCleanupScratch@WinREAgent@@$$V@@YAPEAVCleanupScratch@WinREAgent@@XZ; PbrNew<WinREAgent::CleanupScratch,>(void)
0x18000f594  mov     [rbp+57h+var_A0], rax
0x18000f598  lea     rax, ??_7?$CAutoPbrDelete@PEAVCleanupScratch@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable'
0x18000f59f  mov     [rbp+57h+var_A8], rax
0x18000f5a3  lea     rcx, [rbp+57h+var_A8]
0x18000f5a7  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x18000f5ac  test    al, al
0x18000f5ae  jz      short loc_18000F5F8
0x18000f5b0  lea     rax, aFailedToAlloca_33; "Failed to allocate opCleanupScratch"
0x18000f5b7  mov     [rsp+110h+var_E8], rax
0x18000f5bc  mov     [rsp+110h+var_F0], 1B6h
0x18000f5c4  mov     r9, rsi
0x18000f5c7  mov     r8, r14
0x18000f5ca  mov     edx, 8007000Eh
0x18000f5cf  mov     ecx, 2
0x18000f5d4  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000f5d9  nop
0x18000f5da  lea     rax, ??_7?$CAutoPbrDelete@PEAVCleanupScratch@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable'
0x18000f5e1  mov     [rbp+57h+var_A8], rax
0x18000f5e5  lea     rcx, [rbp+57h+var_A8]
0x18000f5e9  call    ?Release@?$CAutoPbrDelete@PEAVPrepareWinRE@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(void)
0x18000f5ee  nop
0x18000f5ef  mov     [rbp+57h+var_C8], r12
0x18000f5f3  jmp     loc_18000FD94
0x18000f5f8  mov     rax, [rbp+57h+var_A8]
0x18000f5fc  lea     rcx, [rbp+57h+var_A8]
0x18000f600  mov     rax, [rax+18h]
0x18000f604  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f609  mov     byte ptr [rax+90h], 1
0x18000f610  mov     rax, [rbp+57h+var_A8]
0x18000f614  lea     rcx, [rbp+57h+var_A8]
0x18000f618  mov     rax, [rax+20h]
0x18000f61c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f621  mov     [rbp+57h+var_D0], rax
0x18000f625  lea     rdx, [rbp+57h+var_D0]
0x18000f629  lea     rcx, [r15+20h]
0x18000f62d  call    ?Add@?$CAtlArray@PEAUPACKAGE_INFO@WinREAgent@@V?$CElementTraits@PEAUPACKAGE_INFO@WinREAgent@@@ATL@@@ATL@@QEAA_KAEBQEAUPACKAGE_INFO@WinREAgent@@@Z; ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(WinREAgent::PACKAGE_INFO * const &)
0x18000f632  mov     [rbp+57h+var_A0], rbx
0x18000f636  lea     rcx, [rbp+57h+var_88]
0x18000f63a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000f63f  nop
0x18000f640  lea     rdx, aUpdateWim; "update.wim"
0x18000f647  lea     rcx, [rbp+57h+var_D0]
0x18000f64b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000f650  nop
0x18000f651  mov     rcx, [r13+0]
0x18000f655  add     rcx, 0B8h
0x18000f65c  lea     r8, [rbp+57h+var_88]
0x18000f660  lea     rdx, [rbp+57h+var_D0]
0x18000f664  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18000f669  mov     r12d, eax
0x18000f66c  mov     rcx, [rbp+57h+var_D0]
0x18000f670  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000f674  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f679  test    r12d, r12d
0x18000f67c  jns     short loc_18000F6E5
0x18000f67e  lea     rax, aFailedToBuildP_1; "Failed to build path to scratch to copy"...
0x18000f685  mov     [rsp+110h+var_E8], rax
0x18000f68a  mov     [rsp+110h+var_F0], 1C0h
0x18000f692  mov     r9, rsi
0x18000f695  mov     r8, r14
0x18000f698  mov     edx, r12d
0x18000f69b  mov     ecx, 2
0x18000f6a0  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000f6a5  nop
0x18000f6a6  mov     rcx, [rbp+57h+var_88]
0x18000f6aa  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000f6ae  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000f6b3  nop
0x18000f6b4  lea     rax, ??_7?$CAutoPbrDelete@PEAVCleanupScratch@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable'
0x18000f6bb  mov     [rbp+57h+var_A8], rax
0x18000f6bf  lea     rcx, [rbp+57h+var_A8]
0x18000f6c3  call    ?Release@?$CAutoPbrDelete@PEAVPrepareWinRE@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(void)
0x18000f6c8  nop
0x18000f6c9  lea     rax, ??_7?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable'
0x18000f6d0  mov     [rbp+57h+var_C8], rax
0x18000f6d4  lea     rcx, [rbp+57h+var_C8]
0x18000f6d8  call    ?Release@?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(void)
0x18000f6dd  mov     ebx, r12d
0x18000f6e0  jmp     loc_18000F46E
0x18000f6e5  call    ??$PbrNew@VCopyWinRE@WinREAgent@@$$V@@YAPEAVCopyWinRE@WinREAgent@@XZ; PbrNew<WinREAgent::CopyWinRE,>(void)
0x18000f6ea  mov     [rbp+57h+var_90], rax
0x18000f6ee  lea     rax, ??_7?$CAutoPbrDelete@PEAVCleanupScratch@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable'
0x18000f6f5  mov     [rbp+57h+var_98], rax
0x18000f6f9  lea     rcx, [rbp+57h+var_98]
0x18000f6fd  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x18000f702  test    al, al
0x18000f704  jz      short loc_18000F752
0x18000f706  lea     rax, aFailedToAlloca_20; "Failed to allocate opCopyWinRE"
0x18000f70d  mov     [rsp+110h+var_E8], rax
0x18000f712  mov     [rsp+110h+var_F0], 1C3h
0x18000f71a  mov     r9, rsi
0x18000f71d  mov     r8, r14
0x18000f720  mov     edx, 8007000Eh
0x18000f725  mov     ecx, 2
0x18000f72a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000f72f  nop
0x18000f730  lea     rax, ??_7?$CAutoPbrDelete@PEAVCleanupScratch@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable'
0x18000f737  mov     [rbp+57h+var_98], rax
0x18000f73b  lea     rcx, [rbp+57h+var_98]
  ... truncated ...
```
