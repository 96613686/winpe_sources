# TiCoreStartupProcessing

- ea: `0x14000d5c8`
- end: `0x14000dca1`
- name: `TiCoreStartupProcessing`
- size: `1753`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14000a730`

## callees

- `0x1400023e0`
- `0x140002674`
- `0x140006344`
- `0x14000695c`
- `0x1400076ec`
- `0x14000bb20`
- `0x14000ca98`
- `0x14000ceb4`
- `0x14000d12c`
- `0x14000d420`
- `0x14000d5c8`
- `0x14000dca8`
- `0x140016098`
- `0x1400160e4`
- `0x140016180`
- `0x140016210`
- `0x1400165a4`
- `0x1400166f0`
- `0x140017658`
- `0x140019828`
- `0x140019878`
- `0x14001e32c`
- `0x14001e564`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x14000dbff`
- `api-ms-win-core-sysinfo-l1-2-0!GetOsSafeBootMode` at `0x14000dbff`

## string_xrefs

- `0x14000daf3`: `Unable to change Trusted Installer to demand-start service.`
- `0x14000d6ac`: `Failed to open TrustedInstaller service to query and change config.`
- `0x14000d6e7`: `Failed to get current configuration of TrustedInstaller service.`
- `0x14000db3c`: `Startup: Failed initializing for create session notification.`
- `0x14000d7e4`: `Startup: Recovery attempt %d`
- `0x14000da0a`: `Startup: Servicing Stack update applied, finishing startup process.`
- `0x14000d85c`: `Startup: Servicing Stack update applied with other pending operations, restarting TiWorker for further processing.`
- `0x14000d974`: `Keeping Trusted Installer as auto-start`
- `0x14000d99d`: `Failed during startup processing and a reboot is still required.`
- `0x14000da55`: `Startup processing completed.`
- `0x14000db9c`: `Registering for pre-shutdown notification to complete the pended operation`
- `0x14000dbea`: `No startup processing required, TrustedInstaller service was not set as autostart`

## pseudocode

