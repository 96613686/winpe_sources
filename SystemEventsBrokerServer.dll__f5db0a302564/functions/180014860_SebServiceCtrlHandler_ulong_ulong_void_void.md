# SebServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x180014860`
- end: `0x180014900`
- name: `?SebServiceCtrlHandler@@YAKKKPEAX0@Z`
- size: `160`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x180014860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800148f5`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800148f5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800148e8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800148e8`
- `DAB!DabNotifyTimeChange` at `0x1800148c8`
- `DAB!DabNotifyTimeChange` at `0x1800148c8`
- `DAB!DabNotifySessionChange` at `0x180014895`
- `DAB!DabNotifySessionChange` at `0x1800148bd`
- `DAB!DabNotifySessionChange` at `0x180014895`
- `DAB!DabNotifySessionChange` at `0x1800148bd`
- `DAB!DabNotifyPowerEvent` at `0x180014875`
- `DAB!DabNotifyPowerEvent` at `0x180014875`

## pseudocode

```c
__int64 __fastcall SebServiceCtrlHandler(
        DWORD dwControl,
        DWORD dwEventType,
        unsigned int *lpEventData,
        LPVOID lpContext)
{
  DWORD v5; // ecx
  DWORD v6; // ecx
  DWORD v7; // ecx

  if ( dwControl == 4 )
    return 0;
  if ( dwControl == 13 )
  {
    DabNotifyPowerEvent(dwEventType);
    return 0;
  }
  v5 = dwControl - 1;
  if ( !v5 )
  {
    g_ServiceStatus.dwCurrentState = 3;
    SetServiceStatus(g_ServiceHandle, &g_ServiceStatus);
    SetEvent(g_hStopEvent);
    return 0;
  }
  v6 = v5 - 13;
  if ( v6 )
  {
    v7 = v6 - 2;
    if ( !v7 )
    {
      DabNotifyTimeChange(lpEventData);
      return 0;
    }
    if ( v7 == 17 )
    {
      DabNotifySessionChange(dwEventType, lpEventData[1], lpEventData + 2);
      return 0;
    }
    return 120;
  }
  else
  {
    DabNotifySessionChange(dwEventType, lpEventData[1], 0);
    return 0;
  }
}

```

## disassembly

```asm
0x180014860  sub     rsp, 28h
0x180014864  mov     r9, r8
0x180014867  mov     eax, edx
0x180014869  cmp     ecx, 4
0x18001486c  jz      short loc_18001487B
0x18001486e  cmp     ecx, 0Dh
0x180014871  jnz     short loc_180014882
0x180014873  mov     ecx, edx
0x180014875  call    cs:__imp_DabNotifyPowerEvent
0x18001487b  xor     eax, eax
0x18001487d  add     rsp, 28h
0x180014881  retn
0x180014882  sub     ecx, 1
0x180014885  jz      short loc_1800148D0
0x180014887  sub     ecx, 0Dh
0x18001488a  jnz     short loc_1800148A2
0x18001488c  mov     edx, [r9+4]
0x180014890  xor     r8d, r8d
0x180014893  mov     ecx, eax
0x180014895  call    cs:__imp_DabNotifySessionChange
0x18001489b  xor     eax, eax
0x18001489d  add     rsp, 28h
0x1800148a1  retn
0x1800148a2  sub     ecx, 2
0x1800148a5  jz      short loc_1800148C5
0x1800148a7  cmp     ecx, 11h
0x1800148aa  jz      short loc_1800148B3
0x1800148ac  mov     eax, 78h ; 'x'
0x1800148b1  jmp     short loc_18001487D
0x1800148b3  mov     edx, [r9+4]
0x1800148b7  add     r8, 8
0x1800148bb  mov     ecx, eax
0x1800148bd  call    cs:__imp_DabNotifySessionChange
0x1800148c3  jmp     short loc_18001487B
0x1800148c5  mov     rcx, r9
0x1800148c8  call    cs:__imp_DabNotifyTimeChange
0x1800148ce  jmp     short loc_18001487B
0x1800148d0  mov     rcx, cs:?g_ServiceHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x1800148d7  lea     rdx, ?g_ServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x1800148de  mov     cs:?g_ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS g_ServiceStatus ...
0x1800148e8  call    cs:__imp_SetServiceStatus
0x1800148ee  mov     rcx, cs:?g_hStopEvent@@3PEAXEA; hEvent
0x1800148f5  call    cs:__imp_SetEvent
0x1800148fb  jmp     loc_18001487B
```
