# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180016d08`
- end: `0x180016d3c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800153e0`
- `0x18002093c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180016d35`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016d27`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180016d27`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016d19`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180016d19`

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
0x180016d08  push    rbx
0x180016d0a  sub     rsp, 20h
0x180016d0e  xor     r9d, r9d; msWindowLength
0x180016d11  xor     r8d, r8d; msPeriod
0x180016d14  xor     edx, edx; pftDueTime
0x180016d16  mov     rbx, rcx
0x180016d19  call    cs:__imp_SetThreadpoolTimer
0x180016d1f  mov     edx, 1; fCancelPendingCallbacks
0x180016d24  mov     rcx, rbx; pti
0x180016d27  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180016d2d  mov     rcx, rbx
0x180016d30  add     rsp, 20h
0x180016d34  pop     rbx
0x180016d35  jmp     cs:__imp_CloseThreadpoolTimer
```
