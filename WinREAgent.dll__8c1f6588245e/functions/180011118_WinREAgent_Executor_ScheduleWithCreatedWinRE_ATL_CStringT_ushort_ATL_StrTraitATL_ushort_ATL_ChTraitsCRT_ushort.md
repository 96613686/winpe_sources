# WinREAgent::Executor::ScheduleWithCreatedWinRE(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,WinREAgent::TelemetrySession *)

- ea: `0x180011118`
- end: `0x1800117ac`
- name: `?ScheduleWithCreatedWinRE@Executor@WinREAgent@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAVTelemetrySession@2@@Z`
- size: `1684`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x1800183f0`
- `0x18001c970`

## callees

- `0x180003d30`
- `0x180003d64`
- `0x180003fc0`
- `0x1800047f8`
- `0x1800049a4`
- `0x180004af8`
- `0x180005c00`
- `0x1800064a0`
- `0x1800074b8`
- `0x180008f2c`
- `0x18000d394`
- `0x18000d5c0`
- `0x18000d620`
- `0x18000d92c`
- `0x180011118`
- `0x180011ef4`
- `0x180012f70`
- `0x18001e51c`
- `0x18001f228`
- `0x18002dee0`
- `0x18002e06c`
- `0x18002f85c`
- `0x18003717c`
- `0x180037344`
- `0x18006f010`

## string_xrefs

- `0x180011257`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18001176f`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18001175b`: `Execution was already scheduled`
- `0x180011242`: `Attempt to Register WinRE to Recovery BCD`
- `0x1800112c7`: `Failed to create execution context`
- `0x180011328`: `Failed to get WinREAgent root directory`
- `0x180011387`: `Failed to create Rollback Helper`
- `0x18001125e`: `WinREAgent::Executor::ScheduleWithCreatedWinRE`
- `0x180011776`: `WinREAgent::Executor::ScheduleWithCreatedWinRE`
- `0x18001116e`: `Schedule WinRE Servicing execution with created WinRE`
- `0x18001119e`: `UseCreatedWinRE`
- `0x180011472`: `Failed to get the path of the created WinRE`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WinREAgent::Executor::ScheduleWithCreatedWinRE(
        __int64 a1,
        _QWORD *a2,
        WinREAgent::TelemetrySession *a3)
{
  int *v6; // rcx
  int *v7; // rdi
  __int64 v8; // rbx
  signed int v9; // ebx
  __int64 *v10; // r13
  int ExecutionContext; // ebx
  __int64 v13; // rax
  int v14; // eax
  __int64 v15; // rbx
  __int64 v16; // r13
  ATL::CStringData *v17; // r15
  int *v18; // r12
  __int64 v19; // rbx
  __int64 v20; // rax
  void **v21; // rbx
  __int64 v22; // rax
  void **v23; // [rsp+30h] [rbp-49h] BYREF
  __int64 v24; // [rsp+38h] [rbp-41h]
  void **v25; // [rsp+40h] [rbp-39h] BYREF
  WinREAgent::Operation *v26; // [rsp+48h] [rbp-31h]
  __int64 v27; // [rsp+50h] [rbp-29h] BYREF
  __int64 v28; // [rsp+58h] [rbp-21h] BYREF
  __int64 v29; // [rsp+60h] [rbp-19h] BYREF
  __int64 v30; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v31[8]; // [rsp+70h] [rbp-9h] BYREF
  __int64 (__fastcall *v32)(); // [rsp+78h] [rbp-1h]
  WinREAgent::TelemetrySession *v33; // [rsp+80h] [rbp+7h]
  __int64 *v34; // [rsp+88h] [rbp+Fh]
  char *v35; // [rsp+90h] [rbp+17h]
  char v36; // [rsp+E0h] [rbp+67h] BYREF
  unsigned int v37; // [rsp+F8h] [rbp+7Fh]

  if ( *(_QWORD *)(a1 + 40) || *(_QWORD *)(a1 + 72) || *(_BYTE *)(a1 + 272) || *(_BYTE *)(a1 + 304) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147943647LL,
      "WinREAgent::Executor::ScheduleWithCreatedWinRE",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      565,
      L"Execution was already scheduled");
    return 2147943647LL;
  }
  else
  {
    PushButtonReset::Logging::Trace(0, L"Schedule WinRE Servicing execution with created WinRE");
    if ( a3 )
    {
      WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"Goal", L"WinREServicing");
      WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"WinRECreationMehod", L"UseCreatedWinRE");
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v27,
      (__int64)L"FailToSchedule");
    v36 = 1;
    v31[0] = 0;
    v32 = TraceCanExecuteReason;
    v33 = a3;
    v34 = &v27;
    v35 = &v36;
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
        "WinREAgent::Executor::ScheduleWithCreatedWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        593,
        L"Failed to Register WinRE to Recovery BCD");
      if ( a3 )
        WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"RegisterRecoveryBCDFailed", v9);
    }
    v10 = (__int64 *)(a1 + 408);
    ExecutionContext = WinREAgent::CreateExecutionContext((__int64 *)(a1 + 368), 0, (__int64 *)(a1 + 408));
    if ( ExecutionContext < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)ExecutionContext,
        "WinREAgent::Executor::ScheduleWithCreatedWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        604,
        L"Failed to create execution context");
LABEL_17:
      ScopeGuardImplBase::SafeExecute<ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,bool *>>((__int64)v31);
      ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
      return (unsigned int)ExecutionContext;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v28);
    ExecutionContext = WinREAgent::WorkDir::GetRootDir(a1 + 368, (__int64)&v28);
    if ( ExecutionContext < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)ExecutionContext,
        "WinREAgent::Executor::ScheduleWithCreatedWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        609,
        L"Failed to get WinREAgent root directory");
LABEL_20:
      ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
      goto LABEL_17;
    }
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 416) + 8LL))(a1 + 416);
    ExecutionContext = WinREAgent::RollbackHelper::CreateRollbackHelper(&v28, v13);
    if ( ExecutionContext < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)ExecutionContext,
        "WinREAgent::Executor::ScheduleWithCreatedWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        612,
        L"Failed to create Rollback Helper");
      goto LABEL_20;
    }
    *(_QWORD *)(*v10 + 448) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 416) + 32LL))(a1 + 416);
    if ( !*(_BYTE *)(*v10 + 152) )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v27, L"NoRecoveryEnvironment", 21);
      PushButtonReset::Logging::TraceErr(
        2,
        2147500037LL,
        "WinREAgent::Executor::ScheduleWithCreatedWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        624,
        L"WinRE is not available");
      ExecutionContext = -2147467259;
      goto LABEL_20;
    }
    PushButtonReset::Logging::Trace(0, L"Trace partition info");
    v14 = TracePartitionInfo(a3);
    if ( v14 < 0 )
      PushButtonReset::Logging::TraceErr(
        1,
        (unsigned int)v14,
        "WinREAgent::Executor::ScheduleWithCreatedWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        631,
        L"Failed to trace partition info");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v30);
    ExecutionContext = WinREAgent::Executor::GetCreatedWinRE(&v30);
    v37 = ExecutionContext;
    if ( ExecutionContext < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)ExecutionContext,
        "WinREAgent::Executor::ScheduleWithCreatedWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        638,
        L"Failed to get the path of the created WinRE");
      ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
      goto LABEL_20;
    }
    v15 = v30;
    PushButtonReset::Logging::Trace(0, L"Will use WinRE at [%s]", v30);
    v16 = *v10;
    v17 = (ATL::CStringData *)(v15 - 24);
    v18 = (int *)(*(_QWORD *)(v16 + 280) - 24LL);
    if ( (int *)(v15 - 24) != v18 )
    {
      if ( v18[4] >= 0 && *(_QWORD *)v17 == *(_QWORD *)v18 )
      {
        v19 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v15 - 24);
        ATL::CStringData::Release((ATL::CStringData *)v18);
        *(_QWORD *)(v16 + 280) = v19 + 24;
      }
      else
      {
        ATL::CSimpleStringT<unsigned short,0>::SetString(v16 + 280, v15, *(unsigned int *)(v15 - 16));
      }
    }
    v24 = 0;
    v23 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
    v26 = PbrNew<WinREAgent::CleanupScratch,>();
    v25 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
    if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v25) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942414LL,
        "WinREAgent::Executor::ScheduleWithCreatedWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        647,
        L"Failed to allocate opCleanupScratch");
      v25 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v25);
      v23 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
LABEL_41:
      RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v23);
      ATL::CStringData::Release(v17);
      ExecutionContext = -2147024882;
      goto LABEL_20;
    }
    *(_BYTE *)(((__int64 (__fastcall *)(void ***))v25[3])(&v25) + 144) = 1;
    v29 = ((__int64 (__fastcall *)(void ***))v25[4])(&v25);
    ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
      (_QWORD *)(a1 + 32),
      &v29);
    v26 = 0;
    v20 = PbrNew<WinREAgent::SetupCreatedWinRE,>();
    ((void (__fastcall *)(void ***, __int64))v23[6])(&v23, v20);
    if ( ((unsigned __int8 (__fastcall *)(void ***))v23[9])(&v23) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942414LL,
        "WinREAgent::Executor::ScheduleWithCreatedWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        657,
        L"Failed to allocate operation");
LABEL_40:
      v25 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v25);
      v23 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
      goto LABEL_41;
    }
    v29 = ((__int64 (__fastcall *)(void ***))v23[4])(&v23);
    ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
      (_QWORD *)(a1 + 32),
      &v29);
    v24 = 0;
    v21 = v23;
    v22 = PbrNew<WinREAgent::BackupWinRE,>();
    ((void (__fastcall *)(void ***, __int64))v21[6])(&v23, v22);
    if ( ((unsigned __int8 (__fastcall *)(void ***))v23[9])(&v23) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942414LL,
        "WinREAgent::Executor::ScheduleWithCreatedWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        664,
        L"Failed to allocate operation");
      goto LABEL_40;
    }
    v29 = ((__int64 (__fastcall *)(void ***))v23[4])(&v23);
    ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
      (_QWORD *)(a1 + 32),
      &v29);
    v24 = 0;
    *(_BYTE *)(a1 + 272) = 1;
    v36 = 0;
    v25 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v25);
    v23 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v23);
    ATL::CStringData::Release(v17);
    ATL::CStringData::Release((ATL::CStringData *)(v28 - 24));
    ScopeGuardImplBase::SafeExecute<ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,bool *>>((__int64)v31);
    ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
    return v37;
  }
}

```

