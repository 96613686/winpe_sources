# WinREAgent::RollbackHelper::ExecuteRollback(WinREAgent::ExecutionContext *,WinREAgent::TelemetrySession *)

- ea: `0x18002f978`
- end: `0x18002fe72`
- name: `?ExecuteRollback@RollbackHelper@WinREAgent@@QEAAJPEAVExecutionContext@2@PEAVTelemetrySession@2@@Z`
- size: `1274`
- prototype: `__int64 __fastcall(WinREAgent::RollbackHelper *__hidden this, struct WinREAgent::ExecutionContext *, struct WinREAgent::TelemetrySession *)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000e800`

## callees

- `0x1800049a4`
- `0x18000d92c`
- `0x1800240fc`
- `0x180026320`
- `0x180026ae0`
- `0x180026ddc`
- `0x18002a118`
- `0x18002abac`
- `0x18002c0c8`
- `0x18002e834`
- `0x18002e948`
- `0x18002f7c8`
- `0x18002f978`
- `0x18002fef4`
- `0x1800304b4`
- `0x1800307e0`
- `0x180031810`
- `0x180032480`
- `0x18003717c`
- `0x180037344`

## string_xrefs

- `0x18002fa5d`: `RollbackStart`
- `0x18002fad2`: `RollbackStart`
- `0x18002f9bf`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x18002fc65`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x18002fcc3`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x18002fd1c`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x18002fe3e`: `base\diagnosis\srt\winreagent\lib\rollback\src\rollbackhelper.cpp`
- `0x18002f998`: `RollbackHelper::ExecuteRollback Start`
- `0x18002f9c6`: `WinREAgent::RollbackHelper::ExecuteRollback`
- `0x18002fc6c`: `WinREAgent::RollbackHelper::ExecuteRollback`
- `0x18002fcca`: `WinREAgent::RollbackHelper::ExecuteRollback`
- `0x18002fd23`: `WinREAgent::RollbackHelper::ExecuteRollback`
- `0x18002fe45`: `WinREAgent::RollbackHelper::ExecuteRollback`
- `0x18002f9e4`: `RollbackComplete`
- `0x18002fdc5`: `RollbackComplete`
- `0x18002fa37`: `Rollback has already completed`
- `0x18002fa45`: `RollbackHelper::ExecuteRollback Completed`
- `0x18002fda6`: `RollbackHelper::ExecuteRollback Completed`
- `0x18002fab0`: `Have already start rollback execution`
- `0x18002fb37`: `Failed to Save Rollback starts to rollback info`
- `0x18002fb61`: `Failed to resume execution context from rollback info`
- `0x18002fc51`: `Failed to perform a general cleanup for rollback`
- `0x18002fe2a`: `Failed to Save Rollback Completes to rollback info`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WinREAgent::RollbackHelper::ExecuteRollback(
        WinREAgent::RollbackHelper *this,
        struct WinREAgent::ExecutionContext *a2,
        struct WinREAgent::TelemetrySession *a3)
{
  char HasKey; // bl
  char v8; // bl
  unsigned int v9; // ebx
  __int64 v10; // r14
  __int64 v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rax
  int NewWinREPartition; // eax
  int v15; // eax
  _QWORD v16[2]; // [rsp+40h] [rbp-10h] BYREF
  __int64 v17; // [rsp+98h] [rbp+48h] BYREF
  __int64 v18; // [rsp+A8h] [rbp+58h] BYREF

