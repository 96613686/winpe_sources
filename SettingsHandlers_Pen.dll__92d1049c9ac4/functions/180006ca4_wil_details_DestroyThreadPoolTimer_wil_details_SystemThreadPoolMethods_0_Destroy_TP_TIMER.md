# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180006ca4`
- end: `0x180006cd8`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180005f2c`
- `0x18000be74`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006cd1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006cb5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006cb5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006cc3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006cc3`

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
0x180006ca4  push    rbx
0x180006ca6  sub     rsp, 20h
0x180006caa  xor     r9d, r9d; msWindowLength
0x180006cad  xor     r8d, r8d; msPeriod
0x180006cb0  xor     edx, edx; pftDueTime
0x180006cb2  mov     rbx, rcx
0x180006cb5  call    cs:__imp_SetThreadpoolTimer
0x180006cbb  mov     edx, 1; fCancelPendingCallbacks
0x180006cc0  mov     rcx, rbx; pti
0x180006cc3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006cc9  mov     rcx, rbx
0x180006ccc  add     rsp, 20h
0x180006cd0  pop     rbx
0x180006cd1  jmp     cs:__imp_CloseThreadpoolTimer
```
