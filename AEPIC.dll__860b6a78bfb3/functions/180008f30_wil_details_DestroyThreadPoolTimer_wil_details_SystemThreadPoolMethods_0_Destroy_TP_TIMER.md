# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180008f30`
- end: `0x180008f64`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800085b0`
- `0x18000dc64`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180008f5d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008f41`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008f41`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008f4f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180008f4f`

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
0x180008f30  push    rbx
0x180008f32  sub     rsp, 20h
0x180008f36  xor     r9d, r9d; msWindowLength
0x180008f39  xor     r8d, r8d; msPeriod
0x180008f3c  xor     edx, edx; pftDueTime
0x180008f3e  mov     rbx, rcx
0x180008f41  call    cs:__imp_SetThreadpoolTimer
0x180008f47  mov     edx, 1; fCancelPendingCallbacks
0x180008f4c  mov     rcx, rbx; pti
0x180008f4f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008f55  mov     rcx, rbx
0x180008f58  add     rsp, 20h
0x180008f5c  pop     rbx
0x180008f5d  jmp     cs:__imp_CloseThreadpoolTimer
```
