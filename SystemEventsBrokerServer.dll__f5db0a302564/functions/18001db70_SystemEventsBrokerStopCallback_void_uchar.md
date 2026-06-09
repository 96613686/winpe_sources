# SystemEventsBrokerStopCallback(void *,uchar)

- ea: `0x18001db70`
- end: `0x18001dc2f`
- name: `?SystemEventsBrokerStopCallback@@YAXPEAXE@Z`
- size: `191`
- prototype: `void __fastcall(void *, unsigned __int8)`
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x1800030e0`
- `0x18001db70`
- `0x18001e05c`
- `0x18001fc60`
- `0x180021874`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbbb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001dbbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dc05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001dc05`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001dc28`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18001dbb1`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x18001dbb1`
- `DAB!DabTerminate` at `0x18001db7f`
- `DAB!DabTerminate` at `0x18001db7f`

## pseudocode

```c
void __fastcall SystemEventsBrokerStopCallback(void *a1)
{
  DWORD LastError; // eax

  *(_QWORD *)&g_ServiceStatus.dwWin32ExitCode = 1066;
  DabTerminate(a1);
  DeviceServicesBrokerTerminate();
  CSystemEventsBrokerTerminate();
  SystemEventsBrokerTerminate();
  g_ServiceStatus.dwCurrentState = 1;
  g_ServiceStatus.dwWin32ExitCode = 0;
  if ( !UnregisterWaitEx(g_hWaitHandle, 0) )
  {
    LastError = GetLastError();
    if ( LastError != 997
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_74bfb32edf9d3653184415674129274e_Traceguids, LastError);
    }
  }
  g_hWaitHandle = 0;
  CloseHandle(g_hStopEvent);
  g_hStopEvent = 0;
  SetServiceStatus(g_ServiceHandle, &g_ServiceStatus);
}

```

## disassembly

```asm
0x18001db70  sub     rsp, 28h
0x18001db74  mov     qword ptr cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 42Ah; _SERVICE_STATUS g_ServiceStatus ...
0x18001db7f  call    cs:__imp_DabTerminate
0x18001db85  call    DeviceServicesBrokerTerminate
0x18001db8a  call    ?CSystemEventsBrokerTerminate@@YAXXZ; CSystemEventsBrokerTerminate(void)
0x18001db8f  call    ?SystemEventsBrokerTerminate@@YAXXZ; SystemEventsBrokerTerminate(void)
0x18001db94  mov     rcx, cs:?g_hWaitHandle@@3PEAXEA; WaitHandle
0x18001db9b  xor     edx, edx; CompletionEvent
0x18001db9d  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 1; _SERVICE_STATUS g_ServiceStatus ...
0x18001dba7  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS g_ServiceStatus ...
0x18001dbb1  call    cs:__imp_UnregisterWaitEx
0x18001dbb7  test    eax, eax
0x18001dbb9  jnz     short loc_18001DBF3
0x18001dbbb  call    cs:__imp_GetLastError
0x18001dbc1  cmp     eax, 3E5h
0x18001dbc6  jz      short loc_18001DBF3
0x18001dbc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dbcf  test    byte ptr [rcx+1Ch], 10h
0x18001dbd3  jz      short loc_18001DBF3
0x18001dbd5  cmp     byte ptr [rcx+19h], 2
0x18001dbd9  jb      short loc_18001DBF3
0x18001dbdb  mov     rcx, [rcx+10h]
0x18001dbdf  lea     r8, WPP_74bfb32edf9d3653184415674129274e_Traceguids
0x18001dbe6  mov     edx, 0Ah
0x18001dbeb  mov     r9d, eax
0x18001dbee  call    WPP_SF_d
0x18001dbf3  mov     rcx, cs:?g_hStopEvent@@3PEAXEA; hObject
0x18001dbfa  mov     cs:?g_hWaitHandle@@3PEAXEA, 0; void * g_hWaitHandle
0x18001dc05  call    cs:__imp_CloseHandle
0x18001dc0b  mov     rcx, cs:?g_ServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; SERVICE_STATUS_HANDLE__ * g_ServiceHandle
0x18001dc12  lea     rdx, ?g_ServiceStatus@@3U_SERVICE_STATUS@@A; _SERVICE_STATUS g_ServiceStatus
0x18001dc19  mov     cs:?g_hStopEvent@@3PEAXEA, 0; void * g_hStopEvent
0x18001dc24  add     rsp, 28h
0x18001dc28  jmp     cs:__imp_SetServiceStatus
```
