# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000b7c0`
- end: `0x18000b7f4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a6a4`
- `0x18000e5d4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b7df`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b7df`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b7ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b7d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b7d1`

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
0x18000b7c0  push    rbx
0x18000b7c2  sub     rsp, 20h
0x18000b7c6  xor     r9d, r9d; msWindowLength
0x18000b7c9  xor     r8d, r8d; msPeriod
0x18000b7cc  xor     edx, edx; pftDueTime
0x18000b7ce  mov     rbx, rcx
0x18000b7d1  call    cs:__imp_SetThreadpoolTimer
0x18000b7d7  mov     edx, 1; fCancelPendingCallbacks
0x18000b7dc  mov     rcx, rbx; pti
0x18000b7df  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b7e5  mov     rcx, rbx
0x18000b7e8  add     rsp, 20h
0x18000b7ec  pop     rbx
0x18000b7ed  jmp     cs:__imp_CloseThreadpoolTimer
```
