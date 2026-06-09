# CancelTimerCallbacksAndDeleteTimer

- ea: `0x140044f18`
- end: `0x140044f6b`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140045248`
- `0x140045e98`

## callees

- `0x140044f18`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140044f54`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140044f54`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140044f47`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140044f47`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140044f35`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140044f35`

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
0x140044f18  push    rbx
0x140044f1a  sub     rsp, 20h
0x140044f1e  mov     rbx, rcx
0x140044f21  mov     rcx, [rcx+158h]; pti
0x140044f28  test    rcx, rcx
0x140044f2b  jz      short loc_140044F65
0x140044f2d  xor     r9d, r9d; msWindowLength
0x140044f30  xor     r8d, r8d; msPeriod
0x140044f33  xor     edx, edx; pftDueTime
0x140044f35  call    cs:__imp_SetThreadpoolTimer
0x140044f3b  mov     rcx, [rbx+158h]; pti
0x140044f42  mov     edx, 1; fCancelPendingCallbacks
0x140044f47  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140044f4d  mov     rcx, [rbx+158h]; pti
0x140044f54  call    cs:__imp_CloseThreadpoolTimer
0x140044f5a  mov     qword ptr [rbx+158h], 0
0x140044f65  add     rsp, 20h
0x140044f69  pop     rbx
0x140044f6a  retn
```
