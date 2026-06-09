# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140005770`
- end: `0x1400057a4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400028d0`
- `0x140002b50`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000578f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000578f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005781`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140005781`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000579d`

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
0x140005770  push    rbx
0x140005772  sub     rsp, 20h
0x140005776  xor     r9d, r9d; msWindowLength
0x140005779  xor     r8d, r8d; msPeriod
0x14000577c  xor     edx, edx; pftDueTime
0x14000577e  mov     rbx, rcx
0x140005781  call    cs:__imp_SetThreadpoolTimer
0x140005787  mov     edx, 1; fCancelPendingCallbacks
0x14000578c  mov     rcx, rbx; pti
0x14000578f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005795  mov     rcx, rbx
0x140005798  add     rsp, 20h
0x14000579c  pop     rbx
0x14000579d  jmp     cs:__imp_CloseThreadpoolTimer
```
