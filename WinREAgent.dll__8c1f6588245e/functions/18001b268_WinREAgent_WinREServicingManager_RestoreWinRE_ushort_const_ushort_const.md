# WinREAgent::WinREServicingManager::RestoreWinRE(ushort const *,ushort const *)

- ea: `0x18001b268`
- end: `0x18001bbc6`
- name: `?RestoreWinRE@WinREServicingManager@WinREAgent@@SAJPEBG0@Z`
- size: `2398`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800170d0`

## callees

- `0x180003eb0`
- `0x1800049a4`
- `0x180004af8`
- `0x180005cb0`
- `0x180005cc0`
- `0x18000d690`
- `0x18000d6f0`
- `0x18000d92c`
- `0x18000dcc8`
- `0x18000e800`
- `0x180012c00`
- `0x18001586c`
- `0x180016440`
- `0x180016490`
- `0x180019724`
- `0x18001aeb0`
- `0x18001b268`
- `0x18001eecc`
- `0x18001f194`
- `0x18002da30`
- `0x18002e06c`
- `0x18002f120`
- `0x18002f1f8`
- `0x18002f2cc`
- `0x18003717c`
- `0x180037344`
- `0x18004a898`
- `0x18004b35c`
- `0x18004c418`
- `0x18004d1fc`
- `0x18004d2ac`
- `0x180053830`
- `0x180053afc`
- `0x18006f010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001b8e3`
- `KERNEL32!GetLastError` at `0x18001b8e3`
- `ReAgent!WinReInstallOnTargetOS` at `0x18001b8d5`
- `ReAgent!WinReInstallOnTargetOS` at `0x18001b8d5`

## string_xrefs

- `0x18001b4eb`: `Backup directory [%s] doesn't exist`
- `0x18001b334`: `Failed to build log path`
- `0x18001b66f`: `Failed to read WinRE configuration`
- `0x18001b2c0`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001b348`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001b3d4`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001b442`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001b4ff`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001b5b0`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001b608`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001b683`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001b6ef`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001b7d6`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001b857`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001b911`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001b9d1`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001ba4a`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001bab7`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001bb0e`: `base\diagnosis\srt\winreagent\dll\winreservicingmanager.cpp`
- `0x18001b3c0`: `Failed to create work dirs`
- `0x18001b6db`: `Failed to read WinRE configuration from [%s]`
- `0x18001b2c7`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001b34f`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001b3db`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001b449`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001b506`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001b5b7`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001b60f`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001b68a`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001b6f6`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001b7dd`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001b85e`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001b918`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001b9d8`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001ba51`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001babe`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001bb15`: `WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001b387`: `Enter WinREAgent::WinREServicingManager::RestoreWinRE`
- `0x18001b4af`: `Target Windows directory [%s], Backup directory [%s]`
- `0x18001b59c`: `Failed to construct backup WinRE path`
- `0x18001b763`: `There is existing WinRE, will replace it with backup`
- `0x18001b843`: `Failed to rollback WinRE restore`
- `0x18001b870`: `Rollback not supported in current state, move forward`
- `0x18001b8a7`: `Execute in online, try to install the WinRE`
- `0x18001b8fd`: `Failed to install WinRE in [%s]`
- `0x18001b93f`: `InstallWinREError`
- `0x18001b955`: `Copy WinRE to default stage location`
- `0x18001b96d`: `System32\Recovery\WinRE.wim`
- `0x18001b9bd`: `Failed to construct target WinRE path in Recovery directory`
- `0x18001ba0f`: `[%s] already exists, deleting it`
- `0x18001ba36`: `Failed to delete existing [%s]`
- `0x18001ba6d`: `Copy backup WinRE.wim to [%s]`
- `0x18001baa3`: `Failed to copy [%s] to [%s]`
- `0x18001bb2a`: `Restore completes`
- `0x18001bb38`: `Exit WinREAgent::WinREServicingManager::RestoreWinRE`

## pseudocode

