# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000ca30`
- end: `0x18000ca64`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a1c8`
- `0x18001bad4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ca5d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ca4f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ca4f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ca41`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ca41`

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
0x18000ca30  push    rbx
0x18000ca32  sub     rsp, 20h
0x18000ca36  xor     r9d, r9d; msWindowLength
0x18000ca39  xor     r8d, r8d; msPeriod
0x18000ca3c  xor     edx, edx; pftDueTime
0x18000ca3e  mov     rbx, rcx
0x18000ca41  call    cs:__imp_SetThreadpoolTimer
0x18000ca47  mov     edx, 1; fCancelPendingCallbacks
0x18000ca4c  mov     rcx, rbx; pti
0x18000ca4f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ca55  mov     rcx, rbx
0x18000ca58  add     rsp, 20h
0x18000ca5c  pop     rbx
0x18000ca5d  jmp     cs:__imp_CloseThreadpoolTimer
```
