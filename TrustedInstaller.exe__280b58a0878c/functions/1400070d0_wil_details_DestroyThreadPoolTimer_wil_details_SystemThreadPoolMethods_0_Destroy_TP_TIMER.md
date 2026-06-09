# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1400070d0`
- end: `0x140007104`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000670c`
- `0x14000afe8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400070ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400070ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400070fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400070e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400070e1`

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
0x1400070d0  push    rbx
0x1400070d2  sub     rsp, 20h
0x1400070d6  xor     r9d, r9d; msWindowLength
0x1400070d9  xor     r8d, r8d; msPeriod
0x1400070dc  xor     edx, edx; pftDueTime
0x1400070de  mov     rbx, rcx
0x1400070e1  call    cs:__imp_SetThreadpoolTimer
0x1400070e7  mov     edx, 1; fCancelPendingCallbacks
0x1400070ec  mov     rcx, rbx; pti
0x1400070ef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400070f5  mov     rcx, rbx
0x1400070f8  add     rsp, 20h
0x1400070fc  pop     rbx
0x1400070fd  jmp     cs:__imp_CloseThreadpoolTimer
```
