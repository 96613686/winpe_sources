# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180021ecc`
- end: `0x180021f1f`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180022080`
- `0x180022170`

## callees

- `0x180021ecc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180021f08`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180021f08`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180021ee9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180021ee9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180021efb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180021efb`

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
0x180021ecc  push    rbx
0x180021ece  sub     rsp, 20h
0x180021ed2  mov     rbx, rcx
0x180021ed5  mov     rcx, [rcx+158h]; pti
0x180021edc  test    rcx, rcx
0x180021edf  jz      short loc_180021F19
0x180021ee1  xor     r9d, r9d; msWindowLength
0x180021ee4  xor     r8d, r8d; msPeriod
0x180021ee7  xor     edx, edx; pftDueTime
0x180021ee9  call    cs:__imp_SetThreadpoolTimer
0x180021eef  mov     rcx, [rbx+158h]; pti
0x180021ef6  mov     edx, 1; fCancelPendingCallbacks
0x180021efb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180021f01  mov     rcx, [rbx+158h]; pti
0x180021f08  call    cs:__imp_CloseThreadpoolTimer
0x180021f0e  mov     qword ptr [rbx+158h], 0
0x180021f19  add     rsp, 20h
0x180021f1d  pop     rbx
0x180021f1e  retn
```
