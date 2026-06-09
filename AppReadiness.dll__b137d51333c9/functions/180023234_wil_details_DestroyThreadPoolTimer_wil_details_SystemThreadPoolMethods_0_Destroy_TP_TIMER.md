# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180023234`
- end: `0x180023268`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800231f0`
- `0x180034264`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023245`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180023245`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023253`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180023253`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180023261`

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
0x180023234  push    rbx
0x180023236  sub     rsp, 20h
0x18002323a  xor     r9d, r9d; msWindowLength
0x18002323d  xor     r8d, r8d; msPeriod
0x180023240  xor     edx, edx; pftDueTime
0x180023242  mov     rbx, rcx
0x180023245  call    cs:__imp_SetThreadpoolTimer
0x18002324b  mov     edx, 1; fCancelPendingCallbacks
0x180023250  mov     rcx, rbx; pti
0x180023253  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180023259  mov     rcx, rbx
0x18002325c  add     rsp, 20h
0x180023260  pop     rbx
0x180023261  jmp     cs:__imp_CloseThreadpoolTimer
```
