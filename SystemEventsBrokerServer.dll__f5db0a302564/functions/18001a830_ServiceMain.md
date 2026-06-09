# ServiceMain

- ea: `0x18001a830`
- end: `0x18001a996`
- name: `ServiceMain`
- size: `358`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18001a830`
- `0x18001dc38`
- `0x18001df48`
- `0x18001e05c`
- `0x18001fb20`
- `0x18001fc60`
- `0x180021840`
- `0x180021874`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a89d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001a89d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a8af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a956`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a956`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001a875`
- `api-ms-win-service-core-l1-1-0!RegisterServiceCtrlHandlerExW` at `0x18001a875`
- `DAB!DabTerminate` at `0x18001a935`
- `DAB!DabTerminate` at `0x18001a935`
- `DAB!DabInitialize` at `0x18001a8d8`
- `DAB!DabInitialize` at `0x18001a8d8`

## pseudocode

```c
void __fastcall ServiceMain(__int64 a1, LPCWSTR *a2)
{
  DWORD LastError; // eax
  DWORD v4; // ebx
  unsigned int v5; // ecx

  g_ServiceStatus.dwServiceType = 32;
  *(_QWORD *)&g_ServiceStatus.dwControlsAccepted = 513;
  *(_QWORD *)&g_ServiceStatus.dwServiceSpecificExitCode = 0;
  g_ServiceStatus.dwCurrentState = 2;
  g_ServiceHandle = RegisterServiceCtrlHandlerExW(*a2, SebServiceCtrlHandler, 0);
  if ( g_ServiceHandle )
  {
    UpdateState(2u);
    g_hStopEvent = CreateEventW(0, 1, 0, 0);
    if ( g_hStopEvent )
    {
      v4 = SystemEventsBrokerInitialize();
      if ( v4 )
        goto LABEL_11;
      v4 = CSystemEventsBrokerInitialize();
      if ( v4 )
        goto LABEL_11;
      v4 = DeviceServicesBrokerInitialize();
      if ( v4 )
        goto LABEL_11;
      v4 = DabInitialize();
      if ( v4 )
        goto LABEL_11;
      LastError = (*((__int64 (__fastcall **)(HANDLE *, LPCWSTR, HANDLE, void (__fastcall *)(void *, unsigned __int8), _QWORD, int))g_pSvchostGlobals
                   + 24))(
                    &g_hWaitHandle,
                    *a2,
                    g_hStopEvent,
                    SystemEventsBrokerStopCallback,
                    0,
                    24);
    }
    else
    {
      LastError = GetLastError();
    }
    v4 = LastError;
    if ( !LastError )
    {
      g_ServiceStatus.dwControlsAccepted = 4801;
      v5 = 4;
LABEL_14:
      UpdateState(v5);
      return;
    }
LABEL_11:
    DabTerminate();
    DeviceServicesBrokerTerminate();
    CSystemEventsBrokerTerminate();
    SystemEventsBrokerTerminate();
    if ( g_hStopEvent )
    {
      CloseHandle(g_hStopEvent);
      g_hStopEvent = 0;
    }
    g_ServiceStatus.dwWin32ExitCode = 1066;
    g_ServiceStatus.dwServiceSpecificExitCode = v4;
    UpdateState(3u);
    v5 = 1;
    goto LABEL_14;
  }
}

```

## disassembly

