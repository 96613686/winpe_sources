# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18001a790`
- end: `0x18001a7e3`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18001aa2c`
- `0x18001b568`
- `0x18001b720`

## callees

- `0x18001a790`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001a7bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001a7bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001a7cc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001a7cc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001a7ad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001a7ad`

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
0x18001a790  push    rbx
0x18001a792  sub     rsp, 20h
0x18001a796  mov     rbx, rcx
0x18001a799  mov     rcx, [rcx+158h]; pti
0x18001a7a0  test    rcx, rcx
0x18001a7a3  jz      short loc_18001A7DD
0x18001a7a5  xor     r9d, r9d; msWindowLength
0x18001a7a8  xor     r8d, r8d; msPeriod
0x18001a7ab  xor     edx, edx; pftDueTime
0x18001a7ad  call    cs:__imp_SetThreadpoolTimer
0x18001a7b3  mov     rcx, [rbx+158h]; pti
0x18001a7ba  mov     edx, 1; fCancelPendingCallbacks
0x18001a7bf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001a7c5  mov     rcx, [rbx+158h]; pti
0x18001a7cc  call    cs:__imp_CloseThreadpoolTimer
0x18001a7d2  mov     qword ptr [rbx+158h], 0
0x18001a7dd  add     rsp, 20h
0x18001a7e1  pop     rbx
0x18001a7e2  retn
```