  PushButtonReset::Logging::Trace(0, L"RollbackHelper::ExecuteRollback Start");
  if ( !a2 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942487LL,
      "WinREAgent::RollbackHelper::ExecuteRollback",
      "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
      693,
      L"executionContext cannot be null");
    return 2147942487LL;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v18,
    (__int64)L"RollbackComplete");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v17,
    (__int64)L"ExecutionInfo");
  HasKey = WinREAgent::RollbackHelper::HasKey(this, &v17, &v18);
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
  if ( HasKey )
  {
    PushButtonReset::Logging::Trace(0, L"Rollback has already completed");
    PushButtonReset::Logging::Trace(0, L"RollbackHelper::ExecuteRollback Completed");
    return 1;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v18,
    (__int64)L"RollbackStart");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v17,
    (__int64)L"ExecutionInfo");
  v8 = WinREAgent::RollbackHelper::HasKey(this, &v17, &v18);
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
  if ( v8 )
    PushButtonReset::Logging::Trace(1, L"Have already start rollback execution");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)v16,
    (__int64)L"Yes");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v18,
    (__int64)L"RollbackStart");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v17,
    (__int64)L"ExecutionInfo");
  v9 = WinREAgent::RollbackHelper::WriteToConfig(this, &v17, &v18, v16);
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v16[0] - 24LL));
  if ( (v9 & 0x80000000) != 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      v9,
      "WinREAgent::RollbackHelper::ExecuteRollback",
      "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
      712,
      L"Failed to Save Rollback starts to rollback info");
    return v9;
  }
  v9 = WinREAgent::RollbackHelper::ResumeExecutionContext(this, a2);
  if ( (v9 & 0x80000000) != 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      v9,
      "WinREAgent::RollbackHelper::ExecuteRollback",
      "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
      720,
      L"Failed to resume execution context from rollback info");
    return v9;
  }
  v10 = *((_QWORD *)this + 3);
  if ( !v10 )
  {
LABEL_42:
    PushButtonReset::Logging::Trace(0, L"RollbackHelper::ExecuteRollback Completed");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)v16,
      (__int64)L"Yes");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v18,
      (__int64)L"RollbackComplete");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v17,
      (__int64)L"ExecutionInfo");
    v9 = WinREAgent::RollbackHelper::WriteToConfig(this, &v17, &v18, v16);
    ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v18 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v16[0] - 24LL));
    if ( (v9 & 0x80000000) != 0 )
      PushButtonReset::Logging::TraceErr(
        2,
        v9,
        "WinREAgent::RollbackHelper::ExecuteRollback",
        "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
        811,
        L"Failed to Save Rollback Completes to rollback info");
    return v9;
  }
  while ( 1 )
  {
    v11 = *(unsigned int *)ATL::CAtlArray<enum WinREAgent::RollbackCheckpoint,ATL::CElementTraits<enum WinREAgent::RollbackCheckpoint>>::GetAt(
                             (char *)this + 16,
                             (unsigned int)(v10 - 1));
    v13 = WinREAgent::RollbackHelper::CheckpointToString(v12, v11);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v17,
      v13);
    PushButtonReset::Logging::Trace(
      0,
      L"Execute checkpoint [%u] : [%u] [%s]",
      (unsigned int)(v10 - 1),
      (unsigned int)v11,
      v17);
    if ( a3 )
      WinREAgent::TelemetrySession::TraceRollbackCheckpointStarted(a3, v10, (unsigned int)v11, &v17);
    if ( (int)v11 > 5 )
      break;
    switch ( (_DWORD)v11 )
    {
      case 5:
        goto LABEL_39;
      case 0:
        v15 = WinREAgent::RollbackHelper::GeneralCleanup(this);
        if ( v15 < 0 )
          PushButtonReset::Logging::TraceErr(
            1,
            (unsigned int)v15,
            "WinREAgent::RollbackHelper::ExecuteRollback",
            "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
            743,
            L"Failed to perform a general cleanup for rollback");
        goto LABEL_39;
      case 1:
        NewWinREPartition = WinREAgent::DeleteOldWinREHash::Undo(a2);
        break;
      case 2:
        NewWinREPartition = WinREAgent::AddNewWinREHash::Undo(a2);
        break;
      case 3:
        NewWinREPartition = WinREAgent::SwapWinREs::Undo(a2);
        break;
      case 4:
        NewWinREPartition = WinREAgent::UpdateInPartition::Undo(a2);
        break;
      default:
        goto LABEL_31;
    }
LABEL_38:
    v9 = NewWinREPartition;
    if ( NewWinREPartition < 0 )
      goto LABEL_32;
