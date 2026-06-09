# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140004340`
- end: `0x140004374`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001684`
- `0x140001764`
- `0x140001c88`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004351`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140004351`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000436d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000435f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000435f`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x140004340  push    rbx
0x140004342  sub     rsp, 20h
0x140004346  xor     r9d, r9d; msWindowLength
0x140004349  xor     r8d, r8d; msPeriod
0x14000434c  xor     edx, edx; pftDueTime
0x14000434e  mov     rbx, rcx
0x140004351  call    cs:__imp_SetThreadpoolTimer
0x140004357  mov     edx, 1; fCancelPendingCallbacks
0x14000435c  mov     rcx, rbx; pti
0x14000435f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140004365  mov     rcx, rbx
0x140004368  add     rsp, 20h
0x14000436c  pop     rbx
0x14000436d  jmp     cs:__imp_CloseThreadpoolTimer
```
