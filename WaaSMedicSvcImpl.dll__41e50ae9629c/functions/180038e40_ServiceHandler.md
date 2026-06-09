# ServiceHandler

- ea: `0x180038e40`
- end: `0x180038efb`
- name: `ServiceHandler`
- size: `187`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x18002e81c`
- `0x180038e40`
- `0x180039624`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038e55`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180038e55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038ee8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038ee8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180038edb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180038edb`

## string_xrefs

- `0x180038eae`: `WaaSMedic initiating service stop.`
- `0x180038e71`: `WaaSMedic service received shutdown request.`
- `0x180038e9d`: `WaaSMedic service received stop request.`
- `0x180038e7a`: `WaaSMedic service received interrogate request.`

## pseudocode

```c
__int64 __fastcall ServiceHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  unsigned int v5; // edi
  DWORD v6; // ebx
  DWORD v7; // ebx

  v5 = 0;
  EnterCriticalSection(&gcsMedicReady);
  v6 = dwControl - 1;
  if ( v6 )
  {
    v7 = v6 - 3;
    if ( !v7 )
    {
      LogLevelW(4u, L"WaaSMedic service received interrogate request.");
      UpdateServiceStatus(ServiceStatus.dwCurrentState, 0, 0);
      goto LABEL_10;
    }
    if ( v7 != 1 )
    {
      v5 = 120;
      goto LABEL_10;
    }
    LogLevelW(4u, L"WaaSMedic service received shutdown request.");
  }
  else
  {
    LogLevelW(4u, L"WaaSMedic service received stop request.");
  }
  LogLevelW(5u, L"WaaSMedic initiating service stop.");
  UpdateServiceStatus(3u, 0, 0x7530u);
  if ( hObject )
    SetEvent(hObject);
LABEL_10:
  LeaveCriticalSection(&gcsMedicReady);
  return v5;
}

```

## disassembly

```asm
0x180038e40  mov     [rsp+arg_0], rbx
0x180038e45  push    rdi
0x180038e46  sub     rsp, 20h
0x180038e4a  mov     ebx, ecx
0x180038e4c  xor     edi, edi
0x180038e4e  lea     rcx, ?gcsMedicReady@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180038e55  call    cs:__imp_EnterCriticalSection
0x180038e5b  sub     ebx, 1
0x180038e5e  jz      short loc_180038E9D
0x180038e60  sub     ebx, 3
0x180038e63  jz      short loc_180038E7A
0x180038e65  cmp     ebx, 1
0x180038e68  jz      short loc_180038E71
0x180038e6a  mov     edi, 78h ; 'x'
0x180038e6f  jmp     short loc_180038EE1
0x180038e71  lea     rdx, aWaasmedicServi_0; "WaaSMedic service received shutdown req"...
0x180038e78  jmp     short loc_180038EA4
0x180038e7a  lea     rdx, aWaasmedicServi_2; "WaaSMedic service received interrogate "...
0x180038e81  mov     ecx, 4; unsigned __int8
0x180038e86  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180038e8b  mov     ecx, cs:ServiceStatus.dwCurrentState; unsigned int
0x180038e91  xor     r8d, r8d; unsigned int
0x180038e94  xor     edx, edx; unsigned int
0x180038e96  call    ?UpdateServiceStatus@@YAJKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x180038e9b  jmp     short loc_180038EE1
0x180038e9d  lea     rdx, aWaasmedicServi; "WaaSMedic service received stop request"...
0x180038ea4  mov     ecx, 4; unsigned __int8
0x180038ea9  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180038eae  lea     rdx, aWaasmedicIniti; "WaaSMedic initiating service stop."
0x180038eb5  mov     ecx, 5; unsigned __int8
0x180038eba  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180038ebf  xor     edx, edx; unsigned int
0x180038ec1  mov     r8d, 7530h; unsigned int
0x180038ec7  lea     ecx, [rdx+3]; unsigned int
0x180038eca  call    ?UpdateServiceStatus@@YAJKKK@Z; UpdateServiceStatus(ulong,ulong,ulong)
0x180038ecf  mov     rcx, cs:hObject; hEvent
0x180038ed6  test    rcx, rcx
0x180038ed9  jz      short loc_180038EE1
0x180038edb  call    cs:__imp_SetEvent
0x180038ee1  lea     rcx, ?gcsMedicReady@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180038ee8  call    cs:__imp_LeaveCriticalSection
0x180038eee  mov     rbx, [rsp+28h+arg_0]
0x180038ef3  mov     eax, edi
0x180038ef5  add     rsp, 20h
0x180038ef9  pop     rdi
0x180038efa  retn
```