```c
__int64 __fastcall TiCoreStartupProcessing(_DWORD *a1, bool a2)
{
  int v2; // r13d
  Windows::Detail *v4; // rdi
  unsigned int v5; // esi
  struct SC_HANDLE__ *v6; // rdx
  int v7; // eax
  __int64 v8; // rcx
  int v9; // eax
  SC_HANDLE v10; // rbx
  int Config; // eax
  int v12; // eax
  int WorkerProcess; // eax
  int SessionNotifyInitialize; // eax
  __int64 v15; // rdx
  unsigned int v16; // eax
  int v17; // r12d
  char v18; // r13
  char v19; // al
  __int64 v20; // rcx
  int v21; // r9d
  int v22; // eax
  int v23; // eax
  int v24; // eax
  __int64 v25; // rcx
  char v27; // [rsp+30h] [rbp-39h]
  char v28[7]; // [rsp+31h] [rbp-38h] BYREF
  void *v29; // [rsp+38h] [rbp-31h] BYREF
  _BYTE v30[24]; // [rsp+40h] [rbp-29h] BYREF
  unsigned int v31[2]; // [rsp+58h] [rbp-11h] BYREF
  SC_HANDLE hService; // [rsp+60h] [rbp-9h] BYREF
  unsigned int v33; // [rsp+68h] [rbp-1h] BYREF

  v2 = 0;
  v31[0] = 0;
  v4 = 0;
  v33 = 0;
  hService = 0;
  v29 = 0;
  v28[0] = 0;
  if ( !a1 )
  {
    v5 = -2147467261;
    CBSWdsLogLight(0x4000000u, 0x80004003, (size_t *)1, "No processing required result specified");
    goto LABEL_92;
  }
  *a1 = 0;
  WdsSetupInProgress(v31, a2);
  if ( v31[0] )
  {
    CBSWdsLogLight(
      0x4000000u,
      0,
      0,
      "Setup in progress, aborting startup processing checks. Will allow logon if asked by Winlogon.");
    v7 = TiCoreRegisterWinlogonNotification(0, v28);
    v5 = v7;
    if ( v7 < 0 )
      CBSWdsLogLight(
        0x4000000u,
        (unsigned int)v7,
        (size_t *)1,
        "Startup: Failed registering for Winlogon notifications, continuing without it.");
    *a1 = 0;
    goto LABEL_92;
  }
  WdsOobeInProgress(&v33);
  v9 = SvcOpen(v8, 3u, &hService);
  v5 = v9;
  if ( v9 < 0 )
  {
    CBSWdsLogLight(
      0x4000000u,
      (unsigned int)v9,
      (size_t *)1,
      "Failed to open TrustedInstaller service to query and change config.");
    v4 = (Windows::Detail *)hService;
    goto LABEL_92;
  }
  v4 = (Windows::Detail *)hService;
  v10 = 0;
  Config = SvcQueryConfig(hService, (LPQUERY_SERVICE_CONFIGW *)&v29);
  v5 = Config;
  if ( Config >= 0 )
  {
    if ( *((_DWORD *)v29 + 1) == 2 )
    {
      if ( !vbRebootPending )
      {
        if ( !vbReservesRebootPending )
        {
          *a1 = 1;
          TiCoreSuspendWinlogonUI();
          v12 = TiCoreRegisterWinlogonNotification(1, v28);
          if ( v12 < 0 )
            CBSWdsLogLight(
              0x4000000u,
              (unsigned int)v12,
              (size_t *)1,
              "Startup: Failed registering for Winlogon notifications, continuing without it.");
          while ( 1 )
          {
            hService = 0;
            *(_QWORD *)v31 = 0;
            WorkerProcess = TiCoreGetWorkerProcess(0, (void **)&hService);
            v5 = WorkerProcess;
            if ( WorkerProcess < 0 )
              break;
            SessionNotifyInitialize = TiCoreCreateSessionNotifyInitialize();
            v5 = SessionNotifyInitialize;
            if ( SessionNotifyInitialize < 0 )
            {
              CBSWdsLogLight(
                0x4000000u,
                (unsigned int)SessionNotifyInitialize,
                (size_t *)1,
                "Startup: Failed initializing for create session notification.");
              goto LABEL_75;
            }
            MonitoredCritSecLocker::MonitoredCritSecLocker(
              (MonitoredCritSecLocker *)v30,
              (struct MonitoredCritSec *)&stru_1400406F8,
              1);
            dword_140040840 = 0;
            MonitoredCritSecLocker::~MonitoredCritSecLocker((MonitoredCritSecLocker *)v30);
            if ( *(_QWORD *)v31 )
              INTERNAL_ERROR_ACTION(-1073741595);
            if ( (**(__int64 (__fastcall ***)(SC_HANDLE, GUID *, unsigned int *))hService)(
                   hService,
                   &IID_ICbsWorker2,
                   v31) < 0 )
            {
              CBSWdsLogLight(
                0x4000000u,
                0,
                0,
                "Startup: Proceeding with legacy StartupProcessing interface, no recovery from crash supported");
              v16 = (*(__int64 (__fastcall **)(SC_HANDLE))(*(_QWORD *)hService + 64LL))(hService);
            }
            else
            {
              v15 = 1;
              if ( v2 > 0 )
              {
                CBSWdsLogLight(0x4000000u, 0, 0, "Startup: Recovery attempt %d", v2);
                v15 = 2;
              }
              v16 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v31 + 144LL))(*(_QWORD *)v31, v15);
            }
            v17 = 0;
            v5 = v16;
            if ( v16 == 985091 )
            {
              TiCoreSuspendWinlogonUI();
              WaitForTiWorkerToShutdown();
              CBSWdsLogLight(0x4000000u, 0, 0, "Startup: Servicing Stack update applied, finishing startup process.");
              v5 = 0;
              if ( *(_QWORD *)v31 )
              {
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 16LL))(*(_QWORD *)v31);
                *(_QWORD *)v31 = 0;
              }
              if ( hService )
                (*(void (__fastcall **)(SC_HANDLE))(*(_QWORD *)hService + 16LL))(hService);
LABEL_57:
              v18 = 0;
              v27 = 0;
              v17 = 1;
              CBSWdsLogLight(0x4000000u, v5, (size_t *)1, "Startup processing completed.");
              v31[0] = 0;
              goto LABEL_58;
            }
            if ( v16 == 985139 )
            {
              TiCoreSuspendWinlogonUI();
              WaitForTiWorkerToShutdown();
              CBSWdsLogLight(
                0x4000000u,
                0,
                0,
                "Startup: Servicing Stack update applied with other pending operations, restarting TiWorker for further processing.");
            }
            else
            {
              if ( v16 != -2147417848
                && v16 != 1726
                && !(*(unsigned int (__fastcall **)(SC_HANDLE))(*(_QWORD *)hService + 104LL))(hService) )
              {
                if ( v5 == -2147021886 || v5 == -2147021879 )
                {
                  v10 = hService;
                  hService = 0;
                }
LABEL_40:
                if ( *(_QWORD *)v31 )
                {
                  (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 16LL))(*(_QWORD *)v31);
                  *(_QWORD *)v31 = 0;
                }
LABEL_42:
                if ( hService )
                  (*(void (__fastcall **)(SC_HANDLE))(*(_QWORD *)hService + 16LL))(hService);
                if ( v5 == -2147021886 )
                {
                  v18 = 0;
                  v27 = 0;
                  CBSWdsLogLight(0x4000000u, 0, 0, "Keeping Trusted Installer as auto-start");
                  v19 = 0;
                  v31[0] = 1;
                }
                else
                {
                  if ( v5 == -2147021879 )
                  {
                    CBSWdsLogLight(0x4000000u, 0, 0, "Failed during startup processing and a reboot is still required.");
                    v18 = 0;
                    v31[0] = 1;
                    v19 = 0;
                  }
                  else
                  {
                    if ( v5 != -2147467260 )
                      goto LABEL_57;
                    CBSWdsLogLight(
                      0x4000000u,
                      0,
                      0,
                      "Aborted processing startup actions, requiring shutdown processing and will try startup processing "
                      "again in the future.");
                    TiCoreRequireShutdownProcessing(v20);
                    v19 = 1;
                    v31[0] = 0;
                    v18 = 0;
                  }
                  v27 = v19;
                }
                if ( v19 )
                {
LABEL_58:
                  if ( (unsigned __int8)IsRestoreReservesNeeded() )
                    v17 = 0;
                }
                if ( v31[0] && v33 )
                  v18 = v28[0] != 0;
                TiCoreSuspendWinlogonUI();
                TiCoreUnregisterWinlogonNotification(1, v31[0], v17, v21, v18, v27);
                TiCoreCreateSessionNotifyFinalize();
                if ( v27 )
                {
                  v22 = TiCoreRegisterWinlogonNotification(0, 0);
                  v5 = v22;
                  if ( v22 < 0 )
                    CBSWdsLogLight(
                      0x4000000u,
                      (unsigned int)v22,
                      (size_t *)1,
                      "Startup: Failed registering for Winlogon notifications, continuing without it.");
                }
                if ( v17 )
                {
                  v23 = TiCoreSetTiDemandStart();
                  if ( v23 < 0 )
                    CBSWdsLogLight(
                      0x4000000u,
                      (unsigned int)v23,
                      (size_t *)1,
                      "Unable to change Trusted Installer to demand-start service.");
                }
                if ( v31[0] )
                {
                  if ( !v18 )
                  {
                    v24 = TiCoreInitiateRestart(v10);
                    if ( v24 < 0 )
                      CBSWdsLogLight(
                        0x4000000u,
                        (unsigned int)v24,
                        (size_t *)1,
                        "Failed to initiate restart... we'll just have to hope for the best.");
                  }
                }
                goto LABEL_88;
              }
              CBSWdsLogLight(0x4000000u, 0, 0, "Startup: TiWorker likely terminated unexpectedly.");
              v5 = -2146498503;
              if ( v2 >= 2 )
                goto LABEL_40;
              if ( !*(_QWORD *)v31 )
                goto LABEL_42;
              ++v2;
              CBSWdsLogLight(0x4000000u, 0, 0, "Startup: Restarting TiWorker and proceeding with recovery.");
              TiCoreSuspendWinlogonUI();
              WaitForTiWorkerToShutdown();
            }
            if ( *(_QWORD *)v31 )
            {
              (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 16LL))(*(_QWORD *)v31);
              *(_QWORD *)v31 = 0;
            }
            if ( hService )
              (*(void (__fastcall **)(SC_HANDLE))(*(_QWORD *)hService + 16LL))(hService);
          }
          CBSWdsLogLight(0x4000000u, (unsigned int)WorkerProcess, (size_t *)1, "Startup: Failed to get worker process");
LABEL_75:
          if ( *(_QWORD *)v31 )
          {
            (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v31 + 16LL))(*(_QWORD *)v31);
            *(_QWORD *)v31 = 0;
          }
          if ( hService )
            (*(void (__fastcall **)(SC_HANDLE))(*(_QWORD *)hService + 16LL))(hService);
          goto LABEL_88;
        }
LABEL_82:
        CBSWdsLogLight(0x4000000u, 0, 0, "No startup processing executed. Reserves are waiting for a reboot.");
        goto LABEL_88;
      }
    }
    else if ( !vbRebootPending )
    {
      if ( !vbReservesRebootPending )
      {
        v33 = 0;
        CBSWdsLogLight(
          0x4000000u,
          0,
          0,
          "No startup processing required, TrustedInstaller service was not set as autostart");
        if ( (unsigned int)GetOsSafeBootMode(&v33) )
        {
          if ( v33 )
            CBSWdsLogLight(0x4000000u, 0, 0, "NonStart: Windows is in Safe Mode.");
        }
        else
        {
          CBSWdsLogLight(0x4000000u, 0, 0, "Unable to detect if system is in Safe Mode");
        }
        *a1 = 0;
        vbEnsureNoStartupProcessing = 1;
        goto LABEL_88;
      }
      goto LABEL_82;
    }
    CBSWdsLogLight(0x4000000u, 0, 0, "Registering for pre-shutdown notification to complete the pended operation");
    TiCoreRequireShutdownProcessing(v25);
    goto LABEL_88;
  }
  CBSWdsLogLight(
    0x4000000u,
    (unsigned int)Config,
    (size_t *)1,
    "Failed to get current configuration of TrustedInstaller service.");
LABEL_88:
  if ( v29 )
    operator delete(v29);
  if ( v10 )
    (*(void (__fastcall **)(SC_HANDLE))(*(_QWORD *)v10 + 16LL))(v10);
LABEL_92:
  if ( v4 )
    Windows::Detail::CloseWithCloseServiceHandle(v4, v6);
  return v5;
}

```

