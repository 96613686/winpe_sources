# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800269f8`
- end: `0x180026a2c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180008c28`
- `0x18000a558`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180026a25`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026a09`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026a09`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180026a17`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180026a17`

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
0x1800269f8  push    rbx
0x1800269fa  sub     rsp, 20h
0x1800269fe  xor     r9d, r9d; msWindowLength
0x180026a01  xor     r8d, r8d; msPeriod
0x180026a04  xor     edx, edx; pftDueTime
0x180026a06  mov     rbx, rcx
0x180026a09  call    cs:__imp_SetThreadpoolTimer
0x180026a0f  mov     edx, 1; fCancelPendingCallbacks
0x180026a14  mov     rcx, rbx; pti
0x180026a17  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180026a1d  mov     rcx, rbx
0x180026a20  add     rsp, 20h
0x180026a24  pop     rbx
0x180026a25  jmp     cs:__imp_CloseThreadpoolTimer
```
