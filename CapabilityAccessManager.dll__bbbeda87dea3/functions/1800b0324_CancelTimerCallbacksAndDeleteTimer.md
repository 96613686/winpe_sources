# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1800b0324`
- end: `0x1800b0377`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800b06e8`
- `0x1800b132c`

## callees

- `0x1800b0324`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b0360`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800b0360`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b0353`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800b0353`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b0341`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800b0341`

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
0x1800b0324  push    rbx
0x1800b0326  sub     rsp, 20h
0x1800b032a  mov     rbx, rcx
0x1800b032d  mov     rcx, [rcx+158h]; pti
0x1800b0334  test    rcx, rcx
0x1800b0337  jz      short loc_1800B0371
0x1800b0339  xor     r9d, r9d; msWindowLength
0x1800b033c  xor     r8d, r8d; msPeriod
0x1800b033f  xor     edx, edx; pftDueTime
0x1800b0341  call    cs:__imp_SetThreadpoolTimer
0x1800b0347  mov     rcx, [rbx+158h]; pti
0x1800b034e  mov     edx, 1; fCancelPendingCallbacks
0x1800b0353  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800b0359  mov     rcx, [rbx+158h]; pti
0x1800b0360  call    cs:__imp_CloseThreadpoolTimer
0x1800b0366  mov     qword ptr [rbx+158h], 0
0x1800b0371  add     rsp, 20h
0x1800b0375  pop     rbx
0x1800b0376  retn
```
