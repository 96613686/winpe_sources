# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180009510`
- end: `0x180009544`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800089e4`
- `0x18000e808`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000953d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000952f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000952f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009521`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009521`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x180009510  push    rbx
0x180009512  sub     rsp, 20h
0x180009516  xor     r9d, r9d; msWindowLength
0x180009519  xor     r8d, r8d; msPeriod
0x18000951c  xor     edx, edx; pftDueTime
0x18000951e  mov     rbx, rcx
0x180009521  call    cs:__imp_SetThreadpoolTimer
0x180009527  mov     edx, 1; fCancelPendingCallbacks
0x18000952c  mov     rcx, rbx; pti
0x18000952f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009535  mov     rcx, rbx
0x180009538  add     rsp, 20h
0x18000953c  pop     rbx
0x18000953d  jmp     cs:__imp_CloseThreadpoolTimer
```
