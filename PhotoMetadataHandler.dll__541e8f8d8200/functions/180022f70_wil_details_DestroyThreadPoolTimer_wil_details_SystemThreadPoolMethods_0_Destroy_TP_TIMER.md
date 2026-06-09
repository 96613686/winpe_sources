# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180022f70`
- end: `0x180022fa4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f16c`
- `0x180013c34`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022f81`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022f81`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022f8f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022f8f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022f9d`

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
0x180022f70  push    rbx
0x180022f72  sub     rsp, 20h
0x180022f76  xor     r9d, r9d; msWindowLength
0x180022f79  xor     r8d, r8d; msPeriod
0x180022f7c  xor     edx, edx; pftDueTime
0x180022f7e  mov     rbx, rcx
0x180022f81  call    cs:__imp_SetThreadpoolTimer
0x180022f87  mov     edx, 1; fCancelPendingCallbacks
0x180022f8c  mov     rcx, rbx; pti
0x180022f8f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180022f95  mov     rcx, rbx
0x180022f98  add     rsp, 20h
0x180022f9c  pop     rbx
0x180022f9d  jmp     cs:__imp_CloseThreadpoolTimer
```
