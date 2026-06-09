# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1801cb140`
- end: `0x1801cb188`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `72`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1801b1248`
- `0x1801cfd20`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1801cb170`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1801cb170`
- `KERNEL32!CloseThreadpoolTimer` at `0x1801cb17c`
- `KERNEL32!CloseThreadpoolTimer` at `0x1801cb17c`
- `KERNEL32!SetThreadpoolTimer` at `0x1801cb15f`
- `KERNEL32!SetThreadpoolTimer` at `0x1801cb15f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(
        struct _TP_TIMER *a1)
{
  SetThreadpoolTimer(a1, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(a1, 1);
  CloseThreadpoolTimer(a1);
}

```

## disassembly

```asm
0x1801cb140  mov     [rsp+pti], rcx
0x1801cb145  sub     rsp, 38h
0x1801cb149  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1801cb152  xor     r9d, r9d; msWindowLength
0x1801cb155  xor     r8d, r8d; msPeriod
0x1801cb158  xor     edx, edx; pftDueTime
0x1801cb15a  mov     rcx, [rsp+38h+pti]; pti
0x1801cb15f  call    cs:__imp_SetThreadpoolTimer
0x1801cb165  nop
0x1801cb166  mov     edx, 1; fCancelPendingCallbacks
0x1801cb16b  mov     rcx, [rsp+38h+pti]; pti
0x1801cb170  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1801cb176  nop
0x1801cb177  mov     rcx, [rsp+38h+pti]; pti
0x1801cb17c  call    cs:__imp_CloseThreadpoolTimer
0x1801cb182  nop
0x1801cb183  add     rsp, 38h
0x1801cb187  retn
```
