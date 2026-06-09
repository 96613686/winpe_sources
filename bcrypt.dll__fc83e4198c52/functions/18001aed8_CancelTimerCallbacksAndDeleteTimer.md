# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18001aed8`
- end: `0x18001af3e`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18001175c`
- `0x18001b144`

## callees

- `0x18001aed8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001aef5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001aef5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001af0d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001af0d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001af20`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001af20`

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
0x18001aed8  push    rbx
0x18001aeda  sub     rsp, 20h
0x18001aede  mov     rbx, rcx
0x18001aee1  mov     rcx, [rcx+158h]; pti
0x18001aee8  test    rcx, rcx
0x18001aeeb  jz      short loc_18001AF37
0x18001aeed  xor     r9d, r9d; msWindowLength
0x18001aef0  xor     r8d, r8d; msPeriod
0x18001aef3  xor     edx, edx; pftDueTime
0x18001aef5  call    cs:__imp_SetThreadpoolTimer
0x18001aefc  nop     dword ptr [rax+rax+00h]
0x18001af01  mov     rcx, [rbx+158h]; pti
0x18001af08  mov     edx, 1; fCancelPendingCallbacks
0x18001af0d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001af14  nop     dword ptr [rax+rax+00h]
0x18001af19  mov     rcx, [rbx+158h]; pti
0x18001af20  call    cs:__imp_CloseThreadpoolTimer
0x18001af27  nop     dword ptr [rax+rax+00h]
0x18001af2c  mov     qword ptr [rbx+158h], 0
0x18001af37  add     rsp, 20h
0x18001af3b  pop     rbx
0x18001af3c  retn
```
