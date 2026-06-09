# AiSvcpServiceCtrlHandler(ulong,ulong,void *,void *)

- ea: `0x180003af0`
- end: `0x180003bb0`
- name: `?AiSvcpServiceCtrlHandler@@YAKKKPEAX0@Z`
- size: `192`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task`

## callees

- `0x180003af0`
- `0x180004840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003ba2`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180003ba2`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003b4b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003b95`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003b4b`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180003b95`

## pseudocode

```c
__int64 __fastcall AiSvcpServiceCtrlHandler(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)
{
  unsigned int v4; // ebx
  DWORD v5; // ecx
  DWORD v6; // ecx

  v4 = 0;
  v5 = dwControl - 1;
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, lpEventData, lpContext);
    AiSvcpServiceStatus.dwCurrentState = 3;
    SetServiceStatus(AiSvcpServiceStatusHandle, &AiSvcpServiceStatus);
    goto LABEL_13;
  }
  v6 = v5 - 3;
  if ( !v6 )
  {
    SetServiceStatus(AiSvcpServiceStatusHandle, &AiSvcpServiceStatus);
    return v4;
  }
  if ( v6 == 1 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, lpEventData, lpContext);
LABEL_13:
    SetEvent(AiSvcpServiceStopEvent);
    return v4;
  }
  return 120;
}

```

## disassembly

```asm
0x180003af0  push    rbx
0x180003af2  sub     rsp, 20h
0x180003af6  xor     ebx, ebx
0x180003af8  sub     ecx, 1
0x180003afb  jz      short loc_180003B53
0x180003afd  sub     ecx, 3
0x180003b00  jz      short loc_180003B3D
0x180003b02  cmp     ecx, 1
0x180003b05  jz      short loc_180003B11
0x180003b07  mov     ebx, 78h ; 'x'
0x180003b0c  jmp     loc_180003BA8
0x180003b11  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b18  lea     rax, WPP_GLOBAL_Control
0x180003b1f  cmp     rcx, rax
0x180003b22  jz      short loc_180003B9B
0x180003b24  test    dword ptr [rcx+1Ch], 400h
0x180003b2b  jz      short loc_180003B9B
0x180003b2d  mov     rcx, [rcx+10h]
0x180003b31  mov     edx, 21h ; '!'
0x180003b36  call    WPP_SF_
0x180003b3b  jmp     short loc_180003B9B
0x180003b3d  mov     rcx, cs:?AiSvcpServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180003b44  lea     rdx, ?AiSvcpServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180003b4b  call    cs:__imp_SetServiceStatus
0x180003b51  jmp     short loc_180003BA8
0x180003b53  mov     rcx, cs:WPP_GLOBAL_Control
0x180003b5a  lea     rax, WPP_GLOBAL_Control
0x180003b61  cmp     rcx, rax
0x180003b64  jz      short loc_180003B7D
0x180003b66  test    dword ptr [rcx+1Ch], 400h
0x180003b6d  jz      short loc_180003B7D
0x180003b6f  mov     rcx, [rcx+10h]
0x180003b73  mov     edx, 20h ; ' '
0x180003b78  call    WPP_SF_
0x180003b7d  mov     rcx, cs:?AiSvcpServiceStatusHandle@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x180003b84  lea     rdx, ?AiSvcpServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x180003b8b  mov     cs:?AiSvcpServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, 3; _SERVICE_STATUS AiSvcpServiceStatus ...
0x180003b95  call    cs:__imp_SetServiceStatus
0x180003b9b  mov     rcx, cs:?AiSvcpServiceStopEvent@@3PEAXEA; hEvent
0x180003ba2  call    cs:__imp_SetEvent
0x180003ba8  mov     eax, ebx
0x180003baa  add     rsp, 20h
0x180003bae  pop     rbx
0x180003baf  retn
```
