# WinREAgent::Executor::Commit(PushButtonReset::ProgressCallback *,WinREAgent::TelemetrySession *)

- ea: `0x180007570`
- end: `0x180007f34`
- name: `?Commit@Executor@WinREAgent@@QEAAJPEAUProgressCallback@PushButtonReset@@PEAVTelemetrySession@2@@Z`
- size: `2500`
- prototype: `int(WinREAgent::Executor *__hidden this, struct PushButtonReset::ProgressCallback *, struct WinREAgent::TelemetrySession *)`
- caller_count: `2`
- callee_count: `31`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18000dcc8`
- `0x180018e90`

## callees

- `0x1800049a4`
- `0x180004af8`
- `0x18000509c`
- `0x180005c70`
- `0x180007570`
- `0x180009c7c`
- `0x18000bd58`
- `0x18000d92c`
- `0x180011ef4`
- `0x180014ca8`
- `0x180014ce0`
- `0x180014d68`
- `0x180014dd8`
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
- `0x18002ef50`
- `0x1800307e0`
- `0x180032480`
- `0x18003717c`
- `0x180037344`
- `0x18004d7a0`
- `0x18004e47c`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetDiskFreeSpaceExW` at `0x180007a1e`
- `KERNEL32!GetDiskFreeSpaceExW` at `0x180007a1e`
- `KERNEL32!GetLastError` at `0x180007a28`
- `KERNEL32!GetLastError` at `0x180007a6a`
- `KERNEL32!GetLastError` at `0x180007a28`
- `KERNEL32!GetLastError` at `0x180007a6a`

## string_xrefs

- `0x1800075b5`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x18000770f`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x1800077ef`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180007913`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180007981`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x1800079d8`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180007a50`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180007ba8`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180007dc8`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180007e3c`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x180007e9c`: `base\diagnosis\srt\winreagent\dll\executor.cpp`
- `0x1800079c4`: `Failed to get current WinRE directory`
- `0x1800075bc`: `WinREAgent::Executor::Commit`
- `0x180007716`: `WinREAgent::Executor::Commit`
- `0x1800077f6`: `WinREAgent::Executor::Commit`
- `0x18000791a`: `WinREAgent::Executor::Commit`
- `0x180007988`: `WinREAgent::Executor::Commit`
- `0x1800079df`: `WinREAgent::Executor::Commit`
- `0x180007a57`: `WinREAgent::Executor::Commit`
- `0x180007baf`: `WinREAgent::Executor::Commit`
- `0x180007dcf`: `WinREAgent::Executor::Commit`
- `0x180007e43`: `WinREAgent::Executor::Commit`
- `0x180007ea3`: `WinREAgent::Executor::Commit`
- `0x1800075dc`: `Start executing commit operations`
- `0x1800075ea`: `CommitStart`
- `0x1800076a5`: `RollbackStart`
- `0x1800076fb`: `Execution has been rollbacked`
- `0x180007766`: `CommitComplete`
- `0x180007cda`: `CommitComplete`
- `0x1800077b5`: `Commit has completed`
- `0x1800077db`: `Have already executed [%u] operations in commit`
- `0x18000786a`: `Have already start commit execution`
- `0x1800078ff`: `Failed to Save Commit starts to rollback info`
- `0x180007bf7`: `Current remediation strategy is to move forward, ignore this error`
- `0x180007c8b`: `Successfully executed commit operations`
- `0x180007c9e`: `CommitEnd`
- `0x180007d3f`: `Failed to Save Commit completes to rollback info`
- `0x180007e28`: `Failed to log WinRE partition status on complete`
- `0x180007e88`: `Failed to get version of installed WinRE`
- `0x180007ed9`: `Installed WinRE version: [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall WinREAgent::Executor::Commit(
        WinREAgent::Executor *this,
        struct PushButtonReset::ProgressCallback *a2,
        struct WinREAgent::TelemetrySession *a3)
{
  __int64 v7; // r8
  unsigned __int64 i; // r14
  _QWORD *v9; // r15
  int Size; // ebx
  __int64 v11; // rbx
  __int64 v12; // rbx
  __int64 v13; // rbx
  __int64 v14; // rbx
  __int64 v15; // rbx
  unsigned __int64 v16; // rdx
  _QWORD *v17; // rcx
  LPCWSTR v18; // rbx
  signed int LastError; // eax
  signed int v20; // eax
  signed int WinREVersion; // edi
  unsigned __int64 v22; // r14
  __int64 v23; // r8
  __int64 v24; // r14
  WinREAgent::Operation *v25; // r15
  int v26; // eax
  __int64 v27; // rdx
  __int64 v28; // rcx
  __int64 v29; // rbx
  int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+40h] [rbp-69h] BYREF
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+48h] [rbp-61h] BYREF
  LPCWSTR lpDirectoryName; // [rsp+50h] [rbp-59h] BYREF
  unsigned __int64 v36; // [rsp+58h] [rbp-51h] BYREF
  __int64 v37; // [rsp+60h] [rbp-49h] BYREF
  __int64 v38; // [rsp+68h] [rbp-41h] BYREF
  _QWORD v39[2]; // [rsp+70h] [rbp-39h] BYREF
  _QWORD v40[2]; // [rsp+80h] [rbp-29h] BYREF
  __int128 v41; // [rsp+90h] [rbp-19h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-9h]
  int v43; // [rsp+A8h] [rbp-1h]
  __int64 v44; // [rsp+B0h] [rbp+7h]
  __int64 v45; // [rsp+B8h] [rbp+Fh]
  __int64 v46; // [rsp+C0h] [rbp+17h]

  if ( !*((_BYTE *)this + 336) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147942421LL,
      "WinREAgent::Executor::Commit",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      1770,
      L"Must execute Stage first");
    return 2147942421LL;
  }
  PushButtonReset::Logging::Trace(0, L"Start executing commit operations");
  if ( a3 )
    WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"Phase", L"CommitStart");
  v40[0] = &WinREAgent::OperationProgress::`vftable';
  v40[1] = a2;
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  for ( i = 0; i < *((_QWORD *)this + 9); ++i )
  {
    v9 = *(_QWORD **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                       (char *)this + 64,
                       i,
                       v7);
    v37 = 0;
    Size = (*(__int64 (__fastcall **)(_QWORD *, __int64 *))(*v9 + 24LL))(v9, &v37);
    if ( Size < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Size,
        "WinREAgent::Executor::Commit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1790,
        L"Failed to get the weight of operation [%s]",
        v9[5]);
      goto LABEL_72;
    }
    v11 = v37;
    ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(&v41, v37);
    v44 += v11;
  }
  v12 = *(_QWORD *)(*((_QWORD *)this + 51) + 448LL);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&TotalNumberOfFreeBytes,
    (__int64)L"RollbackStart");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&TotalNumberOfBytes,
    (__int64)L"ExecutionInfo");
  LOBYTE(v12) = WinREAgent::RollbackHelper::HasKey(v12, &TotalNumberOfBytes, &TotalNumberOfFreeBytes);
  ATL::CStringData::Release((ATL::CStringData *)(TotalNumberOfBytes.QuadPart - 24));
  ATL::CStringData::Release((ATL::CStringData *)(TotalNumberOfFreeBytes.QuadPart - 24));
  if ( (_BYTE)v12 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147500037LL,
      "WinREAgent::Executor::Commit",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      1798,
      L"Execution has been rollbacked");
