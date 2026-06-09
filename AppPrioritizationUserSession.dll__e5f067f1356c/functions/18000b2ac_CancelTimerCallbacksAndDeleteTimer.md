# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18000b2ac`
- end: `0x18000b2ff`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b308`
- `0x18000bb08`
- `0x18000bcc0`

## callees

- `0x18000b2ac`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b2db`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b2db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b2e8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b2e8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b2c9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b2c9`

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
0x18000b2ac  push    rbx
0x18000b2ae  sub     rsp, 20h
0x18000b2b2  mov     rbx, rcx
0x18000b2b5  mov     rcx, [rcx+158h]; pti
0x18000b2bc  test    rcx, rcx
0x18000b2bf  jz      short loc_18000B2F9
0x18000b2c1  xor     r9d, r9d; msWindowLength
0x18000b2c4  xor     r8d, r8d; msPeriod
0x18000b2c7  xor     edx, edx; pftDueTime
0x18000b2c9  call    cs:__imp_SetThreadpoolTimer
0x18000b2cf  mov     rcx, [rbx+158h]; pti
0x18000b2d6  mov     edx, 1; fCancelPendingCallbacks
0x18000b2db  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b2e1  mov     rcx, [rbx+158h]; pti
0x18000b2e8  call    cs:__imp_CloseThreadpoolTimer
0x18000b2ee  mov     qword ptr [rbx+158h], 0
0x18000b2f9  add     rsp, 20h
0x18000b2fd  pop     rbx
0x18000b2fe  retn
```
