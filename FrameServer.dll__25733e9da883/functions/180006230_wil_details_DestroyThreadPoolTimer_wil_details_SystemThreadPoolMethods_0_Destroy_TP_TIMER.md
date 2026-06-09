# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180006230`
- end: `0x180006264`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180005d7c`
- `0x1800082e4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000625d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000624f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000624f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006241`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006241`

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
0x180006230  push    rbx
0x180006232  sub     rsp, 20h
0x180006236  xor     r9d, r9d; msWindowLength
0x180006239  xor     r8d, r8d; msPeriod
0x18000623c  xor     edx, edx; pftDueTime
0x18000623e  mov     rbx, rcx
0x180006241  call    cs:__imp_SetThreadpoolTimer
0x180006247  mov     edx, 1; fCancelPendingCallbacks
0x18000624c  mov     rcx, rbx; pti
0x18000624f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006255  mov     rcx, rbx
0x180006258  add     rsp, 20h
0x18000625c  pop     rbx
0x18000625d  jmp     cs:__imp_CloseThreadpoolTimer
```
