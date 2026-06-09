# WinREAgent::Executor::RestoreWinRE(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,ushort const *,WinREAgent::TelemetrySession *)

- ea: `0x18000dcc8`
- end: `0x18000e6eb`
- name: `?RestoreWinRE@Executor@WinREAgent@@QEAAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEBGPEAVTelemetrySession@2@@Z`
- size: `2595`
- prototype: `__int64 __usercall@<rax>(WinREAgent::Executor *this@<rcx>, WinREAgent::TelemetrySession *)`
- caller_count: `1`
- callee_count: `29`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18001b268`

## callees

- `0x180003cdc`
- `0x180003d30`
- `0x180003d64`
- `0x180003e5c`
- `0x180003f4c`
- `0x180003ff4`
- `0x180004048`
- `0x180004af8`
- `0x180005c00`
- `0x1800064a0`
- `0x1800074b8`
- `0x180007570`
- `0x18000b300`
- `0x18000d5c0`
- `0x18000d620`
- `0x18000d92c`
- `0x18000dcc8`
- `0x180011ef4`
- `0x180012050`
- `0x18001e51c`
- `0x18001f228`
- `0x18002383c`
- `0x180023d30`
- `0x18002dee0`
- `0x18002e06c`
- `0x18002f85c`
- `0x18003717c`
- `0x180037344`
- `0x18006f010`

## string_xrefs

- `0x18000dde2`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000de88`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000df2d`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000dff3`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000e0b8`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000e246`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000e2bc`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000e3d5`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000e48f`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000e62f`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000e6b1`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000e69d`: `Execution was already scheduled`
- `0x18000de42`: `Failed to create execution context`
- `0x18000de74`: `Failed to get WinREAgent root directory`
- `0x18000dedd`: `Failed to create Rollback Helper`
- `0x18000e3c1`: `Failed to allocate updateInPartitionOp`
- `0x18000dde9`: `WinREAgent::Executor::RestoreWinRE`
- `0x18000de8f`: `WinREAgent::Executor::RestoreWinRE`
- `0x18000df34`: `WinREAgent::Executor::RestoreWinRE`
- `0x18000dffa`: `WinREAgent::Executor::RestoreWinRE`
- `0x18000e0bf`: `WinREAgent::Executor::RestoreWinRE`
- `0x18000e24d`: `WinREAgent::Executor::RestoreWinRE`
- `0x18000e2c3`: `WinREAgent::Executor::RestoreWinRE`
- `0x18000e3dc`: `WinREAgent::Executor::RestoreWinRE`
- `0x18000e496`: `WinREAgent::Executor::RestoreWinRE`
- `0x18000e636`: `WinREAgent::Executor::RestoreWinRE`
- `0x18000e6b8`: `WinREAgent::Executor::RestoreWinRE`
- `0x18000e5d1`: `Operation scheduled, executing`
- `0x18000e61b`: `Failed to commit Restore`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall WinREAgent::Executor::RestoreWinRE(
        WinREAgent::Executor *this,
        __int64 *a2,
        _QWORD *a3,
        const unsigned __int16 *a4,
        WinREAgent::TelemetrySession *a5)
{
  _QWORD *v9; // r13
  WinREAgent::TelemetrySession *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rdx
  int *v13; // rcx
  int *v14; // r15
  __int64 v15; // rbx
  int ExecutionContext; // ebx
  const wchar_t *v18; // r8
  char *v19; // r15
  __int64 v20; // rax
  __int64 v21; // r15
  _QWORD *v22; // r12
  int *v23; // rcx
  int *v24; // r14
  __int64 v25; // rbx
  void **v26; // rbx
  WinREAgent::Operation *v27; // rax
  void **v28; // rbx
  __int64 v29; // rax
  void **v30; // rbx
  WinREAgent::Operation *v31; // rax
  __int64 v32; // r9
  int v33; // eax
  unsigned int v34; // r14d
  __int64 v35; // rax
  __int64 v36; // rax
  void **v37; // rbx
  WinREAgent::Operation *v38; // rax
  void **v39; // rbx
  WinREAgent::Operation *v40; // rax
  void **v41; // rbx
  WinREAgent::Operation *v42; // rax
  unsigned int v43[2]; // [rsp+30h] [rbp-40h] BYREF
  __int64 v44; // [rsp+38h] [rbp-38h] BYREF
  void **v45; // [rsp+40h] [rbp-30h] BYREF
  __int64 v46; // [rsp+48h] [rbp-28h]
  void **v47; // [rsp+50h] [rbp-20h] BYREF
  WinREAgent::Operation *v48; // [rsp+58h] [rbp-18h]
  void **v49; // [rsp+60h] [rbp-10h] BYREF
  __int64 v50; // [rsp+68h] [rbp-8h]
  __int64 v51; // [rsp+B0h] [rbp+40h] BYREF
  _QWORD *v52; // [rsp+C0h] [rbp+50h]

  v52 = a3;
  if ( !*((_QWORD *)this + 5) )
  {
    v9 = (_QWORD *)((char *)this + 64);
    if ( !*((_QWORD *)this + 9) && !*((_BYTE *)this + 272) && !*((_BYTE *)this + 304) )
    {
      v10 = a5;
      if ( a5 )
        WinREAgent::TelemetrySession::TraceDataPoint(a5, L"ServicingInfoGroup", L"Goal", L"RestoreWinRE");
      v11 = L"NULL";
      if ( a4 )
        v11 = a4;
      PushButtonReset::Logging::Trace(0, L"Restore WinRE [%s] for Windows [%s]", *a3, v11);
      v12 = *a2;
      v13 = (int *)(*a2 - 24);
      v14 = (int *)(*((_QWORD *)this + 46) - 24LL);
      if ( v13 != v14 )
      {
        if ( v14[4] >= 0 && *(_QWORD *)v13 == *(_QWORD *)v14 )
        {
          v15 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v13);
          ATL::CStringData::Release((ATL::CStringData *)v14);
          *((_QWORD *)this + 46) = v15 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString((char *)this + 368, v12, *(unsigned int *)(v12 - 16));
        }
      }
      LOBYTE(v51) = 0;
      ExecutionContext = IsClientEdition(a4, (bool *)&v51);
      if ( ExecutionContext < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)ExecutionContext,
          "WinREAgent::Executor::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2455,
          L"Failed to check whether OS is client");
        return (unsigned int)ExecutionContext;
      }
      v18 = &pszFormat;
      if ( !(_BYTE)v51 )
        v18 = L" not";
      PushButtonReset::Logging::Trace(0, L"OS is%s Client", v18);
      v19 = (char *)this + 408;
      ExecutionContext = WinREAgent::CreateExecutionContext((char *)this + 368, a4, (char *)this + 408);
      if ( ExecutionContext < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)ExecutionContext,
          "WinREAgent::Executor::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2460,
          L"Failed to create execution context");
        return (unsigned int)ExecutionContext;
      }
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v44);
      ExecutionContext = WinREAgent::WorkDir::GetRootDir((__int64)this + 368, (__int64)&v44);
      if ( ExecutionContext < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)ExecutionContext,
          "WinREAgent::Executor::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2465,
          L"Failed to get WinREAgent root directory");
