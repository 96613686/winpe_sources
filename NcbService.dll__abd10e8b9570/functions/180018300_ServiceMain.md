# ServiceMain

- ea: `0x180018300`
- end: `0x1800183f1`
- name: `ServiceMain`
- size: `241`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180009740`
- `0x180015690`
- `0x180015924`
- `0x180017f4c`
- `0x180018300`
- `0x1800231c0`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001835d`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001835d`

## string_xrefs

- `0x18001832f`: `NcbService`
- `0x1800183ad`: `NcbService will stop immediately following this log.`
- `0x180018394`: `ServiceMain: NcbService started successfully.`

## pseudocode

```c
SERVICE_STATUS_HANDLE ServiceMain()
{
  SERVICE_STATUS_HANDLE result; // rax
  __int64 v1; // rdx
  __int64 v2; // rcx

  g_StopServiceEventSet = 0;
  g_TracingEnabled = 0;
  g_Stopping = 0;
  g_ErrorCode = 0;
  *(_OWORD *)&g_ServiceStatus.dwWin32ExitCode = 0;
  g_ServiceStatus.dwServiceType = 32;
  *(_QWORD *)&g_ServiceStatus.dwCurrentState = 2;
  result = RegisterServiceCtrlHandlerExW(L"NcbService", ServiceHandler, 0);
  hServiceStatus = result;
  if ( result )
  {
    if ( !(unsigned int)McGenEventRegister_EventRegister() )
      g_TracingEnabled = 1;
    result = (SERVICE_STATUS_HANDLE)StartNcbService();
    if ( (_DWORD)result )
    {
      if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
        McTemplateU0z_EventWriteTransfer(v2, v1, L"NcbService will stop immediately following this log.");
      if ( g_TracingEnabled )
        McGenEventUnregister_EventUnregister();
      return (SERVICE_STATUS_HANDLE)SetNcbServiceStatus(1);
    }
    else if ( (Microsoft_Windows_Network_Connection_BrokerEnableBits & 1) != 0 )
    {
      return (SERVICE_STATUS_HANDLE)McTemplateU0z_EventWriteTransfer(
                                      v2,
                                      v1,
                                      L"ServiceMain: NcbService started successfully.");
    }
  }
  else
  {
    *(_OWORD *)&g_ServiceStatus.dwServiceType = 0;
    *(_OWORD *)&g_ServiceStatus.dwWin32ExitCode = 0;
  }
  return result;
}

```

## disassembly

```asm
0x180018300  sub     rsp, 28h
0x180018304  xorps   xmm0, xmm0
0x180018307  mov     cs:g_StopServiceEventSet, 0
0x180018311  xor     r8d, r8d; lpContext
0x180018314  mov     cs:g_TracingEnabled, 0
0x18001831e  lea     rdx, ServiceHandler; lpHandlerProc
0x180018325  mov     cs:g_Stopping, 0
0x18001832f  lea     rcx, ServiceName; "NcbService"
0x180018336  mov     cs:g_ErrorCode, 0
0x180018340  movdqu  xmmword ptr cs:g_ServiceStatus.dwWin32ExitCode, xmm0
0x180018348  mov     cs:g_ServiceStatus.dwServiceType, 20h ; ' '
0x180018352  mov     qword ptr cs:g_ServiceStatus.dwCurrentState, 2
0x18001835d  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x180018363  mov     cs:hServiceStatus, rax
0x18001836a  test    rax, rax
0x18001836d  jz      short loc_1800183DB
0x18001836f  call    McGenEventRegister_EventRegister
0x180018374  test    eax, eax
0x180018376  jnz     short loc_180018382
0x180018378  mov     cs:g_TracingEnabled, 1
0x180018382  call    StartNcbService
0x180018387  test    eax, eax
0x180018389  jnz     short loc_1800183A4
0x18001838b  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x180018392  jz      short loc_1800183EC
0x180018394  lea     r8, aServicemainNcb; "ServiceMain: NcbService started success"...
0x18001839b  add     rsp, 28h
0x18001839f  jmp     McTemplateU0z_EventWriteTransfer
0x1800183a4  test    byte ptr cs:Microsoft_Windows_Network_Connection_BrokerEnableBits, 1
0x1800183ab  jz      short loc_1800183B9
0x1800183ad  lea     r8, aNcbserviceWill; "NcbService will stop immediately follow"...
0x1800183b4  call    McTemplateU0z_EventWriteTransfer
0x1800183b9  cmp     cs:g_TracingEnabled, 0
0x1800183c0  jz      short loc_1800183C7
0x1800183c2  call    McGenEventUnregister_EventUnregister
0x1800183c7  mov     edx, cs:g_ErrorCode
0x1800183cd  mov     ecx, 1
0x1800183d2  add     rsp, 28h
0x1800183d6  jmp     SetNcbServiceStatus
0x1800183db  xorps   xmm0, xmm0
0x1800183de  movups  xmmword ptr cs:g_ServiceStatus.dwServiceType, xmm0
0x1800183e5  movups  xmmword ptr cs:g_ServiceStatus.dwWin32ExitCode, xmm0
0x1800183ec  add     rsp, 28h
0x1800183f0  retn
```
