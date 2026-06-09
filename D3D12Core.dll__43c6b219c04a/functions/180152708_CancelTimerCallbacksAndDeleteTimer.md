# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180152708`
- end: `0x18015275b`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18009ef30`
- `0x180152a08`

## callees

- `0x180152708`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180152725`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180152725`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180152744`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180152744`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180152737`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180152737`

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
0x180152708  push    rbx
0x18015270a  sub     rsp, 20h
0x18015270e  mov     rbx, rcx
0x180152711  mov     rcx, [rcx+158h]; pti
0x180152718  test    rcx, rcx
0x18015271b  jz      short loc_180152755
0x18015271d  xor     r9d, r9d; msWindowLength
0x180152720  xor     r8d, r8d; msPeriod
0x180152723  xor     edx, edx; pftDueTime
0x180152725  call    cs:__imp_SetThreadpoolTimer
0x18015272b  mov     rcx, [rbx+158h]; pti
0x180152732  mov     edx, 1; fCancelPendingCallbacks
0x180152737  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18015273d  mov     rcx, [rbx+158h]; pti
0x180152744  call    cs:__imp_CloseThreadpoolTimer
0x18015274a  mov     qword ptr [rbx+158h], 0
0x180152755  add     rsp, 20h
0x180152759  pop     rbx
0x18015275a  retn
```
