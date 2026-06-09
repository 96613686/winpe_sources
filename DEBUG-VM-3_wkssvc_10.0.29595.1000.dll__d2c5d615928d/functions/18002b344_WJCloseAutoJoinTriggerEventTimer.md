# WJCloseAutoJoinTriggerEventTimer

- ea: `0x18002b344`
- end: `0x18002b396`
- name: `WJCloseAutoJoinTriggerEventTimer`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001d4c0`
- `0x18002bed8`

## callees

- `0x18002b344`
- `0x18002b444`

## import_xrefs

- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b360`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b38b`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b360`
- `dsreg!DsrWriteAutoJoinSvcDebugEvent` at `0x18002b38b`

## string_xrefs

- `0x18002b359`: `AutoJoinSvc/%s: Canceling thread pool timer to write the auto join trigger event.`
- `0x18002b384`: `AutoJoinSvc/%s: Thread pool timer to write the auto join trigger event is cancelled.`

## pseudocode

```c
__int64 WJCloseAutoJoinTriggerEventTimer()
{
  __int64 result; // rax

  if ( g_AutoJoinTriggerEventTimer )
  {
    DsrWriteAutoJoinSvcDebugEvent(
      L"AutoJoinSvc/%s: Canceling thread pool timer to write the auto join trigger event.",
      L"WJCloseAutoJoinTriggerEventTimer");
    WJCloseThreadPoolTimer(g_AutoJoinTriggerEventTimer);
    g_AutoJoinTriggerEventTimer = 0;
    return DsrWriteAutoJoinSvcDebugEvent(
             L"AutoJoinSvc/%s: Thread pool timer to write the auto join trigger event is cancelled.",
             L"WJCloseAutoJoinTriggerEventTimer");
  }
  return result;
}

```

## disassembly

```asm
0x18002b344  sub     rsp, 28h
0x18002b348  cmp     cs:g_AutoJoinTriggerEventTimer, 0
0x18002b350  jz      short loc_18002B391
0x18002b352  lea     rdx, aWjcloseautojoi; "WJCloseAutoJoinTriggerEventTimer"
0x18002b359  lea     rcx, aAutojoinsvcSCa_0; "AutoJoinSvc/%s: Canceling thread pool t"...
0x18002b360  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002b366  mov     rcx, cs:g_AutoJoinTriggerEventTimer; pti
0x18002b36d  call    WJCloseThreadPoolTimer
0x18002b372  lea     rdx, aWjcloseautojoi; "WJCloseAutoJoinTriggerEventTimer"
0x18002b379  mov     cs:g_AutoJoinTriggerEventTimer, 0
0x18002b384  lea     rcx, aAutojoinsvcSTh_2; "AutoJoinSvc/%s: Thread pool timer to wr"...
0x18002b38b  call    cs:__imp_DsrWriteAutoJoinSvcDebugEvent
0x18002b391  add     rsp, 28h
0x18002b395  retn
```
