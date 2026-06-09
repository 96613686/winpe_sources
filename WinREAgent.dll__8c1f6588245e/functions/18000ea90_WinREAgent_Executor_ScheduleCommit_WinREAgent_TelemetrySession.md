# WinREAgent::Executor::ScheduleCommit(WinREAgent::TelemetrySession *)

- ea: `0x18000ea90`
- end: `0x18000f24c`
- name: `?ScheduleCommit@Executor@WinREAgent@@AEAAJPEAVTelemetrySession@2@@Z`
- size: `1980`
- prototype: `int(WinREAgent::Executor *__hidden this, struct WinREAgent::TelemetrySession *)`
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180012050`

## callees

- `0x180003cdc`
- `0x180003d64`
- `0x180003e5c`
- `0x180003ff4`
- `0x180004048`
- `0x18000407c`
- `0x1800047f8`
- `0x1800049a4`
- `0x1800064a0`
- `0x18000b300`
- `0x18000d620`
- `0x18000d92c`
- `0x18000d9ec`
- `0x18000ea90`
- `0x18000febc`
- `0x180011ef4`
- `0x18002383c`
- `0x180023d30`
- `0x18002dee0`
- `0x18002e06c`
- `0x18003717c`
- `0x180037344`
- `0x18004d2ac`
- `0x18006f010`

## string_xrefs

- `0x18000eb40`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000ebb7`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000ec4a`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000ed6a`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000ee83`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000ef0e`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000f01f`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000f199`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000f200`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000eaab`: `Schedule Commit execution`
- `0x18000f1dc`: `AlreadyScheduled`
- `0x18000f1ec`: `Commit Execution was already scheduled`
- `0x18000eb47`: `WinREAgent::Executor::ScheduleCommit`
- `0x18000ebbe`: `WinREAgent::Executor::ScheduleCommit`
- `0x18000ec51`: `WinREAgent::Executor::ScheduleCommit`
- `0x18000ed71`: `WinREAgent::Executor::ScheduleCommit`
- `0x18000ee8a`: `WinREAgent::Executor::ScheduleCommit`
- `0x18000ef15`: `WinREAgent::Executor::ScheduleCommit`
- `0x18000f026`: `WinREAgent::Executor::ScheduleCommit`
- `0x18000f1a0`: `WinREAgent::Executor::ScheduleCommit`
- `0x18000f207`: `WinREAgent::Executor::ScheduleCommit`
- `0x18000f175`: `NoUpdateWinRE`
- `0x18000f185`: `No Updated WinRE`
- `0x18000ef6f`: `Failed to allocate updateInPartitionOp`
- `0x18000ee0b`: `ReplaceInPlace`
- `0x18000ee02`: `UpdateInPartition`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WinREAgent::Executor::ScheduleCommit(
        WinREAgent::Executor *this,
        struct WinREAgent::TelemetrySession *a2)
{
  int v4; // edi
  _QWORD *v5; // rcx
  const wchar_t *v6; // r8
  WinREAgent::Operation *v7; // rax
  void **v8; // rbx
  WinREAgent::Operation *v9; // rax
  unsigned int *v10; // rbx
  __int64 v11; // r9
  __int64 v12; // rdx
  __int64 v13; // rdx
  const unsigned __int16 *v14; // r9
  __int64 v15; // rax
  __int64 v16; // rax
  void **v17; // rbx
  WinREAgent::Operation *v18; // rax
  void **v19; // rbx
  WinREAgent::Operation *v20; // rax
  void **v21; // rbx
  WinREAgent::Operation *v22; // rax
  void **v24; // [rsp+30h] [rbp-50h] BYREF
  __int64 v25; // [rsp+38h] [rbp-48h]
  void **v26; // [rsp+40h] [rbp-40h] BYREF
  __int64 v27; // [rsp+48h] [rbp-38h]
  _BYTE v28[8]; // [rsp+50h] [rbp-30h] BYREF
  __int64 (__fastcall *v29)(); // [rsp+58h] [rbp-28h]
  struct WinREAgent::TelemetrySession *v30; // [rsp+60h] [rbp-20h]
  __int64 *v31; // [rsp+68h] [rbp-18h]
  char *v32; // [rsp+70h] [rbp-10h]
  __int64 v33; // [rsp+C0h] [rbp+40h] BYREF
  char v34; // [rsp+C8h] [rbp+48h] BYREF
  __int64 v35; // [rsp+D0h] [rbp+50h] BYREF
  __int64 v36; // [rsp+D8h] [rbp+58h] BYREF

