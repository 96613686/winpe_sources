# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x14000b89c`
- end: `0x14000b8d0`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140009198`
- `0x14001af30`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000b8bb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000b8bb`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000b8c9`
- `KERNEL32!SetThreadpoolTimer` at `0x14000b8ad`
- `KERNEL32!SetThreadpoolTimer` at `0x14000b8ad`

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
0x14000b89c  push    rbx
0x14000b89e  sub     rsp, 20h
0x14000b8a2  xor     r9d, r9d; msWindowLength
0x14000b8a5  xor     r8d, r8d; msPeriod
0x14000b8a8  xor     edx, edx; pftDueTime
0x14000b8aa  mov     rbx, rcx
0x14000b8ad  call    cs:__imp_SetThreadpoolTimer
0x14000b8b3  mov     edx, 1; fCancelPendingCallbacks
0x14000b8b8  mov     rcx, rbx; pti
0x14000b8bb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000b8c1  mov     rcx, rbx
0x14000b8c4  add     rsp, 20h
0x14000b8c8  pop     rbx
0x14000b8c9  jmp     cs:__imp_CloseThreadpoolTimer
```
