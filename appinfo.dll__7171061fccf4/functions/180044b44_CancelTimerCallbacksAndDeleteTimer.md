# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180044b44`
- end: `0x180044b97`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180044f08`
- `0x180045b40`

## callees

- `0x180044b44`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180044b80`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180044b80`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180044b73`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180044b73`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180044b61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180044b61`

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
0x180044b44  push    rbx
0x180044b46  sub     rsp, 20h
0x180044b4a  mov     rbx, rcx
0x180044b4d  mov     rcx, [rcx+158h]; pti
0x180044b54  test    rcx, rcx
0x180044b57  jz      short loc_180044B91
0x180044b59  xor     r9d, r9d; msWindowLength
0x180044b5c  xor     r8d, r8d; msPeriod
0x180044b5f  xor     edx, edx; pftDueTime
0x180044b61  call    cs:__imp_SetThreadpoolTimer
0x180044b67  mov     rcx, [rbx+158h]; pti
0x180044b6e  mov     edx, 1; fCancelPendingCallbacks
0x180044b73  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180044b79  mov     rcx, [rbx+158h]; pti
0x180044b80  call    cs:__imp_CloseThreadpoolTimer
0x180044b86  mov     qword ptr [rbx+158h], 0
0x180044b91  add     rsp, 20h
0x180044b95  pop     rbx
0x180044b96  retn
```
