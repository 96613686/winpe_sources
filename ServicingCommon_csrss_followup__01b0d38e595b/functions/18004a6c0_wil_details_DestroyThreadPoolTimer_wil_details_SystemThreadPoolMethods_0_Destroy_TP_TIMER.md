# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18004a6c0`
- end: `0x18004a705`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001ba8c`
- `0x18001d16c`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18004a6e5`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18004a6e5`
- `KERNEL32!CloseThreadpoolTimer` at `0x18004a6f9`
- `KERNEL32!SetThreadpoolTimer` at `0x18004a6d1`
- `KERNEL32!SetThreadpoolTimer` at `0x18004a6d1`

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
0x18004a6c0  push    rbx
0x18004a6c2  sub     rsp, 20h
0x18004a6c6  xor     r9d, r9d; msWindowLength
0x18004a6c9  xor     r8d, r8d; msPeriod
0x18004a6cc  xor     edx, edx; pftDueTime
0x18004a6ce  mov     rbx, rcx
0x18004a6d1  call    cs:__imp_SetThreadpoolTimer
0x18004a6d8  nop     dword ptr [rax+rax+00h]
0x18004a6dd  mov     edx, 1; fCancelPendingCallbacks
0x18004a6e2  mov     rcx, rbx; pti
0x18004a6e5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004a6ec  nop     dword ptr [rax+rax+00h]
0x18004a6f1  mov     rcx, rbx
0x18004a6f4  add     rsp, 20h
0x18004a6f8  pop     rbx
0x18004a6f9  jmp     cs:__imp_CloseThreadpoolTimer
```
