# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1400071f0`
- end: `0x140007224`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140006824`
- `0x14000bc08`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000720f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000720f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007201`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007201`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000721d`

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
0x1400071f0  push    rbx
0x1400071f2  sub     rsp, 20h
0x1400071f6  xor     r9d, r9d; msWindowLength
0x1400071f9  xor     r8d, r8d; msPeriod
0x1400071fc  xor     edx, edx; pftDueTime
0x1400071fe  mov     rbx, rcx
0x140007201  call    cs:__imp_SetThreadpoolTimer
0x140007207  mov     edx, 1; fCancelPendingCallbacks
0x14000720c  mov     rcx, rbx; pti
0x14000720f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140007215  mov     rcx, rbx
0x140007218  add     rsp, 20h
0x14000721c  pop     rbx
0x14000721d  jmp     cs:__imp_CloseThreadpoolTimer
```
