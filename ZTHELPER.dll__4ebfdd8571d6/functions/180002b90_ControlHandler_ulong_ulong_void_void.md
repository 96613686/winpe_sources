# ControlHandler(ulong,ulong,void *,void *)

- ea: `0x180002b90`
- end: `0x180002c63`
- name: `?ControlHandler@@YAKKKPEAX0@Z`
- size: `211`
- prototype: `__int64 __fastcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callees

- `0x180002b90`
- `0x180003570`
- `0x180015008`
- `0x180015178`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002bf4`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180002bf4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002bfe`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002c2e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180002c2e`

## pseudocode

```c
__int64 __fastcall ControlHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  DWORD LastError; // edi
  DWORD v6; // ebx
  DWORD v7; // ebx

  LastError = 0;
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_dd(1026, 14, WPP_fd30cb189484364f2633d135959507bb_Traceguids, dwControl, dwEventType);
  v6 = dwControl - 1;
  if ( v6 )
  {
    v7 = v6 - 1;
    if ( v7 )
    {
      if ( v7 == 3 )
        ServiceStatus.dwCurrentState = 3;
    }
    else
    {
      *(_QWORD *)&ServiceStatus.dwCurrentState = 2;
    }
    if ( !SetServiceStatus(ServiceStatusHandle, &ServiceStatus) )
      LastError = GetLastError();
  }
  else
  {
    ServiceStatus.dwCurrentState = 3;
    ServiceStatus.dwCheckPoint = 0;
    ServiceStatus.dwWaitHint = 60000;
    UpdateStatus();
    SetEvent(g_hStopServiceEvent);
  }
  if ( (xmmword_18001F260 & 4) != 0 )
    WPP_SF_d(1026, 15, WPP_fd30cb189484364f2633d135959507bb_Traceguids, LastError);
  return LastError;
}

```

## disassembly

```asm
0x180002b90  mov     [rsp+arg_0], rbx
0x180002b95  push    rdi
0x180002b96  sub     rsp, 30h
0x180002b9a  mov     eax, edx
0x180002b9c  mov     ebx, ecx
0x180002b9e  xor     edi, edi
0x180002ba0  test    byte ptr cs:xmmword_18001F260, 4
0x180002ba7  jz      short loc_180002BC4
0x180002ba9  lea     edx, [rdi+0Eh]
0x180002bac  mov     [rsp+38h+var_18], eax
0x180002bb0  mov     ecx, 402h
0x180002bb5  lea     r8, WPP_fd30cb189484364f2633d135959507bb_Traceguids
0x180002bbc  mov     r9d, ebx
0x180002bbf  call    WPP_SF_dd
0x180002bc4  sub     ebx, 1
0x180002bc7  jz      short loc_180002C08
0x180002bc9  sub     ebx, 1
0x180002bcc  jz      short loc_180002BDB
0x180002bce  cmp     ebx, 3
0x180002bd1  jnz     short loc_180002BE6
0x180002bd3  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, ebx; _SERVICE_STATUS ServiceStatus ...
0x180002bd9  jmp     short loc_180002BE6
0x180002bdb  mov     qword ptr cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 2; _SERVICE_STATUS ServiceStatus ...
0x180002be6  mov     rcx, cs:?ServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180002bed  lea     rdx, ?ServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180002bf4  call    cs:__imp_SetServiceStatus
0x180002bfa  test    eax, eax
0x180002bfc  jnz     short loc_180002C34
0x180002bfe  call    cs:__imp_GetLastError
0x180002c04  mov     edi, eax
0x180002c06  jmp     short loc_180002C34
0x180002c08  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS ServiceStatus ...
0x180002c12  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCheckPoint, edi; _SERVICE_STATUS ServiceStatus ...
0x180002c18  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwWaitHint, 0EA60h; _SERVICE_STATUS ServiceStatus ...
0x180002c22  call    ?UpdateStatus@@YAKXZ; UpdateStatus(void)
0x180002c27  mov     rcx, cs:?g_hStopServiceEvent@@3PEAXEA; hEvent
0x180002c2e  call    cs:__imp_SetEvent
0x180002c34  test    byte ptr cs:xmmword_18001F260, 4
0x180002c3b  jz      short loc_180002C56
0x180002c3d  mov     edx, 0Fh
0x180002c42  lea     r8, WPP_fd30cb189484364f2633d135959507bb_Traceguids
0x180002c49  mov     ecx, 402h
0x180002c4e  mov     r9d, edi
0x180002c51  call    WPP_SF_d
0x180002c56  mov     rbx, [rsp+38h+arg_0]
0x180002c5b  mov     eax, edi
0x180002c5d  add     rsp, 30h
0x180002c61  pop     rdi
0x180002c62  retn
```
