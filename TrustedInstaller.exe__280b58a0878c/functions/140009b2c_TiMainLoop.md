# TiMainLoop

- ea: `0x140009b2c`
- end: `0x14000a3ef`
- name: `TiMainLoop`
- size: `2243`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x140009650`

## callees

- `0x1400023e0`
- `0x140006344`
- `0x14000695c`
- `0x140006e98`
- `0x140007630`
- `0x140009b2c`
- `0x14000a3f8`
- `0x14000a7cc`
- `0x14000c8e0`
- `0x14000ca08`
- `0x14000cf8c`
- `0x14000d12c`
- `0x14000d4d0`
- `0x14000dca8`
- `0x1400127c8`
- `0x140016210`
- `0x140016554`
- `0x140017658`
- `0x140019878`
- `0x14001a16c`
- `0x14001c680`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x140009ef4`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x140009ef4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009c76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a085`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140009c76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a085`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009cf5`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140009cf5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140009c6c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000a153`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000a1ef`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000a2ed`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000a3b3`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140009c6c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000a153`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000a1ef`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000a2ed`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000a3b3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009d9d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009d9d`
- `api-ms-win-service-private-l1-1-1!I_ScRegisterPreshutdownRestart` at `0x140009fce`
- `api-ms-win-service-private-l1-1-1!I_ScRegisterPreshutdownRestart` at `0x140009fce`

## string_xrefs

- `0x140009b56`: `Starting the TrustedInstaller main loop.`
- `0x140009b9f`: `SOFTWARE\Microsoft\TrustedInstaller`
- `0x140009c8f`: `Failed to set Trusted Installer status to SERVICE_RUNNING.`
- `0x140009ca8`: `TrustedInstaller service starts successfully.`
- `0x140009d01`: `Failed to create context switcher.`
- `0x140009d6b`: `Unable to initialize all COM objects, ignore the failure since service is shutting down or about to enter shutdown processing.`
- `0x140009db8`: `Failed to initialize all COM objects.`
- `0x140009d8f`: `Software\Microsoft\Windows\CurrentVersion\Component Based Servicing\ReservesRebootPending`
- `0x140009e71`: `TI: Startup Processing completes, release startup processing lock.`
- `0x140009ea6`: `Running under Setup's OOBE boot or when PostponeOnlineActions is set, will wait for Winlogon CreateSession notifications before auto-stopping`
- `0x14000a0ce`: `Trusted Installer signaled for shutdown, going to exit.`
- `0x140009ff8`: `TI: Rejected an auto-stop attempt, because WinLogon CreateSession notification has not been called (will not report again) `
- `0x140009fdb`: `Trusted Installer cannot stop right now, because the system shutdown it was waiting for has started.`
- `0x14000a021`: `Failed registering for a pre-shutdown restart, Trusted Installer will stay running.`
- `0x14000a054`: `Trusted Installer successfully registered to be restarted for pre-shutdown.`
- `0x14000a265`: `Trusted Installer is shutting down because: %S`
- `0x14000a3b9`: `Ending the TrustedInstaller main loop.`

## pseudocode

