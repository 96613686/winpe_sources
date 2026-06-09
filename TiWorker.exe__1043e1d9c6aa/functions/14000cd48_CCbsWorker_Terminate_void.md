# CCbsWorker::Terminate(void)

- ea: `0x14000cd48`
- end: `0x14000cdd2`
- name: `?Terminate@CCbsWorker@@UEAAJXZ`
- size: `138`
- prototype: `__int64 __fastcall(CCbsWorker *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x1400099d0`
- `0x14000a0e4`

## callees

- `0x140008860`
- `0x14000caa0`
- `0x14000cd48`
- `0x14000e328`
- `0x140016710`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000cd85`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14000cd85`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000cd97`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14000cd97`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000cd6c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000cd6c`

## string_xrefs

- `0x14000cdb3`: `Error: Not reversed from impersonation on func: %s`

## pseudocode

```c
__int64 __fastcall CCbsWorker::Terminate(CCbsWorker *this)
{
  CCbsLockMonitor *v1; // rcx

  if ( !*((_DWORD *)this - 5) )
  {
    *((_DWORD *)this - 5) = 1;
    TiWorkerCoreLockProcess(0);
    CCbsWorker::StopIdleProcessing();
    SetEvent(vhShutdownEvent);
    CCbsLockMonitor::LeaveCriticalSection(v1, &vTiWorkerLock);
    LeaveCriticalSection(&vTiWorkerLock);
    WaitForSingleObject(vhWorkerExitEvent, 0x9C40u);
  }
  if ( NtCurrentTeb()->IsImpersonating )
    CBSWdsLog(0x4000000u, 0, 0, "Error: Not reversed from impersonation on func: %s", "CCbsWorker::Terminate");
  return 0;
}

```

## disassembly

```asm
0x14000cd48  sub     rsp, 38h
0x14000cd4c  cmp     dword ptr [rcx-14h], 0
0x14000cd50  jnz     short loc_14000CD9D
0x14000cd52  mov     dword ptr [rcx-14h], 1
0x14000cd59  xor     ecx, ecx
0x14000cd5b  call    TiWorkerCoreLockProcess
0x14000cd60  call    ?StopIdleProcessing@CCbsWorker@@SAJXZ; CCbsWorker::StopIdleProcessing(void)
0x14000cd65  mov     rcx, cs:?vhShutdownEvent@@3PEAXEA; hEvent
0x14000cd6c  call    cs:__imp_SetEvent
0x14000cd72  lea     rdx, ?vTiWorkerLock@@3UMonitoredCritSec@@A; struct _RTL_CRITICAL_SECTION *
0x14000cd79  call    ?LeaveCriticalSection@CCbsLockMonitor@@QEAAXPEAU_RTL_CRITICAL_SECTION@@@Z; CCbsLockMonitor::LeaveCriticalSection(_RTL_CRITICAL_SECTION *)
0x14000cd7e  lea     rcx, ?vTiWorkerLock@@3UMonitoredCritSec@@A; lpCriticalSection
0x14000cd85  call    cs:__imp_LeaveCriticalSection
0x14000cd8b  mov     rcx, cs:?vhWorkerExitEvent@@3PEAXEA; hHandle
0x14000cd92  mov     edx, 9C40h; dwMilliseconds
0x14000cd97  call    cs:__imp_WaitForSingleObject
0x14000cd9d  mov     eax, gs:179Ch
0x14000cda5  test    eax, eax
0x14000cda7  jz      short loc_14000CDCB
0x14000cda9  lea     rax, aCcbsworkerTerm; "CCbsWorker::Terminate"
0x14000cdb0  xor     r8d, r8d
0x14000cdb3  lea     r9, aErrorNotRevers; "Error: Not reversed from impersonation "...
0x14000cdba  mov     [rsp+38h+var_18], rax
0x14000cdbf  xor     edx, edx
0x14000cdc1  mov     ecx, 4000000h
0x14000cdc6  call    ?CBSWdsLog@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLog(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000cdcb  xor     eax, eax
0x14000cdcd  add     rsp, 38h
0x14000cdd1  retn
```
