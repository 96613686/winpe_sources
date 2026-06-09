# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800088c0`
- end: `0x1800088f4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800074e8`
- `0x18000e7e4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800088df`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800088df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800088ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800088d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800088d1`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x1800088c0  push    rbx
0x1800088c2  sub     rsp, 20h
0x1800088c6  xor     r9d, r9d; msWindowLength
0x1800088c9  xor     r8d, r8d; msPeriod
0x1800088cc  xor     edx, edx; pftDueTime
0x1800088ce  mov     rbx, rcx
0x1800088d1  call    cs:__imp_SetThreadpoolTimer
0x1800088d7  mov     edx, 1; fCancelPendingCallbacks
0x1800088dc  mov     rcx, rbx; pti
0x1800088df  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800088e5  mov     rcx, rbx
0x1800088e8  add     rsp, 20h
0x1800088ec  pop     rbx
0x1800088ed  jmp     cs:__imp_CloseThreadpoolTimer
```
