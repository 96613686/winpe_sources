# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180043c10`
- end: `0x180043c44`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180016d5c`
- `0x180025380`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180043c21`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180043c21`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180043c3d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180043c2f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180043c2f`

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
0x180043c10  push    rbx
0x180043c12  sub     rsp, 20h
0x180043c16  xor     r9d, r9d; msWindowLength
0x180043c19  xor     r8d, r8d; msPeriod
0x180043c1c  xor     edx, edx; pftDueTime
0x180043c1e  mov     rbx, rcx
0x180043c21  call    cs:__imp_SetThreadpoolTimer
0x180043c27  mov     edx, 1; fCancelPendingCallbacks
0x180043c2c  mov     rcx, rbx; pti
0x180043c2f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180043c35  mov     rcx, rbx
0x180043c38  add     rsp, 20h
0x180043c3c  pop     rbx
0x180043c3d  jmp     cs:__imp_CloseThreadpoolTimer
```
