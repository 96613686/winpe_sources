# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800073b0`
- end: `0x1800073e4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180006370`
- `0x180006fac`
- `0x180008378`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800073cf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800073cf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800073dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800073c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800073c1`

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
0x1800073b0  push    rbx
0x1800073b2  sub     rsp, 20h
0x1800073b6  xor     r9d, r9d; msWindowLength
0x1800073b9  xor     r8d, r8d; msPeriod
0x1800073bc  xor     edx, edx; pftDueTime
0x1800073be  mov     rbx, rcx
0x1800073c1  call    cs:__imp_SetThreadpoolTimer
0x1800073c7  mov     edx, 1; fCancelPendingCallbacks
0x1800073cc  mov     rcx, rbx; pti
0x1800073cf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800073d5  mov     rcx, rbx
0x1800073d8  add     rsp, 20h
0x1800073dc  pop     rbx
0x1800073dd  jmp     cs:__imp_CloseThreadpoolTimer
```