```c
__int64 __fastcall WinREAgent::WinREServicingManager::RestoreWinRE(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2)
{
  int TargetRoot; // ebx
  int LogDir; // edi
  struct WinREAgent::TelemetrySession **v7; // rax
  WinREAgent::TelemetrySession *v8; // rax
  const wchar_t *v9; // r8
  char v10; // bl
  bool v11; // r15
  struct PushButtonReset::WindowsRE::Config **v12; // rax
  struct PushButtonReset::WindowsRE::Config **v13; // rbx
  WinREAgent::TelemetrySession *v14; // rbx
  __int64 v15; // rax
  WinREAgent::Executor *v16; // rbx
  WinREAgent::TelemetrySession *v17; // rax
  WinREAgent::Executor *v18; // rax
  WinREAgent::Executor *v19; // rbx
  struct WinREAgent::TelemetrySession *v20; // rax
  int v21; // eax
  signed int LastError; // eax
  unsigned int v23; // ebx
  WinREAgent::TelemetrySession *v24; // rax
  int v25; // eax
  _BOOL8 v26; // rbx
  _BOOL8 v27; // rbx
  WinREAgent::TelemetrySession *v28; // rax
  __int64 v29; // [rsp+40h] [rbp-29h] BYREF
  __int64 v30; // [rsp+48h] [rbp-21h] BYREF
  __int64 v31; // [rsp+50h] [rbp-19h] BYREF
  _QWORD v32[2]; // [rsp+58h] [rbp-11h] BYREF
  _QWORD v33[2]; // [rsp+68h] [rbp-1h] BYREF
  _QWORD v34[2]; // [rsp+78h] [rbp+Fh] BYREF
  _QWORD v35[3]; // [rsp+88h] [rbp+1Fh] BYREF
  _BOOL8 v36; // [rsp+E0h] [rbp+77h] BYREF
  __int64 v37; // [rsp+E8h] [rbp+7Fh] BYREF

  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v30);
  LOBYTE(v36) = 0;
  TargetRoot = IsWinDirHost(a1, (bool *)&v36);
  if ( TargetRoot < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)TargetRoot,
      "WinREAgent::WinREServicingManager::RestoreWinRE",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1425,
      L"Failed to check whether the Windows is online");
LABEL_3:
    ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
    return (unsigned int)TargetRoot;
  }
  TargetRoot = GetTargetRoot(a1, &v30);
  if ( TargetRoot < 0 )
  {
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)TargetRoot,
      "WinREAgent::WinREServicingManager::RestoreWinRE",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1428,
      L"Failed to get target root");
    goto LABEL_3;
  }
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v31);
  LogDir = WinREAgent::WorkDir::GetLogDir((__int64)&v30, (__int64)&v31);
  if ( LogDir >= 0 )
  {
    LOBYTE(v37) = 0;
    v34[1] = PbrNew<WinREAgent::LogAutoRelease,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> &,bool>(
               &v31,
               &v37);
    v34[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
    PushButtonReset::Logging::Trace(0, L"Enter WinREAgent::WinREServicingManager::RestoreWinRE");
    if ( !a2 )
    {
      v34[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(v34);
      LogDir = -2147024809;
      goto LABEL_56;
    }
    LogDir = WinREAgent::WorkDir::CreateDirs(&v30);
    if ( LogDir < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LogDir,
        "WinREAgent::WinREServicingManager::RestoreWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1446,
        L"Failed to create work dirs");
LABEL_55:
      v34[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(v34);
      goto LABEL_56;
    }
    v33[1] = 0;
    v33[0] = &RAII::CAutoPbrDelete<WinREAgent::TelemetrySession *>::`vftable';
    v7 = (struct WinREAgent::TelemetrySession **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(v33);
    WinREAgent::TelemetrySession::Create(0, v7);
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD *))(v33[0] + 72LL))(v33) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147942414LL,
        "WinREAgent::WinREServicingManager::RestoreWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1450,
        L"Failed to allocate telemetry");
      v33[0] = &RAII::CAutoPbrDelete<WinREAgent::TelemetrySession *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::TelemetrySession *>::Release(v33);
      v34[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(v34);
      LogDir = -2147024882;
      goto LABEL_56;
    }
    v8 = (WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(_QWORD *))(v33[0] + 24LL))(v33);
    WinREAgent::TelemetrySession::TraceWinRERestoreStart(v8);
    v9 = L"NULL";
    if ( a1 )
      v9 = a1;
    PushButtonReset::Logging::Trace(0, L"Target Windows directory [%s], Backup directory [%s]", v9, a2);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v37,
      a2);
    v10 = PushButtonReset::Directory::Exists(&v37);
    ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
    if ( !v10 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147943568LL,
        "WinREAgent::WinREServicingManager::RestoreWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1462,
        L"Backup directory [%s] doesn't exist",
        a2);
