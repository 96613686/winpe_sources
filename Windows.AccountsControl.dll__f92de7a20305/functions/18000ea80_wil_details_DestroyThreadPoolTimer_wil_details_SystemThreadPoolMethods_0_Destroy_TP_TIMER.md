# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000ea80`
- end: `0x18000eab4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000c18c`
- `0x180019e68`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000eaad`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ea9f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ea9f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ea91`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ea91`

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
0x18000ea80  push    rbx
0x18000ea82  sub     rsp, 20h
0x18000ea86  xor     r9d, r9d; msWindowLength
0x18000ea89  xor     r8d, r8d; msPeriod
0x18000ea8c  xor     edx, edx; pftDueTime
0x18000ea8e  mov     rbx, rcx
0x18000ea91  call    cs:__imp_SetThreadpoolTimer
0x18000ea97  mov     edx, 1; fCancelPendingCallbacks
0x18000ea9c  mov     rcx, rbx; pti
0x18000ea9f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000eaa5  mov     rcx, rbx
0x18000eaa8  add     rsp, 20h
0x18000eaac  pop     rbx
0x18000eaad  jmp     cs:__imp_CloseThreadpoolTimer
```