  PushButtonReset::Logging::Trace(0, L"Schedule Commit execution");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v35,
    (__int64)L"FailToSchedule");
  v34 = 1;
  v28[0] = 0;
  v29 = TraceCanCommitReason;
  v30 = a2;
  v31 = &v35;
  v32 = &v34;
  if ( !*((_QWORD *)this + 9) && !*((_BYTE *)this + 304) )
  {
    if ( !*((_BYTE *)this + 336) )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v35, L"NotStaged", 9);
      PushButtonReset::Logging::TraceErr(
        2,
        2147942421LL,
        "WinREAgent::Executor::ScheduleCommit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        704,
        L"Must execute Stage first");
      v4 = -2147024875;
LABEL_51:
      ScopeGuardImplBase::SafeExecute<ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,bool *>>((__int64)v28);
      ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
      return (unsigned int)v4;
    }
    v5 = (_QWORD *)(*((_QWORD *)this + 51) + 280LL);
    if ( !*(_DWORD *)(*v5 - 16LL) || !(unsigned __int8)PushButtonReset::File::Exists(v5) )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v35, L"NoUpdateWinRE", 13);
      PushButtonReset::Logging::TraceErr(
        2,
        2147943568LL,
        "WinREAgent::Executor::ScheduleCommit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        711,
        L"No Updated WinRE");
      v4 = -2147023728;
      goto LABEL_51;
    }
    LOBYTE(v33) = 0;
    v4 = IsClientEdition(0, (bool *)&v33);
    if ( v4 < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v4,
        "WinREAgent::Executor::ScheduleCommit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        716,
        L"Failed to check whether OS is client");
      goto LABEL_51;
    }
    v6 = &pszFormat;
    if ( !(_BYTE)v33 )
      v6 = L" not";
    PushButtonReset::Logging::Trace(0, L"OS is%s Client", v6);
    v25 = 0;
    v24 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
    v7 = PbrNew<WinREAgent::VerifyNewWinREHash,>();
    ((void (__fastcall *)(void ***, WinREAgent::Operation *))RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::operator=)(
      &v24,
      v7);
    if ( ((unsigned __int8 (__fastcall *)(void ***))v24[9])(&v24) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942414LL,
        "WinREAgent::Executor::ScheduleCommit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        724,
        L"Failed to allocate operation");
LABEL_13:
      v24 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
LABEL_14:
      RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v24);
      v4 = -2147024882;
      goto LABEL_51;
    }
    v36 = ((__int64 (__fastcall *)(void ***))v24[4])(&v24);
    ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
      (_QWORD *)this + 8,
      &v36);
    v25 = 0;
    v8 = v24;
    v9 = PbrNew<WinREAgent::AddNewWinREHash,>();
    ((void (__fastcall *)(void ***, WinREAgent::Operation *))v8[6])(&v24, v9);
    if ( ((unsigned __int8 (__fastcall *)(void ***))v24[9])(&v24) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942414LL,
        "WinREAgent::Executor::ScheduleCommit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        731,
        L"Failed to allocate operation");
      goto LABEL_13;
    }
    v36 = ((__int64 (__fastcall *)(void ***))v24[4])(&v24);
    ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
      (_QWORD *)this + 8,
      &v36);
    v25 = 0;
    v10 = (unsigned int *)((char *)this + 432);
    LOBYTE(v11) = v33;
    v4 = WinREAgent::Scenario::DetermineScenarioTypeByWim(
           *((_QWORD *)this + 51) + 120LL,
           *((_QWORD *)this + 51) + 280LL,
           a2,
           v11,
           (char *)this + 432);
    if ( v4 < 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::SetString(&v35, L"FailToDetermineScenario", 23);
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v4,
        "WinREAgent::Executor::ScheduleCommit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        755,
        L"Could not schedule scenario operations");
