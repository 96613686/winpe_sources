# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800090b4`
- end: `0x1800090e8`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000866c`
- `0x18000c424`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800090d3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800090d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800090c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800090c5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800090e1`

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
0x1800090b4  push    rbx
0x1800090b6  sub     rsp, 20h
0x1800090ba  xor     r9d, r9d; msWindowLength
0x1800090bd  xor     r8d, r8d; msPeriod
0x1800090c0  xor     edx, edx; pftDueTime
0x1800090c2  mov     rbx, rcx
0x1800090c5  call    cs:__imp_SetThreadpoolTimer
0x1800090cb  mov     edx, 1; fCancelPendingCallbacks
0x1800090d0  mov     rcx, rbx; pti
0x1800090d3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800090d9  mov     rcx, rbx
0x1800090dc  add     rsp, 20h
0x1800090e0  pop     rbx
0x1800090e1  jmp     cs:__imp_CloseThreadpoolTimer
```
