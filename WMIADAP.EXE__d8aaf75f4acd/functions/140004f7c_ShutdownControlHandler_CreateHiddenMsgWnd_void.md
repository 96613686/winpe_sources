# ShutdownControlHandler::CreateHiddenMsgWnd(void)

- ea: `0x140004f7c`
- end: `0x140005030`
- name: `?CreateHiddenMsgWnd@ShutdownControlHandler@@AEAAXXZ`
- size: `180`
- prototype: `void __fastcall(ShutdownControlHandler *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140005ad0`

## callees

- `0x140004f7c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140004fbb`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140004fbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000501a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000501a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004ff1`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140004ff1`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140004ffe`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140004ffe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004fcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140004fcd`

## pseudocode

```c
void __fastcall ShutdownControlHandler::CreateHiddenMsgWnd(ShutdownControlHandler *this)
{
  signed int LastError; // eax
  ShutdownControlHandler *ThreadId; // [rsp+40h] [rbp+8h] BYREF

  ThreadId = this;
  if ( !ShutdownControlHandler::mg_hThreadPumpHandle )
  {
    LODWORD(ThreadId) = 0;
    ShutdownControlHandler::mg_hThreadPumpHandle = CreateThread(
                                                     0,
                                                     0,
                                                     ShutdownControlHandler::WindowThreadProc,
                                                     0,
                                                     0,
                                                     (LPDWORD)&ThreadId);
    if ( ShutdownControlHandler::mg_hThreadPumpHandle )
    {
      WaitForSingleObject(ShutdownControlHandler::mg_hReadyEvent, 0xFFFFFFFF);
      ResetEvent(ShutdownControlHandler::mg_hReadyEvent);
      LastError = ShutdownControlHandler::mg_hrInit;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      ShutdownControlHandler::mg_hrInit = LastError;
    }
    if ( LastError < 0 )
    {
      if ( ShutdownControlHandler::mg_hThreadPumpHandle )
      {
        CloseHandle(ShutdownControlHandler::mg_hThreadPumpHandle);
        ShutdownControlHandler::mg_hThreadPumpHandle = 0;
      }
    }
  }
}

```

## disassembly

```asm
0x140004f7c  mov     [rsp+ThreadId], rcx
0x140004f81  sub     rsp, 38h
0x140004f85  cmp     cs:?mg_hThreadPumpHandle@ShutdownControlHandler@@0PEAXEA, 0; void * ShutdownControlHandler::mg_hThreadPumpHandle
0x140004f8d  jnz     loc_14000502B
0x140004f93  lea     rax, [rsp+38h+ThreadId]
0x140004f98  mov     dword ptr [rsp+38h+ThreadId], 0
0x140004fa0  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x140004fa5  lea     r8, ?WindowThreadProc@ShutdownControlHandler@@CAKPEAX@Z; lpStartAddress
0x140004fac  xor     r9d, r9d; lpParameter
0x140004faf  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x140004fb7  xor     edx, edx; dwStackSize
0x140004fb9  xor     ecx, ecx; lpThreadAttributes
0x140004fbb  call    cs:__imp_CreateThread
0x140004fc1  mov     cs:?mg_hThreadPumpHandle@ShutdownControlHandler@@0PEAXEA, rax; void * ShutdownControlHandler::mg_hThreadPumpHandle
0x140004fc8  test    rax, rax
0x140004fcb  jnz     short loc_140004FE7
0x140004fcd  call    cs:__imp_GetLastError
0x140004fd3  test    eax, eax
0x140004fd5  jle     short loc_140004FDF
0x140004fd7  movzx   eax, ax
0x140004fda  or      eax, 80070000h
0x140004fdf  mov     cs:?mg_hrInit@ShutdownControlHandler@@0JA, eax; long ShutdownControlHandler::mg_hrInit
0x140004fe5  jmp     short loc_14000500A
0x140004fe7  mov     rcx, cs:?mg_hReadyEvent@ShutdownControlHandler@@0PEAXEA; hHandle
0x140004fee  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140004ff1  call    cs:__imp_WaitForSingleObject
0x140004ff7  mov     rcx, cs:?mg_hReadyEvent@ShutdownControlHandler@@0PEAXEA; hEvent
0x140004ffe  call    cs:__imp_ResetEvent
0x140005004  mov     eax, cs:?mg_hrInit@ShutdownControlHandler@@0JA; long ShutdownControlHandler::mg_hrInit
0x14000500a  test    eax, eax
0x14000500c  jns     short loc_14000502B
0x14000500e  mov     rcx, cs:?mg_hThreadPumpHandle@ShutdownControlHandler@@0PEAXEA; hObject
0x140005015  test    rcx, rcx
0x140005018  jz      short loc_14000502B
0x14000501a  call    cs:__imp_CloseHandle
0x140005020  mov     cs:?mg_hThreadPumpHandle@ShutdownControlHandler@@0PEAXEA, 0; void * ShutdownControlHandler::mg_hThreadPumpHandle
0x14000502b  add     rsp, 38h
0x14000502f  retn
```