```c
__int64 __fastcall TiMainLoop(__int64 a1, _QWORD *a2)
{
  char v3; // r14
  HKEY v4; // rcx
  bool v5; // dl
  unsigned int v6; // ebx
  signed int LastError; // eax
  signed int v8; // ebx
  HRESULT Instance; // eax
  int v10; // eax
  HKEY *InitPointer; // rax
  LSTATUS v12; // eax
  int v13; // eax
  int v14; // eax
  char v15; // r12
  char Session; // r15
  int v17; // esi
  unsigned int v18; // edi
  DWORD v19; // eax
  signed int v20; // eax
  signed int v21; // eax
  int v22; // eax
  int v23; // eax
  const wchar_t *v24; // rax
  int v25; // eax
  int v26; // eax
  unsigned int v28; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v29[2]; // [rsp+48h] [rbp-31h] BYREF
  char v30; // [rsp+58h] [rbp-21h]
  int v31; // [rsp+60h] [rbp-19h] BYREF
  __int128 v32; // [rsp+68h] [rbp-11h] BYREF
  HANDLE Handles[2]; // [rsp+78h] [rbp-1h] BYREF

  CBSWdsLogLight(0x4000000, 0, 0, "Starting the TrustedInstaller main loop.");
  vdwServiceIdleTimeout = 120000;
  v31 = 0;
  v28 = 0;
  LODWORD(Handles[0]) = 0;
  v3 = 1;
  v32 = 0;
  if ( !(unsigned int)CbsRegQueryDWORDValue(v4, L"SOFTWARE\\Microsoft\\TrustedInstaller", 1, L"IdleMinutes", &v28) )
  {
    v6 = v28;
    if ( v28 )
    {
      CBSWdsLogLight(0x4000000, 0, 0, "Custom TI Idle time set to %u minutes", v28);
      vdwServiceIdleTimeout = 60000 * v6;
    }
  }
  WdsSetupInProgress((unsigned int *)Handles, v5);
  if ( LODWORD(Handles[0]) )
  {
    CBSWdsLogLight(0x4000000, 0, 0, "Running under Setup's First boot, setting idle time to %u minutes", 30);
    vdwServiceIdleTimeout = 1800000;
  }
  if ( vbRebootInProgress )
  {
    vdwServiceIdleTimeout = 30000;
    CBSWdsLogLight(0x4000000, 0, 0, "Custom TI Idle time set to %u seconds, due to: reboot-in-progress", 30);
  }
  if ( vhTiService )
  {
    vTiStatus.dwCurrentState = 4;
    *(_QWORD *)&vTiStatus.dwControlsAccepted = 321;
    *(_QWORD *)&vTiStatus.dwCheckPoint = 0;
    if ( !SetServiceStatus(vhTiService, &vTiStatus) )
    {
      LastError = GetLastError();
      v8 = LastError;
      if ( LastError > 0 )
        v8 = (unsigned __int16)LastError | 0x80070000;
      if ( v8 < 0 )
      {
        CBSWdsLogLight(0x4000000, (unsigned int)v8, 1, "Failed to set Trusted Installer status to SERVICE_RUNNING.");
        goto LABEL_109;
      }
    }
  }
  CBSWdsLogLight(0x4000000, 0, 0, "TrustedInstaller service starts successfully.");
  MonitoredCritSecLocker::MonitoredCritSecLocker(
    (MonitoredCritSecLocker *)v29,
    (struct MonitoredCritSec *)&vTiStartupProcessingLock,
    1);
  vComRegPhase = 1;
  Instance = CoCreateInstance(&CLSID_ContextSwitcher, 0, 1u, &GUID_000001da_0000_0000_c000_000000000046, &ppv);
  v8 = Instance;
  if ( Instance < 0 )
  {
    CBSWdsLogLight(0x4000000, (unsigned int)Instance, 1, "Failed to create context switcher.");
LABEL_16:
    MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v29);
    goto LABEL_109;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(), __int128 *, GUID *, int, _QWORD))(*(_QWORD *)ppv + 24LL))(
          ppv,
          ConnectCallback,
          &v32,
          &GUID_000001da_0000_0000_c000_000000000046,
          5,
          0);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !vbServiceShuttingDown )
    {
      CBSWdsLogLight(0x4000000, (unsigned int)v10, 1, "Failed to initialize all COM objects.");
      goto LABEL_16;
    }
    CBSWdsLogLight(
      0x4000000,
      (unsigned int)v10,
      1,
      "Unable to initialize all COM objects, ignore the failure since service is shutting down or about to enter shutdown processing.");
  }
  Handles[0] = 0;
  InitPointer = (HKEY *)Windows::AutoComPtr<IClassFactory>::GetInitPointer(Handles);
  v12 = RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Component Based Servicing\\ReservesRebootPending",
          0,
          1u,
          InitPointer);
  if ( (unsigned int)(v12 - 2) <= 1 )
  {
    vbReservesRebootPending = 0;
  }
  else if ( v12 )
  {
    if ( v8 < 0 )
      CBSWdsLogLight(0x4000000, (unsigned int)v8, 1, "Unable to check whether reserves are waiting for a reboot");
  }
  else
  {
    vbReservesRebootPending = 1;
  }
  if ( vbRequireReboot || vbReservesRebootPending )
  {
    v13 = TiCoreRegisterWinlogonNotification(0, 0);
    LOWORD(v8) = v13;
    if ( v13 < 0 )
      CBSWdsLogLight(0x4000000, (unsigned int)v13, 1, "Unable to re-register for Winlogon notifications after resume.");
  }
  if ( !vbRebootInProgress )
  {
    if ( vbRebootPending )
    {
      CBSWdsLogLight(
        0x4000000,
        0,
        0,
        "TI: started and RebootPending volatile key indicates that a reboot is pending, skip startup processing.");
      TiCoreRequireShutdownProcessing();
    }
    else
    {
      v14 = TiRunStartupProcessingAndWait(&v31);
      v8 = v14;
      if ( v14 < 0 )
      {
        CBSWdsLogLight(0x4000000, (unsigned int)v14, 1, "Failed a critical portion of startup processing.");
        Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(Handles);
        goto LABEL_16;
      }
    }
  }
  v15 = 0;
  CBSWdsLogLight(0x4000000, 0, 0, "TI: Startup Processing completes, release startup processing lock.");
  Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&void Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(Handles);
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v29);
  Session = TiCoreShouldWaitForWinlogonCreateSession();
  if ( Session )
    CBSWdsLogLight(
      0x4000000,
      0,
      0,
      "Running under Setup's OOBE boot or when PostponeOnlineActions is set, will wait for Winlogon CreateSession notific"
      "ations before auto-stopping");
  v17 = 2;
LABEL_39:
  v18 = vdwServiceIdleTimeout;
  while ( 1 )
  {
    Handles[0] = vhShutdownEvent;
    Handles[1] = vhServicingEvent;
    v19 = WaitForMultipleObjectsEx(2u, Handles, 0, 0x3E8u, 0);
    if ( !v19 )
      break;
    switch ( v19 )
    {
      case 1u:
        goto LABEL_39;
      case 0xFFFFFFFF:
        v21 = GetLastError();
        v8 = v21;
        if ( v21 > 0 )
          v8 = (unsigned __int16)v21 | 0x80070000;
        if ( v8 < 0 )
          CBSWdsLogLight(0x4000000, (unsigned int)v8, 1, "Unable to wait for shutdown event... shutting down.");
        v17 = 1;
        goto LABEL_84;
      case 0x102u:
        if ( vbAboutToSleep )
        {
          vbAboutToSleep = 0;
        }
        else
        {
          if ( v18 <= 0x3E8 )
            goto LABEL_48;
          v18 -= 1000;
        }
        break;
      default:
LABEL_48:
        v29[1] = &vTiLock;
        v29[0] = &TiCoreLocker::`vftable';
        v30 = 0;
        if ( !v3 || vcInstances || !MonitoredCritSecLocker::TryLock((MonitoredCritSecLocker *)v29) || vcInstances )
          goto LABEL_67;
        if ( Session )
        {
          if ( !_InterlockedCompareExchange(&dword_14004083C, 0, 0) )
          {
            if ( !v15 )
            {
              CBSWdsLogLight(
                0x4000000,
                0,
                0,
                "TI: Rejected an auto-stop attempt, because WinLogon CreateSession notification has not been called (will"
                " not report again) ");
              v15 = 1;
            }
            goto LABEL_67;
          }
          Session = 0;
        }
        if ( vbRequireShutdownProcessing != 1 && vbAnticipateShutdownProcessingNeeded != 1 || vbRebootInProgress )
          goto LABEL_69;
        v20 = I_ScRegisterPreshutdownRestart(*a2, 0);
        if ( v20 == 1115 )
        {
          CBSWdsLogLight(
            0x4000000,
            0,
            0,
            "Trusted Installer cannot stop right now, because the system shutdown it was waiting for has started.");
        }
        else
        {
          if ( !v20 )
          {
            CBSWdsLogLight(
              0x4000000,
              0,
              0,
              "Trusted Installer successfully registered to be restarted for pre-shutdown.");
LABEL_69:
            vbShuttingdown = 1;
            MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v29);
            goto LABEL_84;
          }
          if ( v20 > 0 )
            v20 = (unsigned __int16)v20 | 0x80070000;
          CBSWdsLogLight(
            0x2000000,
            (unsigned int)v20,
            1,
            "Failed registering for a pre-shutdown restart, Trusted Installer will stay running.");
        }
        v3 = 0;
