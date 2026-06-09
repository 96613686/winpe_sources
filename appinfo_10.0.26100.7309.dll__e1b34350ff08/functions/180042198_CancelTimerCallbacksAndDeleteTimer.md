# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180042198`
- end: `0x1800421fb`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800426cc`
- `0x1800432e8`

## callees

- `0x180042198`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800421cd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800421cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800421b5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800421b5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800421e0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800421e0`

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
0x180042198  push    rbx
0x18004219a  sub     rsp, 20h
0x18004219e  mov     rbx, rcx
0x1800421a1  mov     rcx, [rcx+158h]; pti
0x1800421a8  test    rcx, rcx
0x1800421ab  jz      short loc_1800421F4
0x1800421ad  xor     r9d, r9d; msWindowLength
0x1800421b0  xor     r8d, r8d; msPeriod
0x1800421b3  xor     edx, edx; pftDueTime
0x1800421b5  call    cs:__imp_SetThreadpoolTimer
0x1800421bc  nop     dword ptr [rax+rax+00h]
0x1800421c1  mov     rcx, [rbx+158h]; pti
0x1800421c8  mov     edx, 1; fCancelPendingCallbacks
0x1800421cd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800421d4  nop     dword ptr [rax+rax+00h]
0x1800421d9  mov     rcx, [rbx+158h]; pti
0x1800421e0  call    cs:__imp_CloseThreadpoolTimer
0x1800421e7  nop     dword ptr [rax+rax+00h]
0x1800421ec  and     qword ptr [rbx+158h], 0
0x1800421f4  add     rsp, 20h
0x1800421f8  pop     rbx
0x1800421f9  retn
```
