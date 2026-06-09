# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1800cf660`
- end: `0x1800cf6b3`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800cfa24`
- `0x1800d065c`

## callees

- `0x1800cf660`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800cf69c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800cf69c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800cf68f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800cf68f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800cf67d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800cf67d`

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
0x1800cf660  push    rbx
0x1800cf662  sub     rsp, 20h
0x1800cf666  mov     rbx, rcx
0x1800cf669  mov     rcx, [rcx+158h]; pti
0x1800cf670  test    rcx, rcx
0x1800cf673  jz      short loc_1800CF6AD
0x1800cf675  xor     r9d, r9d; msWindowLength
0x1800cf678  xor     r8d, r8d; msPeriod
0x1800cf67b  xor     edx, edx; pftDueTime
0x1800cf67d  call    cs:__imp_SetThreadpoolTimer
0x1800cf683  mov     rcx, [rbx+158h]; pti
0x1800cf68a  mov     edx, 1; fCancelPendingCallbacks
0x1800cf68f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800cf695  mov     rcx, [rbx+158h]; pti
0x1800cf69c  call    cs:__imp_CloseThreadpoolTimer
0x1800cf6a2  mov     qword ptr [rbx+158h], 0
0x1800cf6ad  add     rsp, 20h
0x1800cf6b1  pop     rbx
0x1800cf6b2  retn
```