LABEL_10:
    Size = -2147467259;
    goto LABEL_72;
  }
  v13 = *(_QWORD *)(*((_QWORD *)this + 51) + 448LL);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&TotalNumberOfFreeBytes,
    (__int64)L"CommitComplete");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&TotalNumberOfBytes,
    (__int64)L"ExecutionInfo");
  LOBYTE(v13) = WinREAgent::RollbackHelper::HasKey(v13, &TotalNumberOfBytes, &TotalNumberOfFreeBytes);
  ATL::CStringData::Release((ATL::CStringData *)(TotalNumberOfBytes.QuadPart - 24));
  ATL::CStringData::Release((ATL::CStringData *)(TotalNumberOfFreeBytes.QuadPart - 24));
  if ( (_BYTE)v13 )
  {
    PushButtonReset::Logging::Trace(0, L"Commit has completed");
    Size = 1;
    goto LABEL_72;
  }
  if ( *((_DWORD *)this + 46) )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147500037LL,
      "WinREAgent::Executor::Commit",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      1807,
      L"Have already executed [%u] operations in commit",
      *((_DWORD *)this + 46));
    goto LABEL_10;
  }
  v14 = *(_QWORD *)(*((_QWORD *)this + 51) + 448LL);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&TotalNumberOfFreeBytes,
    (__int64)L"CommitStart");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&TotalNumberOfBytes,
    (__int64)L"ExecutionInfo");
  LOBYTE(v14) = WinREAgent::RollbackHelper::HasKey(v14, &TotalNumberOfBytes, &TotalNumberOfFreeBytes);
  ATL::CStringData::Release((ATL::CStringData *)(TotalNumberOfBytes.QuadPart - 24));
  ATL::CStringData::Release((ATL::CStringData *)(TotalNumberOfFreeBytes.QuadPart - 24));
  if ( (_BYTE)v14 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      2147500037LL,
      "WinREAgent::Executor::Commit",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      1811,
      L"Have already start commit execution");
    goto LABEL_10;
  }
  v15 = *(_QWORD *)(*((_QWORD *)this + 51) + 448LL);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&lpDirectoryName,
    (__int64)L"Yes");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&TotalNumberOfFreeBytes,
    (__int64)L"CommitStart");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&TotalNumberOfBytes,
    (__int64)L"ExecutionInfo");
  Size = WinREAgent::RollbackHelper::WriteToConfig(v15, &TotalNumberOfBytes, &TotalNumberOfFreeBytes, &lpDirectoryName);
  ATL::CStringData::Release((ATL::CStringData *)(TotalNumberOfBytes.QuadPart - 24));
  ATL::CStringData::Release((ATL::CStringData *)(TotalNumberOfFreeBytes.QuadPart - 24));
  ATL::CStringData::Release((ATL::CStringData *)(lpDirectoryName - 12));
  if ( Size < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Size,
      "WinREAgent::Executor::Commit",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      1818,
      L"Failed to Save Commit starts to rollback info");
    goto LABEL_72;
  }
  v17 = (_QWORD *)(*((_QWORD *)this + 51) + 120LL);
  if ( *(_DWORD *)(*v17 - 16LL) )
  {
    v36 = 0;
    Size = PushButtonReset::File::GetSize(v17, &v36);
    if ( Size < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Size,
        "WinREAgent::Executor::Commit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1824,
        L"Failed to get size of [%s]",
        *(_QWORD *)(*((_QWORD *)this + 51) + 120LL));
      goto LABEL_72;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpDirectoryName);
    Size = PushButtonReset::Path::GetDirectory(*((_QWORD *)this + 51) + 120LL, &lpDirectoryName);
    if ( Size < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Size,
        "WinREAgent::Executor::Commit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1828,
        L"Failed to get current WinRE directory");
      ATL::CStringData::Release((ATL::CStringData *)(lpDirectoryName - 12));
      goto LABEL_72;
    }
    TotalNumberOfBytes.QuadPart = 0;
    TotalNumberOfFreeBytes.QuadPart = 0;
    v18 = lpDirectoryName;
    if ( !GetDiskFreeSpaceExW(lpDirectoryName, 0, &TotalNumberOfBytes, &TotalNumberOfFreeBytes) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LastError,
        "WinREAgent::Executor::Commit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1835,
        L"Failed to get space info for recovery partition");
      v20 = GetLastError();
      WinREVersion = v20;
      if ( v20 > 0 )
        WinREVersion = (unsigned __int16)v20 | 0x80070000;