LABEL_67:
        v18 = vdwServiceIdleTimeout;
        MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v29);
        break;
    }
  }
  CBSWdsLogLight(0x4000000, 0, 0, "Trusted Installer signaled for shutdown, going to exit.");
  MonitoredCritSecLocker::MonitoredCritSecLocker(
    (MonitoredCritSecLocker *)v29,
    (struct MonitoredCritSec *)&vScavengeHandlerLock,
    1);
  if ( CCbsTiSession::m_pIdleScavengeHandler )
  {
    CBSWdsLogLight(0x4000000, 0, 0, "A system shutdown was initiated while idle scavenging was running");
    if ( vhTiService )
    {
      ++vTiStatus.dwCheckPoint;
      *(_QWORD *)&vTiStatus.dwCurrentState = 3;
      vTiStatus.dwWin32ExitCode = 0;
      vTiStatus.dwWaitHint = 3600000;
      SetServiceStatus(vhTiService, &vTiStatus);
    }
    v22 = TiCorePrepareShutdownProcessing();
    if ( v22 < 0 )
      CBSWdsLogLight(0x4000000, (unsigned int)v22, 1, "Unable to prepare for shutdown processing");
    v23 = CCbsIdleHandler::StopScavenging(CCbsTiSession::m_pIdleScavengeHandler);
    if ( v23 < 0 )
      CBSWdsLogLight(0x4000000, (unsigned int)v23, 1, "Unable to stop scavenging");
    TiCoreFinalizeShutdownProcessing();
  }
  MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v29);
  v17 = 3;
  LOWORD(v8) = 0;