LABEL_39:
    if ( a3 )
      WinREAgent::TelemetrySession::TraceRollbackCheckpointFinished((_DWORD)a3, v10, v11, (unsigned int)&v17, 0);
    ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
    if ( !--v10 )
      goto LABEL_42;
  }
  switch ( (_DWORD)v11 )
  {
    case 6:
      NewWinREPartition = WinREAgent::Repartition::UndoShrink(a2);
      goto LABEL_38;
    case 7:
      NewWinREPartition = WinREAgent::Repartition::UndoDeleteWinREPartition(a2);
      goto LABEL_38;
    case 8:
      NewWinREPartition = WinREAgent::Repartition::UndoCreateNewWinREPartition(a2);
      goto LABEL_38;
    case 9:
      goto LABEL_39;
  }
LABEL_31:
  v9 = -2147467259;
  PushButtonReset::Logging::TraceErr(
    2,
    2147500037LL,
    "WinREAgent::RollbackHelper::ExecuteRollback",
    "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
    784,
    L"Get unexpected checkpoint");
LABEL_32:
  if ( a3 )
    WinREAgent::TelemetrySession::TraceRollbackCheckpointFinished((_DWORD)a3, v10, v11, (unsigned int)&v17, v9);
  PushButtonReset::Logging::TraceErr(
    2,
    v9,
    "WinREAgent::RollbackHelper::ExecuteRollback",
    "base\\diagnosis\\srt\\winreagent\\lib\\rollback\\src\\rollbackhelper.cpp",
    795,
    L"Failed to execute checkpoint [%d] [%s]",
    v11,
    v17);
  ATL::CStringData::Release((ATL::CStringData *)(v17 - 24));
  return v9;
}