## disassembly

```asm
0x14000d5c8  push    rbp
0x14000d5ca  push    rbx
0x14000d5cb  push    rsi
0x14000d5cc  push    rdi
0x14000d5cd  push    r12
0x14000d5cf  push    r13
0x14000d5d1  push    r14
0x14000d5d3  push    r15
0x14000d5d5  lea     rbp, [rsp-1Fh]
0x14000d5da  sub     rsp, 88h
0x14000d5e1  mov     rax, cs:__security_cookie
0x14000d5e8  xor     rax, rsp
0x14000d5eb  mov     [rbp+57h+var_50], rax
0x14000d5ef  xor     r13d, r13d
0x14000d5f2  mov     r12, rcx
0x14000d5f5  mov     [rbp+57h+var_68], r13d
0x14000d5f9  mov     edi, r13d
0x14000d5fc  mov     [rbp+57h+var_58], r13d
0x14000d600  mov     [rbp+57h+hService], r13
0x14000d604  mov     [rbp+57h+var_88], r13
0x14000d608  mov     [rbp+57h+var_8F], r13b
0x14000d60c  test    rcx, rcx
0x14000d60f  jnz     short loc_14000D632
0x14000d611  lea     r8d, [rcx+1]
0x14000d615  mov     esi, 80004003h
0x14000d61a  mov     edx, esi
0x14000d61c  lea     r9, aNoProcessingRe; "No processing required result specified"
0x14000d623  mov     ecx, 4000000h
0x14000d628  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d62d  jmp     loc_14000DC67
0x14000d632  mov     [rcx], r13d
0x14000d635  lea     rcx, [rbp+57h+var_68]; unsigned int *
0x14000d639  call    ?WdsSetupInProgress@@YAJPEAK_N@Z; WdsSetupInProgress(ulong *,bool)
0x14000d63e  cmp     [rbp+57h+var_68], r13d
0x14000d642  jbe     short loc_14000D68F
0x14000d644  mov     r14d, 4000000h
0x14000d64a  lea     r9, aSetupInProgres; "Setup in progress, aborting startup pro"...
0x14000d651  mov     ecx, r14d
0x14000d654  xor     r8d, r8d
0x14000d657  xor     edx, edx
0x14000d659  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d65e  lea     rdx, [rbp+57h+var_8F]
0x14000d662  xor     ecx, ecx
0x14000d664  call    TiCoreRegisterWinlogonNotification
0x14000d669  mov     esi, eax
0x14000d66b  test    eax, eax
0x14000d66d  jns     short loc_14000D686
0x14000d66f  lea     r9, aStartupFailedR; "Startup: Failed registering for Winlogo"...
0x14000d676  mov     r8d, 1
0x14000d67c  mov     edx, eax
0x14000d67e  mov     ecx, r14d
0x14000d681  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d686  mov     [r12], r13d
0x14000d68a  jmp     loc_14000DC67
0x14000d68f  lea     rcx, [rbp+57h+var_58]; unsigned int *
0x14000d693  call    ?WdsOobeInProgress@@YAJPEAK@Z; WdsOobeInProgress(ulong *)
0x14000d698  lea     r8, [rbp+57h+hService]
0x14000d69c  mov     edx, 3
0x14000d6a1  call    SvcOpen
0x14000d6a6  mov     esi, eax
0x14000d6a8  test    eax, eax
0x14000d6aa  jns     short loc_14000D6CE
0x14000d6ac  lea     r9, aFailedToOpenTr_0; "Failed to open TrustedInstaller service"...
0x14000d6b3  mov     r8d, 1
0x14000d6b9  mov     edx, eax
0x14000d6bb  mov     ecx, 4000000h
0x14000d6c0  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d6c5  mov     rdi, [rbp+57h+hService]
0x14000d6c9  jmp     loc_14000DC67
0x14000d6ce  mov     rdi, [rbp+57h+hService]
0x14000d6d2  lea     rdx, [rbp+57h+var_88]
0x14000d6d6  mov     rcx, rdi; hService
0x14000d6d9  mov     rbx, r13
0x14000d6dc  call    SvcQueryConfig
0x14000d6e1  mov     esi, eax
0x14000d6e3  test    eax, eax
0x14000d6e5  jns     short loc_14000D705
0x14000d6e7  lea     r9, aFailedToGetCur; "Failed to get current configuration of "...
0x14000d6ee  mov     r8d, 1
0x14000d6f4  mov     ecx, 4000000h
0x14000d6f9  mov     edx, eax
0x14000d6fb  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d700  jmp     loc_14000DC3D
0x14000d705  mov     rax, [rbp+57h+var_88]
0x14000d709  cmp     dword ptr [rax+4], 2
0x14000d70d  jnz     loc_14000DB93
0x14000d713  cmp     cs:?vbRebootPending@@3HA, r13d; int vbRebootPending
0x14000d71a  jnz     loc_14000DB9C
0x14000d720  cmp     cs:?vbReservesRebootPending@@3HA, r13d; int vbReservesRebootPending
0x14000d727  jnz     loc_14000DBC5
0x14000d72d  mov     r15d, 1
0x14000d733  mov     [r12], r15d
0x14000d737  call    TiCoreSuspendWinlogonUI
0x14000d73c  lea     rdx, [rbp+57h+var_8F]
0x14000d740  mov     ecx, r15d
0x14000d743  call    TiCoreRegisterWinlogonNotification
0x14000d748  mov     r14d, 4000000h
0x14000d74e  test    eax, eax
0x14000d750  jns     short loc_14000D766
0x14000d752  lea     r9, aStartupFailedR; "Startup: Failed registering for Winlogo"...
0x14000d759  mov     r8d, r15d
0x14000d75c  mov     edx, eax
0x14000d75e  mov     ecx, r14d
0x14000d761  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d766  lea     rdx, [rbp+57h+hService]
0x14000d76a  mov     [rbp+57h+hService], rbx
0x14000d76e  xor     ecx, ecx
0x14000d770  mov     qword ptr [rbp+57h+var_68], rbx
0x14000d774  call    TiCoreGetWorkerProcess
0x14000d779  mov     esi, eax
0x14000d77b  test    eax, eax
0x14000d77d  js      loc_14000DB45
0x14000d783  call    TiCoreCreateSessionNotifyInitialize
0x14000d788  mov     esi, eax
0x14000d78a  test    eax, eax
0x14000d78c  js      loc_14000DB3C
0x14000d792  mov     r8b, r15b; bool
0x14000d795  lea     rdx, stru_1400406F8; struct MonitoredCritSec *
0x14000d79c  lea     rcx, [rbp+57h+var_80]; this
0x14000d7a0  call    ??0MonitoredCritSecLocker@@QEAA@AEAUMonitoredCritSec@@_N@Z; MonitoredCritSecLocker::MonitoredCritSecLocker(MonitoredCritSec &,bool)
0x14000d7a5  lea     rcx, [rbp+57h+var_80]; this
0x14000d7a9  mov     cs:dword_140040840, ebx
0x14000d7af  call    ??1MonitoredCritSecLocker@@UEAA@XZ; MonitoredCritSecLocker::~MonitoredCritSecLocker(void)
0x14000d7b4  cmp     qword ptr [rbp+57h+var_68], rbx
0x14000d7b8  jnz     loc_14000DC96
0x14000d7be  mov     rcx, [rbp+57h+hService]
0x14000d7c2  lea     r8, [rbp+57h+var_68]
0x14000d7c6  lea     rdx, IID_ICbsWorker2
0x14000d7cd  mov     rax, [rcx]
0x14000d7d0  mov     rax, [rax]
0x14000d7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7d8  test    eax, eax
0x14000d7da  js      short loc_14000D817
0x14000d7dc  mov     edx, r15d
0x14000d7df  test    r13d, r13d
0x14000d7e2  jle     short loc_14000D802
0x14000d7e4  lea     r9, aStartupRecover; "Startup: Recovery attempt %d"
0x14000d7eb  mov     [rsp+0C0h+var_A0], r13d
0x14000d7f0  xor     r8d, r8d
0x14000d7f3  xor     edx, edx
0x14000d7f5  mov     ecx, r14d
0x14000d7f8  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d7fd  mov     edx, 2
0x14000d802  mov     rcx, qword ptr [rbp+57h+var_68]
0x14000d806  mov     rax, [rcx]
0x14000d809  mov     rax, [rax+90h]
0x14000d810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d815  jmp     short loc_14000D83B
0x14000d817  lea     r9, aStartupProceed; "Startup: Proceeding with legacy Startup"...
0x14000d81e  xor     r8d, r8d
0x14000d821  xor     edx, edx
0x14000d823  mov     ecx, r14d
0x14000d826  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d82b  mov     rcx, [rbp+57h+hService]
0x14000d82f  mov     rax, [rcx]
0x14000d832  mov     rax, [rax+40h]
0x14000d836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d83b  xor     r12d, r12d
0x14000d83e  mov     esi, eax
0x14000d840  cmp     eax, 0F0803h
0x14000d845  jz      loc_14000DA00
0x14000d84b  cmp     eax, 0F0833h
0x14000d850  jnz     short loc_14000D872
0x14000d852  call    TiCoreSuspendWinlogonUI
0x14000d857  call    WaitForTiWorkerToShutdown
0x14000d85c  lea     r9, aStartupServici_0; "Startup: Servicing Stack update applied"...
0x14000d863  xor     r8d, r8d
0x14000d866  xor     edx, edx
0x14000d868  mov     ecx, r14d
0x14000d86b  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d870  jmp     short loc_14000D8E4
0x14000d872  cmp     esi, 80010108h
0x14000d878  jz      short loc_14000D89A
0x14000d87a  cmp     esi, 6BEh
0x14000d880  jz      short loc_14000D89A
0x14000d882  mov     rcx, [rbp+57h+hService]
0x14000d886  mov     rax, [rcx]
0x14000d889  mov     rax, [rax+68h]
0x14000d88d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d892  test    eax, eax
0x14000d894  jz      loc_14000D91B
0x14000d89a  lea     r9, aStartupTiworke; "Startup: TiWorker likely terminated une"...
0x14000d8a1  xor     r8d, r8d
0x14000d8a4  xor     edx, edx
0x14000d8a6  mov     ecx, r14d
0x14000d8a9  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d8ae  mov     esi, 800F0839h
0x14000d8b3  cmp     r13d, 2
0x14000d8b7  jge     short loc_14000D937
0x14000d8b9  cmp     qword ptr [rbp+57h+var_68], rbx
0x14000d8bd  jz      loc_14000D954
0x14000d8c3  lea     r9, aStartupRestart; "Startup: Restarting TiWorker and procee"...
0x14000d8ca  xor     r8d, r8d
0x14000d8cd  xor     edx, edx
0x14000d8cf  mov     ecx, r14d
0x14000d8d2  add     r13d, r15d
0x14000d8d5  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d8da  call    TiCoreSuspendWinlogonUI
0x14000d8df  call    WaitForTiWorkerToShutdown
0x14000d8e4  mov     rcx, qword ptr [rbp+57h+var_68]
0x14000d8e8  test    rcx, rcx
0x14000d8eb  jz      short loc_14000D8FD
0x14000d8ed  mov     rax, [rcx]
0x14000d8f0  mov     rax, [rax+10h]
0x14000d8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d8f9  mov     qword ptr [rbp+57h+var_68], rbx
0x14000d8fd  mov     rcx, [rbp+57h+hService]
0x14000d901  test    rcx, rcx
0x14000d904  jz      loc_14000D766
0x14000d90a  mov     rax, [rcx]
0x14000d90d  mov     rax, [rax+10h]
0x14000d911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d916  jmp     loc_14000D766
0x14000d91b  cmp     esi, 80070BC2h
0x14000d921  jz      short loc_14000D92B
0x14000d923  cmp     esi, 80070BC9h
0x14000d929  jnz     short loc_14000D937
0x14000d92b  mov     rbx, [rbp+57h+hService]
0x14000d92f  mov     [rbp+57h+hService], 0
0x14000d937  mov     rcx, qword ptr [rbp+57h+var_68]
0x14000d93b  test    rcx, rcx
0x14000d93e  jz      short loc_14000D954
0x14000d940  mov     rax, [rcx]
0x14000d943  mov     rax, [rax+10h]
0x14000d947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d94c  mov     qword ptr [rbp+57h+var_68], 0
0x14000d954  mov     rcx, [rbp+57h+hService]
0x14000d958  test    rcx, rcx
0x14000d95b  jz      short loc_14000D969
0x14000d95d  mov     rax, [rcx]
0x14000d960  mov     rax, [rax+10h]
0x14000d964  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d969  cmp     esi, 80070BC2h
0x14000d96f  jnz     short loc_14000D995
0x14000d971  xor     r13b, r13b
0x14000d974  lea     r9, aKeepingTrusted; "Keeping Trusted Installer as auto-start"
0x14000d97b  xor     r8d, r8d
0x14000d97e  mov     [rbp+57h+var_90], r13b
0x14000d982  xor     edx, edx
0x14000d984  mov     ecx, r14d
0x14000d987  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d98c  mov     al, r13b
0x14000d98f  mov     [rbp+57h+var_68], r15d
0x14000d993  jmp     short loc_14000D9F1
0x14000d995  cmp     esi, 80070BC9h
0x14000d99b  jnz     short loc_14000D9BC
0x14000d99d  lea     r9, aFailedDuringSt; "Failed during startup processing and a "...
0x14000d9a4  xor     r8d, r8d
0x14000d9a7  xor     edx, edx
0x14000d9a9  mov     ecx, r14d
0x14000d9ac  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d9b1  xor     r13b, r13b
0x14000d9b4  mov     [rbp+57h+var_68], r15d
0x14000d9b8  xor     al, al
0x14000d9ba  jmp     short loc_14000D9EE
0x14000d9bc  cmp     esi, 80004004h
0x14000d9c2  jnz     loc_14000DA4E
0x14000d9c8  lea     r9, aAbortedProcess; "Aborted processing startup actions, req"...
0x14000d9cf  xor     r8d, r8d
0x14000d9d2  xor     edx, edx
0x14000d9d4  mov     ecx, r14d
0x14000d9d7  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d9dc  call    TiCoreRequireShutdownProcessing
0x14000d9e1  mov     al, r15b
0x14000d9e4  mov     [rbp+57h+var_68], 0
0x14000d9eb  xor     r13b, r13b
0x14000d9ee  mov     [rbp+57h+var_90], al
0x14000d9f1  test    r12d, r12d
0x14000d9f4  jnz     short loc_14000DA73
0x14000d9f6  test    al, al
0x14000d9f8  jz      loc_14000DA80
0x14000d9fe  jmp     short loc_14000DA73
0x14000da00  call    TiCoreSuspendWinlogonUI
0x14000da05  call    WaitForTiWorkerToShutdown
0x14000da0a  lea     r9, aStartupServici; "Startup: Servicing Stack update applied"...
0x14000da11  xor     r8d, r8d
0x14000da14  xor     edx, edx
0x14000da16  mov     ecx, r14d
0x14000da19  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000da1e  mov     rcx, qword ptr [rbp+57h+var_68]
0x14000da22  xor     esi, esi
0x14000da24  test    rcx, rcx
0x14000da27  jz      short loc_14000DA39
0x14000da29  mov     rax, [rcx]
0x14000da2c  mov     rax, [rax+10h]
0x14000da30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da35  mov     qword ptr [rbp+57h+var_68], rbx
0x14000da39  mov     rcx, [rbp+57h+hService]
0x14000da3d  test    rcx, rcx
0x14000da40  jz      short loc_14000DA4E
0x14000da42  mov     rax, [rcx]
0x14000da45  mov     rax, [rax+10h]
0x14000da49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000da4e  xor     r13b, r13b
0x14000da51  mov     [rbp+57h+var_90], 0
0x14000da55  lea     r9, aStartupProcess_0; "Startup processing completed."
0x14000da5c  mov     r8d, r15d
0x14000da5f  mov     edx, esi
0x14000da61  mov     ecx, r14d
0x14000da64  mov     r12d, r15d
  ... truncated ...
```
