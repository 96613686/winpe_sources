# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1800405c8`
- end: `0x18004062b`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180040afc`
- `0x180041718`

## callees

- `0x1800405c8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800405e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800405e5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180040610`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180040610`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800405fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800405fd`

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
0x1800405c8  push    rbx
0x1800405ca  sub     rsp, 20h
0x1800405ce  mov     rbx, rcx
0x1800405d1  mov     rcx, [rcx+158h]; pti
0x1800405d8  test    rcx, rcx
0x1800405db  jz      short loc_180040624
0x1800405dd  xor     r9d, r9d; msWindowLength
0x1800405e0  xor     r8d, r8d; msPeriod
0x1800405e3  xor     edx, edx; pftDueTime
0x1800405e5  call    cs:__imp_SetThreadpoolTimer
0x1800405ec  nop     dword ptr [rax+rax+00h]
0x1800405f1  mov     rcx, [rbx+158h]; pti
0x1800405f8  mov     edx, 1; fCancelPendingCallbacks
0x1800405fd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180040604  nop     dword ptr [rax+rax+00h]
0x180040609  mov     rcx, [rbx+158h]; pti
0x180040610  call    cs:__imp_CloseThreadpoolTimer
0x180040617  nop     dword ptr [rax+rax+00h]
0x18004061c  and     qword ptr [rbx+158h], 0
0x180040624  add     rsp, 20h
0x180040628  pop     rbx
0x180040629  retn
```
