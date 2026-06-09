# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180021e88`
- end: `0x180021edb`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18002224c`
- `0x180022e8c`

## callees

- `0x180021e88`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180021ec4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180021ec4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180021ea5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180021ea5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180021eb7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180021eb7`

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
0x180021e88  push    rbx
0x180021e8a  sub     rsp, 20h
0x180021e8e  mov     rbx, rcx
0x180021e91  mov     rcx, [rcx+158h]; pti
0x180021e98  test    rcx, rcx
0x180021e9b  jz      short loc_180021ED5
0x180021e9d  xor     r9d, r9d; msWindowLength
0x180021ea0  xor     r8d, r8d; msPeriod
0x180021ea3  xor     edx, edx; pftDueTime
0x180021ea5  call    cs:__imp_SetThreadpoolTimer
0x180021eab  mov     rcx, [rbx+158h]; pti
0x180021eb2  mov     edx, 1; fCancelPendingCallbacks
0x180021eb7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180021ebd  mov     rcx, [rbx+158h]; pti
0x180021ec4  call    cs:__imp_CloseThreadpoolTimer
0x180021eca  mov     qword ptr [rbx+158h], 0
0x180021ed5  add     rsp, 20h
0x180021ed9  pop     rbx
0x180021eda  retn
```
