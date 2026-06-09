# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140005e7c`
- end: `0x140005eb0`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000395c`
- `0x14000c31c`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140005e9b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140005e9b`
- `KERNEL32!CloseThreadpoolTimer` at `0x140005ea9`
- `KERNEL32!SetThreadpoolTimer` at `0x140005e8d`
- `KERNEL32!SetThreadpoolTimer` at `0x140005e8d`

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
0x140005e7c  push    rbx
0x140005e7e  sub     rsp, 20h
0x140005e82  xor     r9d, r9d; msWindowLength
0x140005e85  xor     r8d, r8d; msPeriod
0x140005e88  xor     edx, edx; pftDueTime
0x140005e8a  mov     rbx, rcx
0x140005e8d  call    cs:__imp_SetThreadpoolTimer
0x140005e93  mov     edx, 1; fCancelPendingCallbacks
0x140005e98  mov     rcx, rbx; pti
0x140005e9b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005ea1  mov     rcx, rbx
0x140005ea4  add     rsp, 20h
0x140005ea8  pop     rbx
0x140005ea9  jmp     cs:__imp_CloseThreadpoolTimer
```
