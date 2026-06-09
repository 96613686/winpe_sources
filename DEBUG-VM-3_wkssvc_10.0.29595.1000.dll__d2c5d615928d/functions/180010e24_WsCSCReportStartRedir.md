# WsCSCReportStartRedir

- ea: `0x180010e24`
- end: `0x180010f27`
- name: `WsCSCReportStartRedir`
- size: `259`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x180005dec`
- `0x18002c59c`

## callees

- `0x180010e24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010e98`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010f0d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010f0d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010e46`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010e66`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010e86`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010e46`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010e66`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180010e86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010eb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ecd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010eea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010eb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010ecd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180010eea`

## string_xrefs

- `0x180010e58`: `WkssvcToAgentStopEvent`
- `0x180010e78`: `AgentToWkssvcEvent`
- `0x180010e3a`: `WkssvcToAgentStartEvent`

## pseudocode

```c
__int64 WsCSCReportStartRedir()
{
  LPSECURITY_ATTRIBUTES v0; // rcx
  DWORD LastError; // ebx

  v0 = heventWkssvcToAgentStart;
  if ( !heventWkssvcToAgentStart )
  {
    heventWkssvcToAgentStart = (LPSECURITY_ATTRIBUTES)CreateEventW(0, 0, 0, aWkssvctoagents);
    if ( !heventWkssvcToAgentStart
      || (heventWkssvcToAgentStop = CreateEventW(0, 0, 0, aWkssvctoagents_0)) == 0
      || (heventAgentToWkssvc = CreateEventW(0, 0, 0, aAgenttowkssvce)) == 0 )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        if ( heventWkssvcToAgentStart )
        {
          CloseHandle(heventWkssvcToAgentStart);
          heventWkssvcToAgentStart = 0;
        }
        if ( heventWkssvcToAgentStop )
        {
          CloseHandle(heventWkssvcToAgentStop);
          heventWkssvcToAgentStop = 0;
        }
        if ( heventAgentToWkssvc )
        {
          CloseHandle(heventAgentToWkssvc);
          heventAgentToWkssvc = 0;
        }
      }
      return LastError;
    }
    v0 = heventWkssvcToAgentStart;
  }
  if ( !vfRedirStarted )
  {
    SetEvent(v0);
    vfRedirStarted = 1;
  }
  return 0;
}

```

## disassembly

```asm
0x180010e24  push    rbx
0x180010e26  sub     rsp, 20h
0x180010e2a  mov     rcx, cs:heventWkssvcToAgentStart; lpEventAttributes
0x180010e31  test    rcx, rcx
0x180010e34  jnz     loc_180010F04
0x180010e3a  lea     r9, aWkssvctoagents; "WkssvcToAgentStartEvent"
0x180010e41  xor     r8d, r8d; bInitialState
0x180010e44  xor     edx, edx; bManualReset
0x180010e46  call    cs:__imp_CreateEventW
0x180010e4c  mov     cs:heventWkssvcToAgentStart, rax
0x180010e53  test    rax, rax
0x180010e56  jz      short loc_180010E98
0x180010e58  lea     r9, aWkssvctoagents_0; "WkssvcToAgentStopEvent"
0x180010e5f  xor     r8d, r8d; bInitialState
0x180010e62  xor     edx, edx; bManualReset
0x180010e64  xor     ecx, ecx; lpEventAttributes
0x180010e66  call    cs:__imp_CreateEventW
0x180010e6c  mov     cs:heventWkssvcToAgentStop, rax
0x180010e73  test    rax, rax
0x180010e76  jz      short loc_180010E98
0x180010e78  lea     r9, aAgenttowkssvce; "AgentToWkssvcEvent"
0x180010e7f  xor     r8d, r8d; bInitialState
0x180010e82  xor     edx, edx; bManualReset
0x180010e84  xor     ecx, ecx; lpEventAttributes
0x180010e86  call    cs:__imp_CreateEventW
0x180010e8c  mov     cs:heventAgentToWkssvc, rax
0x180010e93  test    rax, rax
0x180010e96  jnz     short loc_180010EFD
0x180010e98  call    cs:__imp_GetLastError
0x180010e9e  mov     ebx, eax
0x180010ea0  test    eax, eax
0x180010ea2  jz      short loc_180010F1F
0x180010ea4  mov     rcx, cs:heventWkssvcToAgentStart; hObject
0x180010eab  test    rcx, rcx
0x180010eae  jz      short loc_180010EC1
0x180010eb0  call    cs:__imp_CloseHandle
0x180010eb6  mov     cs:heventWkssvcToAgentStart, 0
0x180010ec1  mov     rcx, cs:heventWkssvcToAgentStop; hObject
0x180010ec8  test    rcx, rcx
0x180010ecb  jz      short loc_180010EDE
0x180010ecd  call    cs:__imp_CloseHandle
0x180010ed3  mov     cs:heventWkssvcToAgentStop, 0
0x180010ede  mov     rcx, cs:heventAgentToWkssvc; hObject
0x180010ee5  test    rcx, rcx
0x180010ee8  jz      short loc_180010F1F
0x180010eea  call    cs:__imp_CloseHandle
0x180010ef0  mov     cs:heventAgentToWkssvc, 0
0x180010efb  jmp     short loc_180010F1F
0x180010efd  mov     rcx, cs:heventWkssvcToAgentStart; hEvent
0x180010f04  cmp     cs:vfRedirStarted, 0
0x180010f0b  jnz     short loc_180010F1D
0x180010f0d  call    cs:__imp_SetEvent
0x180010f13  mov     cs:vfRedirStarted, 1
0x180010f1d  xor     ebx, ebx
0x180010f1f  mov     eax, ebx
0x180010f21  add     rsp, 20h
0x180010f25  pop     rbx
0x180010f26  retn
```