LABEL_71:
      ATL::CStringData::Release((ATL::CStringData *)(v18 - 12));
      Size = WinREVersion;
      goto LABEL_72;
    }
    v22 = v36;
    PushButtonReset::Logging::Trace(
      0,
      L"WinRE partition total space [%llu], free space [%llu], winre size [%llu]",
      TotalNumberOfBytes.QuadPart,
      TotalNumberOfFreeBytes.QuadPart,
      v36);
    if ( a3 )
      WinREAgent::TelemetrySession::TraceWinREPartitionInfoInCommit(
        a3,
        TotalNumberOfBytes.QuadPart,
        TotalNumberOfFreeBytes.QuadPart,
        v22);
    ATL::CStringData::Release((ATL::CStringData *)(v18 - 12));
  }
  Size = WinREAgent::OperationProgress::SetOperation((WinREAgent::OperationProgress *)v40, v16);
  if ( Size < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)Size,
      "WinREAgent::Executor::Commit",
      "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
      1854,
      L"Failed to set start operation index");
    goto LABEL_72;
  }
  v24 = 0;
  if ( !*((_QWORD *)this + 9) )
  {
LABEL_52:
    PushButtonReset::Logging::Trace(0, L"Successfully executed commit operations");
    if ( a3 )
      WinREAgent::TelemetrySession::TraceDataPoint(a3, L"ServicingInfoGroup", L"Phase", L"CommitEnd");
    v29 = *(_QWORD *)(*((_QWORD *)this + 51) + 448LL);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)v39,
      (__int64)L"Yes");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&v38,
      (__int64)L"CommitComplete");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      (__int64)&lpDirectoryName,
      (__int64)L"ExecutionInfo");
    Size = WinREAgent::RollbackHelper::WriteToConfig(v29, &lpDirectoryName, &v38, v39);
    ATL::CStringData::Release((ATL::CStringData *)(lpDirectoryName - 12));
    ATL::CStringData::Release((ATL::CStringData *)(v38 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v39[0] - 24LL));
    if ( Size < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Size,
        "WinREAgent::Executor::Commit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1944,
        L"Failed to Save Commit completes to rollback info");
      goto LABEL_72;
    }
    v30 = LogWinREStatusOnComplete(*((_QWORD *)this + 51) + 120LL, a3);
    if ( v30 < 0 )
      PushButtonReset::Logging::TraceErr(
        1,
        (unsigned int)v30,
        "WinREAgent::Executor::Commit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1949,
        L"Failed to log WinRE partition status on complete");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>((__int64)&lpDirectoryName);
    WinREVersion = GetWinREVersion(
                     *((_QWORD *)this + 51) + 120LL,
                     *((_QWORD *)this + 51) + 216LL,
                     *((_QWORD *)this + 51) + 184LL,
                     &lpDirectoryName);
    if ( WinREVersion >= 0 )
    {
      v18 = lpDirectoryName;
      PushButtonReset::Logging::Trace(0, L"Installed WinRE version: [%s]", lpDirectoryName);
    }
    else
    {
      PushButtonReset::Logging::TraceErr(
        1,
        (unsigned int)WinREVersion,
        "WinREAgent::Executor::Commit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1960,
        L"Failed to get version of installed WinRE");
      WinREVersion = 0;
      ATL::CSimpleStringT<unsigned short,0>::SetString(&lpDirectoryName, &pszFormat, 0);
      v18 = lpDirectoryName;
    }
    McGenEventRegister_EventRegister();
    if ( (Microsoft_Windows_WinREAgentEnableBits & 1) != 0 )
      McTemplateU0z_EventWriteTransfer(v32, v31, v18);
    McGenEventUnregister_EventUnregister();
    goto LABEL_71;
  }
  while ( 1 )
  {
    v25 = *(WinREAgent::Operation **)ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(
                                       (char *)this + 64,
                                       v24,
                                       v23);
    *((_DWORD *)this + 46) = v24 + 1;
    PushButtonReset::Logging::Trace(0, L"Executing operation [%u]: [%s]", (unsigned int)v24, *((_QWORD *)v25 + 5));
    v36 = 0;
    Size = (*(__int64 (__fastcall **)(WinREAgent::Operation *, unsigned __int64 *))(*(_QWORD *)v25 + 24LL))(v25, &v36);
    if ( Size < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Size,
        "WinREAgent::Executor::Commit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1865,
        L"Failed to get the weight of operation [%s]",
        *((_QWORD *)v25 + 5));
      goto LABEL_72;
    }
    if ( a3 )
      WinREAgent::TelemetrySession::TraceOperationExecuteStarted(a3, v24, (char *)v25 + 72, v36);
    v26 = WinREAgent::Operation::Execute(
            v25,
            *((const struct WinREAgent::ExecutionContext **)this + 51),
            (struct PushButtonReset::ProgressCallback *)v40,
            a3);
    Size = v26;
    if ( v26 == -2147023673 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147943623LL,
        "WinREAgent::Executor::Commit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1875,
        L"Operation execution cancelled by caller");
      goto LABEL_61;
    }
    if ( v26 < 0 )
      break;
