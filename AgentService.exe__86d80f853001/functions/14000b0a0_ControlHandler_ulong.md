# ControlHandler(ulong)

- ea: `0x14000b0a0`
- end: `0x14000b1bc`
- name: `?ControlHandler@@YAXK@Z`
- size: `284`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x140003e50`
- `0x14000ac88`
- `0x14000b0a0`
- `0x14000b8cc`
- `0x14000bc4c`
- `0x14000bc7c`

## import_xrefs

- `ADVAPI32!SetServiceStatus` at `0x14000b153`
- `ADVAPI32!SetServiceStatus` at `0x14000b153`
- `ADVAPI32!EventUnregister` at `0x14000b101`
- `ADVAPI32!EventUnregister` at `0x14000b101`
- `KERNEL32!OutputDebugStringW` at `0x14000b181`
- `KERNEL32!OutputDebugStringW` at `0x14000b19e`
- `KERNEL32!OutputDebugStringW` at `0x14000b181`
- `KERNEL32!OutputDebugStringW` at `0x14000b19e`

## string_xrefs

- `0x14000b0be`: `AgentService.ControlHandler: Entry`
- `0x14000b0d4`: `AgentService.ControlHandler: Stop`
- `0x14000b159`: `AgentService.ControlHandler: Exit`
- `0x14000b17a`: `Failed to unregister the UE-V event log service for the Agent Service`
- `0x14000b197`: `Failed to unregister the UE-V event log service for IPC`

## pseudocode

```c
void __fastcall ControlHandler(DWORD dwControl)
{
  char v2; // di
  DWORD v3; // ebx
  unsigned int v4; // ecx
  REGHANDLE v5; // rcx
  __int64 v6; // r8
  _BYTE v7[16]; // [rsp+30h] [rbp-28h] BYREF

  v2 = 0;
  DbgTrace<5>(L"AgentService.ControlHandler: Entry");
  v3 = dwControl - 1;
  if ( !v3 || v3 == 4 )
  {
    DbgTrace<5>(L"AgentService.ControlHandler: Stop");
    ShutdownService(v4);
    v5 = RegHandle;
    dword_1400CB248 = 0;
    RegHandle = 0;
    EventUnregister(v5);
    v2 = 1;
    if ( (Microsoft_User_Experience_Virtualization_App_AgentEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(UevAppAgentProvider_Context, AgentServiceLog_ServiceStopped, v6, 1, v7);
    ServiceStatus.dwWin32ExitCode = 0;
    ServiceStatus.dwCurrentState = 1;
  }
  SetServiceStatus(hStatus, &ServiceStatus);
  DbgTrace<5>(L"AgentService.ControlHandler: Exit");
  if ( v2 )
  {
    if ( (unsigned int)McGenEventUnregister_EventUnregister(UevAppAgentProvider_Context) )
      OutputDebugStringW(L"Failed to unregister the UE-V event log service for the Agent Service");
    if ( (unsigned int)McGenEventUnregister_EventUnregister(UevIPCProvider_Context) )
      OutputDebugStringW(L"Failed to unregister the UE-V event log service for IPC");
  }
}

```

## disassembly

```asm
0x14000b0a0  mov     [rsp+arg_0], rbx
0x14000b0a5  push    rdi
0x14000b0a6  sub     rsp, 50h
0x14000b0aa  mov     rax, cs:__security_cookie
0x14000b0b1  xor     rax, rsp
0x14000b0b4  mov     [rsp+58h+var_18], rax
0x14000b0b9  mov     ebx, ecx
0x14000b0bb  xor     dil, dil
0x14000b0be  lea     rcx, aAgentserviceCo_1; "AgentService.ControlHandler: Entry"
0x14000b0c5  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14000b0ca  sub     ebx, 1
0x14000b0cd  jz      short loc_14000B0D4
0x14000b0cf  cmp     ebx, 4
0x14000b0d2  jnz     short loc_14000B145
0x14000b0d4  lea     rcx, aAgentserviceCo; "AgentService.ControlHandler: Stop"
0x14000b0db  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14000b0e0  call    ?ShutdownService@@YAXK@Z; ShutdownService(ulong)
0x14000b0e5  mov     rcx, cs:RegHandle; RegHandle
0x14000b0ec  mov     cs:dword_1400CB248, 0
0x14000b0f6  mov     cs:RegHandle, 0
0x14000b101  call    cs:__imp_EventUnregister
0x14000b107  test    cs:Microsoft_User_Experience_Virtualization_App_AgentEnableBits, 2
0x14000b10e  mov     edi, 1
0x14000b113  jz      short loc_14000B135
0x14000b115  lea     rax, [rsp+58h+var_28]
0x14000b11a  mov     r9d, edi
0x14000b11d  lea     rdx, AgentServiceLog_ServiceStopped
0x14000b124  mov     [rsp+58h+var_38], rax
0x14000b129  lea     rcx, UevAppAgentProvider_Context
0x14000b130  call    McGenEventWrite_EventWriteTransfer
0x14000b135  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwWin32ExitCode, 0; _SERVICE_STATUS ServiceStatus ...
0x14000b13f  mov     cs:?ServiceStatus@@3U_SERVICE_STATUS@@A.dwCurrentState, edi; _SERVICE_STATUS ServiceStatus ...
0x14000b145  mov     rcx, cs:?hStatus@@3PEAUSERVICE_STATUS_HANDLE__@@EA; hServiceStatus
0x14000b14c  lea     rdx, ?ServiceStatus@@3U_SERVICE_STATUS@@A; lpServiceStatus
0x14000b153  call    cs:__imp_SetServiceStatus
0x14000b159  lea     rcx, aAgentserviceCo_0; "AgentService.ControlHandler: Exit"
0x14000b160  call    ??$DbgTrace@$04@@YAXPEB_W@Z; DbgTrace<5>(wchar_t const *)
0x14000b165  test    dil, dil
0x14000b168  jz      short loc_14000B1A4
0x14000b16a  lea     rcx, UevAppAgentProvider_Context
0x14000b171  call    McGenEventUnregister_EventUnregister
0x14000b176  test    eax, eax
0x14000b178  jz      short loc_14000B187
0x14000b17a  lea     rcx, OutputString; "Failed to unregister the UE-V event log"...
0x14000b181  call    cs:__imp_OutputDebugStringW
0x14000b187  lea     rcx, UevIPCProvider_Context
0x14000b18e  call    McGenEventUnregister_EventUnregister
0x14000b193  test    eax, eax
0x14000b195  jz      short loc_14000B1A4
0x14000b197  lea     rcx, aFailedToUnregi_0; "Failed to unregister the UE-V event log"...
0x14000b19e  call    cs:__imp_OutputDebugStringW
0x14000b1a4  mov     rcx, [rsp+58h+var_18]
0x14000b1a9  xor     rcx, rsp; StackCookie
0x14000b1ac  call    __security_check_cookie
0x14000b1b1  mov     rbx, [rsp+58h+arg_0]
0x14000b1b6  add     rsp, 50h
0x14000b1ba  pop     rdi
0x14000b1bb  retn
```
