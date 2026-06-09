# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1802026bc`
- end: `0x1802026f0`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180202404`
- `0x180202528`
- `0x180202578`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802026db`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1802026db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1802026e9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1802026cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1802026cd`

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
0x1802026bc  push    rbx
0x1802026be  sub     rsp, 20h
0x1802026c2  xor     r9d, r9d; msWindowLength
0x1802026c5  xor     r8d, r8d; msPeriod
0x1802026c8  xor     edx, edx; pftDueTime
0x1802026ca  mov     rbx, rcx
0x1802026cd  call    cs:__imp_SetThreadpoolTimer
0x1802026d3  mov     edx, 1; fCancelPendingCallbacks
0x1802026d8  mov     rcx, rbx; pti
0x1802026db  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1802026e1  mov     rcx, rbx
0x1802026e4  add     rsp, 20h
0x1802026e8  pop     rbx
0x1802026e9  jmp     cs:__imp_CloseThreadpoolTimer
```
