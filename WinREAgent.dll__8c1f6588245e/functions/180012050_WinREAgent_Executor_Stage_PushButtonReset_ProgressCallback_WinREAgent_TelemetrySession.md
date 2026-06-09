# WinREAgent::Executor::Stage(PushButtonReset::ProgressCallback *,WinREAgent::TelemetrySession *)

- ea: `0x180012050`
- end: `0x180012773`
- name: `?Stage@Executor@WinREAgent@@QEAAJPEAUProgressCallback@PushButtonReset@@PEAVTelemetrySession@2@@Z`
- size: `1827`
- prototype: `__int64 __fastcall(WinREAgent::Executor *__hidden this, struct PushButtonReset::ProgressCallback *, struct WinREAgent::TelemetrySession *)`
- caller_count: `2`
- callee_count: `27`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000dcc8`
- `0x18001d6c0`

## callees

- `0x180004af8`
- `0x18000509c`
- `0x180005c70`
- `0x1800068f0`
- `0x180009c7c`
- `0x18000d92c`
- `0x18000ea90`
- `0x180012050`
- `0x180014ca8`
- `0x180014ce0`
- `0x180014d10`
- `0x180014d68`
- `0x18001f6e8`
- `0x180028ae8`
- `0x180028b40`
- `0x180028b60`
- `0x180028dd4`
- `0x180029cb8`
- `0x18002dee0`
- `0x18002e538`
- `0x18002e624`
- `0x18002e720`
- `0x18003207c`
- `0x18003717c`
- `0x180037344`
- `0x18006c690`
- `0x18006f010`

## string_xrefs

- `0x1800120a3`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18001214f`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x1800121d1`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x1800122e1`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180012376`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18001253f`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180012616`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18001265a`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18001271f`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18001208f`: `Cannot execute this API because Stage() was already called`
- `0x1800120aa`: `WinREAgent::Executor::Stage`
- `0x180012156`: `WinREAgent::Executor::Stage`
- `0x1800121d8`: `WinREAgent::Executor::Stage`
- `0x1800122e8`: `WinREAgent::Executor::Stage`
- `0x18001237d`: `WinREAgent::Executor::Stage`
- `0x180012546`: `WinREAgent::Executor::Stage`
- `0x18001261d`: `WinREAgent::Executor::Stage`
- `0x180012661`: `WinREAgent::Executor::Stage`
- `0x180012726`: `WinREAgent::Executor::Stage`
- `0x1800122cd`: `Have already executed [%u] operations in stage`
- `0x180012680`: `Update WinRE version: [%s]`
- `0x1800126b6`: `Stage completes, schedule Commit execution`
- `0x1800126d5`: `Failed to schedule Commit`
- `0x1800126ee`: `Check whether can execute Commit`
- `0x18001270b`: `Cannot Commit WinRE servicing`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WinREAgent::Executor::Stage(
        WinREAgent::Executor *this,
        struct PushButtonReset::ProgressCallback *a2,
        struct WinREAgent::TelemetrySession *a3)
{
  __int64 v7; // r8
  __int64 v8; // rax
  int v9; // ebx
  int WinREVersion; // eax
  unsigned __int16 *v11; // rbx
  __int64 v12; // r14
  _QWORD *v13; // r15
  __int64 v14; // rbx
  __int64 v15; // rcx
  __int64 v16; // r8
  unsigned __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // r14
  WinREAgent::Operation *v20; // r15
  int v21; // eax
  int v22; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  unsigned __int16 *v25; // rbx
  unsigned __int16 *v26; // [rsp+40h] [rbp-59h] BYREF
  __int64 v27; // [rsp+48h] [rbp-51h] BYREF
  _QWORD v28[2]; // [rsp+50h] [rbp-49h] BYREF
  __int128 v29; // [rsp+60h] [rbp-39h] BYREF
  __int64 v30; // [rsp+70h] [rbp-29h]
  int v31; // [rsp+78h] [rbp-21h]
  __int64 v32; // [rsp+80h] [rbp-19h]
  __int64 v33; // [rsp+88h] [rbp-11h]
  __int64 v34; // [rsp+90h] [rbp-9h]
  _QWORD v35[2]; // [rsp+A0h] [rbp+7h] BYREF

