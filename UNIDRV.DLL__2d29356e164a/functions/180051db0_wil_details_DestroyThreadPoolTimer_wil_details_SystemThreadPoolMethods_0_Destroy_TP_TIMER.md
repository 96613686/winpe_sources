# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180051db0`
- end: `0x180051de4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800511a8`
- `0x180056818`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x180051dc1`
- `KERNEL32!SetThreadpoolTimer` at `0x180051dc1`
- `KERNEL32!CloseThreadpoolTimer` at `0x180051ddd`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180051dcf`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180051dcf`

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
0x180051db0  push    rbx
0x180051db2  sub     rsp, 20h
0x180051db6  xor     r9d, r9d; msWindowLength
0x180051db9  xor     r8d, r8d; msPeriod
0x180051dbc  xor     edx, edx; pftDueTime
0x180051dbe  mov     rbx, rcx
0x180051dc1  call    cs:__imp_SetThreadpoolTimer
0x180051dc7  mov     edx, 1; fCancelPendingCallbacks
0x180051dcc  mov     rcx, rbx; pti
0x180051dcf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180051dd5  mov     rcx, rbx
0x180051dd8  add     rsp, 20h
0x180051ddc  pop     rbx
0x180051ddd  jmp     cs:__imp_CloseThreadpoolTimer
```