LABEL_84:
  TiTryChangeState(1);
  if ( vhTiService )
  {
    ++vTiStatus.dwCheckPoint;
    vTiStatus.dwWin32ExitCode = (unsigned __int16)v8;
    *(_QWORD *)&vTiStatus.dwCurrentState = 3;
    vTiStatus.dwWaitHint = 3600000;
    SetServiceStatus(vhTiService, &vTiStatus);
  }
  if ( v17 == 1 )
  {
    v24 = L"SHUTDOWN_REASON_ERROR";
  }
  else if ( v17 == 2 )
  {
    v24 = L"SHUTDOWN_REASON_AUTOSTOP";
  }
  else
  {
    switch ( vControlCommand )
    {
      case 1u:
        v24 = L"SHUTDOWN_REASON_NOTIFICATION:STOP";
        break;
      case 5u:
        v24 = L"SHUTDOWN_REASON_NOTIFICATION:SHUTDOWN";
        break;
      case 0xFu:
        v24 = L"SHUTDOWN_REASON_NOTIFICATION:PRESHUTDOWN";
        break;
      default:
        v24 = L"SHUTDOWN_REASON_NOTIFICATION:UNKNOWN";
        break;
    }
  }
  CBSWdsLogLight(0x4000000, 0, 0, "Trusted Installer is shutting down because: %S", v24);
  if ( !vbRebootInProgress
    && vbRequireShutdownProcessing
    && v17 == 3
    && vControlCommand == 15
    && (v25 = TiCoreShutdownProcessing(), v8 = v25, v25 < 0) )
  {
    CBSWdsLogLight(0x4000000, (unsigned int)v25, 1, "Failed to execute shutdown processing.");
  }
  else
  {
    if ( vhTiService )
    {
      ++vTiStatus.dwCheckPoint;
      vTiStatus.dwWin32ExitCode = (unsigned __int16)v8;
      *(_QWORD *)&vTiStatus.dwCurrentState = 3;
      vTiStatus.dwWaitHint = 15000;
      SetServiceStatus(vhTiService, &vTiStatus);
    }
    v26 = (*(__int64 (__fastcall **)(LPVOID, __int64 (__fastcall *)(), __int128 *, GUID *, int, _QWORD))(*(_QWORD *)ppv + 24LL))(
            ppv,
            DisconnectCallback,
            &v32,
            &GUID_000001da_0000_0000_c000_000000000046,
            5,
            0);
    v8 = v26;
    if ( v26 < 0 )
      CBSWdsLogLight(0x4000000, (unsigned int)v26, 1, "Unable to disconnect all objects.");
    if ( (unsigned int)IsWorkerProcessRunning() )
    {
      dword_14003F060 = 1;
      WaitForTiWorkerToShutdown();
    }
  }
