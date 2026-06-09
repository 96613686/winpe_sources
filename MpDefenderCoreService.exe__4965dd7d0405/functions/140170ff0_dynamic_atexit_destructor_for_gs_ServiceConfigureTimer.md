# _dynamic_atexit_destructor_for__gs_ServiceConfigureTimer__

- ea: `0x140170ff0`
- end: `0x140171011`
- name: `_dynamic_atexit_destructor_for__gs_ServiceConfigureTimer__`
- size: `33`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x140170ff0`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x140171006`
- `KERNEL32!DeleteTimerQueueTimer` at `0x140171006`

## pseudocode

```c
BOOL dynamic_atexit_destructor_for__gs_ServiceConfigureTimer__()
{
  BOOL result; // eax

  if ( gs_ServiceConfigureTimer )
    return DeleteTimerQueueTimer(0, gs_ServiceConfigureTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  return result;
}

```

## disassembly

```asm
0x140170ff0  sub     rsp, 28h
0x140170ff4  mov     rdx, cs:?gs_ServiceConfigureTimer@@3V?$CUniqueHandle@UCAutoDeleteTimerQueueTimer@CommonUtil@@@CommonUtil@@A; Timer
0x140170ffb  test    rdx, rdx
0x140170ffe  jz      short loc_14017100C
0x140171000  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x140171004  xor     ecx, ecx; TimerQueue
0x140171006  call    cs:__imp_DeleteTimerQueueTimer
0x14017100c  add     rsp, 28h
0x140171010  retn
```
