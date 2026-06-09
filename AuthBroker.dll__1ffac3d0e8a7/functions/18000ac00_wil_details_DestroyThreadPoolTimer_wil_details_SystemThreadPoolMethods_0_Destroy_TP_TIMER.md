# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000ac00`
- end: `0x18000ac34`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(_TP_TIMER *threadpoolTimer)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800043a0`
- `0x1800066f8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ac1f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ac1f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ac11`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ac11`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ac2d`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(
        _TP_TIMER *threadpoolTimer)
{
  SetThreadpoolTimer(threadpoolTimer, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(threadpoolTimer, 1);
  CloseThreadpoolTimer(threadpoolTimer);
}

```

## disassembly

```asm
0x18000ac00  push    rbx
0x18000ac02  sub     rsp, 20h
0x18000ac06  xor     r9d, r9d; msWindowLength
0x18000ac09  xor     r8d, r8d; msPeriod
0x18000ac0c  xor     edx, edx; pftDueTime
0x18000ac0e  mov     rbx, threadpoolTimer
0x18000ac11  call    cs:__imp_SetThreadpoolTimer
0x18000ac17  mov     edx, 1; fCancelPendingCallbacks
0x18000ac1c  mov     threadpoolTimer, rbx; pti
0x18000ac1f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ac25  mov     threadpoolTimer, rbx
0x18000ac28  add     rsp, 20h
0x18000ac2c  pop     rbx
0x18000ac2d  jmp     cs:__imp_CloseThreadpoolTimer
```
