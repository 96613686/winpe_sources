# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1800753a8`
- end: `0x1800753fb`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180075404`
- `0x180075438`

## callees

- `0x1800753a8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800753e4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800753e4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800753c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800753c5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800753d7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800753d7`

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
0x1800753a8  push    rbx
0x1800753aa  sub     rsp, 20h
0x1800753ae  mov     rbx, rcx
0x1800753b1  mov     rcx, [rcx+158h]; pti
0x1800753b8  test    rcx, rcx
0x1800753bb  jz      short loc_1800753F5
0x1800753bd  xor     r9d, r9d; msWindowLength
0x1800753c0  xor     r8d, r8d; msPeriod
0x1800753c3  xor     edx, edx; pftDueTime
0x1800753c5  call    cs:__imp_SetThreadpoolTimer
0x1800753cb  mov     rcx, [rbx+158h]; pti
0x1800753d2  mov     edx, 1; fCancelPendingCallbacks
0x1800753d7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800753dd  mov     rcx, [rbx+158h]; pti
0x1800753e4  call    cs:__imp_CloseThreadpoolTimer
0x1800753ea  mov     qword ptr [rbx+158h], 0
0x1800753f5  add     rsp, 20h
0x1800753f9  pop     rbx
0x1800753fa  retn
```