LABEL_18:
      v33[0] = &RAII::CAutoPbrDelete<WinREAgent::TelemetrySession *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::TelemetrySession *>::Release(v33);
      v34[0] = &RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(v34);
      LogDir = -2147023728;
      goto LABEL_56;
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v29);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      v32,
      L"WinRE.wim");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v37,
      a2);
    LogDir = PushButtonReset::Path::Combine(&v37, v32, &v29);
    ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v32[0] - 24LL));
    if ( LogDir < 0 )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        (unsigned int)LogDir,
        "WinREAgent::WinREServicingManager::RestoreWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1468,
        L"Failed to construct backup WinRE path");
      ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
      v33[0] = &RAII::CAutoPbrDelete<WinREAgent::TelemetrySession *>::`vftable';
LABEL_54:
      RAII::CAutoPbrDelete<WinREAgent::TelemetrySession *>::Release(v33);
      goto LABEL_55;
    }
    if ( !(unsigned __int8)PushButtonReset::File::Exists(&v29) )
    {
      PushButtonReset::Logging::TraceErr(
        2,
        2147943568LL,
        "WinREAgent::WinREServicingManager::RestoreWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1474,
        L"There is no WinRE.wim in [%s]",
        a2);
      ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
      goto LABEL_18;
    }
    v35[1] = 0;
    v35[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
    v11 = v36;
    v12 = (struct PushButtonReset::WindowsRE::Config **)RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(v35);
    if ( v11 )
    {
      LogDir = PushButtonReset::WindowsRE::OpenConfig(v12);
      if ( LogDir < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)LogDir,
          "WinREAgent::WinREServicingManager::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1482,
          L"Failed to read WinRE configuration");
        v35[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
LABEL_53:
        RAII::CAutoPbrHeapFree<unsigned short *>::Release(v35);
        ATL::CStringData::Release((ATL::CStringData *)(v29 - 24));
        v33[0] = &RAII::CAutoPbrDelete<WinREAgent::TelemetrySession *>::`vftable';
        goto LABEL_54;
      }
    }
    else
    {
      v13 = v12;
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v36,
        a1);
      LogDir = PushButtonReset::WindowsRE::OpenConfig(&v36, v13);
      ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
      if ( LogDir < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)LogDir,
          "WinREAgent::WinREServicingManager::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1487,
          L"Failed to read WinRE configuration from [%s]",
          a1);
        goto LABEL_52;
      }
    }
    v14 = (WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(_QWORD *))(v33[0] + 24LL))(v33);
    v15 = (*(__int64 (__fastcall **)(_QWORD *))(v35[0] + 24LL))(v35);
    WinREAgent::TelemetrySession::TraceWinRERestoreInfo(v14, v11, *(_DWORD *)(v15 + 8) == 1);
    if ( *(_DWORD *)((*(__int64 (__fastcall **)(_QWORD *))(v35[0] + 24LL))(v35) + 8) == 1 )
    {
      PushButtonReset::Logging::Trace(0, L"There is existing WinRE, will replace it with backup");
      v32[1] = PbrNew<WinREAgent::Executor,>();
      v32[0] = &RAII::CAutoPbrDelete<WinREAgent::Executor *>::`vftable';
      v16 = (WinREAgent::Executor *)RAII::CAutoCleanupBase<void *>::operator->(v32);
      v17 = (WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(_QWORD *))(v33[0] + 32LL))(v33);
      LogDir = WinREAgent::Executor::RestoreWinRE(v16, v17);
      if ( LogDir < 0 )
      {
        PushButtonReset::Logging::TraceErr(
          1,
          (unsigned int)LogDir,
          "WinREAgent::WinREServicingManager::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1507,
          L"Failed to restore WinRE");
        v18 = (WinREAgent::Executor *)(*(__int64 (__fastcall **)(_QWORD *))(v32[0] + 24LL))(v32);
        if ( WinREAgent::Executor::SupportRollback(v18) )
        {
          v19 = (WinREAgent::Executor *)(*(__int64 (__fastcall **)(_QWORD *))(v32[0] + 24LL))(v32);
          v20 = (struct WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(_QWORD *))(v33[0] + 32LL))(v33);
          v21 = WinREAgent::Executor::Rollback(v19, v20);
          if ( v21 < 0 )
            PushButtonReset::Logging::TraceErr(
              1,
              (unsigned int)v21,
              "WinREAgent::WinREServicingManager::RestoreWinRE",
              "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
              1518,
              L"Failed to rollback WinRE restore");
        }
        else
        {
          PushButtonReset::Logging::Trace(0, L"Rollback not supported in current state, move forward");
          LogDir = 0;
        }
      }
      v32[0] = &RAII::CAutoPbrDelete<WinREAgent::Executor *>::`vftable';
      RAII::CAutoPbrDelete<WinREAgent::Executor *>::Release(v32);
      goto LABEL_49;
    }
    PushButtonReset::Logging::Trace(0, L"There is no existing WinRE for the OS");
    if ( v11 )
    {
      PushButtonReset::Logging::Trace(0, L"Execute in online, try to install the WinRE");
      if ( (unsigned int)WinReInstallOnTargetOS(0, 0, 0, 0, a2, 0, 0) )
      {
LABEL_49:
        v28 = (WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(_QWORD *))(v33[0] + 24LL))(v33);
        WinREAgent::TelemetrySession::TraceWinRERestoreFinished(v28, LogDir);
        if ( LogDir >= 0 )
        {
          PushButtonReset::Logging::Trace(0, L"Restore completes");
          PushButtonReset::Logging::Trace(0, L"Exit WinREAgent::WinREServicingManager::RestoreWinRE");
        }
        else
        {
          PushButtonReset::Logging::TraceErr(
            2,
            (unsigned int)LogDir,
            "WinREAgent::WinREServicingManager::RestoreWinRE",
            "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
            1591,
            L"WinRE restore failed");
        }
        goto LABEL_52;
      }
      LastError = GetLastError();
      v23 = LastError;
      if ( LastError > 0 )
        v23 = (unsigned __int16)LastError | 0x80070000;
      PushButtonReset::Logging::TraceErr(
        1,
        v23,
        "WinREAgent::WinREServicingManager::RestoreWinRE",
        "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
        1546,
        L"Failed to install WinRE in [%s]",
        a2);
      v24 = (WinREAgent::TelemetrySession *)(*(__int64 (__fastcall **)(_QWORD *))(v33[0] + 24LL))(v33);
      WinREAgent::TelemetrySession::TraceDataPoint(v24, L"RestoreWinREInfoGroup", L"InstallWinREError", v23);
    }
    PushButtonReset::Logging::Trace(0, L"Copy WinRE to default stage location");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(&v36);
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      v32,
      L"System32\\Recovery\\WinRE.wim");
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
      &v37,
      a1);
    LogDir = PushButtonReset::Path::Combine(&v37, v32, &v36);
    ATL::CStringData::Release((ATL::CStringData *)(v37 - 24));
    ATL::CStringData::Release((ATL::CStringData *)(v32[0] - 24LL));
    if ( LogDir >= 0 )
    {
      if ( (unsigned __int8)PushButtonReset::File::Exists(&v36)
        && (PushButtonReset::Logging::Trace(1, L"[%s] already exists, deleting it", v36),
            v25 = PushButtonReset::File::Delete(&v36),
            v25 < 0) )
      {
        v26 = v36;
        PushButtonReset::Logging::TraceErr(
          1,
          (unsigned int)v25,
          "WinREAgent::WinREServicingManager::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1574,
          L"Failed to delete existing [%s]",
          v36);
      }
      else
      {
        v26 = v36;
      }
      PushButtonReset::Logging::Trace(0, L"Copy backup WinRE.wim to [%s]", v26);
      LogDir = PushButtonReset::File::Copy(&v29, &v36, 0);
      v27 = v36;
      if ( LogDir < 0 )
        PushButtonReset::Logging::TraceErr(
          2,
          (unsigned int)LogDir,
          "WinREAgent::WinREServicingManager::RestoreWinRE",
          "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
          1585,
          L"Failed to copy [%s] to [%s]",
          v29,
          v36);
      ATL::CStringData::Release((ATL::CStringData *)(v27 - 24));
      goto LABEL_49;
    }
    PushButtonReset::Logging::TraceErr(
      2,
      (unsigned int)LogDir,
      "WinREAgent::WinREServicingManager::RestoreWinRE",
      "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
      1565,
      L"Failed to construct target WinRE path in Recovery directory");
    ATL::CStringData::Release((ATL::CStringData *)(v36 - 24));