LABEL_19:
      v24 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v24);
      goto LABEL_51;
    }
    PushButtonReset::Logging::Trace(0, L"Selected [%u] scenario to execute", *v10);
    if ( a2 )
    {
      WinREAgent::TelemetrySession::TraceDataPoint(a2, L"ServicingInfoGroup", L"Scenario", *v10);
      LOBYTE(v13) = 1;
      wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::ReportUsage(
        `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::GetImpl'::`2'::impl,
        v13);
      if ( *v10 )
      {
        switch ( *v10 )
        {
          case 1u:
            v14 = L"ReplaceInPlace";
            break;
          case 2u:
            v14 = L"UpdateInPartition";
            break;
          case 3u:
            v14 = L"Repartition";
            break;
          default:
            v14 = L"Invalid";
            break;
        }
      }
      else
      {
        v14 = L"None";
      }
      WinREAgent::TelemetrySession::TraceDataPoint(a2, L"ServicingInfoGroup", L"ScenarioString", v14);
    }
    v27 = 0;
    v26 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
    switch ( *v10 )
    {
      case 1u:
        v17 = v24;
        v18 = PbrNew<WinREAgent::SwapWinREs,>();
        ((void (__fastcall *)(void ***, WinREAgent::Operation *))v17[6])(&v24, v18);
        if ( ((unsigned __int8 (__fastcall *)(void ***))v24[9])(&v24) )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            2147942414LL,
            "WinREAgent::Executor::ScheduleCommit",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            780,
            L"Failed to allocate operation");
          goto LABEL_43;
        }
        v33 = ((__int64 (__fastcall *)(void ***))v24[4])(&v24);
        ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
          (_QWORD *)this + 8,
          &v33);
        v25 = 0;
        break;
      case 2u:
        v15 = PbrNew<WinREAgent::UpdateInPartition,>();
        ((void (__fastcall *)(void ***, __int64))RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::operator=)(
          &v26,
          v15);
        if ( ((unsigned __int8 (__fastcall *)(void ***))v26[9])(&v26) )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            2147942414LL,
            "WinREAgent::Executor::ScheduleCommit",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            789,
            L"Failed to allocate updateInPartitionOp");
          goto LABEL_43;
        }
        v16 = ((__int64 (__fastcall *)(void ***))v26[3])(&v26);
        WinREAgent::UpdateInPartition::Commit(v16, *((_QWORD *)this + 51) + 120LL, *((_QWORD *)this + 51) + 280LL);
        v33 = ((__int64 (__fastcall *)(void ***))v26[4])(&v26);
        ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
          (_QWORD *)this + 8,
          &v33);
        v27 = 0;
        break;
      case 3u:
        LOBYTE(v12) = 1;
        wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::ReportUsage(
          `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::GetImpl'::`2'::impl,
          v12);
        v4 = WinREAgent::Executor::ScheduleRepartition(this, v33, a2);
        if ( v4 < 0 )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v4,
            "WinREAgent::Executor::ScheduleCommit",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            804,
            L"Failed to schedule repartition scenario");
LABEL_37:
          v26 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
          RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v26);
          goto LABEL_19;
        }
        break;
      default:
        ATL::CSimpleStringT<unsigned short,0>::SetString(&v35, L"InvalidScenario", 15);
        PushButtonReset::Logging::TraceErr(
          2,
          2147500037LL,
          "WinREAgent::Executor::ScheduleCommit",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          816,
          L"Could not schedule scenario operations");
        v26 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v26);
        v24 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v24);
        v4 = -2147467259;
        goto LABEL_51;
    }
    v19 = v24;
    v20 = PbrNew<WinREAgent::DeleteOldWinREHash,>();
    ((void (__fastcall *)(void ***, WinREAgent::Operation *))v19[6])(&v24, v20);
    if ( ((unsigned __int8 (__fastcall *)(void ***))v24[9])(&v24) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942414LL,
        "WinREAgent::Executor::ScheduleCommit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        822,
        L"Failed to allocate operation");
    }
    else
    {
      v33 = ((__int64 (__fastcall *)(void ***))v24[4])(&v24);
      ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
        (_QWORD *)this + 8,
        &v33);
      v25 = 0;
      v21 = v24;
      v22 = PbrNew<WinREAgent::CleanupScratch,>();
      ((void (__fastcall *)(void ***, WinREAgent::Operation *))v21[6])(&v24, v22);
      if ( !((unsigned __int8 (__fastcall *)(void ***))v24[9])(&v24) )
      {
        v33 = ((__int64 (__fastcall *)(void ***))v24[4])(&v24);
        ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
          (_QWORD *)this + 8,
          &v33);
        v25 = 0;
        *((_BYTE *)this + 304) = 1;
        v34 = 0;
        goto LABEL_37;
      }
      PushButtonReset::Logging::TraceErr(
        2,
        2147942414LL,
        "WinREAgent::Executor::ScheduleCommit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        829,
        L"Failed to allocate operation");
    }
