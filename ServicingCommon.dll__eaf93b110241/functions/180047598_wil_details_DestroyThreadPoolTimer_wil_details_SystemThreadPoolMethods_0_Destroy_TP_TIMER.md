# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180047598`
- end: `0x1800475dd`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180011a8c`
- `0x18001e914`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800475bd`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800475bd`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800475d1`
- `KERNEL32!SetThreadpoolTimer` at `0x1800475a9`
- `KERNEL32!SetThreadpoolTimer` at `0x1800475a9`

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
0x180047598  push    rbx
0x18004759a  sub     rsp, 20h
0x18004759e  xor     r9d, r9d; msWindowLength
0x1800475a1  xor     r8d, r8d; msPeriod
0x1800475a4  xor     edx, edx; pftDueTime
0x1800475a6  mov     rbx, rcx
0x1800475a9  call    cs:__imp_SetThreadpoolTimer
0x1800475b0  nop     dword ptr [rax+rax+00h]
0x1800475b5  mov     edx, 1; fCancelPendingCallbacks
0x1800475ba  mov     rcx, rbx; pti
0x1800475bd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800475c4  nop     dword ptr [rax+rax+00h]
0x1800475c9  mov     rcx, rbx
0x1800475cc  add     rsp, 20h
0x1800475d0  pop     rbx
0x1800475d1  jmp     cs:__imp_CloseThreadpoolTimer
```
