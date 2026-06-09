# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18000b320`
- end: `0x18000b373`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: `void __fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b1d0`
- `0x18000b5bc`
- `0x18000c0e8`

## callees

- `0x18000b320`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b33d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b33d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b35c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b35c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b34f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b34f`

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
0x18000b320  push    rbx
0x18000b322  sub     rsp, 20h
0x18000b326  mov     rbx, rcx
0x18000b329  mov     rcx, [rcx+158h]; pti
0x18000b330  test    rcx, rcx
0x18000b333  jz      short loc_18000B36D
0x18000b335  xor     r9d, r9d; msWindowLength
0x18000b338  xor     r8d, r8d; msPeriod
0x18000b33b  xor     edx, edx; pftDueTime
0x18000b33d  call    cs:__imp_SetThreadpoolTimer
0x18000b343  mov     rcx, [rbx+158h]; pti
0x18000b34a  mov     edx, 1; fCancelPendingCallbacks
0x18000b34f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b355  mov     rcx, [rbx+158h]; pti
0x18000b35c  call    cs:__imp_CloseThreadpoolTimer
0x18000b362  mov     qword ptr [rbx+158h], 0
0x18000b36d  add     rsp, 20h
0x18000b371  pop     rbx
0x18000b372  retn
```