LABEL_23:
        ATL::CStringData::Release((ATL::CStringData *)(v44 - 24));
        return (unsigned int)ExecutionContext;
      }
      v20 = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 52) + 8LL))((char *)this + 416);
      ExecutionContext = WinREAgent::RollbackHelper::CreateRollbackHelper(&v44, v20);
      if ( ExecutionContext < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)ExecutionContext,
          "WinREAgent::Executor::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2468,
          L"Failed to create Rollback Helper");
        goto LABEL_23;
      }
      *(_QWORD *)(*(_QWORD *)v19 + 448LL) = (*(__int64 (__fastcall **)(char *))(*((_QWORD *)this + 52) + 32LL))((char *)this + 416);
      v21 = *(_QWORD *)v19;
      if ( !*(_BYTE *)(v21 + 152) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147500037LL,
          "WinREAgent::Executor::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2475,
          L"WinRE is not available");
LABEL_28:
        ExecutionContext = -2147467259;
        goto LABEL_23;
      }
      v22 = v52;
      v23 = (int *)(*v52 - 24LL);
      v24 = (int *)(*(_QWORD *)(v21 + 280) - 24LL);
      if ( v23 != v24 )
      {
        if ( v24[4] >= 0 && *(_QWORD *)v23 == *(_QWORD *)v24 )
        {
          v25 = ATL::CSimpleStringT<unsigned short,0>::CloneData(v23);
          ATL::CStringData::Release((ATL::CStringData *)v24);
          *(_QWORD *)(v21 + 280) = v25 + 24;
        }
        else
        {
          ATL::CSimpleStringT<unsigned short,0>::SetString(v21 + 280, *v52, *(unsigned int *)(*v52 - 16LL));
        }
      }
      v46 = 0;
      v45 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
      v48 = PbrNew<WinREAgent::CleanupScratch,>();
      v47 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
      if ( (unsigned __int8)RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!((__int64 *)&v47) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "WinREAgent::Executor::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2484,
          L"Failed to allocate opCleanupScratch");
        v47 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v47);
        v45 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
