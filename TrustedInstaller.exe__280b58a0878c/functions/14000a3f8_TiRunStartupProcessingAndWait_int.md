# TiRunStartupProcessingAndWait(int *)

- ea: `0x14000a3f8`
- end: `0x14000a723`
- name: `?TiRunStartupProcessingAndWait@@YAJPEAH@Z`
- size: `811`
- prototype: `__int64 __fastcall(int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x140009b2c`

## callees

- `0x1400023e0`
- `0x14000a3f8`
- `0x14000c8e0`
- `0x14000ca08`
- `0x14000ca98`
- `0x14000cf8c`
- `0x14000dca8`
- `0x140017658`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14000a4c4`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14000a4c4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000a5ed`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000a5ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a45b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a4de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a5a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a67a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a6aa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a45b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a4de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a5a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a67a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000a6aa`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x14000a66a`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeThread` at `0x14000a66a`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x14000a59e`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x14000a59e`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14000a44d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14000a44d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a6e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000a6e6`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000a571`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000a571`

## string_xrefs

- `0x14000a472`: `Failed to create startup processing thread.`
- `0x14000a526`: `Startup: A system shutdown was initiated while waiting for startup to complete`
- `0x14000a583`: `Startup: Attempting to terminate the startup thread.`
- `0x14000a5bb`: `Startup: Failed attempting to terminate the startup thread.`
- `0x14000a5fe`: `Startup: Startup processing completed.  Allowing shutdown to proceed`
- `0x14000a6c0`: `Startup: Failed to wait on startup thread.  Wait result: 0x%x`
- `0x14000a509`: `Startup processing thread terminated normally`
- `0x14000a4f3`: `Failed to wait on startup thread.  Wait result: 0x%x`
- `0x14000a68d`: `Failed getting startup thread result`

## pseudocode

