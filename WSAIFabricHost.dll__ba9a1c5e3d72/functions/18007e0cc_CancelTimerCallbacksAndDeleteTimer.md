# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18007e0cc`
- end: `0x18007e11f`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18007e368`
- `0x18007ee88`
- `0x18007ef9c`

## callees

- `0x18007e0cc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007e0fb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007e0fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007e108`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007e108`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007e0e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007e0e9`

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
0x18007e0cc  push    rbx
0x18007e0ce  sub     rsp, 20h
0x18007e0d2  mov     rbx, rcx
0x18007e0d5  mov     rcx, [rcx+158h]; pti
0x18007e0dc  test    rcx, rcx
0x18007e0df  jz      short loc_18007E119
0x18007e0e1  xor     r9d, r9d; msWindowLength
0x18007e0e4  xor     r8d, r8d; msPeriod
0x18007e0e7  xor     edx, edx; pftDueTime
0x18007e0e9  call    cs:__imp_SetThreadpoolTimer
0x18007e0ef  mov     rcx, [rbx+158h]; pti
0x18007e0f6  mov     edx, 1; fCancelPendingCallbacks
0x18007e0fb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007e101  mov     rcx, [rbx+158h]; pti
0x18007e108  call    cs:__imp_CloseThreadpoolTimer
0x18007e10e  mov     qword ptr [rbx+158h], 0
0x18007e119  add     rsp, 20h
0x18007e11d  pop     rbx
0x18007e11e  retn
```
