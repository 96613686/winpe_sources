# CancelTimerCallbacksAndDeleteTimer

- ea: `0x140047e90`
- end: `0x140047ee3`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1400481c0`
- `0x140048e08`

## callees

- `0x140047e90`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140047ebf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140047ebf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140047ead`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140047ead`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140047ecc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140047ecc`

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
0x140047e90  push    rbx
0x140047e92  sub     rsp, 20h
0x140047e96  mov     rbx, rcx
0x140047e99  mov     rcx, [rcx+158h]; pti
0x140047ea0  test    rcx, rcx
0x140047ea3  jz      short loc_140047EDD
0x140047ea5  xor     r9d, r9d; msWindowLength
0x140047ea8  xor     r8d, r8d; msPeriod
0x140047eab  xor     edx, edx; pftDueTime
0x140047ead  call    cs:__imp_SetThreadpoolTimer
0x140047eb3  mov     rcx, [rbx+158h]; pti
0x140047eba  mov     edx, 1; fCancelPendingCallbacks
0x140047ebf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140047ec5  mov     rcx, [rbx+158h]; pti
0x140047ecc  call    cs:__imp_CloseThreadpoolTimer
0x140047ed2  mov     qword ptr [rbx+158h], 0
0x140047edd  add     rsp, 20h
0x140047ee1  pop     rbx
0x140047ee2  retn
```
