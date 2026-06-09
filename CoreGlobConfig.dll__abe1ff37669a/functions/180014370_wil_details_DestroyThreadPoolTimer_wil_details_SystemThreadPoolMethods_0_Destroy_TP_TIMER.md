# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180014370`
- end: `0x1800143a4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800114c8`
- `0x18001ec20`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014381`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180014381`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001438f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001438f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001439d`

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
0x180014370  push    rbx
0x180014372  sub     rsp, 20h
0x180014376  xor     r9d, r9d; msWindowLength
0x180014379  xor     r8d, r8d; msPeriod
0x18001437c  xor     edx, edx; pftDueTime
0x18001437e  mov     rbx, rcx
0x180014381  call    cs:__imp_SetThreadpoolTimer
0x180014387  mov     edx, 1; fCancelPendingCallbacks
0x18001438c  mov     rcx, rbx; pti
0x18001438f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180014395  mov     rcx, rbx
0x180014398  add     rsp, 20h
0x18001439c  pop     rbx
0x18001439d  jmp     cs:__imp_CloseThreadpoolTimer
```