LABEL_36:
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v45);
        ExecutionContext = -2147024882;
        goto LABEL_23;
      }
      *(_BYTE *)(((__int64 (__fastcall *)(void ***))v47[3])(&v47) + 144) = 1;
      *(_QWORD *)v43 = ((__int64 (__fastcall *)(void ***))v47[4])(&v47);
      ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
        (_QWORD *)this + 4,
        v43);
      v48 = 0;
      v26 = v45;
      v27 = PbrNew<WinREAgent::SaveWinREHash,>();
      ((void (__fastcall *)(void ***, WinREAgent::Operation *))v26[6])(&v45, v27);
      if ( ((unsigned __int8 (__fastcall *)(void ***))v45[9])(&v45) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "WinREAgent::Executor::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2494,
          L"Failed to allocate operation");
LABEL_39:
        v47 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v47);
        v45 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        goto LABEL_36;
      }
      *(_QWORD *)v43 = ((__int64 (__fastcall *)(void ***))v45[4])(&v45);
      ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
        (_QWORD *)this + 4,
        v43);
      v46 = 0;
      v28 = v45;
      v29 = PbrNew<WinREAgent::BackupWinRE,>();
      ((void (__fastcall *)(void ***, __int64))v28[6])(&v45, v29);
      if ( ((unsigned __int8 (__fastcall *)(void ***))v45[9])(&v45) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "WinREAgent::Executor::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2501,
          L"Failed to allocate operation");
        goto LABEL_39;
      }
      *(_QWORD *)v43 = ((__int64 (__fastcall *)(void ***))v45[4])(&v45);
      ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(
        (_QWORD *)this + 4,
        v43);
      v46 = 0;
      *((_BYTE *)this + 272) = 1;
      v30 = v45;
      v31 = PbrNew<WinREAgent::AddNewWinREHash,>();
      ((void (__fastcall *)(void ***, WinREAgent::Operation *))v30[6])(&v45, v31);
      if ( ((unsigned __int8 (__fastcall *)(void ***))v45[9])(&v45) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "WinREAgent::Executor::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2510,
          L"Failed to allocate operation");
        goto LABEL_39;
      }
      *(_QWORD *)v43 = ((__int64 (__fastcall *)(void ***))v45[4])(&v45);
      ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(v9, v43);
      v46 = 0;
      v43[0] = 0;
      LOBYTE(v32) = v51;
      v33 = WinREAgent::Scenario::DetermineScenarioTypeByWim(*((_QWORD *)this + 51) + 120LL, v22, v10, v32, v43);
      ExecutionContext = v33;
      if ( v33 < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v33,
          "WinREAgent::Executor::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2533,
          L"Could not schedule scenario operations");
LABEL_70:
        v47 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v47);
        v45 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
        RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v45);
        goto LABEL_23;
      }
      v34 = v43[0];
      PushButtonReset::Logging::Trace(0, L"Selected [%u] scenario to execute", v43[0]);
      if ( v10 )
        WinREAgent::TelemetrySession::TraceDataPoint(v10, L"ServicingInfoGroup", L"Scenario", v34);
      v50 = 0;
      v49 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
      switch ( v34 )
      {
        case 1u:
          v37 = v45;
          v38 = PbrNew<WinREAgent::SwapWinREs,>();
          ((void (__fastcall *)(void ***, WinREAgent::Operation *))v37[6])(&v45, v38);
          if ( ((unsigned __int8 (__fastcall *)(void ***))v45[9])(&v45) )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              2147942414LL,
              "WinREAgent::Executor::RestoreWinRE",
              "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
              2551,
              L"Failed to allocate operation");
LABEL_58:
            v49 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
            goto LABEL_59;
          }
          v51 = ((__int64 (__fastcall *)(void ***))v45[4])(&v45);
          ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(v9, &v51);
          v46 = 0;
          break;
        case 2u:
          v35 = PbrNew<WinREAgent::UpdateInPartition,>();
          ((void (__fastcall *)(void ***, __int64))RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::operator=)(
            &v49,
            v35);
          if ( ((unsigned __int8 (__fastcall *)(void ***))v49[9])(&v49) )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              2147942414LL,
              "WinREAgent::Executor::RestoreWinRE",
              "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
              2564,
              L"Failed to allocate updateInPartitionOp");
            v49 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
