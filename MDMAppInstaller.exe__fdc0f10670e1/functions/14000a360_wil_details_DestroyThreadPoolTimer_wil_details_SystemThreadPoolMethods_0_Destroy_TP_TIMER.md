# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x14000a360`
- end: `0x14000a394`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140009330`
- `0x140012c04`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x14000a38d`
- `KERNEL32!SetThreadpoolTimer` at `0x14000a371`
- `KERNEL32!SetThreadpoolTimer` at `0x14000a371`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000a37f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000a37f`

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
0x14000a360  push    rbx
0x14000a362  sub     rsp, 20h
0x14000a366  xor     r9d, r9d; msWindowLength
0x14000a369  xor     r8d, r8d; msPeriod
0x14000a36c  xor     edx, edx; pftDueTime
0x14000a36e  mov     rbx, rcx
0x14000a371  call    cs:__imp_SetThreadpoolTimer
0x14000a377  mov     edx, 1; fCancelPendingCallbacks
0x14000a37c  mov     rcx, rbx; pti
0x14000a37f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000a385  mov     rcx, rbx
0x14000a388  add     rsp, 20h
0x14000a38c  pop     rbx
0x14000a38d  jmp     cs:__imp_CloseThreadpoolTimer
```
