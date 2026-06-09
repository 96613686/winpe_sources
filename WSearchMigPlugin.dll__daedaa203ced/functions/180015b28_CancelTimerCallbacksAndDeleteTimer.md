# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180015b28`
- end: `0x180015b7b`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180015dc4`
- `0x1800168e8`
- `0x1800169fc`

## callees

- `0x180015b28`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015b45`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015b45`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015b64`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180015b64`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015b57`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180015b57`

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
0x180015b28  push    rbx
0x180015b2a  sub     rsp, 20h
0x180015b2e  mov     rbx, rcx
0x180015b31  mov     rcx, [rcx+158h]; pti
0x180015b38  test    rcx, rcx
0x180015b3b  jz      short loc_180015B75
0x180015b3d  xor     r9d, r9d; msWindowLength
0x180015b40  xor     r8d, r8d; msPeriod
0x180015b43  xor     edx, edx; pftDueTime
0x180015b45  call    cs:__imp_SetThreadpoolTimer
0x180015b4b  mov     rcx, [rbx+158h]; pti
0x180015b52  mov     edx, 1; fCancelPendingCallbacks
0x180015b57  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180015b5d  mov     rcx, [rbx+158h]; pti
0x180015b64  call    cs:__imp_CloseThreadpoolTimer
0x180015b6a  mov     qword ptr [rbx+158h], 0
0x180015b75  add     rsp, 20h
0x180015b79  pop     rbx
0x180015b7a  retn
```