LABEL_109:
  TiTryChangeState(1);
  if ( ppv )
  {
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
    ppv = 0;
  }
  if ( vhTiService )
  {
    ++vTiStatus.dwCheckPoint;
    vTiStatus.dwWin32ExitCode = (unsigned __int16)v8;
    *(_QWORD *)&vTiStatus.dwCurrentState = 3;
    vTiStatus.dwWaitHint = 300000;
    SetServiceStatus(vhTiService, &vTiStatus);
  }
  CBSWdsLogLight(0x4000000, 0, 0, "Ending the TrustedInstaller main loop.");
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140009b2c  push    rbp
0x140009b2e  push    rbx
0x140009b2f  push    rsi
0x140009b30  push    rdi
0x140009b31  push    r12
0x140009b33  push    r13
0x140009b35  push    r14
0x140009b37  push    r15
0x140009b39  lea     rbp, [rsp-1Fh]
0x140009b3e  sub     rsp, 98h
0x140009b45  mov     rax, cs:__security_cookie
0x140009b4c  xor     rax, rsp
0x140009b4f  mov     [rbp+57h+var_48], rax
0x140009b53  mov     r13, rdx
0x140009b56  lea     r9, aStartingTheTru_0; "Starting the TrustedInstaller main loop"...
0x140009b5d  mov     r15d, 4000000h
0x140009b63  xor     r8d, r8d
0x140009b66  mov     ecx, r15d
0x140009b69  xor     edx, edx
0x140009b6b  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009b70  xor     edi, edi
0x140009b72  mov     cs:?vdwServiceIdleTimeout@@3KA, 1D4C0h; ulong vdwServiceIdleTimeout
0x140009b7c  xorps   xmm0, xmm0
0x140009b7f  mov     [rbp+57h+var_70], edi
0x140009b82  lea     rax, [rbp+57h+var_90]
0x140009b86  mov     [rbp+57h+var_90], edi
0x140009b89  lea     r9, aIdleminutes; "IdleMinutes"
0x140009b90  mov     dword ptr [rbp+57h+Handles], edi
0x140009b93  lea     r14d, [rdi+1]
0x140009b97  mov     [rsp+0D0h+ppv], rax; unsigned int *
0x140009b9c  mov     r8d, r14d; unsigned int
0x140009b9f  lea     rdx, aSoftwareMicros_1; "SOFTWARE\\Microsoft\\TrustedInstaller"
0x140009ba6  movups  [rbp+57h+var_68], xmm0
0x140009baa  call    ?CbsRegQueryDWORDValue@@YAJPEAUHKEY__@@PEB_WK1PEAK@Z; CbsRegQueryDWORDValue(HKEY__ *,wchar_t const *,ulong,wchar_t const *,ulong *)
0x140009baf  test    eax, eax
0x140009bb1  jnz     short loc_140009BDE
0x140009bb3  mov     ebx, [rbp+57h+var_90]
0x140009bb6  test    ebx, ebx
0x140009bb8  jz      short loc_140009BDE
0x140009bba  lea     r9, aCustomTiIdleTi; "Custom TI Idle time set to %u minutes"
0x140009bc1  mov     dword ptr [rsp+0D0h+ppv], ebx
0x140009bc5  xor     r8d, r8d
0x140009bc8  xor     edx, edx
0x140009bca  mov     ecx, r15d
0x140009bcd  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009bd2  imul    eax, ebx, 0EA60h
0x140009bd8  mov     cs:?vdwServiceIdleTimeout@@3KA, eax; ulong vdwServiceIdleTimeout
0x140009bde  lea     rcx, [rbp+57h+Handles]; unsigned int *
0x140009be2  call    ?WdsSetupInProgress@@YAJPEAK_N@Z; WdsSetupInProgress(ulong *,bool)
0x140009be7  mov     ebx, 1Eh
0x140009bec  cmp     dword ptr [rbp+57h+Handles], edi
0x140009bef  jbe     short loc_140009C13
0x140009bf1  lea     r9, aRunningUnderSe; "Running under Setup's First boot, setti"...
0x140009bf8  mov     dword ptr [rsp+0D0h+ppv], ebx
0x140009bfc  xor     r8d, r8d
0x140009bff  xor     edx, edx
0x140009c01  mov     ecx, r15d
0x140009c04  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009c09  mov     cs:?vdwServiceIdleTimeout@@3KA, 1B7740h; ulong vdwServiceIdleTimeout
0x140009c13  cmp     cs:?vbRebootInProgress@@3HA, edi; int vbRebootInProgress
0x140009c19  jz      short loc_140009C3D
0x140009c1b  lea     r9, aCustomTiIdleTi_0; "Custom TI Idle time set to %u seconds, "...
0x140009c22  mov     cs:?vdwServiceIdleTimeout@@3KA, 7530h; ulong vdwServiceIdleTimeout
0x140009c2c  xor     r8d, r8d
0x140009c2f  mov     dword ptr [rsp+0D0h+ppv], ebx
0x140009c33  xor     edx, edx
0x140009c35  mov     ecx, r15d
0x140009c38  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009c3d  mov     rcx, cs:?vhTiService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x140009c44  test    rcx, rcx
0x140009c47  jz      short loc_140009CA8
0x140009c49  lea     rdx, ?vTiStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x140009c50  mov     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 4; _SERVICE_STATUS vTiStatus ...
0x140009c5a  mov     qword ptr cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 141h; _SERVICE_STATUS vTiStatus ...
0x140009c65  mov     qword ptr cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, rdi; _SERVICE_STATUS vTiStatus ...
0x140009c6c  call    cs:__imp_SetServiceStatus
0x140009c72  test    eax, eax
0x140009c74  jnz     short loc_140009CA8
0x140009c76  call    cs:__imp_GetLastError
0x140009c7c  mov     ebx, eax
0x140009c7e  test    eax, eax
0x140009c80  jle     short loc_140009C8B
0x140009c82  movzx   ebx, ax
0x140009c85  or      ebx, 80070000h
0x140009c8b  test    ebx, ebx
0x140009c8d  jns     short loc_140009CA8
0x140009c8f  lea     r9, aFailedToSetTru; "Failed to set Trusted Installer status "...
0x140009c96  mov     edx, ebx
0x140009c98  mov     r8d, r14d
0x140009c9b  mov     ecx, r15d
0x140009c9e  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009ca3  jmp     loc_14000A354
0x140009ca8  lea     r9, aTrustedinstall_6; "TrustedInstaller service starts success"...
0x140009caf  xor     r8d, r8d
0x140009cb2  xor     edx, edx
0x140009cb4  mov     ecx, r15d
0x140009cb7  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009cbc  mov     r8b, r14b; bool
0x140009cbf  lea     rdx, ?vTiStartupProcessingLock@@3UMonitoredCritSec@@A; struct MonitoredCritSec *
0x140009cc6  lea     rcx, [rbp+57h+var_88]; this
0x140009cca  call    ??0MonitoredCritSecLocker@@QEAA@AEAUMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(MonitoredCritSec &,bool)
0x140009ccf  lea     rax, ppv
0x140009cd6  mov     cs:?vComRegPhase@@3W4COM_REGISTER_PHASE@@A, r14d; COM_REGISTER_PHASE vComRegPhase
0x140009cdd  lea     r9, _GUID_000001da_0000_0000_c000_000000000046; riid
0x140009ce4  mov     [rsp+0D0h+ppv], rax; ppv
0x140009ce9  mov     r8d, r14d; dwClsContext
0x140009cec  lea     rcx, CLSID_ContextSwitcher; rclsid
0x140009cf3  xor     edx, edx; pUnkOuter
0x140009cf5  call    cs:__imp_CoCreateInstance
0x140009cfb  mov     ebx, eax
0x140009cfd  test    eax, eax
0x140009cff  jns     short loc_140009D23
0x140009d01  lea     r9, aFailedToCreate_19; "Failed to create context switcher."
0x140009d08  mov     r8d, r14d
0x140009d0b  mov     edx, eax
0x140009d0d  mov     ecx, r15d
0x140009d10  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009d15  lea     rcx, [rbp+57h+var_88]; this
0x140009d19  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x140009d1e  jmp     loc_14000A354
0x140009d23  mov     rcx, cs:ppv
0x140009d2a  lea     r9, _GUID_000001da_0000_0000_c000_000000000046
0x140009d31  mov     [rsp+0D0h+var_A8], rdi
0x140009d36  lea     r8, [rbp+57h+var_68]
0x140009d3a  lea     rdx, ConnectCallback
0x140009d41  mov     dword ptr [rsp+0D0h+ppv], 5
0x140009d49  mov     rax, [rcx]
0x140009d4c  mov     rax, [rax+18h]
0x140009d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009d55  mov     ebx, eax
0x140009d57  test    eax, eax
0x140009d59  jns     short loc_140009D77
0x140009d5b  cmp     cs:?vbServiceShuttingDown@@3HA, edi; int vbServiceShuttingDown
0x140009d61  mov     r8d, r14d
0x140009d64  mov     edx, eax
0x140009d66  mov     ecx, r15d
0x140009d69  jz      short loc_140009DB8
0x140009d6b  lea     r9, aUnableToInitia_1; "Unable to initialize all COM objects, i"...
0x140009d72  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009d77  lea     rcx, [rbp+57h+Handles]
0x140009d7b  mov     [rbp+57h+Handles], rdi
0x140009d7f  call    ?GetInitPointer@?$AutoComPtr@UIClassFactory@@@Windows@@QEAAPEAPEAUIClassFactory@@XZ; Windows::AutoComPtr<IClassFactory>::GetInitPointer(void)
0x140009d84  mov     r9d, r14d; samDesired
0x140009d87  mov     [rsp+0D0h+ppv], rax; phkResult
0x140009d8c  xor     r8d, r8d; ulOptions
0x140009d8f  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140009d96  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140009d9d  call    cs:__imp_RegOpenKeyExW
0x140009da3  lea     ecx, [rax-2]
0x140009da6  cmp     ecx, r14d
0x140009da9  jbe     short loc_140009DDE
0x140009dab  test    eax, eax
0x140009dad  jnz     short loc_140009DC4
0x140009daf  mov     cs:?vbReservesRebootPending@@3HA, r14d; int vbReservesRebootPending
0x140009db6  jmp     short loc_140009DE4
0x140009db8  lea     r9, aFailedToInitia_5; "Failed to initialize all COM objects."
0x140009dbf  jmp     loc_140009D10
0x140009dc4  test    ebx, ebx
0x140009dc6  jns     short loc_140009DE4
0x140009dc8  lea     r9, aUnableToCheckW; "Unable to check whether reserves are wa"...
0x140009dcf  mov     r8d, r14d
0x140009dd2  mov     edx, ebx
0x140009dd4  mov     ecx, r15d
0x140009dd7  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009ddc  jmp     short loc_140009DE4
0x140009dde  mov     cs:?vbReservesRebootPending@@3HA, edi; int vbReservesRebootPending
0x140009de4  cmp     cs:?vbRequireReboot@@3HA, edi; int vbRequireReboot
0x140009dea  jnz     short loc_140009DF4
0x140009dec  cmp     cs:?vbReservesRebootPending@@3HA, edi; int vbReservesRebootPending
0x140009df2  jz      short loc_140009E17
0x140009df4  xor     edx, edx
0x140009df6  xor     ecx, ecx
0x140009df8  call    TiCoreRegisterWinlogonNotification
0x140009dfd  mov     ebx, eax
0x140009dff  test    eax, eax
0x140009e01  jns     short loc_140009E17
0x140009e03  lea     r9, aUnableToReRegi; "Unable to re-register for Winlogon noti"...
0x140009e0a  mov     r8d, r14d
0x140009e0d  mov     edx, eax
0x140009e0f  mov     ecx, r15d
0x140009e12  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009e17  cmp     cs:?vbRebootInProgress@@3HA, edi; int vbRebootInProgress
0x140009e1d  jnz     short loc_140009E71
0x140009e1f  cmp     cs:?vbRebootPending@@3HA, edi; int vbRebootPending
0x140009e25  jnz     short loc_140009E58
0x140009e27  lea     rcx, [rbp+57h+var_70]; int *
0x140009e2b  call    ?TiRunStartupProcessingAndWait@@YAJPEAH@Z; TiRunStartupProcessingAndWait(int *)
0x140009e30  mov     ebx, eax
0x140009e32  test    eax, eax
0x140009e34  jns     short loc_140009E71
0x140009e36  lea     r9, aFailedACritica; "Failed a critical portion of startup pr"...
0x140009e3d  mov     r8d, r14d
0x140009e40  mov     edx, eax
0x140009e42  mov     ecx, r15d
0x140009e45  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009e4a  lea     rcx, [rbp+57h+Handles]
0x140009e4e  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x140009e53  jmp     loc_140009D15
0x140009e58  lea     r9, aTiStartedAndRe; "TI: started and RebootPending volatile "...
0x140009e5f  xor     r8d, r8d
0x140009e62  xor     edx, edx
0x140009e64  mov     ecx, r15d
0x140009e67  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009e6c  call    TiCoreRequireShutdownProcessing
0x140009e71  lea     r9, aTiStartupProce; "TI: Startup Processing completes, relea"...
0x140009e78  xor     r8d, r8d
0x140009e7b  xor     edx, edx
0x140009e7d  mov     ecx, r15d
0x140009e80  mov     r12b, dil
0x140009e83  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009e88  lea     rcx, [rbp+57h+Handles]
0x140009e8c  call    ?Close@?$AutoGenericHandleBase@PEAUHKEY__@@$0A@V?$AutoGenericHandle@PEAUHKEY__@@$0A@$1?CloseWithRegCloseKey@Detail@Windows@@YAXPEAU1@@Z@Windows@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<HKEY__ *,0,Windows::AutoGenericHandle<HKEY__ *,0,&Windows::Detail::CloseWithRegCloseKey(HKEY__ *)>>::Close(void)
0x140009e91  lea     rcx, [rbp+57h+var_88]; this
0x140009e95  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x140009e9a  call    TiCoreShouldWaitForWinlogonCreateSession
0x140009e9f  mov     r15b, al
0x140009ea2  test    al, al
0x140009ea4  jz      short loc_140009EBC
0x140009ea6  lea     r9, aRunningUnderSe_0; "Running under Setup's OOBE boot or when"...
0x140009ead  xor     r8d, r8d
0x140009eb0  xor     edx, edx
0x140009eb2  mov     ecx, 4000000h
0x140009eb7  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009ebc  mov     esi, 2
0x140009ec1  mov     edi, cs:?vdwServiceIdleTimeout@@3KA; ulong vdwServiceIdleTimeout
0x140009ec7  mov     rax, cs:?vhShutdownEvent@@3PEAXEA; void * vhShutdownEvent
0x140009ece  lea     rdx, [rbp+57h+Handles]; lpHandles
0x140009ed2  mov     [rbp+57h+Handles], rax
0x140009ed6  mov     r9d, 3E8h; dwMilliseconds
0x140009edc  mov     rax, cs:?vhServicingEvent@@3PEAXEA; void * vhServicingEvent
0x140009ee3  xor     r8d, r8d; bWaitAll
0x140009ee6  mov     ecx, esi; nCount
0x140009ee8  mov     [rbp+57h+var_50], rax
0x140009eec  mov     dword ptr [rsp+0D0h+ppv], 0; bAlertable
0x140009ef4  call    cs:__imp_WaitForMultipleObjectsEx
0x140009efa  test    eax, eax
0x140009efc  jz      loc_14000A0C8
0x140009f02  cmp     eax, 1
0x140009f05  jz      short loc_140009EC1
0x140009f07  cmp     eax, 0FFFFFFFFh
0x140009f0a  jz      loc_14000A085
0x140009f10  cmp     eax, 102h
0x140009f15  jnz     short loc_140009F3C
0x140009f17  cmp     cs:?vbAboutToSleep@@3HA, 0; int vbAboutToSleep
0x140009f1e  jz      short loc_140009F2C
0x140009f20  mov     cs:?vbAboutToSleep@@3HA, 0; int vbAboutToSleep
0x140009f2a  jmp     short loc_140009EC7
0x140009f2c  cmp     edi, 3E8h
0x140009f32  jbe     short loc_140009F3C
0x140009f34  add     edi, 0FFFFFC18h
0x140009f3a  jmp     short loc_140009EC7
0x140009f3c  lea     rax, vTiLock
0x140009f43  xor     edi, edi
0x140009f45  mov     [rbp+57h+var_80], rax
0x140009f49  lea     rax, ??_7TiCoreLocker@@6B@; const TiCoreLocker::`vftable'
0x140009f50  mov     [rbp+57h+var_88], rax
0x140009f54  mov     [rbp+57h+var_78], dil
0x140009f58  test    r14b, r14b
0x140009f5b  jz      loc_14000A03A
0x140009f61  cmp     cs:?vcInstances@@3JA, edi; long vcInstances
0x140009f67  jnz     loc_14000A03A
0x140009f6d  lea     rcx, [rbp+57h+var_88]; this
0x140009f71  call    ?TryLock@MonitoredCritSecLocker@@UEAA_NXZ; MonitoredCritSecLocker::TryLock(void)
0x140009f76  test    al, al
0x140009f78  jz      loc_14000A03A
0x140009f7e  cmp     cs:?vcInstances@@3JA, edi; long vcInstances
0x140009f84  jnz     loc_14000A03A
0x140009f8a  test    r15b, r15b
0x140009f8d  jz      short loc_140009FA0
0x140009f8f  mov     ecx, edi
0x140009f91  xor     eax, eax
0x140009f93  lock cmpxchg cs:dword_14004083C, ecx
0x140009f9b  jz      short loc_140009FF3
0x140009f9d  mov     r15b, dil
0x140009fa0  mov     r14d, 1
0x140009fa6  cmp     cs:?vbRequireShutdownProcessing@@3HA, r14d; int vbRequireShutdownProcessing
0x140009fad  jz      short loc_140009FBC
0x140009faf  cmp     cs:?vbAnticipateShutdownProcessingNeeded@@3HA, r14d; int vbAnticipateShutdownProcessingNeeded
0x140009fb6  jnz     loc_14000A06A
0x140009fbc  cmp     cs:?vbRebootInProgress@@3HA, edi; int vbRebootInProgress
0x140009fc2  jnz     loc_14000A06A
0x140009fc8  mov     rcx, [r13+0]
0x140009fcc  xor     edx, edx
0x140009fce  call    cs:__imp_I_ScRegisterPreshutdownRestart
0x140009fd4  cmp     eax, 45Bh
0x140009fd9  jnz     short loc_14000A013
0x140009fdb  lea     r9, aTrustedInstall_2; "Trusted Installer cannot stop right now"...
0x140009fe2  xor     r8d, r8d
0x140009fe5  xor     edx, edx
0x140009fe7  mov     ecx, 4000000h
0x140009fec  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x140009ff1  jmp     short loc_14000A037
0x140009ff3  test    r12b, r12b
0x140009ff6  jnz     short loc_14000A03A
0x140009ff8  lea     r9, aTiRejectedAnAu; "TI: Rejected an auto-stop attempt, beca"...
0x140009fff  xor     r8d, r8d
0x14000a002  xor     edx, edx
0x14000a004  mov     ecx, 4000000h
0x14000a009  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a00e  mov     r12b, 1
  ... truncated ...
```