```asm
0x18001a830  mov     [rsp+arg_0], rbx
0x18001a835  push    rdi
0x18001a836  sub     rsp, 40h
0x18001a83a  mov     rdi, rdx
0x18001a83d  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceType, 20h ; ' '; _SERVICE_STATUS g_ServiceStatus ...
0x18001a847  mov     qword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 201h; _SERVICE_STATUS g_ServiceStatus ...
0x18001a852  lea     rdx, ?SebServiceCtrlHandler@@YAKKKPEAX0@Z; lpHandlerProc
0x18001a859  mov     qword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, 0; _SERVICE_STATUS g_ServiceStatus ...
0x18001a864  mov     ebx, 2
0x18001a869  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, ebx; _SERVICE_STATUS g_ServiceStatus ...
0x18001a86f  xor     r8d, r8d; lpContext
0x18001a872  mov     rcx, [rdi]; lpServiceName
0x18001a875  call    cs:__imp_RegisterServiceCtrlHandlerExW
0x18001a87b  mov     cs:?g_ServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA, rax; SERVICE_STATUS_HANDLE__ * g_ServiceHandle
0x18001a882  test    rax, rax
0x18001a885  jz      loc_18001A98B
0x18001a88b  mov     ecx, ebx; unsigned int
0x18001a88d  call    ?UpdateState@@YAXK@Z; UpdateState(ulong)
0x18001a892  xor     r9d, r9d; lpName
0x18001a895  lea     edx, [rbx-1]; bManualReset
0x18001a898  xor     r8d, r8d; bInitialState
0x18001a89b  xor     ecx, ecx; lpEventAttributes
0x18001a89d  call    cs:__imp_CreateEventW
0x18001a8a3  mov     cs:?g_hStopEvent@@3PEAXEA, rax; void * g_hStopEvent
0x18001a8aa  test    rax, rax
0x18001a8ad  jnz     short loc_18001A8B7
0x18001a8af  call    cs:__imp_GetLastError
0x18001a8b5  jmp     short loc_18001A920
0x18001a8b7  call    ?SystemEventsBrokerInitialize@@YAKXZ; SystemEventsBrokerInitialize(void)
0x18001a8bc  mov     ebx, eax
0x18001a8be  test    eax, eax
0x18001a8c0  jnz     short loc_18001A935
0x18001a8c2  call    ?CSystemEventsBrokerInitialize@@YAKXZ; CSystemEventsBrokerInitialize(void)
0x18001a8c7  mov     ebx, eax
0x18001a8c9  test    eax, eax
0x18001a8cb  jnz     short loc_18001A935
0x18001a8cd  call    DeviceServicesBrokerInitialize
0x18001a8d2  mov     ebx, eax
0x18001a8d4  test    eax, eax
0x18001a8d6  jnz     short loc_18001A935
0x18001a8d8  call    cs:__imp_DabInitialize
0x18001a8de  mov     ebx, eax
0x18001a8e0  test    eax, eax
0x18001a8e2  jnz     short loc_18001A935
0x18001a8e4  mov     rax, cs:?g_pSvchostGlobals@@3PEAU_SVCHOST_GLOBAL_DATA@@EA; _SVCHOST_GLOBAL_DATA * g_pSvchostGlobals
0x18001a8eb  lea     r9, ?SystemEventsBrokerStopCallback@@YAXPEAXE@Z; SystemEventsBrokerStopCallback(void *,uchar)
0x18001a8f2  mov     r8, cs:?g_hStopEvent@@3PEAXEA; void * g_hStopEvent
0x18001a8f9  lea     rcx, ?g_hWaitHandle@@3PEAXEA; void * g_hWaitHandle
0x18001a900  mov     rdx, [rdi]
0x18001a903  mov     [rsp+48h+var_20], 18h
0x18001a90b  mov     rax, [rax+0C0h]
0x18001a912  mov     [rsp+48h+var_28], 0
0x18001a91b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a920  mov     ebx, eax
0x18001a922  test    eax, eax
0x18001a924  jnz     short loc_18001A935
0x18001a926  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwControlsAccepted, 12C1h; _SERVICE_STATUS g_ServiceStatus ...
0x18001a930  lea     ecx, [rax+4]
0x18001a933  jmp     short loc_18001A986
0x18001a935  call    cs:__imp_DabTerminate
0x18001a93b  call    DeviceServicesBrokerTerminate
0x18001a940  call    ?CSystemEventsBrokerTerminate@@YAXXZ; CSystemEventsBrokerTerminate(void)
0x18001a945  call    ?SystemEventsBrokerTerminate@@YAXXZ; SystemEventsBrokerTerminate(void)
0x18001a94a  mov     rcx, cs:?g_hStopEvent@@3PEAXEA; hObject
0x18001a951  test    rcx, rcx
0x18001a954  jz      short loc_18001A967
0x18001a956  call    cs:__imp_CloseHandle
0x18001a95c  mov     cs:?g_hStopEvent@@3PEAXEA, 0; void * g_hStopEvent
0x18001a967  mov     ecx, 3; unsigned int
0x18001a96c  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 42Ah; _SERVICE_STATUS g_ServiceStatus ...
0x18001a976  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwServiceSpecificExitCode, ebx; _SERVICE_STATUS g_ServiceStatus ...
0x18001a97c  call    ?UpdateState@@YAXK@Z; UpdateState(ulong)
0x18001a981  mov     ecx, 1; unsigned int
0x18001a986  call    ?UpdateState@@YAXK@Z; UpdateState(ulong)
0x18001a98b  mov     rbx, [rsp+48h+arg_0]
0x18001a990  add     rsp, 40h
0x18001a994  pop     rdi
0x18001a995  retn
```
