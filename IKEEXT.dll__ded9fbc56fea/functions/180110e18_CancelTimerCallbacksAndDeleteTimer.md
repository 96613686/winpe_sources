# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180110e18`
- end: `0x180110e6b`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1801111c8`
- `0x180111a5c`

## callees

- `0x180110e18`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180110e35`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180110e35`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180110e54`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180110e54`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180110e47`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180110e47`

## pseudocode

```c
void __fastcall CancelTimerCallbacksAndDeleteTimer(__int64 a1)
{
  struct _TP_TIMER *v2; // rcx

  v2 = *(struct _TP_TIMER **)(a1 + 344);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)(a1 + 344), 1);
    CloseThreadpoolTimer(*(PTP_TIMER *)(a1 + 344));
    *(_QWORD *)(a1 + 344) = 0;
  }
}

```

## disassembly

```asm
0x180110e18  push    rbx
0x180110e1a  sub     rsp, 20h
0x180110e1e  mov     rbx, rcx
0x180110e21  mov     rcx, [rcx+158h]; pti
0x180110e28  test    rcx, rcx
0x180110e2b  jz      short loc_180110E65
0x180110e2d  xor     r9d, r9d; msWindowLength
0x180110e30  xor     r8d, r8d; msPeriod
0x180110e33  xor     edx, edx; pftDueTime
0x180110e35  call    cs:__imp_SetThreadpoolTimer
0x180110e3b  mov     rcx, [rbx+158h]; pti
0x180110e42  mov     edx, 1; fCancelPendingCallbacks
0x180110e47  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180110e4d  mov     rcx, [rbx+158h]; pti
0x180110e54  call    cs:__imp_CloseThreadpoolTimer
0x180110e5a  mov     qword ptr [rbx+158h], 0
0x180110e65  add     rsp, 20h
0x180110e69  pop     rbx
0x180110e6a  retn
```
