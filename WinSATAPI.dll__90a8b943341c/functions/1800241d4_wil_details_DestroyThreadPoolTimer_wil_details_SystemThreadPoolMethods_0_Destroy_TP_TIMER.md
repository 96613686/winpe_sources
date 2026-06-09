# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800241d4`
- end: `0x180024219`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000fc28`
- `0x18000fd14`
- `0x180011638`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x18002420d`
- `KERNEL32!SetThreadpoolTimer` at `0x1800241e5`
- `KERNEL32!SetThreadpoolTimer` at `0x1800241e5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800241f9`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800241f9`

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
0x1800241d4  push    rbx
0x1800241d6  sub     rsp, 20h
0x1800241da  xor     r9d, r9d; msWindowLength
0x1800241dd  xor     r8d, r8d; msPeriod
0x1800241e0  xor     edx, edx; pftDueTime
0x1800241e2  mov     rbx, rcx
0x1800241e5  call    cs:__imp_SetThreadpoolTimer
0x1800241ec  nop     dword ptr [rax+rax+00h]
0x1800241f1  mov     edx, 1; fCancelPendingCallbacks
0x1800241f6  mov     rcx, rbx; pti
0x1800241f9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180024200  nop     dword ptr [rax+rax+00h]
0x180024205  mov     rcx, rbx
0x180024208  add     rsp, 20h
0x18002420c  pop     rbx
0x18002420d  jmp     cs:__imp_CloseThreadpoolTimer
```
