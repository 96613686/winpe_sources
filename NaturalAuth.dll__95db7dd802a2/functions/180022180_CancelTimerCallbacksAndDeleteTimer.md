# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180022180`
- end: `0x1800221d3`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180022544`
- `0x180023170`

## callees

- `0x180022180`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800221bc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800221bc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002219d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002219d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800221af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800221af`

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
0x180022180  push    rbx
0x180022182  sub     rsp, 20h
0x180022186  mov     rbx, rcx
0x180022189  mov     rcx, [rcx+158h]; pti
0x180022190  test    rcx, rcx
0x180022193  jz      short loc_1800221CD
0x180022195  xor     r9d, r9d; msWindowLength
0x180022198  xor     r8d, r8d; msPeriod
0x18002219b  xor     edx, edx; pftDueTime
0x18002219d  call    cs:__imp_SetThreadpoolTimer
0x1800221a3  mov     rcx, [rbx+158h]; pti
0x1800221aa  mov     edx, 1; fCancelPendingCallbacks
0x1800221af  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800221b5  mov     rcx, [rbx+158h]; pti
0x1800221bc  call    cs:__imp_CloseThreadpoolTimer
0x1800221c2  mov     qword ptr [rbx+158h], 0
0x1800221cd  add     rsp, 20h
0x1800221d1  pop     rbx
0x1800221d2  retn
```