```

## disassembly

```asm
0x18002f978  mov     [rsp-38h+arg_0], rbx
0x18002f97d  push    rbp
0x18002f97e  push    rsi
0x18002f97f  push    rdi
0x18002f980  push    r12
0x18002f982  push    r13
0x18002f984  push    r14
0x18002f986  push    r15
0x18002f988  mov     rbp, rsp
0x18002f98b  sub     rsp, 50h
0x18002f98f  mov     r12, r8
0x18002f992  mov     rsi, rdx
0x18002f995  mov     r15, rcx
0x18002f998  lea     rdx, aRollbackhelper_1; "RollbackHelper::ExecuteRollback Start"
0x18002f99f  xor     ecx, ecx
0x18002f9a1  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002f9a6  test    rsi, rsi
0x18002f9a9  jnz     short loc_18002F9E4
0x18002f9ab  lea     rax, aExecutionconte_0; "executionContext cannot be null"
0x18002f9b2  mov     [rsp+50h+var_28], rax
0x18002f9b7  mov     dword ptr [rsp+50h+var_30], 2B5h
0x18002f9bf  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002f9c6  lea     r8, aWinreagentRoll_1; "WinREAgent::RollbackHelper::ExecuteRoll"...
0x18002f9cd  mov     edx, 80070057h
0x18002f9d2  lea     ecx, [rsi+2]
0x18002f9d5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002f9da  mov     eax, 80070057h
0x18002f9df  jmp     loc_18002FE5A
0x18002f9e4  lea     rdx, aRollbackcomple; "RollbackComplete"
0x18002f9eb  lea     rcx, [rbp+arg_18]
0x18002f9ef  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002f9f4  nop
0x18002f9f5  lea     rdx, aExecutioninfo; "ExecutionInfo"
0x18002f9fc  lea     rcx, [rbp+arg_8]
0x18002fa00  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002fa05  nop
0x18002fa06  lea     r8, [rbp+arg_18]
0x18002fa0a  lea     rdx, [rbp+arg_8]
0x18002fa0e  mov     rcx, r15
0x18002fa11  call    ?HasKey@RollbackHelper@WinREAgent@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WinREAgent::RollbackHelper::HasKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002fa16  mov     bl, al
0x18002fa18  mov     rcx, [rbp+arg_8]
0x18002fa1c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002fa20  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002fa25  nop
0x18002fa26  mov     rcx, [rbp+arg_18]
0x18002fa2a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002fa2e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002fa33  test    bl, bl
0x18002fa35  jz      short loc_18002FA5D
0x18002fa37  lea     rdx, aRollbackHasAlr; "Rollback has already completed"
0x18002fa3e  xor     ecx, ecx
0x18002fa40  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002fa45  lea     rdx, aRollbackhelper_8; "RollbackHelper::ExecuteRollback Complet"...
0x18002fa4c  xor     ecx, ecx
0x18002fa4e  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002fa53  mov     eax, 1
0x18002fa58  jmp     loc_18002FE5A
0x18002fa5d  lea     rdx, aRollbackstart; "RollbackStart"
0x18002fa64  lea     rcx, [rbp+arg_18]
0x18002fa68  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002fa6d  nop
0x18002fa6e  lea     rdx, aExecutioninfo; "ExecutionInfo"
0x18002fa75  lea     rcx, [rbp+arg_8]
0x18002fa79  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002fa7e  nop
0x18002fa7f  lea     r8, [rbp+arg_18]
0x18002fa83  lea     rdx, [rbp+arg_8]
0x18002fa87  mov     rcx, r15
0x18002fa8a  call    ?HasKey@RollbackHelper@WinREAgent@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WinREAgent::RollbackHelper::HasKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002fa8f  mov     bl, al
0x18002fa91  mov     rcx, [rbp+arg_8]
0x18002fa95  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002fa99  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002fa9e  nop
0x18002fa9f  mov     rcx, [rbp+arg_18]
0x18002faa3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002faa7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002faac  test    bl, bl
0x18002faae  jz      short loc_18002FAC1
0x18002fab0  lea     rdx, aHaveAlreadySta; "Have already start rollback execution"
0x18002fab7  mov     ecx, 1
0x18002fabc  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002fac1  lea     rdx, aYes; "Yes"
0x18002fac8  lea     rcx, [rbp+var_10]
0x18002facc  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002fad1  nop
0x18002fad2  lea     rdx, aRollbackstart; "RollbackStart"
0x18002fad9  lea     rcx, [rbp+arg_18]
0x18002fadd  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002fae2  nop
0x18002fae3  lea     rdx, aExecutioninfo; "ExecutionInfo"
0x18002faea  lea     rcx, [rbp+arg_8]
0x18002faee  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002faf3  nop
0x18002faf4  lea     r9, [rbp+var_10]
0x18002faf8  lea     r8, [rbp+arg_18]
0x18002fafc  lea     rdx, [rbp+arg_8]
0x18002fb00  mov     rcx, r15
0x18002fb03  call    ?WriteToConfig@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00@Z; WinREAgent::RollbackHelper::WriteToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002fb08  mov     ebx, eax
0x18002fb0a  mov     rcx, [rbp+arg_8]
0x18002fb0e  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002fb12  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002fb17  nop
0x18002fb18  mov     rcx, [rbp+arg_18]
0x18002fb1c  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002fb20  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002fb25  nop
0x18002fb26  mov     rcx, [rbp+var_10]
0x18002fb2a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002fb2e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002fb33  test    ebx, ebx
0x18002fb35  jns     short loc_18002FB50
0x18002fb37  lea     rax, aFailedToSaveRo_0; "Failed to Save Rollback starts to rollb"...
0x18002fb3e  mov     [rsp+50h+var_28], rax
0x18002fb43  mov     dword ptr [rsp+50h+var_30], 2C8h
0x18002fb4b  jmp     loc_18002FE3E
0x18002fb50  mov     rdx, rsi; struct WinREAgent::ExecutionContext *
0x18002fb53  mov     rcx, r15; this
0x18002fb56  call    ?ResumeExecutionContext@RollbackHelper@WinREAgent@@AEAAJPEAVExecutionContext@2@@Z; WinREAgent::RollbackHelper::ResumeExecutionContext(WinREAgent::ExecutionContext *)
0x18002fb5b  mov     ebx, eax
0x18002fb5d  test    eax, eax
0x18002fb5f  jns     short loc_18002FB7A
0x18002fb61  lea     rax, aFailedToResume; "Failed to resume execution context from"...
0x18002fb68  mov     [rsp+50h+var_28], rax
0x18002fb6d  mov     dword ptr [rsp+50h+var_30], 2D0h
0x18002fb75  jmp     loc_18002FE3E
0x18002fb7a  mov     r14, [r15+18h]
0x18002fb7e  test    r14, r14
0x18002fb81  jz      loc_18002FDA6
0x18002fb87  lea     ebx, [r14-1]
0x18002fb8b  mov     edx, ebx
0x18002fb8d  lea     rcx, [r15+10h]
0x18002fb91  call    ?GetAt@?$CAtlArray@W4RollbackCheckpoint@WinREAgent@@V?$CElementTraits@W4RollbackCheckpoint@WinREAgent@@@ATL@@@ATL@@QEAAAEAW4RollbackCheckpoint@WinREAgent@@_K@Z; ATL::CAtlArray<WinREAgent::RollbackCheckpoint,ATL::CElementTraits<WinREAgent::RollbackCheckpoint>>::GetAt(unsigned __int64)
0x18002fb96  mov     edi, [rax]
0x18002fb98  mov     edx, edi
0x18002fb9a  call    ?CheckpointToString@RollbackHelper@WinREAgent@@QEAAPEBGW4RollbackCheckpoint@2@@Z; WinREAgent::RollbackHelper::CheckpointToString(WinREAgent::RollbackCheckpoint)
0x18002fb9f  mov     rdx, rax
0x18002fba2  lea     rcx, [rbp+arg_8]
0x18002fba6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002fbab  nop
0x18002fbac  mov     rax, [rbp+arg_8]
0x18002fbb0  mov     [rsp+50h+var_30], rax
0x18002fbb5  mov     r9d, edi
0x18002fbb8  mov     r8d, ebx
0x18002fbbb  lea     rdx, aExecuteCheckpo; "Execute checkpoint [%u] : [%u] [%s]"
0x18002fbc2  xor     ecx, ecx
0x18002fbc4  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002fbc9  test    r12, r12
0x18002fbcc  jz      short loc_18002FBE0
0x18002fbce  lea     r9, [rbp+arg_8]
0x18002fbd2  mov     r8d, edi
0x18002fbd5  mov     rdx, r14
0x18002fbd8  mov     rcx, r12
0x18002fbdb  call    ?TraceRollbackCheckpointStarted@TelemetrySession@WinREAgent@@QEBAX_KKAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::TelemetrySession::TraceRollbackCheckpointStarted(unsigned __int64,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002fbe0  cmp     edi, 5
0x18002fbe3  jg      loc_18002FC84
0x18002fbe9  jz      loc_18002FD6F
0x18002fbef  mov     ecx, edi
0x18002fbf1  test    edi, edi
0x18002fbf3  jz      short loc_18002FC41
0x18002fbf5  sub     ecx, 1
0x18002fbf8  jz      short loc_18002FC34
0x18002fbfa  sub     ecx, 1
0x18002fbfd  jz      short loc_18002FC27
0x18002fbff  sub     ecx, 1
0x18002fc02  jz      short loc_18002FC1A
0x18002fc04  cmp     ecx, 1
0x18002fc07  jnz     loc_18002FCAA
0x18002fc0d  mov     rcx, rsi; struct WinREAgent::ExecutionContext *
0x18002fc10  call    ?Undo@UpdateInPartition@WinREAgent@@SAJPEAVExecutionContext@2@@Z; WinREAgent::UpdateInPartition::Undo(WinREAgent::ExecutionContext *)
0x18002fc15  jmp     loc_18002FD65
0x18002fc1a  mov     rcx, rsi; struct WinREAgent::ExecutionContext *
0x18002fc1d  call    ?Undo@SwapWinREs@WinREAgent@@SAJPEAVExecutionContext@2@@Z; WinREAgent::SwapWinREs::Undo(WinREAgent::ExecutionContext *)
0x18002fc22  jmp     loc_18002FD65
0x18002fc27  mov     rcx, rsi; struct WinREAgent::ExecutionContext *
0x18002fc2a  call    ?Undo@AddNewWinREHash@WinREAgent@@SAJPEAVExecutionContext@2@@Z; WinREAgent::AddNewWinREHash::Undo(WinREAgent::ExecutionContext *)
0x18002fc2f  jmp     loc_18002FD65
0x18002fc34  mov     rcx, rsi; struct WinREAgent::ExecutionContext *
0x18002fc37  call    ?Undo@DeleteOldWinREHash@WinREAgent@@SAJPEAVExecutionContext@2@@Z; WinREAgent::DeleteOldWinREHash::Undo(WinREAgent::ExecutionContext *)
0x18002fc3c  jmp     loc_18002FD65
0x18002fc41  mov     rcx, r15; this
0x18002fc44  call    ?GeneralCleanup@RollbackHelper@WinREAgent@@AEAAJXZ; WinREAgent::RollbackHelper::GeneralCleanup(void)
0x18002fc49  test    eax, eax
0x18002fc4b  jns     loc_18002FD6F
0x18002fc51  lea     rcx, aFailedToPerfor; "Failed to perform a general cleanup for"...
0x18002fc58  mov     [rsp+50h+var_28], rcx
0x18002fc5d  mov     dword ptr [rsp+50h+var_30], 2E7h
0x18002fc65  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002fc6c  lea     r8, aWinreagentRoll_1; "WinREAgent::RollbackHelper::ExecuteRoll"...
0x18002fc73  mov     edx, eax
0x18002fc75  mov     ecx, 1
0x18002fc7a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002fc7f  jmp     loc_18002FD6F
0x18002fc84  mov     ecx, edi
0x18002fc86  sub     ecx, 6
0x18002fc89  jz      loc_18002FD5D
0x18002fc8f  sub     ecx, 1
0x18002fc92  jz      loc_18002FD53
0x18002fc98  sub     ecx, 1
0x18002fc9b  jz      loc_18002FD49
0x18002fca1  cmp     ecx, 1
0x18002fca4  jz      loc_18002FD6F
0x18002fcaa  mov     ebx, 80004005h
0x18002fcaf  lea     rax, aGetUnexpectedC; "Get unexpected checkpoint"
0x18002fcb6  mov     [rsp+50h+var_28], rax
0x18002fcbb  mov     dword ptr [rsp+50h+var_30], 310h
0x18002fcc3  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002fcca  lea     r8, aWinreagentRoll_1; "WinREAgent::RollbackHelper::ExecuteRoll"...
0x18002fcd1  mov     edx, 80004005h
0x18002fcd6  mov     ecx, 2
0x18002fcdb  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002fce0  test    r12, r12
0x18002fce3  jz      short loc_18002FCFB
0x18002fce5  mov     dword ptr [rsp+50h+var_30], ebx
0x18002fce9  lea     r9, [rbp+arg_8]
0x18002fced  mov     r8d, edi
0x18002fcf0  mov     rdx, r14
0x18002fcf3  mov     rcx, r12
0x18002fcf6  call    ?TraceRollbackCheckpointFinished@TelemetrySession@WinREAgent@@AEBAX_KKAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceRollbackCheckpointFinished(unsigned __int64,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18002fcfb  mov     rax, [rbp+arg_8]
0x18002fcff  mov     [rsp+50h+var_18], rax
0x18002fd04  mov     [rsp+50h+var_20], edi
0x18002fd08  lea     rax, aFailedToExecut_2; "Failed to execute checkpoint [%d] [%s]"
0x18002fd0f  mov     [rsp+50h+var_28], rax
0x18002fd14  mov     dword ptr [rsp+50h+var_30], 31Bh
0x18002fd1c  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
0x18002fd23  lea     r8, aWinreagentRoll_1; "WinREAgent::RollbackHelper::ExecuteRoll"...
0x18002fd2a  mov     edx, ebx
0x18002fd2c  mov     ecx, 2
0x18002fd31  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18002fd36  nop
0x18002fd37  mov     rcx, [rbp+arg_8]
0x18002fd3b  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002fd3f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002fd44  jmp     loc_18002FE58
0x18002fd49  mov     rcx, rsi; struct WinREAgent::ExecutionContext *
0x18002fd4c  call    ?UndoCreateNewWinREPartition@Repartition@WinREAgent@@SAJPEAVExecutionContext@2@@Z; WinREAgent::Repartition::UndoCreateNewWinREPartition(WinREAgent::ExecutionContext *)
0x18002fd51  jmp     short loc_18002FD65
0x18002fd53  mov     rcx, rsi; struct WinREAgent::ExecutionContext *
0x18002fd56  call    ?UndoDeleteWinREPartition@Repartition@WinREAgent@@SAJPEAVExecutionContext@2@@Z; WinREAgent::Repartition::UndoDeleteWinREPartition(WinREAgent::ExecutionContext *)
0x18002fd5b  jmp     short loc_18002FD65
0x18002fd5d  mov     rcx, rsi; struct WinREAgent::ExecutionContext *
0x18002fd60  call    ?UndoShrink@Repartition@WinREAgent@@SAJPEAVExecutionContext@2@@Z; WinREAgent::Repartition::UndoShrink(WinREAgent::ExecutionContext *)
0x18002fd65  mov     ebx, eax
0x18002fd67  test    eax, eax
0x18002fd69  js      loc_18002FCE0
0x18002fd6f  test    r12, r12
0x18002fd72  jz      short loc_18002FD8F
0x18002fd74  mov     dword ptr [rsp+50h+var_30], 0
0x18002fd7c  lea     r9, [rbp+arg_8]
0x18002fd80  mov     r8d, edi
0x18002fd83  mov     rdx, r14
0x18002fd86  mov     rcx, r12
0x18002fd89  call    ?TraceRollbackCheckpointFinished@TelemetrySession@WinREAgent@@AEBAX_KKAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@J@Z; WinREAgent::TelemetrySession::TraceRollbackCheckpointFinished(unsigned __int64,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,long)
0x18002fd8e  nop
0x18002fd8f  mov     rcx, [rbp+arg_8]
0x18002fd93  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002fd97  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002fd9c  sub     r14, 1
0x18002fda0  jnz     loc_18002FB87
0x18002fda6  lea     rdx, aRollbackhelper_8; "RollbackHelper::ExecuteRollback Complet"...
0x18002fdad  xor     ecx, ecx
0x18002fdaf  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18002fdb4  lea     rdx, aYes; "Yes"
0x18002fdbb  lea     rcx, [rbp+var_10]
0x18002fdbf  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002fdc4  nop
0x18002fdc5  lea     rdx, aRollbackcomple; "RollbackComplete"
0x18002fdcc  lea     rcx, [rbp+arg_18]
0x18002fdd0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002fdd5  nop
0x18002fdd6  lea     rdx, aExecutioninfo; "ExecutionInfo"
0x18002fddd  lea     rcx, [rbp+arg_8]
0x18002fde1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18002fde6  nop
0x18002fde7  lea     r9, [rbp+var_10]
0x18002fdeb  lea     r8, [rbp+arg_18]
0x18002fdef  lea     rdx, [rbp+arg_8]
0x18002fdf3  mov     rcx, r15
0x18002fdf6  call    ?WriteToConfig@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00@Z; WinREAgent::RollbackHelper::WriteToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18002fdfb  mov     ebx, eax
0x18002fdfd  mov     rcx, [rbp+arg_8]
0x18002fe01  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002fe05  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002fe0a  nop
0x18002fe0b  mov     rcx, [rbp+arg_18]
0x18002fe0f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002fe13  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002fe18  nop
0x18002fe19  mov     rcx, [rbp+var_10]
0x18002fe1d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18002fe21  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18002fe26  test    ebx, ebx
0x18002fe28  jns     short loc_18002FE58
0x18002fe2a  lea     rax, aFailedToSaveRo; "Failed to Save Rollback Completes to ro"...
0x18002fe31  mov     [rsp+50h+var_28], rax
0x18002fe36  mov     dword ptr [rsp+50h+var_30], 32Bh
0x18002fe3e  lea     r9, aBaseDiagnosisS_4; "base\\diagnosis\\srt\\winreagent\\lib\\"...
  ... truncated ...
```
