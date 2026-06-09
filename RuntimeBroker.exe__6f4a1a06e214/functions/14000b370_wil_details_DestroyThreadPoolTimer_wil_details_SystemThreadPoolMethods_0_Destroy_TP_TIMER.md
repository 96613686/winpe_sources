# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x14000b370`
- end: `0x14000b3a4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400082f4`
- `0x14000849c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b39d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b38f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b38f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b381`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b381`

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
0x14000b370  push    rbx
0x14000b372  sub     rsp, 20h
0x14000b376  xor     r9d, r9d; msWindowLength
0x14000b379  xor     r8d, r8d; msPeriod
0x14000b37c  xor     edx, edx; pftDueTime
0x14000b37e  mov     rbx, rcx
0x14000b381  call    cs:__imp_SetThreadpoolTimer
0x14000b387  mov     edx, 1; fCancelPendingCallbacks
0x14000b38c  mov     rcx, rbx; pti
0x14000b38f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000b395  mov     rcx, rbx
0x14000b398  add     rsp, 20h
0x14000b39c  pop     rbx
0x14000b39d  jmp     cs:__imp_CloseThreadpoolTimer
```
