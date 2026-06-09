# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180009cf8`
- end: `0x180009d2c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180009550`
- `0x18000c730`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009d25`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009d17`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009d17`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009d09`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009d09`

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
0x180009cf8  push    rbx
0x180009cfa  sub     rsp, 20h
0x180009cfe  xor     r9d, r9d; msWindowLength
0x180009d01  xor     r8d, r8d; msPeriod
0x180009d04  xor     edx, edx; pftDueTime
0x180009d06  mov     rbx, rcx
0x180009d09  call    cs:__imp_SetThreadpoolTimer
0x180009d0f  mov     edx, 1; fCancelPendingCallbacks
0x180009d14  mov     rcx, rbx; pti
0x180009d17  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009d1d  mov     rcx, rbx
0x180009d20  add     rsp, 20h
0x180009d24  pop     rbx
0x180009d25  jmp     cs:__imp_CloseThreadpoolTimer
```
