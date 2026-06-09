# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180098fcc`
- end: `0x18009901f`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180099390`
- `0x180099fc0`

## callees

- `0x180098fcc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180099008`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180099008`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180098ffb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180098ffb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180098fe9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180098fe9`

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
0x180098fcc  push    rbx
0x180098fce  sub     rsp, 20h
0x180098fd2  mov     rbx, rcx
0x180098fd5  mov     rcx, [rcx+158h]; pti
0x180098fdc  test    rcx, rcx
0x180098fdf  jz      short loc_180099019
0x180098fe1  xor     r9d, r9d; msWindowLength
0x180098fe4  xor     r8d, r8d; msPeriod
0x180098fe7  xor     edx, edx; pftDueTime
0x180098fe9  call    cs:__imp_SetThreadpoolTimer
0x180098fef  mov     rcx, [rbx+158h]; pti
0x180098ff6  mov     edx, 1; fCancelPendingCallbacks
0x180098ffb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180099001  mov     rcx, [rbx+158h]; pti
0x180099008  call    cs:__imp_CloseThreadpoolTimer
0x18009900e  mov     qword ptr [rbx+158h], 0
0x180099019  add     rsp, 20h
0x18009901d  pop     rbx
0x18009901e  retn
```