LABEL_59:
            RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v49);
            goto LABEL_39;
          }
          v36 = ((__int64 (__fastcall *)(void ***))v49[3])(&v49);
          WinREAgent::UpdateInPartition::Commit(v36, *((_QWORD *)this + 51) + 120LL, *((_QWORD *)this + 51) + 280LL);
          v51 = ((__int64 (__fastcall *)(void ***))v49[4])(&v49);
          ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(v9, &v51);
          v50 = 0;
          break;
        case 3u:
          PushButtonReset::Logging::TraceErr(
            2,
            2147500033LL,
            "WinREAgent::Executor::RestoreWinRE",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            2558,
            L"Scenario case is not implemented");
          v49 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
          RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v49);
          v47 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
          RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v47);
          v45 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
          RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v45);
          ExecutionContext = -2147467263;
          goto LABEL_23;
        default:
          PushButtonReset::Logging::TraceErr(
            2,
            2147500037LL,
            "WinREAgent::Executor::RestoreWinRE",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            2573,
            L"Could not schedule scenario operations");
          v49 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
          RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v49);
          v47 = &RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable';
          RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(&v47);
          v45 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
          RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v45);
          goto LABEL_28;
      }
      v39 = v45;
      v40 = PbrNew<WinREAgent::DeleteOldWinREHash,>();
      ((void (__fastcall *)(void ***, WinREAgent::Operation *))v39[6])(&v45, v40);
      if ( ((unsigned __int8 (__fastcall *)(void ***))v45[9])(&v45) )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "WinREAgent::Executor::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2579,
          L"Failed to allocate operation");
      }
      else
      {
        v51 = ((__int64 (__fastcall *)(void ***))v45[4])(&v45);
        ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(v9, &v51);
        v46 = 0;
        v41 = v45;
        v42 = PbrNew<WinREAgent::CleanupScratch,>();
        ((void (__fastcall *)(void ***, WinREAgent::Operation *))v41[6])(&v45, v42);
        if ( !((unsigned __int8 (__fastcall *)(void ***))v45[9])(&v45) )
        {
          v51 = ((__int64 (__fastcall *)(void ***))v45[4])(&v45);
          ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(v9, &v51);
          v46 = 0;
          *((_BYTE *)this + 304) = 1;
          *((_DWORD *)this + 108) = v34;
          PushButtonReset::Logging::Trace(0, L"Operation scheduled, executing");
          ExecutionContext = WinREAgent::Executor::Stage(this, 0, v10);
          if ( ExecutionContext >= 0 )
          {
            ExecutionContext = WinREAgent::Executor::Commit(this, 0, v10);
            if ( ExecutionContext >= 0 )
              PushButtonReset::Logging::Trace(0, L"Restore WinRE succeed");
            else
              PushButtonReset::Logging::TraceErr(
                2,
                (unsigned int)ExecutionContext,
                "WinREAgent::Executor::RestoreWinRE",
                "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
                2600,
                L"Failed to commit Restore");
          }
          else
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)ExecutionContext,
              "WinREAgent::Executor::RestoreWinRE",
              "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
              2597,
              L"Failed to stage Restore");
          }
          v49 = &RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable';
          RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(&v49);
          goto LABEL_70;
        }
        PushButtonReset::Logging::TraceErr(
          2,
          2147942414LL,
          "WinREAgent::Executor::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          2586,
          L"Failed to allocate operation");
      }
      goto LABEL_58;
    }
  }
  PushButtonReset::Logging::TraceErr(
    2,
    2147943647LL,
    "WinREAgent::Executor::RestoreWinRE",
    "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
    2437,
    L"Execution was already scheduled");
  return 2147943647LL;
}