LABEL_43:
    v26 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
    RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v26);
    v24 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
    goto LABEL_14;
  }
  ATL::CSimpleStringT<unsigned short,0>::SetString(&v35, L"AlreadyScheduled", 16);
  PushButtonReset::Logging::TraceErr(
    2,
    2147943647LL,
    "WinREAgent::Executor::ScheduleCommit",
    "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
    697,
    L"Commit Execution was already scheduled");
  ScopeGuardImplBase::SafeExecute<ScopeGuardImpl3<void (*)(WinREAgent::TelemetrySession const *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const *,bool *),WinREAgent::TelemetrySession *,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> *,bool *>>((__int64)v28);
  ATL::CStringData::Release((ATL::CStringData *)(v35 - 24));
  return 2147943647LL;
}

```

## disassembly

```asm
0x18000ea90  push    rbp
0x18000ea92  push    rbx
0x18000ea93  push    rsi
0x18000ea94  push    rdi
0x18000ea95  push    r13
0x18000ea97  push    r14
0x18000ea99  push    r15
0x18000ea9b  mov     rbp, rsp
0x18000ea9e  sub     rsp, 80h
0x18000eaa5  mov     r14, rdx
0x18000eaa8  mov     rsi, rcx
0x18000eaab  lea     rdx, aScheduleCommit; "Schedule Commit execution"
0x18000eab2  xor     ecx, ecx
0x18000eab4  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18000eab9  lea     rdx, aFailtoschedule; "FailToSchedule"
0x18000eac0  lea     rcx, [rbp+arg_10]
0x18000eac4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000eac9  nop
0x18000eaca  mov     [rbp+arg_8], 1
0x18000eace  xor     r13d, r13d
0x18000ead1  mov     [rbp+var_30], r13b
0x18000ead5  lea     rax, TraceCanCommitReason
0x18000eadc  mov     [rbp+var_28], rax
0x18000eae0  mov     [rbp+var_20], r14
0x18000eae4  lea     rax, [rbp+arg_10]
0x18000eae8  mov     [rbp+var_18], rax
0x18000eaec  lea     rax, [rbp+arg_8]
0x18000eaf0  mov     [rbp+var_10], rax
0x18000eaf4  lea     r15, [rsi+40h]
0x18000eaf8  cmp     [r15+8], r13
0x18000eafc  jnz     loc_18000F1D6
0x18000eb02  cmp     [rsi+130h], r13b
0x18000eb09  jnz     loc_18000F1D6
0x18000eb0f  cmp     [rsi+150h], r13b
0x18000eb16  jnz     short loc_18000EB66
0x18000eb18  lea     r8d, [r13+9]
0x18000eb1c  lea     rdx, aNotstaged; "NotStaged"
0x18000eb23  lea     rcx, [rbp+arg_10]
0x18000eb27  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000eb2c  lea     rax, aMustExecuteSta; "Must execute Stage first"
0x18000eb33  mov     [rsp+80h+var_58], rax
0x18000eb38  mov     dword ptr [rsp+80h+var_60], 2C0h
0x18000eb40  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000eb47  lea     r8, aWinreagentExec_15; "WinREAgent::Executor::ScheduleCommit"
0x18000eb4e  mov     edx, 80070015h
0x18000eb53  lea     ecx, [r13+2]
0x18000eb57  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000eb5c  mov     edi, 80070015h
0x18000eb61  jmp     loc_18000F1BB
0x18000eb66  mov     rcx, [rsi+198h]
0x18000eb6d  add     rcx, 118h
0x18000eb74  mov     rax, [rcx]
0x18000eb77  cmp     [rax-10h], r13d
0x18000eb7b  jz      loc_18000F16F
0x18000eb81  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000eb86  test    al, al
0x18000eb88  jz      loc_18000F16F
0x18000eb8e  mov     byte ptr [rbp+arg_0], r13b
0x18000eb92  lea     rdx, [rbp+arg_0]; bool *
0x18000eb96  xor     ecx, ecx; unsigned __int16 *
0x18000eb98  call    ?IsClientEdition@@YAJPEBGPEA_N@Z; IsClientEdition(ushort const *,bool *)
0x18000eb9d  mov     edi, eax
0x18000eb9f  test    eax, eax
0x18000eba1  jns     short loc_18000EBD6
0x18000eba3  lea     rax, aFailedToCheckW_9; "Failed to check whether OS is client"
0x18000ebaa  mov     [rsp+80h+var_58], rax
0x18000ebaf  mov     dword ptr [rsp+80h+var_60], 2CCh
0x18000ebb7  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000ebbe  lea     r8, aWinreagentExec_15; "WinREAgent::Executor::ScheduleCommit"
0x18000ebc5  mov     edx, edi
0x18000ebc7  mov     ecx, 2
0x18000ebcc  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000ebd1  jmp     loc_18000F1BB
0x18000ebd6  lea     r8, pszFormat
0x18000ebdd  lea     rax, aNot; " not"
0x18000ebe4  cmp     byte ptr [rbp+arg_0], r13b
0x18000ebe8  cmovz   r8, rax
0x18000ebec  lea     rdx, aOsIsSClient; "OS is%s Client"
0x18000ebf3  xor     ecx, ecx
0x18000ebf5  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18000ebfa  mov     [rbp+var_48], r13
0x18000ebfe  lea     rdi, ??_7?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable'
0x18000ec05  mov     [rbp+var_50], rdi
0x18000ec09  call    ??$PbrNew@VVerifyNewWinREHash@WinREAgent@@$$V@@YAPEAVVerifyNewWinREHash@WinREAgent@@XZ; PbrNew<WinREAgent::VerifyNewWinREHash,>(void)
0x18000ec0e  mov     rdx, rax
0x18000ec11  lea     rcx, [rbp+var_50]
0x18000ec15  mov     rax, cs:off_180070C88
0x18000ec1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec21  mov     rax, [rbp+var_50]
0x18000ec25  lea     rcx, [rbp+var_50]
0x18000ec29  mov     rax, [rax+48h]
0x18000ec2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec32  test    al, al
0x18000ec34  jz      short loc_18000EC7F
0x18000ec36  lea     rax, aFailedToAlloca_9; "Failed to allocate operation"
0x18000ec3d  mov     [rsp+80h+var_58], rax
0x18000ec42  mov     dword ptr [rsp+80h+var_60], 2D4h
0x18000ec4a  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000ec51  lea     r8, aWinreagentExec_15; "WinREAgent::Executor::ScheduleCommit"
0x18000ec58  mov     edx, 8007000Eh
0x18000ec5d  mov     ecx, 2
0x18000ec62  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000ec67  nop
0x18000ec68  mov     [rbp+var_50], rdi
0x18000ec6c  lea     rcx, [rbp+var_50]
0x18000ec70  call    ?Release@?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(void)
0x18000ec75  mov     edi, 8007000Eh
0x18000ec7a  jmp     loc_18000F1BB
0x18000ec7f  mov     rax, [rbp+var_50]
0x18000ec83  lea     rcx, [rbp+var_50]
0x18000ec87  mov     rax, [rax+20h]
0x18000ec8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec90  mov     [rbp+arg_18], rax
0x18000ec94  lea     rdx, [rbp+arg_18]
0x18000ec98  mov     rcx, r15
0x18000ec9b  call    ?Add@?$CAtlArray@PEAUPACKAGE_INFO@WinREAgent@@V?$CElementTraits@PEAUPACKAGE_INFO@WinREAgent@@@ATL@@@ATL@@QEAA_KAEBQEAUPACKAGE_INFO@WinREAgent@@@Z; ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(WinREAgent::PACKAGE_INFO * const &)
0x18000eca0  mov     [rbp+var_48], r13
0x18000eca4  mov     rbx, [rbp+var_50]
0x18000eca8  call    ??$PbrNew@VAddNewWinREHash@WinREAgent@@$$V@@YAPEAVAddNewWinREHash@WinREAgent@@XZ; PbrNew<WinREAgent::AddNewWinREHash,>(void)
0x18000ecad  mov     rdx, rax
0x18000ecb0  lea     rcx, [rbp+var_50]
0x18000ecb4  mov     rax, [rbx+30h]
0x18000ecb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecbd  mov     rax, [rbp+var_50]
0x18000ecc1  lea     rcx, [rbp+var_50]
0x18000ecc5  mov     rax, [rax+48h]
0x18000ecc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecce  test    al, al
0x18000ecd0  jz      short loc_18000ECEB
0x18000ecd2  lea     rax, aFailedToAlloca_9; "Failed to allocate operation"
0x18000ecd9  mov     [rsp+80h+var_58], rax
0x18000ecde  mov     dword ptr [rsp+80h+var_60], 2DBh
0x18000ece6  jmp     loc_18000EC4A
0x18000eceb  mov     rax, [rbp+var_50]
0x18000ecef  lea     rcx, [rbp+var_50]
0x18000ecf3  mov     rax, [rax+20h]
0x18000ecf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ecfc  mov     [rbp+arg_18], rax
0x18000ed00  lea     rdx, [rbp+arg_18]
0x18000ed04  mov     rcx, r15
0x18000ed07  call    ?Add@?$CAtlArray@PEAUPACKAGE_INFO@WinREAgent@@V?$CElementTraits@PEAUPACKAGE_INFO@WinREAgent@@@ATL@@@ATL@@QEAA_KAEBQEAUPACKAGE_INFO@WinREAgent@@@Z; ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(WinREAgent::PACKAGE_INFO * const &)
0x18000ed0c  mov     [rbp+var_48], r13
0x18000ed10  mov     rcx, [rsi+198h]
0x18000ed17  lea     rbx, [rsi+1B0h]
0x18000ed1e  lea     rdx, [rcx+118h]
0x18000ed25  add     rcx, 78h ; 'x'
0x18000ed29  mov     [rsp+80h+var_60], rbx
0x18000ed2e  mov     r9b, byte ptr [rbp+arg_0]
0x18000ed32  mov     r8, r14
0x18000ed35  call    ?DetermineScenarioTypeByWim@Scenario@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAVTelemetrySession@2@_NAEAW4ScenarioType@2@@Z; WinREAgent::Scenario::DetermineScenarioTypeByWim(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,WinREAgent::TelemetrySession *,bool,WinREAgent::ScenarioType &)
0x18000ed3a  mov     edi, eax
0x18000ed3c  test    eax, eax
0x18000ed3e  jns     short loc_18000ED9E
0x18000ed40  mov     r8d, 17h
0x18000ed46  lea     rdx, aFailtodetermin; "FailToDetermineScenario"
0x18000ed4d  lea     rcx, [rbp+arg_10]
0x18000ed51  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000ed56  lea     rax, aCouldNotSchedu; "Could not schedule scenario operations"
0x18000ed5d  mov     [rsp+80h+var_58], rax
0x18000ed62  mov     dword ptr [rsp+80h+var_60], 2F3h
0x18000ed6a  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000ed71  lea     r8, aWinreagentExec_15; "WinREAgent::Executor::ScheduleCommit"
0x18000ed78  mov     edx, edi
0x18000ed7a  mov     ecx, 2
0x18000ed7f  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000ed84  nop
0x18000ed85  lea     rax, ??_7?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable'
0x18000ed8c  mov     [rbp+var_50], rax
0x18000ed90  lea     rcx, [rbp+var_50]
0x18000ed94  call    ?Release@?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(void)
0x18000ed99  jmp     loc_18000F1BB
0x18000ed9e  mov     r8d, [rbx]
0x18000eda1  lea     rdx, aSelectedUScena; "Selected [%u] scenario to execute"
0x18000eda8  xor     ecx, ecx
0x18000edaa  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18000edaf  test    r14, r14
0x18000edb2  jz      short loc_18000EE31
0x18000edb4  mov     r9d, [rbx]; unsigned int
0x18000edb7  lea     r8, aScenario; "Scenario"
0x18000edbe  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x18000edc5  mov     rcx, r14; this
0x18000edc8  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG0K@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ulong)
0x18000edcd  mov     dl, 1
0x18000edcf  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing> `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::GetImpl(void)'::`2'::impl
0x18000edd6  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000eddb  mov     ecx, [rbx]
0x18000eddd  test    ecx, ecx
0x18000eddf  jz      short loc_18000EE14
0x18000ede1  sub     ecx, 1
0x18000ede4  jz      short loc_18000EE0B
0x18000ede6  sub     ecx, 1
0x18000ede9  jz      short loc_18000EE02
0x18000edeb  cmp     ecx, 1
0x18000edee  jz      short loc_18000EDF9
0x18000edf0  lea     r9, aInvalid; "Invalid"
0x18000edf7  jmp     short loc_18000EE1B
0x18000edf9  lea     r9, aRepartition; "Repartition"
0x18000ee00  jmp     short loc_18000EE1B
0x18000ee02  lea     r9, aUpdateinpartit_0; "UpdateInPartition"
0x18000ee09  jmp     short loc_18000EE1B
0x18000ee0b  lea     r9, aReplaceinplace; "ReplaceInPlace"
0x18000ee12  jmp     short loc_18000EE1B
0x18000ee14  lea     r9, aNone; "None"
0x18000ee1b  lea     r8, aScenariostring; "ScenarioString"
0x18000ee22  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x18000ee29  mov     rcx, r14; this
0x18000ee2c  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x18000ee31  mov     [rbp+var_38], r13
0x18000ee35  lea     rax, ??_7?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable'
0x18000ee3c  mov     [rbp+var_40], rax
0x18000ee40  mov     ecx, [rbx]
0x18000ee42  sub     ecx, 1
0x18000ee45  jz      loc_18000EFDD
0x18000ee4b  sub     ecx, 1
0x18000ee4e  jz      loc_18000EF42
0x18000ee54  cmp     ecx, 1
0x18000ee57  jz      short loc_18000EED4
0x18000ee59  mov     r8d, 0Fh
0x18000ee5f  lea     rdx, aInvalidscenari; "InvalidScenario"
0x18000ee66  lea     rcx, [rbp+arg_10]
0x18000ee6a  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000ee6f  lea     rax, aCouldNotSchedu; "Could not schedule scenario operations"
0x18000ee76  mov     [rsp+80h+var_58], rax
0x18000ee7b  mov     dword ptr [rsp+80h+var_60], 330h
0x18000ee83  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000ee8a  lea     r8, aWinreagentExec_15; "WinREAgent::Executor::ScheduleCommit"
0x18000ee91  mov     edx, 80004005h
0x18000ee96  mov     ecx, 2
0x18000ee9b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000eea0  nop
0x18000eea1  lea     rax, ??_7?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable'
0x18000eea8  mov     [rbp+var_40], rax
0x18000eeac  lea     rcx, [rbp+var_40]
0x18000eeb0  call    ?Release@?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(void)
0x18000eeb5  nop
0x18000eeb6  lea     rax, ??_7?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable'
0x18000eebd  mov     [rbp+var_50], rax
0x18000eec1  lea     rcx, [rbp+var_50]
0x18000eec5  call    ?Release@?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(void)
0x18000eeca  mov     edi, 80004005h
0x18000eecf  jmp     loc_18000F1BB
0x18000eed4  mov     dl, 1
0x18000eed6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing> `wil::Feature<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::GetImpl(void)'::`2'::impl
0x18000eedd  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_WinREAgent_PartitionResizing@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WinREAgent_PartitionResizing>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18000eee2  mov     r8, r14; struct WinREAgent::TelemetrySession *
0x18000eee5  mov     dl, byte ptr [rbp+arg_0]; bool
0x18000eee8  mov     rcx, rsi; this
0x18000eeeb  call    ?ScheduleRepartition@Executor@WinREAgent@@AEAAJ_NPEAVTelemetrySession@2@@Z; WinREAgent::Executor::ScheduleRepartition(bool,WinREAgent::TelemetrySession *)
0x18000eef0  mov     edi, eax
0x18000eef2  test    eax, eax
0x18000eef4  jns     loc_18000F087
0x18000eefa  lea     rax, aFailedToSchedu_1; "Failed to schedule repartition scenario"
0x18000ef01  mov     [rsp+80h+var_58], rax
0x18000ef06  mov     dword ptr [rsp+80h+var_60], 324h
0x18000ef0e  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000ef15  lea     r8, aWinreagentExec_15; "WinREAgent::Executor::ScheduleCommit"
0x18000ef1c  mov     edx, edi
0x18000ef1e  mov     ecx, 2
0x18000ef23  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000ef28  nop
0x18000ef29  lea     rax, ??_7?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable'
0x18000ef30  mov     [rbp+var_40], rax
0x18000ef34  lea     rcx, [rbp+var_40]
0x18000ef38  call    ?Release@?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(void)
0x18000ef3d  jmp     loc_18000ED85
0x18000ef42  call    ??$PbrNew@VUpdateInPartition@WinREAgent@@$$V@@YAPEAVUpdateInPartition@WinREAgent@@XZ; PbrNew<WinREAgent::UpdateInPartition,>(void)
0x18000ef47  mov     rdx, rax
0x18000ef4a  lea     rcx, [rbp+var_40]
0x18000ef4e  mov     rax, cs:off_180070C88
0x18000ef55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef5a  mov     rax, [rbp+var_40]
0x18000ef5e  lea     rcx, [rbp+var_40]
0x18000ef62  mov     rax, [rax+48h]
0x18000ef66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef6b  test    al, al
0x18000ef6d  jz      short loc_18000EF88
0x18000ef6f  lea     rax, aFailedToAlloca_11; "Failed to allocate updateInPartitionOp"
0x18000ef76  mov     [rsp+80h+var_58], rax
0x18000ef7b  mov     dword ptr [rsp+80h+var_60], 315h
0x18000ef83  jmp     loc_18000F01F
0x18000ef88  mov     rax, [rbp+var_40]
0x18000ef8c  lea     rcx, [rbp+var_40]
0x18000ef90  mov     rax, [rax+18h]
0x18000ef94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef99  mov     rdx, [rsi+198h]
0x18000efa0  lea     r8, [rdx+118h]
0x18000efa7  add     rdx, 78h ; 'x'
0x18000efab  mov     rcx, rax
0x18000efae  call    ?Commit@UpdateInPartition@WinREAgent@@QEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WinREAgent::UpdateInPartition::Commit(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18000efb3  mov     rax, [rbp+var_40]
0x18000efb7  lea     rcx, [rbp+var_40]
0x18000efbb  mov     rax, [rax+20h]
0x18000efbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000efc4  mov     [rbp+arg_0], rax
0x18000efc8  lea     rdx, [rbp+arg_0]
0x18000efcc  mov     rcx, r15
0x18000efcf  call    ?Add@?$CAtlArray@PEAUPACKAGE_INFO@WinREAgent@@V?$CElementTraits@PEAUPACKAGE_INFO@WinREAgent@@@ATL@@@ATL@@QEAA_KAEBQEAUPACKAGE_INFO@WinREAgent@@@Z; ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(WinREAgent::PACKAGE_INFO * const &)
0x18000efd4  mov     [rbp+var_38], r13
0x18000efd8  jmp     loc_18000F087
0x18000efdd  mov     rbx, [rbp+var_50]
  ... truncated ...
```
