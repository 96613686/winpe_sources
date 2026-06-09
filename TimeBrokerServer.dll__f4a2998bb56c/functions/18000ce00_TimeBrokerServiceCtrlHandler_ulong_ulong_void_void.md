# TimeBrokerServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x18000ce00`
- end: `0x18000ce6d`
- name: `?TimeBrokerServiceCtrlHandler@@YAKKKPEAX0@Z`
- size: `109`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, _QWORD *lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18000ce00`
- `0x18000ce74`
- `0x18000cec0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ce65`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ce65`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000ce58`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18000ce58`

## pseudocode

```c
__int64 __fastcall TimeBrokerServiceCtrlHandler(
        DWORD dwControl,
        DWORD dwEventType,
        _QWORD *lpEventData,
        LPVOID lpContext)
{
  DWORD v4; // ecx
  DWORD v5; // ecx
  DWORD v6; // ecx

  v4 = dwControl - 1;
  if ( v4 )
  {
    v5 = v4 - 3;
    if ( v5 )
    {
      v6 = v5 - 9;
      if ( v6 )
      {
        if ( v6 != 3 )
          return 120;
        TimerBrokerTimeChange(*lpEventData - lpEventData[1]);
      }
      else if ( dwEventType == 7 )
      {
        TimeBrokerOnResumeFromSleep();
      }
    }
  }
  else
  {
    g_ServiceStatus.dwCurrentState = 3;
    SetServiceStatus(g_ServiceHandle, &g_ServiceStatus);
    SetEvent(g_hStopEvent);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ce00  sub     rsp, 28h
0x18000ce04  sub     ecx, 1
0x18000ce07  jz      short loc_18000CE40
0x18000ce09  sub     ecx, 3
0x18000ce0c  jz      short loc_18000CE27
0x18000ce0e  sub     ecx, 9
0x18000ce11  jz      short loc_18000CE22
0x18000ce13  cmp     ecx, 3
0x18000ce16  jz      short loc_18000CE32
0x18000ce18  mov     eax, 78h ; 'x'
0x18000ce1d  add     rsp, 28h
0x18000ce21  retn
0x18000ce22  cmp     edx, 7
0x18000ce25  jz      short loc_18000CE2B
0x18000ce27  xor     eax, eax
0x18000ce29  jmp     short loc_18000CE1D
0x18000ce2b  call    ?TimeBrokerOnResumeFromSleep@@YAXXZ; TimeBrokerOnResumeFromSleep(void)
0x18000ce30  jmp     short loc_18000CE27
0x18000ce32  mov     rcx, [r8]
0x18000ce35  sub     rcx, [r8+8]; __int64
0x18000ce39  call    ?TimerBrokerTimeChange@@YAX_J@Z; TimerBrokerTimeChange(__int64)
0x18000ce3e  jmp     short loc_18000CE27
0x18000ce40  mov     rcx, cs:?g_ServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x18000ce47  lea     rdx, ?g_ServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x18000ce4e  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS g_ServiceStatus ...
0x18000ce58  call    cs:__imp_SetServiceStatus
0x18000ce5e  mov     rcx, cs:?g_hStopEvent@@3PEAXEA; hEvent
0x18000ce65  call    cs:__imp_SetEvent
0x18000ce6b  jmp     short loc_18000CE27
```
