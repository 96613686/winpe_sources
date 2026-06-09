# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180022a00`
- end: `0x180022a34`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180021304`
- `0x1800265f0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022a11`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180022a11`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022a1f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180022a1f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180022a2d`

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
0x180022a00  push    rbx
0x180022a02  sub     rsp, 20h
0x180022a06  xor     r9d, r9d; msWindowLength
0x180022a09  xor     r8d, r8d; msPeriod
0x180022a0c  xor     edx, edx; pftDueTime
0x180022a0e  mov     rbx, rcx
0x180022a11  call    cs:__imp_SetThreadpoolTimer
0x180022a17  mov     edx, 1; fCancelPendingCallbacks
0x180022a1c  mov     rcx, rbx; pti
0x180022a1f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180022a25  mov     rcx, rbx
0x180022a28  add     rsp, 20h
0x180022a2c  pop     rbx
0x180022a2d  jmp     cs:__imp_CloseThreadpoolTimer
```
