# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180023d24`
- end: `0x180023d58`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001568c`
- `0x1800156dc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023d35`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023d35`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023d51`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023d43`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023d43`

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
0x180023d24  push    rbx
0x180023d26  sub     rsp, 20h
0x180023d2a  xor     r9d, r9d; msWindowLength
0x180023d2d  xor     r8d, r8d; msPeriod
0x180023d30  xor     edx, edx; pftDueTime
0x180023d32  mov     rbx, rcx
0x180023d35  call    cs:__imp_SetThreadpoolTimer
0x180023d3b  mov     edx, 1; fCancelPendingCallbacks
0x180023d40  mov     rcx, rbx; pti
0x180023d43  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180023d49  mov     rcx, rbx
0x180023d4c  add     rsp, 20h
0x180023d50  pop     rbx
0x180023d51  jmp     cs:__imp_CloseThreadpoolTimer
```
