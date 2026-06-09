# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140052910`
- end: `0x140052944`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400528b4`
- `0x1400546f8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140052921`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140052921`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14005293d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14005292f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14005292f`

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
0x140052910  push    rbx
0x140052912  sub     rsp, 20h
0x140052916  xor     r9d, r9d; msWindowLength
0x140052919  xor     r8d, r8d; msPeriod
0x14005291c  xor     edx, edx; pftDueTime
0x14005291e  mov     rbx, rcx
0x140052921  call    cs:__imp_SetThreadpoolTimer
0x140052927  mov     edx, 1; fCancelPendingCallbacks
0x14005292c  mov     rcx, rbx; pti
0x14005292f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140052935  mov     rcx, rbx
0x140052938  add     rsp, 20h
0x14005293c  pop     rbx
0x14005293d  jmp     cs:__imp_CloseThreadpoolTimer
```
