# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001ff30`
- end: `0x18001ff64`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001f6d0`
- `0x18002376c`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18001ff41`
- `KERNEL32!SetThreadpoolTimer` at `0x18001ff41`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001ff4f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18001ff4f`
- `KERNEL32!CloseThreadpoolTimer` at `0x18001ff5d`

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
0x18001ff30  push    rbx
0x18001ff32  sub     rsp, 20h
0x18001ff36  xor     r9d, r9d; msWindowLength
0x18001ff39  xor     r8d, r8d; msPeriod
0x18001ff3c  xor     edx, edx; pftDueTime
0x18001ff3e  mov     rbx, rcx
0x18001ff41  call    cs:__imp_SetThreadpoolTimer
0x18001ff47  mov     edx, 1; fCancelPendingCallbacks
0x18001ff4c  mov     rcx, rbx; pti
0x18001ff4f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001ff55  mov     rcx, rbx
0x18001ff58  add     rsp, 20h
0x18001ff5c  pop     rbx
0x18001ff5d  jmp     cs:__imp_CloseThreadpoolTimer
```