LABEL_47:
    PushButtonReset::Logging::Trace(0, L"The operation executed successfully");
    if ( a3 )
      WinREAgent::TelemetrySession::TraceOperationExecuted(a3, v24, (char *)v25 + 72);
    Size = WinREAgent::Operation::ApplyEffects(v25, *((struct WinREAgent::ExecutionContext **)this + 51));
    if ( Size < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)Size,
        "WinREAgent::Executor::Commit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1921,
        L"Operation failed to apply effects after operation [%s]",
        *((_QWORD *)v25 + 5));
      goto LABEL_72;
    }
    WinREAgent::OperationProgress::CompletedOperation((WinREAgent::OperationProgress *)v40);
    if ( PushButtonReset::OverallProgress::Cancel((PushButtonReset::OverallProgress *)v40) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147943623LL,
        "WinREAgent::Executor::Commit",
        "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
        1927,
        L"Execution cancelled by caller");
LABEL_61:
      Size = -2147023673;
      goto LABEL_72;
    }
    if ( (unsigned __int64)++v24 >= *((_QWORD *)this + 9) )
      goto LABEL_52;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)v26,
    "WinREAgent::Executor::Commit",
    "base\\diagnosis\\srt\\winreagent\\dll\\executor.cpp",
    1884,
    L"Failed to execute operation [%s]",
    *((_QWORD *)v25 + 5));
  McGenEventRegister_EventRegister();
  if ( (Microsoft_Windows_WinREAgentEnableBits & 2) != 0 )
    McTemplateU0dd_EventWriteTransfer(v28, v27, 3, (unsigned int)Size);
  McGenEventUnregister_EventUnregister();
  if ( *(_DWORD *)(*((_QWORD *)this + 51) + 440LL) == 1 )
  {
    PushButtonReset::Logging::Trace(0, L"Current remediation strategy is to move forward, ignore this error");
    if ( a3 )
      WinREAgent::TelemetrySession::TraceOperationFailed((_DWORD)a3, v24, (_DWORD)v25 + 72, Size, 1);
    goto LABEL_47;
  }
  if ( a3 )
    WinREAgent::TelemetrySession::TraceOperationFailed((_DWORD)a3, v24, (_DWORD)v25 + 72, Size, 0);
