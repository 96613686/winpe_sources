# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800536b4`
- end: `0x1800536f9`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800529cc`
- `0x180058274`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x1800536c5`
- `KERNEL32!SetThreadpoolTimer` at `0x1800536c5`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800536ed`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800536d9`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800536d9`

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
0x1800536b4  push    rbx
0x1800536b6  sub     rsp, 20h
0x1800536ba  xor     r9d, r9d; msWindowLength
0x1800536bd  xor     r8d, r8d; msPeriod
0x1800536c0  xor     edx, edx; pftDueTime
0x1800536c2  mov     rbx, rcx
0x1800536c5  call    cs:__imp_SetThreadpoolTimer
0x1800536cc  nop     dword ptr [rax+rax+00h]
0x1800536d1  mov     edx, 1; fCancelPendingCallbacks
0x1800536d6  mov     rcx, rbx; pti
0x1800536d9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800536e0  nop     dword ptr [rax+rax+00h]
0x1800536e5  mov     rcx, rbx
0x1800536e8  add     rsp, 20h
0x1800536ec  pop     rbx
0x1800536ed  jmp     cs:__imp_CloseThreadpoolTimer
```
