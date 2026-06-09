# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,1>::Destroy(_TP_TIMER *)

- ea: `0x1800dac5c`
- end: `0x1800dac8d`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$00@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800da96c`
- `0x1800dc634`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800dac86`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800dac78`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800dac78`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800dac6d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800dac6d`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,1>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 0);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x1800dac5c  push    rbx
0x1800dac5e  sub     rsp, 20h
0x1800dac62  xor     r9d, r9d; msWindowLength
0x1800dac65  xor     r8d, r8d; msPeriod
0x1800dac68  xor     edx, edx; pftDueTime
0x1800dac6a  mov     rbx, rcx
0x1800dac6d  call    cs:__imp_SetThreadpoolTimer
0x1800dac73  xor     edx, edx; fCancelPendingCallbacks
0x1800dac75  mov     rcx, rbx; pti
0x1800dac78  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800dac7e  mov     rcx, rbx
0x1800dac81  add     rsp, 20h
0x1800dac85  pop     rbx
0x1800dac86  jmp     cs:__imp_CloseThreadpoolTimer
```
