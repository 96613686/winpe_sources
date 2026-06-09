# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180006610`
- end: `0x180006644`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180005ccc`
- `0x18000aa74`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006621`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006621`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000662f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000662f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000663d`

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
0x180006610  push    rbx
0x180006612  sub     rsp, 20h
0x180006616  xor     r9d, r9d; msWindowLength
0x180006619  xor     r8d, r8d; msPeriod
0x18000661c  xor     edx, edx; pftDueTime
0x18000661e  mov     rbx, rcx
0x180006621  call    cs:__imp_SetThreadpoolTimer
0x180006627  mov     edx, 1; fCancelPendingCallbacks
0x18000662c  mov     rcx, rbx; pti
0x18000662f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006635  mov     rcx, rbx
0x180006638  add     rsp, 20h
0x18000663c  pop     rbx
0x18000663d  jmp     cs:__imp_CloseThreadpoolTimer
```