## disassembly

```asm
0x180011118  mov     [rsp-8+arg_8], rbx
0x18001111d  push    rbp
0x18001111e  push    rsi
0x18001111f  push    rdi
0x180011120  push    r12
0x180011122  push    r13
0x180011124  push    r14
0x180011126  push    r15
0x180011128  lea     rbp, [rsp-27h]
0x18001112d  sub     rsp, 0A0h
0x180011134  mov     r15, r8
0x180011137  mov     rbx, rdx
0x18001113a  mov     r14, rcx
0x18001113d  xor     r13d, r13d
0x180011140  cmp     [rcx+28h], r13
0x180011144  jnz     loc_18001175B
0x18001114a  cmp     [rcx+48h], r13
0x18001114e  jnz     loc_18001175B
0x180011154  cmp     [rcx+110h], r13b
0x18001115b  jnz     loc_18001175B
0x180011161  cmp     [rcx+130h], r13b
0x180011168  jnz     loc_18001175B
0x18001116e  lea     rdx, aScheduleWinreS_1; "Schedule WinRE Servicing execution with"...
0x180011175  xor     ecx, ecx
0x180011177  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001117c  test    r15, r15
0x18001117f  jz      short loc_1800111BB
0x180011181  lea     r9, aWinreservicing; "WinREServicing"
0x180011188  lea     r8, aGoal; "Goal"
0x18001118f  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x180011196  mov     rcx, r15; this
0x180011199  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x18001119e  lea     r9, aUsecreatedwinr; "UseCreatedWinRE"
0x1800111a5  lea     r8, aWinrecreationm; "WinRECreationMehod"
0x1800111ac  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x1800111b3  mov     rcx, r15; this
0x1800111b6  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x1800111bb  lea     rdx, aFailtoschedule; "FailToSchedule"
0x1800111c2  lea     rcx, [rbp+57h+var_80]
0x1800111c6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800111cb  nop
0x1800111cc  mov     [rbp+57h+arg_0], 1
0x1800111d0  mov     [rbp+57h+var_60], r13b
0x1800111d4  lea     rax, TraceCanExecuteReason
0x1800111db  mov     [rbp+57h+var_58], rax
0x1800111df  mov     [rbp+57h+var_50], r15
0x1800111e3  lea     rax, [rbp+57h+var_80]
0x1800111e7  mov     [rbp+57h+var_48], rax
0x1800111eb  lea     rax, [rbp+57h+arg_0]
0x1800111ef  mov     [rbp+57h+var_40], rax
0x1800111f3  lea     r12, [r14+170h]
0x1800111fa  mov     rdx, [rbx]
0x1800111fd  lea     rcx, [rdx-18h]
0x180011201  mov     rdi, [r12]
0x180011205  add     rdi, 0FFFFFFFFFFFFFFE8h
0x180011209  cmp     rcx, rdi
0x18001120c  jz      short loc_180011242
0x18001120e  cmp     [rdi+10h], r13d
0x180011212  jl      short loc_180011236
0x180011214  mov     rax, [rdi]
0x180011217  cmp     [rcx], rax
0x18001121a  jnz     short loc_180011236
0x18001121c  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x180011221  mov     rbx, rax
0x180011224  mov     rcx, rdi; this
0x180011227  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001122c  lea     rax, [rbx+18h]
0x180011230  mov     [r12], rax
0x180011234  jmp     short loc_180011242
0x180011236  mov     r8d, [rdx-10h]
0x18001123a  mov     rcx, r12
0x18001123d  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x180011242  lea     rdx, aAttemptToRegis; "Attempt to Register WinRE to Recovery B"...
0x180011249  xor     ecx, ecx
0x18001124b  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180011250  call    ?RegisterToRecoveryBCD@@YAJXZ; RegisterToRecoveryBCD(void)
0x180011255  mov     ebx, eax
0x180011257  lea     rdi, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001125e  lea     rsi, aWinreagentExec_1; "WinREAgent::Executor::ScheduleWithCreat"...
0x180011265  test    eax, eax
0x180011267  jns     short loc_1800112AD
0x180011269  lea     rax, aFailedToRegist; "Failed to Register WinRE to Recovery BC"...
0x180011270  mov     [rsp+0D0h+var_A8], rax
0x180011275  mov     [rsp+0D0h+var_B0], 251h
0x18001127d  mov     r9, rdi
0x180011280  mov     r8, rsi
0x180011283  mov     edx, ebx
0x180011285  mov     ecx, 1
0x18001128a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001128f  test    r15, r15
0x180011292  jz      short loc_1800112AD
0x180011294  mov     r9d, ebx; unsigned int
0x180011297  lea     r8, aRegisterrecove; "RegisterRecoveryBCDFailed"
0x18001129e  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x1800112a5  mov     rcx, r15; this
0x1800112a8  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ulong)
0x1800112ad  lea     r13, [r14+198h]
0x1800112b4  mov     r8, r13
0x1800112b7  xor     edx, edx
0x1800112b9  mov     rcx, r12
0x1800112bc  call    ?CreateExecutionContext@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAPEAVExecutionContext@1@@Z; WinREAgent::CreateExecutionContext(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *,WinREAgent::ExecutionContext * *)
0x1800112c1  mov     ebx, eax
0x1800112c3  test    eax, eax
0x1800112c5  jns     short loc_18001130C
0x1800112c7  lea     rax, aFailedToCreate_6; "Failed to create execution context"
0x1800112ce  mov     [rsp+0D0h+var_A8], rax
0x1800112d3  mov     [rsp+0D0h+var_B0], 25Ch
0x1800112db  mov     r9, rdi
0x1800112de  mov     r8, rsi
0x1800112e1  mov     edx, ebx
0x1800112e3  mov     ecx, 2
0x1800112e8  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800112ed  nop
0x1800112ee  lea     rcx, [rbp+57h+var_60]
0x1800112f2  call    ??$SafeExecute@V?$ScopeGuardImpl3@P6AXPEBVTelemetrySession@WinREAgent@@PEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@ZPEAV12@PEAV34@PEA_N@@@ScopeGuardImplBase@@KAXAEAV?$ScopeGuardImpl3@P6AXPEBVTelemetrySession@WinREAgent@@PEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_N@ZPEAV12@PEAV34@PEA_N@@@Z; ScopeGuardImplBase::SafeExecute<ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,bool *>>(ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *,bool *> &)
0x1800112f7  nop
0x1800112f8  mov     rcx, [rbp+57h+var_80]
0x1800112fc  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180011300  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180011305  mov     eax, ebx
0x180011307  jmp     loc_180011791
0x18001130c  lea     rcx, [rbp+57h+var_78]
0x180011310  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180011315  nop
0x180011316  lea     rdx, [rbp+57h+var_78]
0x18001131a  mov     rcx, r12
0x18001131d  call    ?GetRootDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetRootDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180011322  mov     ebx, eax
0x180011324  test    eax, eax
0x180011326  jns     short loc_18001135E
0x180011328  lea     rax, aFailedToGetWin; "Failed to get WinREAgent root directory"
0x18001132f  mov     [rsp+0D0h+var_A8], rax
0x180011334  mov     [rsp+0D0h+var_B0], 261h
0x18001133c  mov     r9, rdi
0x18001133f  mov     r8, rsi
0x180011342  mov     edx, ebx
0x180011344  mov     ecx, 2
0x180011349  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001134e  nop
0x18001134f  mov     rcx, [rbp+57h+var_78]
0x180011353  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180011357  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001135c  jmp     short loc_1800112EE
0x18001135e  lea     r12, [r14+1A0h]
0x180011365  mov     rax, [r12]
0x180011369  mov     rcx, r12
0x18001136c  mov     rax, [rax+8]
0x180011370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011375  mov     rdx, rax
0x180011378  lea     rcx, [rbp+57h+var_78]
0x18001137c  call    ?CreateRollbackHelper@RollbackHelper@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; WinREAgent::RollbackHelper::CreateRollbackHelper(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,WinREAgent::RollbackHelper * *)
0x180011381  mov     ebx, eax
0x180011383  test    eax, eax
0x180011385  jns     short loc_18001139D
0x180011387  lea     rax, aFailedToCreate_2; "Failed to create Rollback Helper"
0x18001138e  mov     [rsp+0D0h+var_A8], rax
0x180011393  mov     [rsp+0D0h+var_B0], 264h
0x18001139b  jmp     short loc_18001133C
0x18001139d  mov     rax, [r12]
0x1800113a1  mov     rcx, r12
0x1800113a4  mov     rax, [rax+20h]
0x1800113a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113ad  mov     rcx, [r13+0]
0x1800113b1  mov     [rcx+1C0h], rax
0x1800113b8  mov     rax, [r13+0]
0x1800113bc  cmp     byte ptr [rax+98h], 0
0x1800113c3  jnz     short loc_18001140E
0x1800113c5  mov     r8d, 15h
0x1800113cb  lea     rdx, aNorecoveryenvi; "NoRecoveryEnvironment"
0x1800113d2  lea     rcx, [rbp+57h+var_80]
0x1800113d6  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x1800113db  lea     rax, aWinreIsNotAvai; "WinRE is not available"
0x1800113e2  mov     [rsp+0D0h+var_A8], rax
0x1800113e7  mov     [rsp+0D0h+var_B0], 270h
0x1800113ef  mov     r9, rdi
0x1800113f2  mov     r8, rsi
0x1800113f5  mov     edx, 80004005h
0x1800113fa  mov     ecx, 2
0x1800113ff  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180011404  mov     ebx, 80004005h
0x180011409  jmp     loc_18001134F
0x18001140e  lea     rdx, aTracePartition; "Trace partition info"
0x180011415  xor     ecx, ecx
0x180011417  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001141c  mov     rdx, [r13+0]
0x180011420  add     rdx, 78h ; 'x'
0x180011424  mov     rcx, r15; this
0x180011427  call    ?TracePartitionInfo@@YAJPEAVTelemetrySession@WinREAgent@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; TracePartitionInfo(WinREAgent::TelemetrySession *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001142c  test    eax, eax
0x18001142e  jns     short loc_180011456
0x180011430  lea     rcx, aFailedToTraceP; "Failed to trace partition info"
0x180011437  mov     [rsp+0D0h+var_A8], rcx
0x18001143c  mov     [rsp+0D0h+var_B0], 277h
0x180011444  mov     r9, rdi
0x180011447  mov     r8, rsi
0x18001144a  mov     edx, eax
0x18001144c  mov     ecx, 1
0x180011451  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180011456  lea     rcx, [rbp+57h+var_68]
0x18001145a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001145f  nop
0x180011460  lea     rcx, [rbp+57h+var_68]
0x180011464  call    ?GetCreatedWinRE@Executor@WinREAgent@@CAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::Executor::GetCreatedWinRE(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x180011469  mov     ebx, eax
0x18001146b  mov     [rbp+57h+arg_18], eax
0x18001146e  test    eax, eax
0x180011470  jns     short loc_1800114AB
0x180011472  lea     rax, aFailedToGetThe_3; "Failed to get the path of the created W"...
0x180011479  mov     [rsp+0D0h+var_A8], rax
0x18001147e  mov     [rsp+0D0h+var_B0], 27Eh
0x180011486  mov     r9, rdi
0x180011489  mov     r8, rsi
0x18001148c  mov     edx, ebx
0x18001148e  mov     ecx, 2
0x180011493  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180011498  nop
0x180011499  mov     rcx, [rbp+57h+var_68]
0x18001149d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800114a1  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800114a6  jmp     loc_18001134F
0x1800114ab  mov     rbx, [rbp+57h+var_68]
0x1800114af  mov     r8, rbx
0x1800114b2  lea     rdx, aWillUseWinreAt; "Will use WinRE at [%s]"
0x1800114b9  xor     ecx, ecx
0x1800114bb  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800114c0  mov     r13, [r13+0]
0x1800114c4  lea     r15, [rbx-18h]
0x1800114c8  mov     r12, [r13+118h]
0x1800114cf  add     r12, 0FFFFFFFFFFFFFFE8h
0x1800114d3  cmp     r15, r12
0x1800114d6  jz      short loc_18001151C
0x1800114d8  cmp     dword ptr [r12+10h], 0
0x1800114de  jl      short loc_180011509
0x1800114e0  mov     rax, [r12]
0x1800114e4  cmp     [r15], rax
0x1800114e7  jnz     short loc_180011509
0x1800114e9  mov     rcx, r15
0x1800114ec  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x1800114f1  mov     rbx, rax
0x1800114f4  mov     rcx, r12; this
0x1800114f7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800114fc  lea     rax, [rbx+18h]
0x180011500  mov     [r13+118h], rax
0x180011507  jmp     short loc_18001151C
0x180011509  mov     r8d, [rbx-10h]
0x18001150d  mov     rdx, rbx
0x180011510  lea     rcx, [r13+118h]
0x180011517  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18001151c  xor     r13d, r13d
0x18001151f  mov     [rbp+57h+var_98], r13
0x180011523  lea     rbx, ??_7?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable'
0x18001152a  mov     [rbp+57h+var_A0], rbx
0x18001152e  call    ??$PbrNew@VCleanupScratch@WinREAgent@@$$V@@YAPEAVCleanupScratch@WinREAgent@@XZ; PbrNew<WinREAgent::CleanupScratch,>(void)
0x180011533  mov     [rbp+57h+var_88], rax
0x180011537  lea     r12, ??_7?$CAutoPbrDelete@PEAVCleanupScratch@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable'
0x18001153e  mov     [rbp+57h+var_90], r12
0x180011542  lea     rcx, [rbp+57h+var_90]
0x180011546  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x18001154b  test    al, al
0x18001154d  jz      short loc_18001158F
0x18001154f  lea     rax, aFailedToAlloca_33; "Failed to allocate opCleanupScratch"
0x180011556  mov     [rsp+0D0h+var_A8], rax
0x18001155b  mov     [rsp+0D0h+var_B0], 287h
0x180011563  mov     r9, rdi
0x180011566  mov     r8, rsi
0x180011569  mov     edx, 8007000Eh
0x18001156e  lea     ecx, [r13+2]
0x180011572  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180011577  nop
0x180011578  mov     [rbp+57h+var_90], r12
0x18001157c  lea     rcx, [rbp+57h+var_90]
0x180011580  call    ?Release@?$CAutoPbrDelete@PEAVPrepareWinRE@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(void)
0x180011585  nop
0x180011586  mov     [rbp+57h+var_A0], rbx
0x18001158a  jmp     loc_1800116B1
0x18001158f  mov     rax, [rbp+57h+var_90]
0x180011593  lea     rcx, [rbp+57h+var_90]
0x180011597  mov     rax, [rax+18h]
0x18001159b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115a0  mov     byte ptr [rax+90h], 1
0x1800115a7  mov     rax, [rbp+57h+var_90]
0x1800115ab  lea     rcx, [rbp+57h+var_90]
0x1800115af  mov     rax, [rax+20h]
0x1800115b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115b8  mov     [rbp+57h+var_70], rax
0x1800115bc  lea     rdx, [rbp+57h+var_70]
0x1800115c0  lea     r12, [r14+20h]
0x1800115c4  mov     rcx, r12
0x1800115c7  call    ?Add@?$CAtlArray@PEAUPACKAGE_INFO@WinREAgent@@V?$CElementTraits@PEAUPACKAGE_INFO@WinREAgent@@@ATL@@@ATL@@QEAA_KAEBQEAUPACKAGE_INFO@WinREAgent@@@Z; ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(WinREAgent::PACKAGE_INFO * const &)
0x1800115cc  mov     [rbp+57h+var_88], r13
0x1800115d0  mov     rbx, [rbp+57h+var_A0]
0x1800115d4  call    ??$PbrNew@VSetupCreatedWinRE@WinREAgent@@$$V@@YAPEAVSetupCreatedWinRE@WinREAgent@@XZ; PbrNew<WinREAgent::SetupCreatedWinRE,>(void)
0x1800115d9  mov     rdx, rax
0x1800115dc  lea     rcx, [rbp+57h+var_A0]
0x1800115e0  mov     rax, [rbx+30h]
0x1800115e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115e9  mov     rax, [rbp+57h+var_A0]
0x1800115ed  lea     rcx, [rbp+57h+var_A0]
0x1800115f1  mov     rax, [rax+48h]
0x1800115f5  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
