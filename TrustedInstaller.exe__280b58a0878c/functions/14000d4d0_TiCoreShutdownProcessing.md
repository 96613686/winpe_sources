# TiCoreShutdownProcessing

- ea: `0x14000d4d0`
- end: `0x14000d5bf`
- name: `TiCoreShutdownProcessing`
- size: `239`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, installer_update`

## callers

- `0x140009b2c`

## callees

- `0x1400023e0`
- `0x14000ca98`
- `0x14000d4d0`
- `0x140017658`
- `0x14002b010`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000d58e`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000d58e`

## string_xrefs

- `0x14000d4e5`: `Starting shutdown processing in TrustedInstaller service.`

## pseudocode

```c
__int64 TiCoreShutdownProcessing()
{
  int WorkerProcess; // eax
  unsigned int v1; // ebx
  int v2; // eax
  void *v4; // [rsp+20h] [rbp-18h] BYREF

  v4 = 0;
  CBSWdsLogLight(0x4000000u, 0, 0, "Starting shutdown processing in TrustedInstaller service.");
  WorkerProcess = TiCoreGetWorkerProcess(0, &v4);
  v1 = WorkerProcess;
  if ( WorkerProcess < 0 )
    CBSWdsLogLight(0x4000000u, (unsigned int)WorkerProcess, (size_t *)1, "Unable to get worker process.");
  if ( v4 )
  {
    v2 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v4 + 72LL))(v4);
    v1 = v2;
    if ( v2 < 0 )
      CBSWdsLogLight(0x4000000u, (unsigned int)v2, (size_t *)1, "Unable to call Shutdown Processing on Worker process.");
  }
  vTiStatus.dwCheckPoint += 2;
  *(_QWORD *)&vTiStatus.dwCurrentState = 3;
  vTiStatus.dwWaitHint = 30000;
  SetServiceStatus(vhTiService, &vTiStatus);
  if ( v4 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 16LL))(v4);
  return v1;
}

```

## disassembly

```asm
0x14000d4d0  push    rbx
0x14000d4d2  sub     rsp, 30h
0x14000d4d6  mov     rax, cs:__security_cookie
0x14000d4dd  xor     rax, rsp
0x14000d4e0  mov     [rsp+38h+var_10], rax
0x14000d4e5  lea     r9, aStartingShutdo; "Starting shutdown processing in Trusted"...
0x14000d4ec  mov     [rsp+38h+var_18], 0
0x14000d4f5  xor     r8d, r8d
0x14000d4f8  xor     edx, edx
0x14000d4fa  mov     ecx, 4000000h
0x14000d4ff  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d504  lea     rdx, [rsp+38h+var_18]
0x14000d509  xor     ecx, ecx
0x14000d50b  call    TiCoreGetWorkerProcess
0x14000d510  mov     ebx, eax
0x14000d512  test    eax, eax
0x14000d514  jns     short loc_14000D52F
0x14000d516  lea     r9, aUnableToGetWor; "Unable to get worker process."
0x14000d51d  mov     r8d, 1
0x14000d523  mov     edx, eax
0x14000d525  mov     ecx, 4000000h
0x14000d52a  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d52f  mov     rcx, [rsp+38h+var_18]
0x14000d534  test    rcx, rcx
0x14000d537  jz      short loc_14000D564
0x14000d539  mov     rax, [rcx]
0x14000d53c  mov     rax, [rax+48h]
0x14000d540  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d545  mov     ebx, eax
0x14000d547  test    eax, eax
0x14000d549  jns     short loc_14000D564
0x14000d54b  lea     r9, aUnableToCallSh; "Unable to call Shutdown Processing on W"...
0x14000d552  mov     r8d, 1
0x14000d558  mov     edx, eax
0x14000d55a  mov     ecx, 4000000h
0x14000d55f  call    ?CBSWdsLogLight@@YAXW4tagLOG_SETUPLOG_SEVERITY@@J_NPEBDZZ; CBSWdsLogLight(tagLOG_SETUPLOG_SEVERITY,long,bool,char const *,...)
0x14000d564  mov     rcx, cs:?vhTiService@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x14000d56b  lea     rdx, ?vTiStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x14000d572  add     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, 2; _SERVICE_STATUS vTiStatus ...
0x14000d579  mov     qword ptr cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS vTiStatus ...
0x14000d584  mov     cs:?vTiStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 7530h; _SERVICE_STATUS vTiStatus ...
0x14000d58e  call    cs:__imp_SetServiceStatus
0x14000d594  mov     rcx, [rsp+38h+var_18]
0x14000d599  test    rcx, rcx
0x14000d59c  jz      short loc_14000D5AA
0x14000d59e  mov     rax, [rcx]
0x14000d5a1  mov     rax, [rax+10h]
0x14000d5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d5aa  mov     eax, ebx
0x14000d5ac  mov     rcx, [rsp+38h+var_10]
0x14000d5b1  xor     rcx, rsp; StackCookie
0x14000d5b4  call    __security_check_cookie
0x14000d5b9  add     rsp, 30h
0x14000d5bd  pop     rbx
0x14000d5be  retn
```
