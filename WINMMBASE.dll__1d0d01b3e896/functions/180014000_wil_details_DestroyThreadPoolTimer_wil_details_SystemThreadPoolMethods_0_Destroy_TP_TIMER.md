# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180014000`
- end: `0x180014034`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180013b24`
- `0x180016794`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001402d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001401f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001401f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014011`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014011`

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
0x180014000  push    rbx
0x180014002  sub     rsp, 20h
0x180014006  xor     r9d, r9d; msWindowLength
0x180014009  xor     r8d, r8d; msPeriod
0x18001400c  xor     edx, edx; pftDueTime
0x18001400e  mov     rbx, rcx
0x180014011  call    cs:__imp_SetThreadpoolTimer
0x180014017  mov     edx, 1; fCancelPendingCallbacks
0x18001401c  mov     rcx, rbx; pti
0x18001401f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014025  mov     rcx, rbx
0x180014028  add     rsp, 20h
0x18001402c  pop     rbx
0x18001402d  jmp     cs:__imp_CloseThreadpoolTimer
```