  if ( *((_BYTE *)this + 336) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942485LL,
      "WinREAgent::Executor::Stage",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      1591,
      L"Cannot execute this API because Stage() was already called");
    return 2147942485LL;
  }
  PushButtonReset::Logging::Trace(0, L"Start executing stage operations");
  if ( a3 )
    WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"Phase", L"StageStart");
  v8 = *((_QWORD *)this + 51);
  if ( !v8
    || !*(_QWORD *)(v8 + 448)
    || (PushButtonReset::Logging::Trace(0, L"Stage: Add checkpoint [%u]", 0),
        v9 = WinREAgent::RollbackHelper::SetCheckpoint(*(_QWORD *)(*((_QWORD *)this + 51) + 448LL), 0),
        v9 >= 0) )
  {
    if ( *((_QWORD *)this + 51) )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v26);
      WinREVersion = GetWinREVersion(
                       *((_QWORD *)this + 51) + 120LL,
                       *((_QWORD *)this + 51) + 216LL,
                       *((_QWORD *)this + 51) + 184LL,
                       &v26);
      v9 = WinREVersion;
      if ( WinREVersion < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)WinREVersion,
          "WinREAgent::Executor::Stage",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          1619,
          L"Failed to get version of [%s]",
          *(_QWORD *)(*((_QWORD *)this + 51) + 120LL));
        ATL::CStringData::Release((ATL::CStringData *)(v26 - 12));
        return (unsigned int)v9;
      }
      v11 = v26;
      PushButtonReset::Logging::Trace(0, L"Current WinRE version: [%s]", v26);
      if ( a3 )
        WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"OldWinREVer", v11);
      ATL::CStringData::Release((ATL::CStringData *)(v11 - 12));
    }
    v28[0] = &WinREAgent::OperationProgress::`vftable';
    v28[1] = a2;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v12 = 0;
    if ( *((_QWORD *)this + 5) )
    {
      while ( 1 )
      {
        v13 = *(_QWORD **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                            (char *)this + 32,
                            v12,
                            v7);
        v27 = 0;
        v9 = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v13 + 24LL))(v13, &v27);
        if ( v9 < 0 )
          break;
        v14 = v27;
        ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(&v29, v27);
        v32 += v14;
        if ( (unsigned __int64)++v12 >= *((_QWORD *)this + 5) )
          goto LABEL_18;
      }
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v9,
        "WinREAgent::Executor::Stage",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1639,
        L"Failed to get the weight of operation [%s]",
        v13[5]);
      goto LABEL_59;
    }
LABEL_18:
    if ( *((_DWORD *)this + 38) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147500037LL,
        "WinREAgent::Executor::Stage",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1646,
        L"Have already executed [%u] operations in stage",
        *((_DWORD *)this + 38));
LABEL_58:
      v9 = -2147467259;
      goto LABEL_59;
    }
    McGenEventRegister_EventRegister();
    if ( (Microsoft_Windows_WinREAgentEnableBits & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v15, WINRESERVICE_START, v16, 1, v35);
    McGenEventUnregister_EventUnregister();
    v9 = WinREAgent::OperationProgress::SetOperation((WinREAgent::OperationProgress *)v28, v17);
    if ( v9 >= 0 )
    {
      v19 = 0;
      if ( *((_QWORD *)this + 5) )
      {
        while ( 1 )
        {
          v20 = *(WinREAgent::Operation **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                             (char *)this + 32,
                                             v19,
                                             v18);
          *((_DWORD *)this + 38) = v19 + 1;
          PushButtonReset::Logging::Trace(0, L"Executing operation [%u]: [%s]", (unsigned int)v19, *((_QWORD *)v20 + 5));
          v35[0] = 0;
          v9 = (*(__int64 (__fastcall **)(WinREAgent::Operation *, _QWORD *))(*(_QWORD *)v20 + 24LL))(v20, v35);
          if ( v9 < 0 )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v9,
              "WinREAgent::Executor::Stage",
              "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
              1667,
              L"Failed to get the weight of operation [%s]",
              *((_QWORD *)v20 + 5));
            goto LABEL_59;
          }
          if ( a3 )
            WinREAgent::TelemetrySession::TraceOperationExecuteStarted(a3, v19, (char *)v20 + 72, v35[0]);
          v21 = WinREAgent::Operation::Execute(
                  v20,
                  *((const struct WinREAgent::ExecutionContext **)this + 51),
                  (struct PushButtonReset::ProgressCallback *)v28,
                  a3);
          v9 = v21;
          if ( v21 == -2147023673 )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              2147943623LL,
              "WinREAgent::Executor::Stage",
              "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
              1677,
              L"Operation execution cancelled by caller");
            goto LABEL_49;
          }
          if ( v21 < 0 )
            break;
          PushButtonReset::Logging::Trace(0, L"The operation executed successfully");
          if ( a3 )
            WinREAgent::TelemetrySession::TraceOperationExecuted(a3, v19, (char *)v20 + 72);
          v9 = WinREAgent::Operation::ApplyEffects(v20, *((struct WinREAgent::ExecutionContext **)this + 51));
          if ( v9 < 0 )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              (unsigned int)v9,
              "WinREAgent::Executor::Stage",
              "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
              1707,
              L"Operation failed to apply effects after operation [%s]",
              *((_QWORD *)v20 + 5));
            goto LABEL_59;
          }
          WinREAgent::OperationProgress::CompletedOperation((WinREAgent::OperationProgress *)v28);
          if ( PushButtonReset::OverallProgress::Cancel((PushButtonReset::OverallProgress *)v28) )
          {
            PushButtonReset::Logging::TraceErr(
              2,
              2147943623LL,
              "WinREAgent::Executor::Stage",
              "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
              1713,
              L"Execution cancelled by caller");
LABEL_49:
            v9 = -2147023673;
            goto LABEL_59;
          }
          if ( (unsigned __int64)++v19 >= *((_QWORD *)this + 5) )
            goto LABEL_36;
        }
        if ( a3 )
          WinREAgent::TelemetrySession::TraceOperationFailed((_DWORD)a3, v19, (_DWORD)v20 + 72, v21, 0);
        McGenEventRegister_EventRegister();
        if ( (Microsoft_Windows_WinREAgentEnableBits & 2) != 0 )
          McTemplateU0dd_EventWriteTransfer(v24, v23, 1, (unsigned int)v9);
        McGenEventUnregister_EventUnregister();
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v9,
          "WinREAgent::Executor::Stage",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          1697,
          L"Failed to execute operation [%s]",
          *((_QWORD *)v20 + 5));
        goto LABEL_59;
      }
LABEL_36:
      PushButtonReset::Logging::Trace(0, L"Successfully executed stage operations");
      *((_BYTE *)this + 336) = 1;
      if ( a3 )
        WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"Phase", L"StageEnd");
      if ( *((_QWORD *)this + 51) )
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&v26);
        v22 = GetWinREVersion(
                *((_QWORD *)this + 51) + 280LL,
                *((_QWORD *)this + 51) + 216LL,
                *((_QWORD *)this + 51) + 184LL,
                &v26);
        v9 = v22;
        if ( v22 < 0 )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)v22,
            "WinREAgent::Executor::Stage",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            1734,
            L"Failed to get version of [%s]",
            *(_QWORD *)(*((_QWORD *)this + 51) + 280LL));
          ATL::CStringData::Release((ATL::CStringData *)(v26 - 12));
          goto LABEL_59;
        }
        v25 = v26;
        PushButtonReset::Logging::Trace(0, L"Update WinRE version: [%s]", v26);
        if ( a3 )
          WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"NewWinREVer", v25);
        ATL::CStringData::Release((ATL::CStringData *)(v25 - 12));
      }
      PushButtonReset::Logging::Trace(0, L"Stage completes, schedule Commit execution");
      v9 = WinREAgent::Executor::ScheduleCommit(this, a3);
      if ( v9 >= 0 )
      {
        PushButtonReset::Logging::Trace(0, L"Check whether can execute Commit");
        if ( !WinREAgent::Executor::CanCommit(this, a3) )
        {
          PushButtonReset::Logging::TraceErr(
            2,
            2147500037LL,
            "WinREAgent::Executor::Stage",
            "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
            1754,
            L"Cannot Commit WinRE servicing");
          goto LABEL_58;
        }
      }
      else
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)v9,
          "WinREAgent::Executor::Stage",
          "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
          1748,
          L"Failed to schedule Commit");
      }
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)v9,
        "WinREAgent::Executor::Stage",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1656,
        L"Failed to set start operation index");
    }
LABEL_59:
    ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>((void **)&v29);
    return (unsigned int)v9;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)v9,
    "WinREAgent::Executor::Stage",
    "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
    1608,
    L"Failed to set checkpoint for Cleanup");
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180012050  mov     [rsp-8+arg_8], rbx
0x180012055  push    rbp
0x180012056  push    rsi
0x180012057  push    rdi
0x180012058  push    r12
0x18001205a  push    r13
0x18001205c  push    r14
0x18001205e  push    r15
0x180012060  lea     rbp, [rsp-27h]
0x180012065  sub     rsp, 0C0h
0x18001206c  mov     rax, cs:__security_cookie
0x180012073  xor     rax, rsp
0x180012076  mov     [rbp+57h+var_40], rax
0x18001207a  mov     rsi, r8
0x18001207d  mov     r14, rdx
0x180012080  mov     rdi, rcx
0x180012083  xor     r12d, r12d
0x180012086  cmp     [rcx+150h], r12b
0x18001208d  jz      short loc_1800120CA
0x18001208f  lea     rax, aCannotExecuteT_2; "Cannot execute this API because Stage()"...
0x180012096  mov     [rsp+0F0h+var_C8], rax
0x18001209b  mov     dword ptr [rsp+0F0h+var_D0], 637h
0x1800120a3  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800120aa  lea     r8, aWinreagentExec_8; "WinREAgent::Executor::Stage"
0x1800120b1  mov     edx, 80070055h
0x1800120b6  lea     ecx, [r12+2]
0x1800120bb  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800120c0  mov     eax, 80070055h
0x1800120c5  jmp     loc_18001274C
0x1800120ca  lea     rdx, aStartExecuting; "Start executing stage operations"
0x1800120d1  xor     ecx, ecx
0x1800120d3  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800120d8  test    rsi, rsi
0x1800120db  jz      short loc_1800120FA
0x1800120dd  lea     r9, aStagestart; "StageStart"
0x1800120e4  lea     r8, aPhase; "Phase"
0x1800120eb  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x1800120f2  mov     rcx, rsi; this
0x1800120f5  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x1800120fa  mov     rax, [rdi+198h]
0x180012101  test    rax, rax
0x180012104  jz      short loc_18001216E
0x180012106  cmp     [rax+1C0h], r12
0x18001210d  jz      short loc_18001216E
0x18001210f  xor     r8d, r8d
0x180012112  lea     rdx, aStageAddCheckp; "Stage: Add checkpoint [%u]"
0x180012119  xor     ecx, ecx
0x18001211b  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180012120  mov     rcx, [rdi+198h]
0x180012127  xor     edx, edx
0x180012129  mov     rcx, [rcx+1C0h]
0x180012130  call    ?SetCheckpoint@RollbackHelper@WinREAgent@@QEAAJW4RollbackCheckpoint@2@@Z; WinREAgent::RollbackHelper::SetCheckpoint(WinREAgent::RollbackCheckpoint)
0x180012135  mov     ebx, eax
0x180012137  test    eax, eax
0x180012139  jns     short loc_18001216E
0x18001213b  lea     rax, aFailedToSetChe_3; "Failed to set checkpoint for Cleanup"
0x180012142  mov     [rsp+0F0h+var_C8], rax
0x180012147  mov     dword ptr [rsp+0F0h+var_D0], 648h
0x18001214f  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180012156  lea     r8, aWinreagentExec_8; "WinREAgent::Executor::Stage"
0x18001215d  mov     edx, ebx
0x18001215f  mov     ecx, 2
0x180012164  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180012169  jmp     loc_18001274A
0x18001216e  cmp     [rdi+198h], r12
0x180012175  jz      loc_18001223B
0x18001217b  lea     rcx, [rbp+57h+var_B0]
0x18001217f  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x180012184  nop
0x180012185  mov     rcx, [rdi+198h]
0x18001218c  lea     r8, [rcx+0B8h]
0x180012193  lea     rdx, [rcx+0D8h]
0x18001219a  add     rcx, 78h ; 'x'
0x18001219e  lea     r9, [rbp+57h+var_B0]
0x1800121a2  call    ?GetWinREVersion@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00PEAV12@@Z; GetWinREVersion(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x1800121a7  mov     ebx, eax
0x1800121a9  test    eax, eax
0x1800121ab  jns     short loc_1800121FE
0x1800121ad  mov     rcx, [rdi+198h]
0x1800121b4  mov     rdx, [rcx+78h]
0x1800121b8  mov     [rsp+0F0h+var_C0], rdx
0x1800121bd  lea     rcx, aFailedToGetVer_0; "Failed to get version of [%s]"
0x1800121c4  mov     [rsp+0F0h+var_C8], rcx
0x1800121c9  mov     dword ptr [rsp+0F0h+var_D0], 653h
0x1800121d1  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800121d8  lea     r8, aWinreagentExec_8; "WinREAgent::Executor::Stage"
0x1800121df  mov     edx, eax
0x1800121e1  mov     ecx, 2
0x1800121e6  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800121eb  nop
0x1800121ec  mov     rcx, [rbp+57h+var_B0]
0x1800121f0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800121f4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800121f9  jmp     loc_18001274A
0x1800121fe  mov     rbx, [rbp+57h+var_B0]
0x180012202  mov     r8, rbx
0x180012205  lea     rdx, aCurrentWinreVe; "Current WinRE version: [%s]"
0x18001220c  xor     ecx, ecx
0x18001220e  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180012213  test    rsi, rsi
0x180012216  jz      short loc_180012232
0x180012218  mov     r9, rbx; unsigned __int16 *
0x18001221b  lea     r8, aOldwinrever; "OldWinREVer"
0x180012222  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x180012229  mov     rcx, rsi; this
0x18001222c  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x180012231  nop
0x180012232  lea     rcx, [rbx-18h]; this
0x180012236  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001223b  lea     rax, ??_7OperationProgress@WinREAgent@@6B@; const WinREAgent::OperationProgress::`vftable'
0x180012242  mov     [rbp+57h+var_A0], rax
0x180012246  mov     [rbp+57h+var_98], r14
0x18001224a  xorps   xmm0, xmm0
0x18001224d  movdqa  [rbp+57h+var_90], xmm0
0x180012252  mov     [rbp+57h+var_80], r12
0x180012256  mov     [rbp+57h+var_78], r12d
0x18001225a  mov     [rbp+57h+var_70], r12
0x18001225e  mov     [rbp+57h+var_68], r12
0x180012262  mov     [rbp+57h+var_60], r12
0x180012266  mov     r14, r12
0x180012269  cmp     [rdi+28h], r12
0x18001226d  jbe     short loc_1800122BF
0x18001226f  mov     rdx, r14
0x180012272  lea     rcx, [rdi+20h]
0x180012276  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18001227b  mov     r15, [rax]
0x18001227e  mov     [rbp+57h+var_A8], 0
0x180012286  mov     rax, [r15]
0x180012289  lea     rdx, [rbp+57h+var_A8]
0x18001228d  mov     rcx, r15
0x180012290  mov     rax, [rax+18h]
0x180012294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012299  mov     ebx, eax
0x18001229b  test    eax, eax
0x18001229d  js      short loc_180012303
0x18001229f  mov     rbx, [rbp+57h+var_A8]
0x1800122a3  mov     rdx, rbx
0x1800122a6  lea     rcx, [rbp+57h+var_90]
0x1800122aa  call    ?Add@?$CAtlArray@_JV?$CElementTraits@_J@ATL@@@ATL@@QEAA_K_J@Z; ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(__int64)
0x1800122af  add     [rbp+57h+var_70], rbx
0x1800122b3  inc     r14
0x1800122b6  cmp     r14, [rdi+28h]
0x1800122ba  jb      short loc_18001226F
0x1800122bc  xor     r12d, r12d
0x1800122bf  mov     eax, [rdi+98h]
0x1800122c5  test    eax, eax
0x1800122c7  jz      short loc_180012325
0x1800122c9  mov     dword ptr [rsp+0F0h+var_C0], eax
0x1800122cd  lea     rax, aHaveAlreadyExe_0; "Have already executed [%u] operations i"...
0x1800122d4  mov     [rsp+0F0h+var_C8], rax
0x1800122d9  mov     dword ptr [rsp+0F0h+var_D0], 66Eh
0x1800122e1  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800122e8  lea     r8, aWinreagentExec_8; "WinREAgent::Executor::Stage"
0x1800122ef  mov     edx, 80004005h
0x1800122f4  mov     ecx, 2
0x1800122f9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800122fe  jmp     loc_18001273C
0x180012303  mov     rax, [r15+28h]
0x180012307  mov     [rsp+0F0h+var_C0], rax
0x18001230c  lea     rax, aFailedToGetThe_0; "Failed to get the weight of operation ["...
0x180012313  mov     [rsp+0F0h+var_C8], rax
0x180012318  mov     dword ptr [rsp+0F0h+var_D0], 667h
0x180012320  jmp     loc_18001265A
0x180012325  call    McGenEventRegister_EventRegister
0x18001232a  test    cs:Microsoft_Windows_WinREAgentEnableBits, 1
0x180012331  jz      short loc_18001234E
0x180012333  lea     rax, [rbp+57h+var_50]
0x180012337  mov     [rsp+0F0h+var_D0], rax
0x18001233c  mov     r9d, 1
0x180012342  lea     rdx, WINRESERVICE_START
0x180012349  call    McGenEventWrite_EventWriteTransfer
0x18001234e  call    McGenEventUnregister_EventUnregister
0x180012353  lea     rcx, [rbp+57h+var_A0]; this
0x180012357  call    ?SetOperation@OperationProgress@WinREAgent@@QEAAJ_K@Z; WinREAgent::OperationProgress::SetOperation(unsigned __int64)
0x18001235c  mov     ebx, eax
0x18001235e  test    eax, eax
0x180012360  jns     short loc_180012395
0x180012362  lea     rax, aFailedToSetSta; "Failed to set start operation index"
0x180012369  mov     [rsp+0F0h+var_C8], rax
0x18001236e  mov     dword ptr [rsp+0F0h+var_D0], 678h
0x180012376  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001237d  lea     r8, aWinreagentExec_8; "WinREAgent::Executor::Stage"
0x180012384  mov     edx, ebx
0x180012386  mov     ecx, 2
0x18001238b  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180012390  jmp     loc_180012741
0x180012395  mov     r14, r12
0x180012398  cmp     [rdi+28h], r12
0x18001239c  jbe     loc_18001249B
0x1800123a2  mov     rdx, r14
0x1800123a5  lea     rcx, [rdi+20h]
0x1800123a9  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x1800123ae  mov     r15, [rax]
0x1800123b1  lea     eax, [r14+1]
0x1800123b5  mov     [rdi+98h], eax
0x1800123bb  mov     r9, [r15+28h]
0x1800123bf  mov     r8d, r14d
0x1800123c2  lea     rdx, aExecutingOpera; "Executing operation [%u]: [%s]"
0x1800123c9  xor     ecx, ecx
0x1800123cb  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800123d0  mov     [rbp+57h+var_50], r12
0x1800123d4  mov     rax, [r15]
0x1800123d7  lea     rdx, [rbp+57h+var_50]
0x1800123db  mov     rcx, r15
0x1800123de  mov     rax, [rax+18h]
0x1800123e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123e7  mov     ebx, eax
0x1800123e9  test    eax, eax
0x1800123eb  js      loc_18001263D
0x1800123f1  lea     r12, [r15+48h]
0x1800123f5  test    rsi, rsi
0x1800123f8  jz      short loc_18001240C
0x1800123fa  mov     r9, [rbp+57h+var_50]
0x1800123fe  mov     r8, r12
0x180012401  mov     rdx, r14
0x180012404  mov     rcx, rsi
0x180012407  call    ?TraceOperationExecuteStarted@TelemetrySession@WinREAgent@@QEBAX_KAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WinREAgent::TelemetrySession::TraceOperationExecuteStarted(unsigned __int64,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64)
0x18001240c  mov     r9, rsi; struct WinREAgent::TelemetrySession *
0x18001240f  lea     r8, [rbp+57h+var_A0]; struct PushButtonReset::ProgressCallback *
0x180012413  mov     rdx, [rdi+198h]; struct WinREAgent::ExecutionContext *
0x18001241a  mov     rcx, r15; this
0x18001241d  call    ?Execute@Operation@WinREAgent@@QEAAJPEBVExecutionContext@2@PEAUProgressCallback@PushButtonReset@@PEAVTelemetrySession@2@@Z; WinREAgent::Operation::Execute(WinREAgent::ExecutionContext const *,PushButtonReset::ProgressCallback *,WinREAgent::TelemetrySession *)
0x180012422  mov     ebx, eax
0x180012424  cmp     eax, 800704C7h
0x180012429  jz      loc_180012602
0x18001242f  test    eax, eax
0x180012431  js      loc_1800125A7
0x180012437  lea     rdx, aTheOperationEx; "The operation executed successfully"
0x18001243e  xor     ecx, ecx
0x180012440  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x180012445  test    rsi, rsi
0x180012448  jz      short loc_180012458
0x18001244a  mov     r8, r12
0x18001244d  mov     rdx, r14
0x180012450  mov     rcx, rsi
0x180012453  call    ?TraceOperationExecuted@TelemetrySession@WinREAgent@@QEBAX_KAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::TelemetrySession::TraceOperationExecuted(unsigned __int64,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180012458  mov     rdx, [rdi+198h]; struct WinREAgent::ExecutionContext *
0x18001245f  mov     rcx, r15; this
0x180012462  call    ?ApplyEffects@Operation@WinREAgent@@QEAAJPEAVExecutionContext@2@@Z; WinREAgent::Operation::ApplyEffects(WinREAgent::ExecutionContext *)
0x180012467  mov     ebx, eax
0x180012469  xor     r12d, r12d
0x18001246c  test    eax, eax
0x18001246e  js      loc_180012585
0x180012474  lea     rcx, [rbp+57h+var_A0]; this
0x180012478  call    ?CompletedOperation@OperationProgress@WinREAgent@@QEAAXXZ; WinREAgent::OperationProgress::CompletedOperation(void)
0x18001247d  lea     rcx, [rbp+57h+var_A0]; this
0x180012481  call    ?Cancel@OverallProgress@PushButtonReset@@UEAA_NXZ; PushButtonReset::OverallProgress::Cancel(void)
0x180012486  test    al, al
0x180012488  jnz     loc_18001256C
0x18001248e  inc     r14
0x180012491  cmp     r14, [rdi+28h]
0x180012495  jb      loc_1800123A2
0x18001249b  lea     rdx, aSuccessfullyEx; "Successfully executed stage operations"
0x1800124a2  xor     ecx, ecx
0x1800124a4  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800124a9  mov     byte ptr [rdi+150h], 1
0x1800124b0  test    rsi, rsi
0x1800124b3  jz      short loc_1800124D2
0x1800124b5  lea     r9, aStageend; "StageEnd"
0x1800124bc  lea     r8, aPhase; "Phase"
0x1800124c3  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x1800124ca  mov     rcx, rsi; this
0x1800124cd  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x1800124d2  cmp     [rdi+198h], r12
0x1800124d9  jz      loc_1800126B6
0x1800124df  lea     rcx, [rbp+57h+var_B0]
0x1800124e3  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800124e8  nop
0x1800124e9  mov     rcx, [rdi+198h]
0x1800124f0  lea     r8, [rcx+0B8h]
0x1800124f7  lea     rdx, [rcx+0D8h]
0x1800124fe  add     rcx, 118h
0x180012505  lea     r9, [rbp+57h+var_B0]
0x180012509  call    ?GetWinREVersion@@YAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00PEAV12@@Z; GetWinREVersion(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18001250e  mov     ebx, eax
0x180012510  test    eax, eax
0x180012512  jns     loc_180012679
0x180012518  mov     rcx, [rdi+198h]
0x18001251f  mov     rdx, [rcx+118h]
0x180012526  mov     [rsp+0F0h+var_C0], rdx
0x18001252b  lea     rcx, aFailedToGetVer_0; "Failed to get version of [%s]"
0x180012532  mov     [rsp+0F0h+var_C8], rcx
0x180012537  mov     dword ptr [rsp+0F0h+var_D0], 6C6h
0x18001253f  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180012546  lea     r8, aWinreagentExec_8; "WinREAgent::Executor::Stage"
0x18001254d  mov     edx, eax
0x18001254f  mov     ecx, 2
0x180012554  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180012559  nop
0x18001255a  mov     rcx, [rbp+57h+var_B0]
0x18001255e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180012562  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180012567  jmp     loc_180012741
0x18001256c  lea     rax, aExecutionCance; "Execution cancelled by caller"
0x180012573  mov     [rsp+0F0h+var_C8], rax
0x180012578  mov     dword ptr [rsp+0F0h+var_D0], 6B1h
0x180012580  jmp     loc_180012616
0x180012585  mov     rax, [r15+28h]
0x180012589  mov     [rsp+0F0h+var_C0], rax
0x18001258e  lea     rax, aOperationFaile; "Operation failed to apply effects after"...
  ... truncated ...
```
