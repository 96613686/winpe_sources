# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180077e14`
- end: `0x180077e7a`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180077e80`
- `0x180077ec0`

## callees

- `0x180077e14`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180077e5c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180077e5c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180077e31`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180077e31`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180077e49`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180077e49`

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
0x180077e14  push    rbx
0x180077e16  sub     rsp, 20h
0x180077e1a  mov     rbx, rcx
0x180077e1d  mov     rcx, [rcx+158h]; pti
0x180077e24  test    rcx, rcx
0x180077e27  jz      short loc_180077E73
0x180077e29  xor     r9d, r9d; msWindowLength
0x180077e2c  xor     r8d, r8d; msPeriod
0x180077e2f  xor     edx, edx; pftDueTime
0x180077e31  call    cs:__imp_SetThreadpoolTimer
0x180077e38  nop     dword ptr [rax+rax+00h]
0x180077e3d  mov     rcx, [rbx+158h]; pti
0x180077e44  mov     edx, 1; fCancelPendingCallbacks
0x180077e49  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180077e50  nop     dword ptr [rax+rax+00h]
0x180077e55  mov     rcx, [rbx+158h]; pti
0x180077e5c  call    cs:__imp_CloseThreadpoolTimer
0x180077e63  nop     dword ptr [rax+rax+00h]
0x180077e68  mov     qword ptr [rbx+158h], 0
0x180077e73  add     rsp, 20h
0x180077e77  pop     rbx
0x180077e78  retn
```
