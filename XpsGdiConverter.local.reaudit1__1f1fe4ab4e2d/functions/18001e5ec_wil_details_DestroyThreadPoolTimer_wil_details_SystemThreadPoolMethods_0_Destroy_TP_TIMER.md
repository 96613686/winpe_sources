# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001e5ec`
- end: `0x18001e620`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001da9c`
- `0x18002308c`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18001e5fd`
- `KERNEL32!SetThreadpoolTimer` at `0x18001e5fd`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001e619`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001e60b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001e60b`

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
0x18001e5ec  push    rbx
0x18001e5ee  sub     rsp, 20h
0x18001e5f2  xor     r9d, r9d; msWindowLength
0x18001e5f5  xor     r8d, r8d; msPeriod
0x18001e5f8  xor     edx, edx; pftDueTime
0x18001e5fa  mov     rbx, rcx
0x18001e5fd  call    cs:__imp_SetThreadpoolTimer
0x18001e603  mov     edx, 1; fCancelPendingCallbacks
0x18001e608  mov     rcx, rbx; pti
0x18001e60b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001e611  mov     rcx, rbx
0x18001e614  add     rsp, 20h
0x18001e618  pop     rbx
0x18001e619  jmp     cs:__imp_CloseThreadpoolTimer
```
