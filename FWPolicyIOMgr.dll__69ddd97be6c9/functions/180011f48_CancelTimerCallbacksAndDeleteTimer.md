# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180011f48`
- end: `0x180011f9b`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180011e18`
- `0x180011f14`

## callees

- `0x180011f48`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011f77`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011f77`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011f65`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011f65`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011f84`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011f84`

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
0x180011f48  push    rbx
0x180011f4a  sub     rsp, 20h
0x180011f4e  mov     rbx, rcx
0x180011f51  mov     rcx, [rcx+158h]; pti
0x180011f58  test    rcx, rcx
0x180011f5b  jz      short loc_180011F95
0x180011f5d  xor     r9d, r9d; msWindowLength
0x180011f60  xor     r8d, r8d; msPeriod
0x180011f63  xor     edx, edx; pftDueTime
0x180011f65  call    cs:__imp_SetThreadpoolTimer
0x180011f6b  mov     rcx, [rbx+158h]; pti
0x180011f72  mov     edx, 1; fCancelPendingCallbacks
0x180011f77  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011f7d  mov     rcx, [rbx+158h]; pti
0x180011f84  call    cs:__imp_CloseThreadpoolTimer
0x180011f8a  mov     qword ptr [rbx+158h], 0
0x180011f95  add     rsp, 20h
0x180011f99  pop     rbx
0x180011f9a  retn
```
