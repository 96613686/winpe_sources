# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18004eae4`
- end: `0x18004eb4a`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18004e9ac`
- `0x18004eaa4`

## callees

- `0x18004eae4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004eb19`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004eb19`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004eb2c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004eb2c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004eb01`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004eb01`

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
0x18004eae4  push    rbx
0x18004eae6  sub     rsp, 20h
0x18004eaea  mov     rbx, rcx
0x18004eaed  mov     rcx, [rcx+158h]; pti
0x18004eaf4  test    rcx, rcx
0x18004eaf7  jz      short loc_18004EB43
0x18004eaf9  xor     r9d, r9d; msWindowLength
0x18004eafc  xor     r8d, r8d; msPeriod
0x18004eaff  xor     edx, edx; pftDueTime
0x18004eb01  call    cs:__imp_SetThreadpoolTimer
0x18004eb08  nop     dword ptr [rax+rax+00h]
0x18004eb0d  mov     rcx, [rbx+158h]; pti
0x18004eb14  mov     edx, 1; fCancelPendingCallbacks
0x18004eb19  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004eb20  nop     dword ptr [rax+rax+00h]
0x18004eb25  mov     rcx, [rbx+158h]; pti
0x18004eb2c  call    cs:__imp_CloseThreadpoolTimer
0x18004eb33  nop     dword ptr [rax+rax+00h]
0x18004eb38  mov     qword ptr [rbx+158h], 0
0x18004eb43  add     rsp, 20h
0x18004eb47  pop     rbx
0x18004eb48  retn
```