LABEL_72:
  ATL::CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>::~CAtlArray<unsigned char,ATL::CElementTraits<unsigned char>>((void **)&v41);
  return (unsigned int)Size;
}

```

## disassembly

```asm
0x180007570  mov     [rsp-8+arg_8], rbx
0x180007575  push    rbp
0x180007576  push    rsi
0x180007577  push    rdi
0x180007578  push    r12
0x18000757a  push    r13
0x18000757c  push    r14
0x18000757e  push    r15
0x180007580  lea     rbp, [rsp-27h]
0x180007585  sub     rsp, 0D0h
0x18000758c  mov     rsi, r8
0x18000758f  mov     rbx, rdx
0x180007592  mov     rdi, rcx
0x180007595  xor     r12d, r12d
0x180007598  cmp     [rcx+150h], r12b
0x18000759f  jnz     short loc_1800075DC
0x1800075a1  lea     rax, aMustExecuteSta; "Must execute Stage first"
0x1800075a8  mov     [rsp+100h+var_D8], rax
0x1800075ad  mov     dword ptr [rsp+100h+var_E0], 6EAh
0x1800075b5  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800075bc  lea     r8, aWinreagentExec; "WinREAgent::Executor::Commit"
0x1800075c3  mov     edx, 80070015h
0x1800075c8  lea     ecx, [r12+2]
0x1800075cd  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800075d2  mov     eax, 80070015h
0x1800075d7  jmp     loc_180007F19
0x1800075dc  lea     rdx, aStartExecuting_1; "Start executing commit operations"
0x1800075e3  xor     ecx, ecx
0x1800075e5  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800075ea  lea     r13, aCommitstart; "CommitStart"
0x1800075f1  test    rsi, rsi
0x1800075f4  jz      short loc_18000760F
0x1800075f6  mov     r9, r13; unsigned __int16 *
0x1800075f9  lea     r8, aPhase; "Phase"
0x180007600  lea     rdx, aServicinginfog; "ServicingInfoGroup"
0x180007607  mov     rcx, rsi; this
0x18000760a  call    ?TraceDataPoint@TelemetrySession@WinREAgent@@QEBAXPEBG00@Z; WinREAgent::TelemetrySession::TraceDataPoint(ushort const *,ushort const *,ushort const *)
0x18000760f  lea     rax, ??_7OperationProgress@WinREAgent@@6B@; const WinREAgent::OperationProgress::`vftable'
0x180007616  mov     [rbp+57h+var_80], rax
0x18000761a  mov     [rbp+57h+var_78], rbx
0x18000761e  xorps   xmm0, xmm0
0x180007621  movdqa  [rbp+57h+var_70], xmm0
0x180007626  mov     [rbp+57h+var_60], r12
0x18000762a  mov     [rbp+57h+var_58], r12d
0x18000762e  mov     [rbp+57h+var_50], r12
0x180007632  mov     [rbp+57h+var_48], r12
0x180007636  mov     [rbp+57h+var_40], r12
0x18000763a  mov     r14, r12
0x18000763d  cmp     [rdi+48h], r12
0x180007641  jbe     short loc_180007697
0x180007643  mov     rdx, r14
0x180007646  lea     rcx, [rdi+40h]
0x18000764a  call    ?GetAt@?$CAtlArray@PEAVProperty@PushButtonReset@@V?$CElementTraits@PEAVProperty@PushButtonReset@@@ATL@@@ATL@@QEBAAEBQEAVProperty@PushButtonReset@@_K@Z; ATL::CAtlArray<PushButtonReset::Property *,ATL::CElementTraits<PushButtonReset::Property *>>::GetAt(unsigned __int64)
0x18000764f  mov     r15, [rax]
0x180007652  mov     [rbp+57h+var_A0], 0
0x18000765a  mov     rax, [r15]
0x18000765d  lea     rdx, [rbp+57h+var_A0]
0x180007661  mov     rcx, r15
0x180007664  mov     rax, [rax+18h]
0x180007668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000766d  mov     ebx, eax
0x18000766f  test    eax, eax
0x180007671  js      loc_180007736
0x180007677  mov     rbx, [rbp+57h+var_A0]
0x18000767b  mov     rdx, rbx
0x18000767e  lea     rcx, [rbp+57h+var_70]
0x180007682  call    ?Add@?$CAtlArray@_JV?$CElementTraits@_J@ATL@@@ATL@@QEAA_K_J@Z; ATL::CAtlArray<__int64,ATL::CElementTraits<__int64>>::Add(__int64)
0x180007687  add     [rbp+57h+var_50], rbx
0x18000768b  inc     r14
0x18000768e  cmp     r14, [rdi+48h]
0x180007692  jb      short loc_180007643
0x180007694  xor     r12d, r12d
0x180007697  mov     rax, [rdi+198h]
0x18000769e  mov     rbx, [rax+1C0h]
0x1800076a5  lea     rdx, aRollbackstart; "RollbackStart"
0x1800076ac  lea     rcx, [rbp+57h+TotalNumberOfFreeBytes]
0x1800076b0  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800076b5  nop
0x1800076b6  lea     r15, aExecutioninfo; "ExecutionInfo"
0x1800076bd  mov     rdx, r15
0x1800076c0  lea     rcx, [rbp+57h+TotalNumberOfBytes]
0x1800076c4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800076c9  nop
0x1800076ca  lea     r8, [rbp+57h+TotalNumberOfFreeBytes]
0x1800076ce  lea     rdx, [rbp+57h+TotalNumberOfBytes]
0x1800076d2  mov     rcx, rbx
0x1800076d5  call    ?HasKey@RollbackHelper@WinREAgent@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WinREAgent::RollbackHelper::HasKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800076da  mov     bl, al
0x1800076dc  mov     rcx, qword ptr [rbp+57h+TotalNumberOfBytes]
0x1800076e0  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800076e4  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800076e9  nop
0x1800076ea  mov     rcx, qword ptr [rbp+57h+TotalNumberOfFreeBytes]
0x1800076ee  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800076f2  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800076f7  test    bl, bl
0x1800076f9  jz      short loc_180007758
0x1800076fb  lea     rax, aExecutionHasBe; "Execution has been rollbacked"
0x180007702  mov     [rsp+100h+var_D8], rax
0x180007707  mov     dword ptr [rsp+100h+var_E0], 706h
0x18000770f  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180007716  lea     r8, aWinreagentExec; "WinREAgent::Executor::Commit"
0x18000771d  mov     edx, 80004005h
0x180007722  mov     ecx, 2
0x180007727  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000772c  mov     ebx, 80004005h
0x180007731  jmp     loc_180007F0E
0x180007736  mov     rax, [r15+28h]
0x18000773a  mov     [rsp+100h+var_D0], rax
0x18000773f  lea     rax, aFailedToGetThe_0; "Failed to get the weight of operation ["...
0x180007746  mov     [rsp+100h+var_D8], rax
0x18000774b  mov     dword ptr [rsp+100h+var_E0], 6FEh
0x180007753  jmp     loc_180007981
0x180007758  mov     rax, [rdi+198h]
0x18000775f  mov     rbx, [rax+1C0h]
0x180007766  lea     rdx, aCommitcomplete; "CommitComplete"
0x18000776d  lea     rcx, [rbp+57h+TotalNumberOfFreeBytes]
0x180007771  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180007776  nop
0x180007777  mov     rdx, r15
0x18000777a  lea     rcx, [rbp+57h+TotalNumberOfBytes]
0x18000777e  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180007783  nop
0x180007784  lea     r8, [rbp+57h+TotalNumberOfFreeBytes]
0x180007788  lea     rdx, [rbp+57h+TotalNumberOfBytes]
0x18000778c  mov     rcx, rbx
0x18000778f  call    ?HasKey@RollbackHelper@WinREAgent@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WinREAgent::RollbackHelper::HasKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180007794  mov     bl, al
0x180007796  mov     rcx, qword ptr [rbp+57h+TotalNumberOfBytes]
0x18000779a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18000779e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800077a3  nop
0x1800077a4  mov     rcx, qword ptr [rbp+57h+TotalNumberOfFreeBytes]
0x1800077a8  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800077ac  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800077b1  test    bl, bl
0x1800077b3  jz      short loc_1800077CD
0x1800077b5  lea     rdx, aCommitHasCompl; "Commit has completed"
0x1800077bc  xor     ecx, ecx
0x1800077be  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x1800077c3  mov     ebx, 1
0x1800077c8  jmp     loc_180007F0E
0x1800077cd  mov     eax, [rdi+0B8h]
0x1800077d3  test    eax, eax
0x1800077d5  jz      short loc_180007811
0x1800077d7  mov     dword ptr [rsp+100h+var_D0], eax
0x1800077db  lea     rax, aHaveAlreadyExe; "Have already executed [%u] operations i"...
0x1800077e2  mov     [rsp+100h+var_D8], rax
0x1800077e7  mov     dword ptr [rsp+100h+var_E0], 70Fh
0x1800077ef  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800077f6  lea     r8, aWinreagentExec; "WinREAgent::Executor::Commit"
0x1800077fd  mov     edx, 80004005h
0x180007802  mov     ecx, 2
0x180007807  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000780c  jmp     loc_18000772C
0x180007811  mov     rax, [rdi+198h]
0x180007818  mov     rbx, [rax+1C0h]
0x18000781f  mov     rdx, r13
0x180007822  lea     rcx, [rbp+57h+TotalNumberOfFreeBytes]
0x180007826  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18000782b  nop
0x18000782c  mov     rdx, r15
0x18000782f  lea     rcx, [rbp+57h+TotalNumberOfBytes]
0x180007833  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180007838  nop
0x180007839  lea     r8, [rbp+57h+TotalNumberOfFreeBytes]
0x18000783d  lea     rdx, [rbp+57h+TotalNumberOfBytes]
0x180007841  mov     rcx, rbx
0x180007844  call    ?HasKey@RollbackHelper@WinREAgent@@QEAA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0@Z; WinREAgent::RollbackHelper::HasKey(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180007849  mov     bl, al
0x18000784b  mov     rcx, qword ptr [rbp+57h+TotalNumberOfBytes]
0x18000784f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180007853  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007858  nop
0x180007859  mov     rcx, qword ptr [rbp+57h+TotalNumberOfFreeBytes]
0x18000785d  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180007861  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007866  test    bl, bl
0x180007868  jz      short loc_180007883
0x18000786a  lea     rax, aHaveAlreadySta_0; "Have already start commit execution"
0x180007871  mov     [rsp+100h+var_D8], rax
0x180007876  mov     dword ptr [rsp+100h+var_E0], 713h
0x18000787e  jmp     loc_18000770F
0x180007883  mov     rax, [rdi+198h]
0x18000788a  mov     rbx, [rax+1C0h]
0x180007891  lea     rdx, aYes; "Yes"
0x180007898  lea     rcx, [rbp+57h+lpDirectoryName]
0x18000789c  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800078a1  nop
0x1800078a2  mov     rdx, r13
0x1800078a5  lea     rcx, [rbp+57h+TotalNumberOfFreeBytes]
0x1800078a9  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800078ae  nop
0x1800078af  mov     rdx, r15
0x1800078b2  lea     rcx, [rbp+57h+TotalNumberOfBytes]
0x1800078b6  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x1800078bb  nop
0x1800078bc  lea     r9, [rbp+57h+lpDirectoryName]
0x1800078c0  lea     r8, [rbp+57h+TotalNumberOfFreeBytes]
0x1800078c4  lea     rdx, [rbp+57h+TotalNumberOfBytes]
0x1800078c8  mov     rcx, rbx
0x1800078cb  call    ?WriteToConfig@RollbackHelper@WinREAgent@@QEAAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@00@Z; WinREAgent::RollbackHelper::WriteToConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x1800078d0  mov     ebx, eax
0x1800078d2  mov     rcx, qword ptr [rbp+57h+TotalNumberOfBytes]
0x1800078d6  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800078da  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800078df  nop
0x1800078e0  mov     rcx, qword ptr [rbp+57h+TotalNumberOfFreeBytes]
0x1800078e4  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800078e8  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800078ed  nop
0x1800078ee  mov     rcx, [rbp+57h+lpDirectoryName]
0x1800078f2  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800078f6  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x1800078fb  test    ebx, ebx
0x1800078fd  jns     short loc_180007932
0x1800078ff  lea     rax, aFailedToSaveCo_2; "Failed to Save Commit starts to rollbac"...
0x180007906  mov     [rsp+100h+var_D8], rax
0x18000790b  mov     dword ptr [rsp+100h+var_E0], 71Ah
0x180007913  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18000791a  lea     r8, aWinreagentExec; "WinREAgent::Executor::Commit"
0x180007921  mov     edx, ebx
0x180007923  mov     ecx, 2
0x180007928  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000792d  jmp     loc_180007F0E
0x180007932  mov     rcx, [rdi+198h]
0x180007939  add     rcx, 78h ; 'x'
0x18000793d  mov     rax, [rcx]
0x180007940  cmp     [rax-10h], r12d
0x180007944  jz      loc_180007AC1
0x18000794a  mov     [rbp+57h+var_A8], r12
0x18000794e  lea     rdx, [rbp+57h+var_A8]
0x180007952  call    ?GetSize@File@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEA_K@Z; PushButtonReset::File::GetSize(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,unsigned __int64 *)
0x180007957  mov     ebx, eax
0x180007959  test    eax, eax
0x18000795b  jns     short loc_1800079A0
0x18000795d  mov     rcx, [rdi+198h]
0x180007964  mov     rdx, [rcx+78h]
0x180007968  mov     [rsp+100h+var_D0], rdx
0x18000796d  lea     rax, aFailedToGetSiz_2; "Failed to get size of [%s]"
0x180007974  mov     [rsp+100h+var_D8], rax
0x180007979  mov     dword ptr [rsp+100h+var_E0], 720h
0x180007981  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180007988  lea     r8, aWinreagentExec; "WinREAgent::Executor::Commit"
0x18000798f  mov     edx, ebx
0x180007991  mov     ecx, 2
0x180007996  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18000799b  jmp     loc_180007F0E
0x1800079a0  lea     rcx, [rbp+57h+lpDirectoryName]
0x1800079a4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x1800079a9  nop
0x1800079aa  mov     rcx, [rdi+198h]
0x1800079b1  add     rcx, 78h ; 'x'
0x1800079b5  lea     rdx, [rbp+57h+lpDirectoryName]
0x1800079b9  call    ?GetDirectory@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z; PushButtonReset::Path::GetDirectory(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x1800079be  mov     ebx, eax
0x1800079c0  test    eax, eax
0x1800079c2  jns     short loc_180007A05
0x1800079c4  lea     rax, aFailedToGetCur_1; "Failed to get current WinRE directory"
0x1800079cb  mov     [rsp+100h+var_D8], rax
0x1800079d0  mov     dword ptr [rsp+100h+var_E0], 724h
0x1800079d8  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x1800079df  lea     r8, aWinreagentExec; "WinREAgent::Executor::Commit"
0x1800079e6  mov     edx, ebx
0x1800079e8  mov     ecx, 2
0x1800079ed  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x1800079f2  nop
0x1800079f3  mov     rcx, [rbp+57h+lpDirectoryName]
0x1800079f7  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x1800079fb  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180007a00  jmp     loc_180007F0E
0x180007a05  mov     qword ptr [rbp+57h+TotalNumberOfBytes], r12
0x180007a09  mov     qword ptr [rbp+57h+TotalNumberOfFreeBytes], r12
0x180007a0d  lea     r9, [rbp+57h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x180007a11  lea     r8, [rbp+57h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x180007a15  xor     edx, edx; lpFreeBytesAvailableToCaller
0x180007a17  mov     rbx, [rbp+57h+lpDirectoryName]
0x180007a1b  mov     rcx, rbx; lpDirectoryName
0x180007a1e  call    cs:__imp_GetDiskFreeSpaceExW
0x180007a24  test    eax, eax
0x180007a26  jnz     short loc_180007A80
0x180007a28  call    cs:__imp_GetLastError
0x180007a2e  mov     esi, 80070000h
0x180007a33  test    eax, eax
0x180007a35  jle     short loc_180007A3C
0x180007a37  movzx   eax, ax
0x180007a3a  or      eax, esi
0x180007a3c  lea     rcx, aFailedToGetSpa; "Failed to get space info for recovery p"...
0x180007a43  mov     [rsp+100h+var_D8], rcx
0x180007a48  mov     dword ptr [rsp+100h+var_E0], 72Bh
0x180007a50  lea     r9, aBaseDiagnosisS_11; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x180007a57  lea     r8, aWinreagentExec; "WinREAgent::Executor::Commit"
0x180007a5e  mov     edx, eax
0x180007a60  mov     ecx, 2
0x180007a65  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x180007a6a  call    cs:__imp_GetLastError
0x180007a70  mov     edi, eax
0x180007a72  test    eax, eax
0x180007a74  jle     short loc_180007A7B
0x180007a76  movzx   edi, ax
  ... truncated ...
```
