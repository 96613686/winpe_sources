# ServiceMain

- ea: `0x1400037d0`
- end: `0x1400038a4`
- name: `ServiceMain`
- size: `212`
- prototype: `int()`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task`

## callees

- `0x1400028f8`
- `0x1400037d0`
- `0x140007750`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003838`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140003838`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003887`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003887`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x14000385c`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x14000385c`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000382b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140003878`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x14000382b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x140003878`

## pseudocode

```c
int ServiceMain()
{
  signed int v0; // ebx
  SERVICE_STATUS_HANDLE v1; // rcx
  SERVICE_STATUS_HANDLE v2; // rax
  SERVICE_STATUS_HANDLE hServiceStatus[2]; // [rsp+20h] [rbp-40h] BYREF
  _SERVICE_STATUS ServiceStatus; // [rsp+30h] [rbp-30h] BYREF

  ServiceStatus.dwServiceType = 16;
  memset(&ServiceStatus.dwCurrentState, 0, 24);
  *(_OWORD *)hServiceStatus = 0;
  v0 = InitializeService(hServiceStatus);
  if ( v0 < 0 )
  {
    v2 = RegisterServiceCtrlHandlerExW(L"GameInputSvc", NopSvcControlHandler, 0);
    if ( !v2 )
      goto LABEL_6;
    ServiceStatus.dwWin32ExitCode = v0;
    v1 = v2;
  }
  else
  {
    ServiceStatus.dwCurrentState = 4;
    ServiceStatus.dwControlsAccepted = 133;
    SetServiceStatus(hServiceStatus[1], &ServiceStatus);
    WaitForSingleObject(hServiceStatus[0], 0xFFFFFFFF);
    v1 = hServiceStatus[1];
    ServiceStatus.dwWin32ExitCode = 0;
  }
  ServiceStatus.dwCurrentState = 1;
  LODWORD(v2) = SetServiceStatus(v1, &ServiceStatus);
LABEL_6:
  if ( hServiceStatus[0] )
    LODWORD(v2) = CloseHandle(hServiceStatus[0]);
  return (int)v2;
}

```

## disassembly

```asm
0x1400037d0  mov     [rsp-8+arg_0], rbx
0x1400037d5  push    rbp
0x1400037d6  mov     rbp, rsp
0x1400037d9  sub     rsp, 60h
0x1400037dd  mov     rax, cs:__security_cookie
0x1400037e4  xor     rax, rsp
0x1400037e7  mov     [rbp+var_10], rax
0x1400037eb  xorps   xmm0, xmm0
0x1400037ee  mov     qword ptr [rbp+ServiceStatus.dwCheckPoint], 0
0x1400037f6  lea     rcx, [rbp+hServiceStatus]; lpContext
0x1400037fa  mov     [rbp+ServiceStatus.dwServiceType], 10h
0x140003801  movdqu  xmmword ptr [rbp+ServiceStatus.dwCurrentState], xmm0
0x140003806  movups  xmmword ptr [rbp+hServiceStatus], xmm0
0x14000380a  call    InitializeService
0x14000380f  mov     ebx, eax
0x140003811  test    eax, eax
0x140003813  js      short loc_14000384B
0x140003815  mov     rcx, [rbp+hServiceStatus+8]; hServiceStatus
0x140003819  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x14000381d  mov     [rbp+ServiceStatus.dwCurrentState], 4
0x140003824  mov     [rbp+ServiceStatus.dwControlsAccepted], 85h
0x14000382b  call    cs:__imp_SetServiceStatus
0x140003831  mov     rcx, [rbp+hServiceStatus]; hHandle
0x140003835  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140003838  call    cs:__imp_WaitForSingleObject
0x14000383e  mov     rcx, [rbp+hServiceStatus+8]
0x140003842  mov     [rbp+ServiceStatus.dwWin32ExitCode], 0
0x140003849  jmp     short loc_14000386D
0x14000384b  xor     r8d, r8d; lpContext
0x14000384e  lea     rdx, NopSvcControlHandler; lpHandlerProc
0x140003855  lea     rcx, ServiceName; "GameInputSvc"
0x14000385c  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x140003862  test    rax, rax
0x140003865  jz      short loc_14000387E
0x140003867  mov     [rbp+ServiceStatus.dwWin32ExitCode], ebx
0x14000386a  mov     rcx, rax; hServiceStatus
0x14000386d  lea     rdx, [rbp+ServiceStatus]; lpServiceStatus
0x140003871  mov     [rbp+ServiceStatus.dwCurrentState], 1
0x140003878  call    cs:__imp_SetServiceStatus
0x14000387e  mov     rcx, [rbp+hServiceStatus]; hObject
0x140003882  test    rcx, rcx
0x140003885  jz      short loc_14000388D
0x140003887  call    cs:__imp_CloseHandle
0x14000388d  mov     rcx, [rbp+var_10]
0x140003891  xor     rcx, rsp; StackCookie
0x140003894  call    __security_check_cookie
0x140003899  mov     rbx, [rsp+60h+arg_0]
0x14000389e  add     rsp, 60h
0x1400038a2  pop     rbp
0x1400038a3  retn
```
