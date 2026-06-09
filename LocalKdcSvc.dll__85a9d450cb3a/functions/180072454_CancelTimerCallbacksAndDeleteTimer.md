# CancelTimerCallbacksAndDeleteTimer

- ea: `0x180072454`
- end: `0x1800724a7`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `83`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180072818`
- `0x18007345c`

## callees

- `0x180072454`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180072490`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180072490`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180072483`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180072483`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180072471`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180072471`

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
0x180072454  push    rbx
0x180072456  sub     rsp, 20h
0x18007245a  mov     rbx, rcx
0x18007245d  mov     rcx, [rcx+158h]; pti
0x180072464  test    rcx, rcx
0x180072467  jz      short loc_1800724A1
0x180072469  xor     r9d, r9d; msWindowLength
0x18007246c  xor     r8d, r8d; msPeriod
0x18007246f  xor     edx, edx; pftDueTime
0x180072471  call    cs:__imp_SetThreadpoolTimer
0x180072477  mov     rcx, [rbx+158h]; pti
0x18007247e  mov     edx, 1; fCancelPendingCallbacks
0x180072483  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180072489  mov     rcx, [rbx+158h]; pti
0x180072490  call    cs:__imp_CloseThreadpoolTimer
0x180072496  mov     qword ptr [rbx+158h], 0
0x1800724a1  add     rsp, 20h
0x1800724a5  pop     rbx
0x1800724a6  retn
```