```

## disassembly

```asm
0x18000dcc8  mov     [rsp-38h+arg_8], rbx
0x18000dccd  mov     [rsp-38h+arg_10], r8
0x18000dcd2  push    rbp
0x18000dcd3  push    rsi
0x18000dcd4  push    rdi
0x18000dcd5  push    r12
0x18000dcd7  push    r13
0x18000dcd9  push    r14
0x18000dcdb  push    r15
0x18000dcdd  mov     rbp, rsp
0x18000dce0  sub     rsp, 70h
0x18000dce4  mov     r12, r9
0x18000dce7  mov     rbx, r8
0x18000dcea  mov     r15, rdx
0x18000dced  mov     rdi, rcx
0x18000dcf0  xor     r14d, r14d
0x18000dcf3  cmp     [rcx+28h], r14
0x18000dcf7  jnz     loc_18000E69D
0x18000dcfd  lea     r13, [rcx+40h]
0x18000dd01  cmp     [r13+8], r14
0x18000dd05  jnz     loc_18000E69D
0x18000dd0b  cmp     [rcx+110h], r14b
0x18000dd12  jnz     loc_18000E69D
0x18000dd18  cmp     [rcx+130h], r14b
0x18000dd1f  jnz     loc_18000E69D
0x18000dd25  mov     rsi, [rbp+arg_20]
0x18000dd29  test    rsi, rsi
0x18000dd2c  jz      short loc_18000DD4B
0x18000dd2e  lea     r9, aRestorewinre_0; "RestoreWinRE"
0x18000dd35  lea     r8, aGoal; "Goal"
0x18000dd3c  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x18000dd43  mov     rcx, rsi; this
0x18000dd46  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x18000dd4b  lea     r9, aNull_0; "NULL"
0x18000dd52  test    r12, r12
0x18000dd55  cmovnz  r9, r12
0x18000dd59  mov     r8, [rbx]
0x18000dd5c  lea     rdx, aRestoreWinreSF; "Restore WinRE [%s] for Windows [%s]"
0x18000dd63  xor     ecx, ecx
0x18000dd65  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18000dd6a  lea     r14, [rdi+170h]
0x18000dd71  mov     rdx, [r15]
0x18000dd74  lea     rcx, [rdx-18h]
0x18000dd78  mov     r15, [r14]
0x18000dd7b  add     r15, 0FFFFFFFFFFFFFFE8h
0x18000dd7f  cmp     rcx, r15
0x18000dd82  jz      short loc_18000DDB8
0x18000dd84  cmp     dword ptr [r15+10h], 0
0x18000dd89  jl      short loc_18000DDAC
0x18000dd8b  mov     rax, [r15]
0x18000dd8e  cmp     [rcx], rax
0x18000dd91  jnz     short loc_18000DDAC
0x18000dd93  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000dd98  mov     rbx, rax
0x18000dd9b  mov     rcx, r15; this
0x18000dd9e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000dda3  lea     rax, [rbx+18h]
0x18000dda7  mov     [r14], rax
0x18000ddaa  jmp     short loc_18000DDB8
0x18000ddac  mov     r8d, [rdx-10h]
0x18000ddb0  mov     rcx, r14
0x18000ddb3  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000ddb8  mov     byte ptr [rbp+arg_0], 0
0x18000ddbc  lea     rdx, [rbp+arg_0]; bool *
0x18000ddc0  mov     rcx, r12; unsigned __int16 *
0x18000ddc3  call    ?IsClientEdition@@YAJPEBGPEA_N@Z; IsClientEdition(ushort const *,bool *)
0x18000ddc8  mov     ebx, eax
0x18000ddca  test    eax, eax
0x18000ddcc  jns     short loc_18000DE03
0x18000ddce  lea     rax, aFailedToCheckW_9; "Failed to check whether OS is client"
0x18000ddd5  mov     [rsp+70h+var_48], rax
0x18000ddda  mov     dword ptr [rsp+70h+var_50], 997h
0x18000dde2  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000dde9  lea     r8, aWinreagentExec_11; "WinREAgent::Executor::RestoreWinRE"
0x18000ddf0  mov     edx, ebx
0x18000ddf2  mov     ecx, 2
0x18000ddf7  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000ddfc  mov     eax, ebx
0x18000ddfe  jmp     loc_18000E6D3
0x18000de03  lea     r8, pszFormat
0x18000de0a  lea     rax, aNot; " not"
0x18000de11  cmp     byte ptr [rbp+arg_0], 0
0x18000de15  cmovz   r8, rax
0x18000de19  lea     rdx, aOsIsSClient; "OS is%s Client"
0x18000de20  xor     ecx, ecx
0x18000de22  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18000de27  lea     r15, [rdi+198h]
0x18000de2e  mov     r8, r15
0x18000de31  mov     rdx, r12
0x18000de34  mov     rcx, r14
0x18000de37  call    ?CreateExecutionContext@WinREAgent@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEBGPEAPEAVExecutionContext@1@@Z; WinREAgent::CreateExecutionContext(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ushort const *,WinREAgent::ExecutionContext * *)
0x18000de3c  mov     ebx, eax
0x18000de3e  test    eax, eax
0x18000de40  jns     short loc_18000DE58
0x18000de42  lea     rax, aFailedToCreate_6; "Failed to create execution context"
0x18000de49  mov     [rsp+70h+var_48], rax
0x18000de4e  mov     dword ptr [rsp+70h+var_50], 99Ch
0x18000de56  jmp     short loc_18000DDE2
0x18000de58  lea     rcx, [rbp+var_38]
0x18000de5c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18000de61  nop
0x18000de62  lea     rdx, [rbp+var_38]
0x18000de66  mov     rcx, r14
0x18000de69  call    ?GetRootDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetRootDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18000de6e  mov     ebx, eax
0x18000de70  test    eax, eax
0x18000de72  jns     short loc_18000DEB5
0x18000de74  lea     rax, aFailedToGetWin; "Failed to get WinREAgent root directory"
0x18000de7b  mov     [rsp+70h+var_48], rax
0x18000de80  mov     dword ptr [rsp+70h+var_50], 9A1h
0x18000de88  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000de8f  lea     r8, aWinreagentExec_11; "WinREAgent::Executor::RestoreWinRE"
0x18000de96  mov     edx, ebx
0x18000de98  mov     ecx, 2
0x18000de9d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000dea2  nop
0x18000dea3  mov     rcx, [rbp+var_38]
0x18000dea7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000deab  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000deb0  jmp     loc_18000DDFC
0x18000deb5  lea     r14, [rdi+1A0h]
0x18000debc  mov     rax, [r14]
0x18000debf  mov     rcx, r14
0x18000dec2  mov     rax, [rax+8]
0x18000dec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000decb  mov     rdx, rax
0x18000dece  lea     rcx, [rbp+var_38]
0x18000ded2  call    ?CreateRollbackHelper@RollbackHelper@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAV12@@Z; WinREAgent::RollbackHelper::CreateRollbackHelper(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,WinREAgent::RollbackHelper * *)
0x18000ded7  mov     ebx, eax
0x18000ded9  test    eax, eax
0x18000dedb  jns     short loc_18000DEF3
0x18000dedd  lea     rax, aFailedToCreate_2; "Failed to create Rollback Helper"
0x18000dee4  mov     [rsp+70h+var_48], rax
0x18000dee9  mov     dword ptr [rsp+70h+var_50], 9A4h
0x18000def1  jmp     short loc_18000DE88
0x18000def3  mov     rax, [r14]
0x18000def6  mov     rcx, r14
0x18000def9  mov     rax, [rax+20h]
0x18000defd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000df02  mov     rcx, [r15]
0x18000df05  mov     [rcx+1C0h], rax
0x18000df0c  mov     r15, [r15]
0x18000df0f  cmp     byte ptr [r15+98h], 0
0x18000df17  jnz     short loc_18000DF54
0x18000df19  lea     rax, aWinreIsNotAvai; "WinRE is not available"
0x18000df20  mov     [rsp+70h+var_48], rax
0x18000df25  mov     dword ptr [rsp+70h+var_50], 9ABh
0x18000df2d  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000df34  lea     r8, aWinreagentExec_11; "WinREAgent::Executor::RestoreWinRE"
0x18000df3b  mov     edx, 80004005h
0x18000df40  mov     ecx, 2
0x18000df45  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000df4a  mov     ebx, 80004005h
0x18000df4f  jmp     loc_18000DEA3
0x18000df54  mov     r12, [rbp+arg_10]
0x18000df58  mov     rdx, [r12]
0x18000df5c  lea     rcx, [rdx-18h]
0x18000df60  mov     r14, [r15+118h]
0x18000df67  add     r14, 0FFFFFFFFFFFFFFE8h
0x18000df6b  cmp     rcx, r14
0x18000df6e  jz      short loc_18000DFAC
0x18000df70  cmp     dword ptr [r14+10h], 0
0x18000df75  jl      short loc_18000DF9C
0x18000df77  mov     rax, [r14]
0x18000df7a  cmp     [rcx], rax
0x18000df7d  jnz     short loc_18000DF9C
0x18000df7f  call    ?CloneData@?$CSimpleStringT@G$0A@@ATL@@CAPEAUCStringData@2@PEAU32@@Z; ATL::CSimpleStringT<ushort,0>::CloneData(ATL::CStringData *)
0x18000df84  mov     rbx, rax
0x18000df87  mov     rcx, r14; this
0x18000df8a  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18000df8f  lea     rax, [rbx+18h]
0x18000df93  mov     [r15+118h], rax
0x18000df9a  jmp     short loc_18000DFAC
0x18000df9c  mov     r8d, [rdx-10h]
0x18000dfa0  lea     rcx, [r15+118h]
0x18000dfa7  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *,int)
0x18000dfac  xor     r15d, r15d
0x18000dfaf  mov     [rbp+var_28], r15
0x18000dfb3  lea     rbx, ??_7?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable'
0x18000dfba  mov     [rbp+var_30], rbx
0x18000dfbe  call    ??$PbrNew@VCleanupScratch@WinREAgent@@$$V@@YAPEAVCleanupScratch@WinREAgent@@XZ; PbrNew<WinREAgent::CleanupScratch,>(void)
0x18000dfc3  mov     [rbp+var_18], rax
0x18000dfc7  lea     r14, ??_7?$CAutoPbrDelete@PEAVCleanupScratch@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable'
0x18000dfce  mov     [rbp+var_20], r14
0x18000dfd2  lea     rcx, [rbp+var_20]
0x18000dfd6  call    ??7?$CAutoCleanupBase@PEAUISetupOneSettings@@@RAII@@UEBA_NXZ; RAII::CAutoCleanupBase<ISetupOneSettings *>::operator!(void)
0x18000dfdb  test    al, al
0x18000dfdd  jz      short loc_18000E035
0x18000dfdf  lea     rax, aFailedToAlloca_33; "Failed to allocate opCleanupScratch"
0x18000dfe6  mov     [rsp+70h+var_48], rax
0x18000dfeb  mov     dword ptr [rsp+70h+var_50], 9B4h
0x18000dff3  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000dffa  lea     r8, aWinreagentExec_11; "WinREAgent::Executor::RestoreWinRE"
0x18000e001  mov     edx, 8007000Eh
0x18000e006  lea     ecx, [r15+2]
0x18000e00a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000e00f  nop
0x18000e010  mov     [rbp+var_20], r14
0x18000e014  lea     rcx, [rbp+var_20]
0x18000e018  call    ?Release@?$CAutoPbrDelete@PEAVPrepareWinRE@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(void)
0x18000e01d  nop
0x18000e01e  mov     [rbp+var_30], rbx
0x18000e022  lea     rcx, [rbp+var_30]
0x18000e026  call    ?Release@?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::Release(void)
0x18000e02b  mov     ebx, 8007000Eh
0x18000e030  jmp     loc_18000DEA3
0x18000e035  mov     rax, [rbp+var_20]
0x18000e039  lea     rcx, [rbp+var_20]
0x18000e03d  mov     rax, [rax+18h]
0x18000e041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e046  mov     byte ptr [rax+90h], 1
0x18000e04d  mov     rax, [rbp+var_20]
0x18000e051  lea     rcx, [rbp+var_20]
0x18000e055  mov     rax, [rax+20h]
0x18000e059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e05e  mov     qword ptr [rbp+var_40], rax
0x18000e062  lea     rdx, [rbp+var_40]
0x18000e066  lea     r14, [rdi+20h]
0x18000e06a  mov     rcx, r14
0x18000e06d  call    ?Add@?$CAtlArray@PEAUPACKAGE_INFO@WinREAgent@@V?$CElementTraits@PEAUPACKAGE_INFO@WinREAgent@@@ATL@@@ATL@@QEAA_KAEBQEAUPACKAGE_INFO@WinREAgent@@@Z; ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(WinREAgent::PACKAGE_INFO * const &)
0x18000e072  mov     [rbp+var_18], r15
0x18000e076  mov     rbx, [rbp+var_30]
0x18000e07a  call    ??$PbrNew@VSaveWinREHash@WinREAgent@@$$V@@YAPEAVSaveWinREHash@WinREAgent@@XZ; PbrNew<WinREAgent::SaveWinREHash,>(void)
0x18000e07f  mov     rdx, rax
0x18000e082  lea     rcx, [rbp+var_30]
0x18000e086  mov     rax, [rbx+30h]
0x18000e08a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e08f  mov     rax, [rbp+var_30]
0x18000e093  lea     rcx, [rbp+var_30]
0x18000e097  mov     rax, [rax+48h]
0x18000e09b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0a0  test    al, al
0x18000e0a2  jz      short loc_18000E0FB
0x18000e0a4  lea     rax, aFailedToAlloca_9; "Failed to allocate operation"
0x18000e0ab  mov     [rsp+70h+var_48], rax
0x18000e0b0  mov     dword ptr [rsp+70h+var_50], 9BEh
0x18000e0b8  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000e0bf  lea     r8, aWinreagentExec_11; "WinREAgent::Executor::RestoreWinRE"
0x18000e0c6  mov     edx, 8007000Eh
0x18000e0cb  mov     ecx, 2
0x18000e0d0  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000e0d5  nop
0x18000e0d6  lea     rax, ??_7?$CAutoPbrDelete@PEAVCleanupScratch@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::CleanupScratch *>::`vftable'
0x18000e0dd  mov     [rbp+var_20], rax
0x18000e0e1  lea     rcx, [rbp+var_20]
0x18000e0e5  call    ?Release@?$CAutoPbrDelete@PEAVPrepareWinRE@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::PrepareWinRE *>::Release(void)
0x18000e0ea  nop
0x18000e0eb  lea     rax, ??_7?$CAutoPbrDelete@PEAVUpdateInPartition@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::UpdateInPartition *>::`vftable'
0x18000e0f2  mov     [rbp+var_30], rax
0x18000e0f6  jmp     loc_18000E022
0x18000e0fb  mov     rax, [rbp+var_30]
0x18000e0ff  lea     rcx, [rbp+var_30]
0x18000e103  mov     rax, [rax+20h]
0x18000e107  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e10c  mov     qword ptr [rbp+var_40], rax
0x18000e110  lea     rdx, [rbp+var_40]
0x18000e114  mov     rcx, r14
0x18000e117  call    ?Add@?$CAtlArray@PEAUPACKAGE_INFO@WinREAgent@@V?$CElementTraits@PEAUPACKAGE_INFO@WinREAgent@@@ATL@@@ATL@@QEAA_KAEBQEAUPACKAGE_INFO@WinREAgent@@@Z; ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(WinREAgent::PACKAGE_INFO * const &)
0x18000e11c  mov     [rbp+var_28], r15
0x18000e120  mov     rbx, [rbp+var_30]
0x18000e124  call    ??$PbrNew@VBackupWinRE@WinREAgent@@$$V@@YAPEAVBackupWinRE@WinREAgent@@XZ; PbrNew<WinREAgent::BackupWinRE,>(void)
0x18000e129  mov     rdx, rax
0x18000e12c  lea     rcx, [rbp+var_30]
0x18000e130  mov     rax, [rbx+30h]
0x18000e134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e139  mov     rax, [rbp+var_30]
0x18000e13d  lea     rcx, [rbp+var_30]
0x18000e141  mov     rax, [rax+48h]
0x18000e145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e14a  test    al, al
0x18000e14c  jz      short loc_18000E167
0x18000e14e  lea     rax, aFailedToAlloca_9; "Failed to allocate operation"
0x18000e155  mov     [rsp+70h+var_48], rax
0x18000e15a  mov     dword ptr [rsp+70h+var_50], 9C5h
0x18000e162  jmp     loc_18000E0B8
0x18000e167  mov     rax, [rbp+var_30]
0x18000e16b  lea     rcx, [rbp+var_30]
0x18000e16f  mov     rax, [rax+20h]
0x18000e173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e178  mov     qword ptr [rbp+var_40], rax
0x18000e17c  lea     rdx, [rbp+var_40]
0x18000e180  mov     rcx, r14
0x18000e183  call    ?Add@?$CAtlArray@PEAUPACKAGE_INFO@WinREAgent@@V?$CElementTraits@PEAUPACKAGE_INFO@WinREAgent@@@ATL@@@ATL@@QEAA_KAEBQEAUPACKAGE_INFO@WinREAgent@@@Z; ATL::CAtlArray<WinREAgent::PACKAGE_INFO *,ATL::CElementTraits<WinREAgent::PACKAGE_INFO *>>::Add(WinREAgent::PACKAGE_INFO * const &)
0x18000e188  mov     [rbp+var_28], r15
0x18000e18c  mov     byte ptr [rdi+110h], 1
0x18000e193  mov     rbx, [rbp+var_30]
0x18000e197  call    ??$PbrNew@VAddNewWinREHash@WinREAgent@@$$V@@YAPEAVAddNewWinREHash@WinREAgent@@XZ; PbrNew<WinREAgent::AddNewWinREHash,>(void)
0x18000e19c  mov     rdx, rax
0x18000e19f  lea     rcx, [rbp+var_30]
0x18000e1a3  mov     rax, [rbx+30h]
0x18000e1a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1ac  mov     rax, [rbp+var_30]
0x18000e1b0  lea     rcx, [rbp+var_30]
0x18000e1b4  mov     rax, [rax+48h]
0x18000e1b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1bd  test    al, al
0x18000e1bf  jz      short loc_18000E1DA
0x18000e1c1  lea     rax, aFailedToAlloca_9; "Failed to allocate operation"
0x18000e1c8  mov     [rsp+70h+var_48], rax
0x18000e1cd  mov     dword ptr [rsp+70h+var_50], 9CEh
  ... truncated ...
```
