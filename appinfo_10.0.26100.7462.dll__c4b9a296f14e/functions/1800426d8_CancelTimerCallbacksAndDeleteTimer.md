# CancelTimerCallbacksAndDeleteTimer

- ea: `0x1800426d8`
- end: `0x18004273b`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180042c0c`
- `0x180043828`

## callees

- `0x1800426d8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004270d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004270d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800426f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800426f5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180042720`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180042720`

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
0x1800426d8  push    rbx
0x1800426da  sub     rsp, 20h
0x1800426de  mov     rbx, rcx
0x1800426e1  mov     rcx, [rcx+158h]; pti
0x1800426e8  test    rcx, rcx
0x1800426eb  jz      short loc_180042734
0x1800426ed  xor     r9d, r9d; msWindowLength
0x1800426f0  xor     r8d, r8d; msPeriod
0x1800426f3  xor     edx, edx; pftDueTime
0x1800426f5  call    cs:__imp_SetThreadpoolTimer
0x1800426fc  nop     dword ptr [rax+rax+00h]
0x180042701  mov     rcx, [rbx+158h]; pti
0x180042708  mov     edx, 1; fCancelPendingCallbacks
0x18004270d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180042714  nop     dword ptr [rax+rax+00h]
0x180042719  mov     rcx, [rbx+158h]; pti
0x180042720  call    cs:__imp_CloseThreadpoolTimer
0x180042727  nop     dword ptr [rax+rax+00h]
0x18004272c  and     qword ptr [rbx+158h], 0
0x180042734  add     rsp, 20h
0x180042738  pop     rbx
0x180042739  retn
```