LABEL_52:
    v35[0] = &RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable';
    goto LABEL_53;
  }
  PushButtonReset::Logging::TraceErr(
    2,
    (unsigned int)LogDir,
    "WinREAgent::WinREServicingManager::RestoreWinRE",
    "base\\diagnosis\\srt\\winreagent\\dll\\winreservicingmanager.cpp",
    1432,
    L"Failed to build log path");
LABEL_56:
  ATL::CStringData::Release((ATL::CStringData *)(v31 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v30 - 24));
  return (unsigned int)LogDir;
}

```

## disassembly

```asm
0x18001b268  mov     [rsp-8+arg_0], rbx
0x18001b26d  mov     [rsp-8+arg_8], rsi
0x18001b272  push    rbp
0x18001b273  push    rdi
0x18001b274  push    r13
0x18001b276  push    r14
0x18001b278  push    r15
0x18001b27a  lea     rbp, [rsp-37h]
0x18001b27f  sub     rsp, 0A0h
0x18001b286  mov     rsi, rdx
0x18001b289  mov     r14, rcx
0x18001b28c  lea     rcx, [rbp+57h+var_78]
0x18001b290  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001b295  nop
0x18001b296  mov     byte ptr [rbp+57h+arg_10], 0
0x18001b29a  lea     rdx, [rbp+57h+arg_10]; bool *
0x18001b29e  mov     rcx, r14; unsigned __int16 *
0x18001b2a1  call    ?IsWinDirHost@@YAJPEBGPEA_N@Z; IsWinDirHost(ushort const *,bool *)
0x18001b2a6  mov     ebx, eax
0x18001b2a8  test    eax, eax
0x18001b2aa  jns     short loc_18001B2EF
0x18001b2ac  lea     rax, aFailedToCheckW_11; "Failed to check whether the Windows is "...
0x18001b2b3  mov     [rsp+0C0h+var_98], rax
0x18001b2b8  mov     dword ptr [rsp+0C0h+var_A0], 591h
0x18001b2c0  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001b2c7  lea     r8, aWinreagentWinr_17; "WinREAgent::WinREServicingManager::Rest"...
0x18001b2ce  mov     edx, ebx
0x18001b2d0  mov     ecx, 2
0x18001b2d5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001b2da  nop
0x18001b2db  mov     rcx, [rbp+57h+var_78]
0x18001b2df  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001b2e3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001b2e8  mov     eax, ebx
0x18001b2ea  jmp     loc_18001BBAA
0x18001b2ef  lea     rdx, [rbp+57h+var_78]
0x18001b2f3  mov     rcx, r14
0x18001b2f6  call    ?GetTargetRoot@@YAJPEBGAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; GetTargetRoot(ushort const *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001b2fb  mov     ebx, eax
0x18001b2fd  test    eax, eax
0x18001b2ff  jns     short loc_18001B317
0x18001b301  lea     rax, aFailedToGetTar_0; "Failed to get target root"
0x18001b308  mov     [rsp+0C0h+var_98], rax
0x18001b30d  mov     dword ptr [rsp+0C0h+var_A0], 594h
0x18001b315  jmp     short loc_18001B2C0
0x18001b317  lea     rcx, [rbp+57h+var_70]
0x18001b31b  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001b320  nop
0x18001b321  lea     rdx, [rbp+57h+var_70]
0x18001b325  lea     rcx, [rbp+57h+var_78]
0x18001b329  call    ?GetLogDir@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAV34@@Z; WinREAgent::WorkDir::GetLogDir(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18001b32e  mov     edi, eax
0x18001b330  test    eax, eax
0x18001b332  jns     short loc_18001B367
0x18001b334  lea     rax, aFailedToBuildL; "Failed to build log path"
0x18001b33b  mov     [rsp+0C0h+var_98], rax
0x18001b340  mov     dword ptr [rsp+0C0h+var_A0], 598h
0x18001b348  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001b34f  lea     r8, aWinreagentWinr_17; "WinREAgent::WinREServicingManager::Rest"...
0x18001b356  mov     edx, edi
0x18001b358  mov     ecx, 2
0x18001b35d  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001b362  jmp     loc_18001BB8D
0x18001b367  mov     byte ptr [rbp+57h+arg_18], 0
0x18001b36b  lea     rdx, [rbp+57h+arg_18]
0x18001b36f  lea     rcx, [rbp+57h+var_70]
0x18001b373  call    ??$PbrNew@VLogAutoRelease@WinREAgent@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@_N@@YAPEAVLogAutoRelease@WinREAgent@@AEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@$$QEA_N@Z; PbrNew<WinREAgent::LogAutoRelease,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &,bool &&)
0x18001b378  mov     [rbp+57h+var_40], rax
0x18001b37c  lea     r13, ??_7?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::`vftable'
0x18001b383  mov     [rbp+57h+var_48], r13
0x18001b387  lea     rdx, aEnterWinreagen_11; "Enter WinREAgent::WinREServicingManager"...
0x18001b38e  xor     ecx, ecx
0x18001b390  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001b395  test    rsi, rsi
0x18001b398  jnz     short loc_18001B3B1
0x18001b39a  mov     [rbp+57h+var_48], r13
0x18001b39e  lea     rcx, [rbp+57h+var_48]
0x18001b3a2  call    ?Release@?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(void)
0x18001b3a7  mov     edi, 80070057h
0x18001b3ac  jmp     loc_18001BB8D
0x18001b3b1  lea     rcx, [rbp+57h+var_78]
0x18001b3b5  call    ?CreateDirs@WorkDir@WinREAgent@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; WinREAgent::WorkDir::CreateDirs(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001b3ba  mov     edi, eax
0x18001b3bc  test    eax, eax
0x18001b3be  jns     short loc_18001B3F3
0x18001b3c0  lea     rax, aFailedToCreate_36; "Failed to create work dirs"
0x18001b3c7  mov     [rsp+0C0h+var_98], rax
0x18001b3cc  mov     dword ptr [rsp+0C0h+var_A0], 5A6h
0x18001b3d4  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001b3db  lea     r8, aWinreagentWinr_17; "WinREAgent::WinREServicingManager::Rest"...
0x18001b3e2  mov     edx, edi
0x18001b3e4  mov     ecx, 2
0x18001b3e9  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001b3ee  jmp     loc_18001BB7F
0x18001b3f3  mov     [rbp+57h+var_50], 0
0x18001b3fb  lea     r15, ??_7?$CAutoPbrDelete@PEAVTelemetrySession@WinREAgent@@@RAII@@6B@; const RAII::CAutoPbrDelete<WinREAgent::TelemetrySession *>::`vftable'
0x18001b402  mov     [rbp+57h+var_58], r15
0x18001b406  lea     rcx, [rbp+57h+var_58]
0x18001b40a  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18001b40f  mov     rdx, rax; struct WinREAgent::TelemetrySession **
0x18001b412  xor     ecx, ecx; char *
0x18001b414  call    ?Create@TelemetrySession@WinREAgent@@SAJPEBDPEAPEAV12@@Z; WinREAgent::TelemetrySession::Create(char const *,WinREAgent::TelemetrySession * *)
0x18001b419  mov     rax, [rbp+57h+var_58]
0x18001b41d  lea     rcx, [rbp+57h+var_58]
0x18001b421  mov     rax, [rax+48h]
0x18001b425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b42a  test    al, al
0x18001b42c  jz      short loc_18001B485
0x18001b42e  lea     rax, aFailedToAlloca_12; "Failed to allocate telemetry"
0x18001b435  mov     [rsp+0C0h+var_98], rax
0x18001b43a  mov     dword ptr [rsp+0C0h+var_A0], 5AAh
0x18001b442  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001b449  lea     r8, aWinreagentWinr_17; "WinREAgent::WinREServicingManager::Rest"...
0x18001b450  mov     edx, 8007000Eh
0x18001b455  mov     ecx, 2
0x18001b45a  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001b45f  nop
0x18001b460  mov     [rbp+57h+var_58], r15
0x18001b464  lea     rcx, [rbp+57h+var_58]
0x18001b468  call    ?Release@?$CAutoPbrDelete@PEAVTelemetrySession@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::TelemetrySession *>::Release(void)
0x18001b46d  nop
0x18001b46e  mov     [rbp+57h+var_48], r13
0x18001b472  lea     rcx, [rbp+57h+var_48]
0x18001b476  call    ?Release@?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(void)
0x18001b47b  mov     edi, 8007000Eh
0x18001b480  jmp     loc_18001BB8D
0x18001b485  mov     rax, [rbp+57h+var_58]
0x18001b489  lea     rcx, [rbp+57h+var_58]
0x18001b48d  mov     rax, [rax+18h]
0x18001b491  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b496  mov     rcx, rax; this
0x18001b499  call    ?TraceWinRERestoreStart@TelemetrySession@WinREAgent@@QEBAXXZ; WinREAgent::TelemetrySession::TraceWinRERestoreStart(void)
0x18001b49e  lea     r8, aNull_0; "NULL"
0x18001b4a5  test    r14, r14
0x18001b4a8  cmovnz  r8, r14
0x18001b4ac  mov     r9, rsi
0x18001b4af  lea     rdx, aTargetWindowsD; "Target Windows directory [%s], Backup d"...
0x18001b4b6  xor     ecx, ecx
0x18001b4b8  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001b4bd  mov     rdx, rsi
0x18001b4c0  lea     rcx, [rbp+57h+arg_18]
0x18001b4c4  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001b4c9  nop
0x18001b4ca  lea     rcx, [rbp+57h+arg_18]
0x18001b4ce  call    ?Exists@Directory@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::Directory::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001b4d3  mov     bl, al
0x18001b4d5  mov     rcx, [rbp+57h+arg_18]
0x18001b4d9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001b4dd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001b4e2  test    bl, bl
0x18001b4e4  jnz     short loc_18001B542
0x18001b4e6  mov     [rsp+0C0h+var_90], rsi
0x18001b4eb  lea     rax, aBackupDirector; "Backup directory [%s] doesn't exist"
0x18001b4f2  mov     [rsp+0C0h+var_98], rax
0x18001b4f7  mov     dword ptr [rsp+0C0h+var_A0], 5B6h
0x18001b4ff  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001b506  lea     r8, aWinreagentWinr_17; "WinREAgent::WinREServicingManager::Rest"...
0x18001b50d  mov     edx, 80070490h
0x18001b512  mov     ecx, 2
0x18001b517  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001b51c  nop
0x18001b51d  mov     [rbp+57h+var_58], r15
0x18001b521  lea     rcx, [rbp+57h+var_58]
0x18001b525  call    ?Release@?$CAutoPbrDelete@PEAVTelemetrySession@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::TelemetrySession *>::Release(void)
0x18001b52a  nop
0x18001b52b  mov     [rbp+57h+var_48], r13
0x18001b52f  lea     rcx, [rbp+57h+var_48]
0x18001b533  call    ?Release@?$CAutoPbrDelete@PEAVLogAutoRelease@WinREAgent@@@RAII@@UEAAXXZ; RAII::CAutoPbrDelete<WinREAgent::LogAutoRelease *>::Release(void)
0x18001b538  mov     edi, 80070490h
0x18001b53d  jmp     loc_18001BB8D
0x18001b542  lea     rcx, [rbp+57h+var_80]
0x18001b546  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(void)
0x18001b54b  nop
0x18001b54c  lea     rdx, aWinreWim; "WinRE.wim"
0x18001b553  lea     rcx, [rbp+57h+var_68]
0x18001b557  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001b55c  nop
0x18001b55d  mov     rdx, rsi
0x18001b560  lea     rcx, [rbp+57h+arg_18]
0x18001b564  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001b569  nop
0x18001b56a  lea     r8, [rbp+57h+var_80]
0x18001b56e  lea     rdx, [rbp+57h+var_68]
0x18001b572  lea     rcx, [rbp+57h+arg_18]
0x18001b576  call    ?Combine@Path@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@0PEAV34@@Z; PushButtonReset::Path::Combine(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)
0x18001b57b  mov     edi, eax
0x18001b57d  mov     rcx, [rbp+57h+arg_18]
0x18001b581  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001b585  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001b58a  nop
0x18001b58b  mov     rcx, [rbp+57h+var_68]
0x18001b58f  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001b593  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001b598  test    edi, edi
0x18001b59a  jns     short loc_18001B5E2
0x18001b59c  lea     rax, aFailedToConstr_5; "Failed to construct backup WinRE path"
0x18001b5a3  mov     [rsp+0C0h+var_98], rax
0x18001b5a8  mov     dword ptr [rsp+0C0h+var_A0], 5BCh
0x18001b5b0  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001b5b7  lea     r8, aWinreagentWinr_17; "WinREAgent::WinREServicingManager::Rest"...
0x18001b5be  mov     edx, edi
0x18001b5c0  mov     ecx, 2
0x18001b5c5  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001b5ca  nop
0x18001b5cb  mov     rcx, [rbp+57h+var_80]
0x18001b5cf  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001b5d3  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001b5d8  nop
0x18001b5d9  mov     [rbp+57h+var_58], r15
0x18001b5dd  jmp     loc_18001BB75
0x18001b5e2  lea     rcx, [rbp+57h+var_80]
0x18001b5e6  call    ?Exists@File@PushButtonReset@@SA_NAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z; PushButtonReset::File::Exists(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x18001b5eb  test    al, al
0x18001b5ed  jnz     short loc_18001B638
0x18001b5ef  mov     [rsp+0C0h+var_90], rsi
0x18001b5f4  lea     rax, aThereIsNoWinre; "There is no WinRE.wim in [%s]"
0x18001b5fb  mov     [rsp+0C0h+var_98], rax
0x18001b600  mov     dword ptr [rsp+0C0h+var_A0], 5C2h
0x18001b608  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001b60f  lea     r8, aWinreagentWinr_17; "WinREAgent::WinREServicingManager::Rest"...
0x18001b616  mov     edx, 80070490h
0x18001b61b  mov     ecx, 2
0x18001b620  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001b625  nop
0x18001b626  mov     rcx, [rbp+57h+var_80]
0x18001b62a  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001b62e  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001b633  jmp     loc_18001B51D
0x18001b638  mov     [rbp+57h+var_30], 0
0x18001b640  lea     rbx, ??_7?$CAutoPbrDelete@PEAVConfig@WindowsRE@PushButtonReset@@@RAII@@6B@; const RAII::CAutoPbrDelete<PushButtonReset::WindowsRE::Config *>::`vftable'
0x18001b647  mov     [rbp+57h+var_38], rbx
0x18001b64b  mov     r15b, byte ptr [rbp+57h+arg_10]
0x18001b64f  lea     rcx, [rbp+57h+var_38]
0x18001b653  call    ??I?$CAutoCleanupBase@PEAVCleanupWinRE@WinREAgent@@@RAII@@UEAAPEAPEAVCleanupWinRE@WinREAgent@@XZ; RAII::CAutoCleanupBase<WinREAgent::CleanupWinRE *>::operator&(void)
0x18001b658  test    r15b, r15b
0x18001b65b  jz      short loc_18001B6A7
0x18001b65d  mov     rcx, rax; struct PushButtonReset::WindowsRE::Config **
0x18001b660  call    ?OpenConfig@WindowsRE@PushButtonReset@@SAJPEAPEAVConfig@12@@Z; PushButtonReset::WindowsRE::OpenConfig(PushButtonReset::WindowsRE::Config * *)
0x18001b665  mov     edi, eax
0x18001b667  test    eax, eax
0x18001b669  jns     loc_18001B70E
0x18001b66f  lea     rax, aFailedToReadWi_0; "Failed to read WinRE configuration"
0x18001b676  mov     [rsp+0C0h+var_98], rax
0x18001b67b  mov     dword ptr [rsp+0C0h+var_A0], 5CAh
0x18001b683  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001b68a  lea     r8, aWinreagentWinr_17; "WinREAgent::WinREServicingManager::Rest"...
0x18001b691  mov     edx, edi
0x18001b693  mov     ecx, 2
0x18001b698  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001b69d  nop
0x18001b69e  mov     [rbp+57h+var_38], rbx
0x18001b6a2  jmp     loc_18001BB52
0x18001b6a7  mov     rbx, rax
0x18001b6aa  mov     rdx, r14
0x18001b6ad  lea     rcx, [rbp+57h+arg_10]
0x18001b6b1  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18001b6b6  nop
0x18001b6b7  mov     rdx, rbx
0x18001b6ba  lea     rcx, [rbp+57h+arg_10]
0x18001b6be  call    ?OpenConfig@WindowsRE@PushButtonReset@@SAJAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAPEAVConfig@12@@Z; PushButtonReset::WindowsRE::OpenConfig(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,PushButtonReset::WindowsRE::Config * *)
0x18001b6c3  mov     edi, eax
0x18001b6c5  mov     rcx, [rbp+57h+arg_10]
0x18001b6c9  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18001b6cd  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18001b6d2  test    edi, edi
0x18001b6d4  jns     short loc_18001B70E
0x18001b6d6  mov     [rsp+0C0h+var_90], r14
0x18001b6db  lea     rax, aFailedToReadWi_1; "Failed to read WinRE configuration from"...
0x18001b6e2  mov     [rsp+0C0h+var_98], rax
0x18001b6e7  mov     dword ptr [rsp+0C0h+var_A0], 5CFh
0x18001b6ef  lea     r9, aBaseDiagnosisS_8; "base\\diagnosis\\srt\\winreagent\\dll\\"...
0x18001b6f6  lea     r8, aWinreagentWinr_17; "WinREAgent::WinREServicingManager::Rest"...
0x18001b6fd  mov     edx, edi
0x18001b6ff  mov     ecx, 2
0x18001b704  call    ?TraceErr@Logging@PushButtonReset@@SAXW4Severity@2@KPEBD1KPEBGZZ; PushButtonReset::Logging::TraceErr(PushButtonReset::Severity,ulong,char const *,char const *,ulong,ushort const *,...)
0x18001b709  jmp     loc_18001BB47
0x18001b70e  mov     rax, [rbp+57h+var_58]
0x18001b712  lea     rcx, [rbp+57h+var_58]
0x18001b716  mov     rax, [rax+18h]
0x18001b71a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b71f  mov     rbx, rax
0x18001b722  mov     rcx, [rbp+57h+var_38]
0x18001b726  mov     rax, [rcx+18h]
0x18001b72a  lea     rcx, [rbp+57h+var_38]
0x18001b72e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b733  cmp     dword ptr [rax+8], 1
0x18001b737  setz    r8b; bool
0x18001b73b  mov     dl, r15b; bool
0x18001b73e  mov     rcx, rbx; this
0x18001b741  call    ?TraceWinRERestoreInfo@TelemetrySession@WinREAgent@@QEBAX_N0@Z; WinREAgent::TelemetrySession::TraceWinRERestoreInfo(bool,bool)
0x18001b746  mov     rax, [rbp+57h+var_38]
0x18001b74a  lea     rcx, [rbp+57h+var_38]
0x18001b74e  mov     rax, [rax+18h]
0x18001b752  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b757  xor     ecx, ecx
0x18001b759  cmp     dword ptr [rax+8], 1
0x18001b75d  jnz     loc_18001B892
0x18001b763  lea     rdx, aThereIsExistin; "There is existing WinRE, will replace i"...
0x18001b76a  call    ?Trace@Logging@PushButtonReset@@SAXW4Severity@2@PEBGZZ; PushButtonReset::Logging::Trace(PushButtonReset::Severity,ushort const *,...)
0x18001b76f  call    ??$PbrNew@VExecutor@WinREAgent@@$$V@@YAPEAVExecutor@WinREAgent@@XZ; PbrNew<WinREAgent::Executor,>(void)
  ... truncated ...
```
