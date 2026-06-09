# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140011cb0`
- end: `0x140011ce4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000edd4`
- `0x14002c328`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x140011cc1`
- `KERNEL32!SetThreadpoolTimer` at `0x140011cc1`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140011ccf`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140011ccf`
- `KERNEL32!CloseThreadpoolTimer` at `0x140011cdd`

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
0x140011cb0  push    rbx
0x140011cb2  sub     rsp, 20h
0x140011cb6  xor     r9d, r9d; msWindowLength
0x140011cb9  xor     r8d, r8d; msPeriod
0x140011cbc  xor     edx, edx; pftDueTime
0x140011cbe  mov     rbx, rcx
0x140011cc1  call    cs:__imp_SetThreadpoolTimer
0x140011cc7  mov     edx, 1; fCancelPendingCallbacks
0x140011ccc  mov     rcx, rbx; pti
0x140011ccf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140011cd5  mov     rcx, rbx
0x140011cd8  add     rsp, 20h
0x140011cdc  pop     rbx
0x140011cdd  jmp     cs:__imp_CloseThreadpoolTimer
```
