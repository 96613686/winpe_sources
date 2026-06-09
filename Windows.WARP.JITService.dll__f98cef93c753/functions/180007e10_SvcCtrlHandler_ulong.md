# SvcCtrlHandler(ulong)

- ea: `0x180007e10`
- end: `0x180007e78`
- name: `?SvcCtrlHandler@@YAXK@Z`
- size: `104`
- prototype: `void __fastcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task`

## callees

- `0x180007df4`
- `0x180007e10`
- `0x180007eb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007e6c`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180007e6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007e3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180007e3a`

## string_xrefs

- `0x180007e43`: `Service::CtrlHandler`
- `0x180007e4d`: `%s - PID=%d - %s SERVICE_STOP_PENDING\n`

## pseudocode

```c
void __fastcall SvcCtrlHandler(DWORD dwControl)
{
  Service *v1; // rcx
  Service *v2; // rcx

  v1 = (Service *)(dwControl - 1);
  if ( (_DWORD)v1 )
  {
    if ( (_DWORD)v1 == 3 )
      Service::ReportStatus(v1, ServiceStatus.dwCurrentState, 0);
  }
  else
  {
    GetCurrentProcessId();
    JitServiceDebugPrint("%s - PID=%d - %s SERVICE_STOP_PENDING\n");
    Service::ReportStatus(v2, 3u, 0);
    SetEvent(hEvent);
  }
}

```

## disassembly

```asm
0x180007e10  push    rbx
0x180007e12  sub     rsp, 20h
0x180007e16  sub     ecx, 1; this
0x180007e19  jz      short loc_180007E33
0x180007e1b  cmp     ecx, 3
0x180007e1e  jnz     short loc_180007E72
0x180007e20  mov     edx, cs:ServiceStatus.dwCurrentState; unsigned int
0x180007e26  xor     r8d, r8d; unsigned int
0x180007e29  add     rsp, 20h
0x180007e2d  pop     rbx
0x180007e2e  jmp     ?ReportStatus@Service@@AEAAXKK@Z; Service::ReportStatus(ulong,ulong)
0x180007e33  mov     rbx, cs:qword_18000F670
0x180007e3a  call    cs:__imp_GetCurrentProcessId
0x180007e40  mov     r9, rbx
0x180007e43  lea     rdx, aServiceCtrlhan; "Service::CtrlHandler"
0x180007e4a  mov     r8d, eax
0x180007e4d  lea     rcx, aSPidDSServiceS; "%s - PID=%d - %s SERVICE_STOP_PENDING\n"
0x180007e54  call    ?JitServiceDebugPrint@@YAXPEBDZZ; JitServiceDebugPrint(char const *,...)
0x180007e59  xor     r8d, r8d; unsigned int
0x180007e5c  lea     edx, [r8+3]; unsigned int
0x180007e60  call    ?ReportStatus@Service@@AEAAXKK@Z; Service::ReportStatus(ulong,ulong)
0x180007e65  mov     rcx, cs:hEvent; hEvent
0x180007e6c  call    cs:__imp_SetEvent
0x180007e72  add     rsp, 20h
0x180007e76  pop     rbx
0x180007e77  retn
```
