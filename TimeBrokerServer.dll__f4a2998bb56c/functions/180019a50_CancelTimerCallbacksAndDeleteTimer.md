# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180019a50`
- end: `0x180019aa3`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180019b40`
- `0x180019b74`

## callees

- `0x180019a50`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019a6d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180019a6d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019a8c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180019a8c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019a7f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180019a7f`

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
0x180019a50  push    rbx
0x180019a52  sub     rsp, 20h
0x180019a56  mov     rbx, rcx
0x180019a59  mov     rcx, [rcx+158h]; pti
0x180019a60  test    rcx, rcx
0x180019a63  jz      short loc_180019A9D
0x180019a65  xor     r9d, r9d; msWindowLength
0x180019a68  xor     r8d, r8d; msPeriod
0x180019a6b  xor     edx, edx; pftDueTime
0x180019a6d  call    cs:__imp_SetThreadpoolTimer
0x180019a73  mov     rcx, [rbx+158h]; pti
0x180019a7a  mov     edx, 1; fCancelPendingCallbacks
0x180019a7f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180019a85  mov     rcx, [rbx+158h]; pti
0x180019a8c  call    cs:__imp_CloseThreadpoolTimer
0x180019a92  mov     qword ptr [rbx+158h], 0
0x180019a9d  add     rsp, 20h
0x180019aa1  pop     rbx
0x180019aa2  retn
```
