# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180018718`
- end: `0x18001874c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800093e0`
- `0x18000a52c`
- `0x1800186fc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018729`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180018729`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180018737`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180018737`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180018745`

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
0x180018718  push    rbx
0x18001871a  sub     rsp, 20h
0x18001871e  xor     r9d, r9d; msWindowLength
0x180018721  xor     r8d, r8d; msPeriod
0x180018724  xor     edx, edx; pftDueTime
0x180018726  mov     rbx, rcx
0x180018729  call    cs:__imp_SetThreadpoolTimer
0x18001872f  mov     edx, 1; fCancelPendingCallbacks
0x180018734  mov     rcx, rbx; pti
0x180018737  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001873d  mov     rcx, rbx
0x180018740  add     rsp, 20h
0x180018744  pop     rbx
0x180018745  jmp     cs:__imp_CloseThreadpoolTimer
```