```c
__int64 __fastcall TiRunStartupProcessingAndWait(int *a1)
{
  HANDLE Thread; // r14
  signed int LastError; // eax
  signed int v4; // ebx
  DWORD v5; // eax
  DWORD v6; // edi
  signed int v7; // eax
  const char *v8; // r9
  int v9; // eax
  signed int v10; // eax
  bool v11; // sf
  DWORD v12; // r15d
  int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  __int64 dwCreationFlags; // [rsp+20h] [rbp-78h]
  void *v18; // [rsp+30h] [rbp-68h] BYREF
  DWORD ExitCode; // [rsp+38h] [rbp-60h] BYREF
  HANDLE Handles[2]; // [rsp+40h] [rbp-58h] BYREF

  *a1 = 0;
  ExitCode = 0;
  v18 = 0;
  Thread = CreateThread(0, 0, TiStartupThreadProc, 0, 0, 0);
  if ( !Thread )
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 >= 0 )
      v4 = -2147467259;
    CBSWdsLogLight(0x4000000u, (unsigned int)v4, (size_t *)1, "Failed to create startup processing thread.");
    goto LABEL_46;
  }
  Handles[0] = vhShutdownEvent;
  Handles[1] = Thread;
  v5 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
  v6 = v5;
  if ( !v5 )
  {
    CBSWdsLogLight(0x4000000u, 0, 0, "Startup: A system shutdown was initiated while waiting for startup to complete");
    if ( vhTiService )
    {
      ++vTiStatus.dwCheckPoint;
      *(_QWORD *)&vTiStatus.dwCurrentState = 3;
      vTiStatus.dwWin32ExitCode = 0;
      vTiStatus.dwWaitHint = 30000;
      SetServiceStatus(vhTiService, &vTiStatus);
    }
    v9 = TiCorePrepareShutdownProcessing();
    if ( v9 == -2146498272 )
    {
      CBSWdsLogLight(0x4000000u, 0, 0, "Startup: Attempting to terminate the startup thread.");
      if ( !TerminateThread(Thread, 0x800F0920) )
      {
        v10 = GetLastError();
        v11 = v10 < 0;
        if ( v10 > 0 )
        {
          v10 = (unsigned __int16)v10 | 0x80070000;
          v11 = v10 < 0;
        }
        if ( v11 )
          CBSWdsLogLight(
            0x4000000u,
            (unsigned int)v10,
            (size_t *)1,
            "Startup: Failed attempting to terminate the startup thread.");
      }
    }
    else
    {
      if ( v9 < 0 )
        CBSWdsLogLight(0x4000000u, (unsigned int)v9, (size_t *)1, "Startup: Failed preparing for shutdown processing");
      v12 = WaitForSingleObject(Thread, 0xFFFFFFFF);
      if ( v12 )
      {
        v15 = GetLastError();
        v4 = v15;
        if ( v15 > 0 )
          v4 = (unsigned __int16)v15 | 0x80070000;
        LODWORD(dwCreationFlags) = v12;
        v8 = "Startup: Failed to wait on startup thread.  Wait result: 0x%x";
        goto LABEL_41;
      }
      CBSWdsLogLight(0x4000000u, 0, 0, "Startup: Startup processing completed.  Allowing shutdown to proceed");
      if ( (unsigned int)IsWorkerProcessRunning() )
        TiCoreFinalizeShutdownProcessing();
    }
    if ( (unsigned int)IsWorkerProcessRunning() )
    {
      if ( (int)TiCoreGetWorkerProcess(0, &v18) >= 0 )
      {
        v13 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v18 + 80LL))(v18);
        if ( v13 < 0 )
          CBSWdsLogLight(
            0x4000000u,
            (unsigned int)v13,
            (size_t *)1,
            "Startup: Failed to indicate reboot in progress to CBS.");
      }
    }
    *a1 = 1;
LABEL_31:
    if ( GetExitCodeThread(Thread, &ExitCode) )
    {
      v4 = ExitCode;
    }
    else
    {
      v14 = GetLastError();
      v4 = v14;
      if ( v14 > 0 )
        v4 = (unsigned __int16)v14 | 0x80070000;
      if ( v4 >= 0 )
        v4 = -2147467259;
      CBSWdsLogLight(0x4000000u, (unsigned int)v4, (size_t *)1, "Failed getting startup thread result");
    }
    goto LABEL_44;
  }
  if ( v5 == 1 )
  {
    CBSWdsLogLight(0x4000000u, 0, 0, "Startup processing thread terminated normally");
    goto LABEL_31;
  }
  v7 = GetLastError();
  v4 = v7;
  if ( v7 > 0 )
    v4 = (unsigned __int16)v7 | 0x80070000;
  LODWORD(dwCreationFlags) = v6;
  v8 = "Failed to wait on startup thread.  Wait result: 0x%x";
LABEL_41:
  if ( v4 >= 0 )
    v4 = -2147467259;
  CBSWdsLogLight(0x4000000u, (unsigned int)v4, (size_t *)1, v8, dwCreationFlags);
LABEL_44:
  if ( Thread != (HANDLE)-1LL )
    CloseHandle(Thread);
LABEL_46:
  if ( v18 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
  WaitForTiWorkerToShutdown();
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x14000a3f8  push    rbx
0x14000a3fa  push    rbp
0x14000a3fb  push    rsi
0x14000a3fc  push    rdi
0x14000a3fd  push    r14
0x14000a3ff  push    r15
0x14000a401  sub     rsp, 68h
0x14000a405  mov     rax, cs:__security_cookie
0x14000a40c  xor     rax, rsp
0x14000a40f  mov     [rsp+98h+var_48], rax
0x14000a414  mov     rbx, rcx
0x14000a417  mov     dword ptr [rcx], 0
0x14000a41d  xor     ecx, ecx; lpThreadAttributes
0x14000a41f  mov     [rsp+98h+lpThreadId], 0; lpThreadId
0x14000a428  xor     r9d, r9d; lpParameter
0x14000a42b  mov     [rsp+98h+ExitCode], 0
0x14000a433  lea     r8, ?TiStartupThreadProc@@YAKPEAX@Z; lpStartAddress
0x14000a43a  mov     [rsp+98h+var_68], 0
0x14000a443  xor     edx, edx; dwStackSize
0x14000a445  mov     dword ptr [rsp+98h+dwCreationFlags], 0; dwCreationFlags
0x14000a44d  call    cs:__imp_CreateThread
0x14000a453  mov     r14, rax
0x14000a456  test    rax, rax
0x14000a459  jnz     short loc_14000A498
0x14000a45b  call    cs:__imp_GetLastError
0x14000a461  mov     ebx, eax
0x14000a463  test    eax, eax
0x14000a465  jle     short loc_14000A470
0x14000a467  movzx   ebx, ax
0x14000a46a  or      ebx, 80070000h
0x14000a470  test    ebx, ebx
0x14000a472  lea     r9, aFailedToCreate_12; "Failed to create startup processing thr"...
0x14000a479  mov     eax, 80004005h
0x14000a47e  mov     r8d, 1
0x14000a484  cmovns  ebx, eax
0x14000a487  mov     ecx, 4000000h
0x14000a48c  mov     edx, ebx
0x14000a48e  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a493  jmp     loc_14000A6EC
0x14000a498  mov     rax, cs:?vhShutdownEvent@@3PEAXEA; void * vhShutdownEvent
0x14000a49f  lea     rdx, [rsp+98h+Handles]; lpHandles
0x14000a4a4  xor     r8d, r8d; bWaitAll
0x14000a4a7  mov     [rsp+98h+Handles], rax
0x14000a4ac  or      r15d, 0FFFFFFFFh
0x14000a4b0  mov     [rsp+98h+var_50], r14
0x14000a4b5  mov     r9d, r15d; dwMilliseconds
0x14000a4b8  mov     dword ptr [rsp+98h+dwCreationFlags], 0; bAlertable
0x14000a4c0  lea     ecx, [r8+2]; nCount
0x14000a4c4  call    cs:__imp_WaitForMultipleObjectsEx
0x14000a4ca  mov     ebp, 80070000h
0x14000a4cf  mov     esi, 1
0x14000a4d4  mov     edi, eax
0x14000a4d6  test    eax, eax
0x14000a4d8  jz      short loc_14000A521
0x14000a4da  cmp     eax, esi
0x14000a4dc  jz      short loc_14000A504
0x14000a4de  call    cs:__imp_GetLastError
0x14000a4e4  mov     ebx, eax
0x14000a4e6  test    eax, eax
0x14000a4e8  jle     short loc_14000A4EF
0x14000a4ea  movzx   ebx, ax
0x14000a4ed  or      ebx, ebp
0x14000a4ef  mov     dword ptr [rsp+98h+dwCreationFlags], edi
0x14000a4f3  lea     r9, aFailedToWaitOn; "Failed to wait on startup thread.  Wait"...
0x14000a4fa  mov     ecx, 4000000h
0x14000a4ff  jmp     loc_14000A6C9
0x14000a504  mov     edi, 4000000h
0x14000a509  lea     r9, aStartupProcess; "Startup processing thread terminated no"...
0x14000a510  mov     ecx, edi
0x14000a512  xor     r8d, r8d
0x14000a515  xor     edx, edx
0x14000a517  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a51c  jmp     loc_14000A662
0x14000a521  mov     edi, 4000000h
0x14000a526  lea     r9, aStartupASystem; "Startup: A system shutdown was initiate"...
0x14000a52d  mov     ecx, edi
0x14000a52f  xor     r8d, r8d
0x14000a532  xor     edx, edx
0x14000a534  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a539  mov     rcx, cs:?vhTiService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x14000a540  test    rcx, rcx
0x14000a543  jz      short loc_14000A577
0x14000a545  add     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, esi; _SERVICE_STATUS vTiStatus ...
0x14000a54b  lea     rdx, ?vTiStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x14000a552  mov     qword ptr cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS vTiStatus ...
0x14000a55d  mov     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS vTiStatus ...
0x14000a567  mov     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 7530h; _SERVICE_STATUS vTiStatus ...
0x14000a571  call    cs:__imp_SetServiceStatus
0x14000a577  call    TiCorePrepareShutdownProcessing
0x14000a57c  cmp     eax, 800F0920h
0x14000a581  jnz     short loc_14000A5D0
0x14000a583  lea     r9, aStartupAttempt; "Startup: Attempting to terminate the st"...
0x14000a58a  xor     r8d, r8d
0x14000a58d  xor     edx, edx
0x14000a58f  mov     ecx, edi
0x14000a591  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a596  mov     edx, 800F0920h; dwExitCode
0x14000a59b  mov     rcx, r14; hThread
0x14000a59e  call    cs:__imp_TerminateThread
0x14000a5a4  test    eax, eax
0x14000a5a6  jnz     short loc_14000A61F
0x14000a5a8  call    cs:__imp_GetLastError
0x14000a5ae  test    eax, eax
0x14000a5b0  jle     short loc_14000A5B9
0x14000a5b2  movzx   eax, ax
0x14000a5b5  or      eax, ebp
0x14000a5b7  test    eax, eax
0x14000a5b9  jns     short loc_14000A61F
0x14000a5bb  lea     r9, aStartupFailedA; "Startup: Failed attempting to terminate"...
0x14000a5c2  mov     r8d, esi
0x14000a5c5  mov     edx, eax
0x14000a5c7  mov     ecx, edi
0x14000a5c9  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a5ce  jmp     short loc_14000A61F
0x14000a5d0  test    eax, eax
0x14000a5d2  jns     short loc_14000A5E7
0x14000a5d4  lea     r9, aStartupFailedP; "Startup: Failed preparing for shutdown "...
0x14000a5db  mov     r8d, esi
0x14000a5de  mov     edx, eax
0x14000a5e0  mov     ecx, edi
0x14000a5e2  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a5e7  mov     edx, r15d; dwMilliseconds
0x14000a5ea  mov     rcx, r14; hHandle
0x14000a5ed  call    cs:__imp_WaitForSingleObject
0x14000a5f3  mov     r15d, eax
0x14000a5f6  test    eax, eax
0x14000a5f8  jnz     loc_14000A6AA
0x14000a5fe  lea     r9, aStartupStartup; "Startup: Startup processing completed. "...
0x14000a605  xor     r8d, r8d
0x14000a608  xor     edx, edx
0x14000a60a  mov     ecx, edi
0x14000a60c  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a611  call    IsWorkerProcessRunning
0x14000a616  test    eax, eax
0x14000a618  jz      short loc_14000A61F
0x14000a61a  call    TiCoreFinalizeShutdownProcessing
0x14000a61f  call    IsWorkerProcessRunning
0x14000a624  test    eax, eax
0x14000a626  jz      short loc_14000A660
0x14000a628  lea     rdx, [rsp+98h+var_68]
0x14000a62d  xor     ecx, ecx
0x14000a62f  call    TiCoreGetWorkerProcess
0x14000a634  test    eax, eax
0x14000a636  js      short loc_14000A660
0x14000a638  mov     rcx, [rsp+98h+var_68]
0x14000a63d  mov     rax, [rcx]
0x14000a640  mov     rax, [rax+50h]
0x14000a644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a649  test    eax, eax
0x14000a64b  jns     short loc_14000A660
0x14000a64d  lea     r9, aStartupFailedT_1; "Startup: Failed to indicate reboot in p"...
0x14000a654  mov     r8d, esi
0x14000a657  mov     edx, eax
0x14000a659  mov     ecx, edi
0x14000a65b  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a660  mov     [rbx], esi
0x14000a662  lea     rdx, [rsp+98h+ExitCode]; lpExitCode
0x14000a667  mov     rcx, r14; hThread
0x14000a66a  call    cs:__imp_GetExitCodeThread
0x14000a670  test    eax, eax
0x14000a672  jz      short loc_14000A67A
0x14000a674  mov     ebx, [rsp+98h+ExitCode]
0x14000a678  jmp     short loc_14000A6DD
0x14000a67a  call    cs:__imp_GetLastError
0x14000a680  mov     ebx, eax
0x14000a682  test    eax, eax
0x14000a684  jle     short loc_14000A68B
0x14000a686  movzx   ebx, ax
0x14000a689  or      ebx, ebp
0x14000a68b  test    ebx, ebx
0x14000a68d  lea     r9, aFailedGettingS; "Failed getting startup thread result"
0x14000a694  mov     eax, 80004005h
0x14000a699  mov     r8d, esi
0x14000a69c  cmovns  ebx, eax
0x14000a69f  mov     ecx, edi
0x14000a6a1  mov     edx, ebx
0x14000a6a3  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a6a8  jmp     short loc_14000A6DD
0x14000a6aa  call    cs:__imp_GetLastError
0x14000a6b0  mov     ebx, eax
0x14000a6b2  test    eax, eax
0x14000a6b4  jle     short loc_14000A6BB
0x14000a6b6  movzx   ebx, ax
0x14000a6b9  or      ebx, ebp
0x14000a6bb  mov     dword ptr [rsp+98h+dwCreationFlags], r15d
0x14000a6c0  lea     r9, aStartupFailedT; "Startup: Failed to wait on startup thre"...
0x14000a6c7  mov     ecx, edi
0x14000a6c9  test    ebx, ebx
0x14000a6cb  mov     eax, 80004005h
0x14000a6d0  mov     r8d, esi
0x14000a6d3  cmovns  ebx, eax
0x14000a6d6  mov     edx, ebx
0x14000a6d8  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000a6dd  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x14000a6e1  jz      short loc_14000A6EC
0x14000a6e3  mov     rcx, r14; hObject
0x14000a6e6  call    cs:__imp_CloseHandle
0x14000a6ec  mov     rcx, [rsp+98h+var_68]
0x14000a6f1  test    rcx, rcx
0x14000a6f4  jz      short loc_14000A702
0x14000a6f6  mov     rdx, [rcx]
0x14000a6f9  mov     rax, [rdx+10h]
0x14000a6fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a702  call    WaitForTiWorkerToShutdown
0x14000a707  mov     eax, ebx
0x14000a709  mov     rcx, [rsp+98h+var_48]
0x14000a70e  xor     rcx, rsp; StackCookie
0x14000a711  call    __security_check_cookie
0x14000a716  add     rsp, 68h
0x14000a71a  pop     r15
0x14000a71c  pop     r14
0x14000a71e  pop     rdi
0x14000a71f  pop     rsi
0x14000a720  pop     rbp
0x14000a721  pop     rbx
0x14000a722  retn
```
