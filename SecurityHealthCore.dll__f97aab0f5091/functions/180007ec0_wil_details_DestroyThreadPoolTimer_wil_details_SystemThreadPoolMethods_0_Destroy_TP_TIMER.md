# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180007ec0`
- end: `0x180007ef4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180007590`
- `0x18000bfb4`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180007edf`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x180007edf`
- `KERNEL32!CloseThreadpoolTimer` at `0x180007eed`
- `KERNEL32!SetThreadpoolTimer` at `0x180007ed1`
- `KERNEL32!SetThreadpoolTimer` at `0x180007ed1`

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
0x180007ec0  push    rbx
0x180007ec2  sub     rsp, 20h
0x180007ec6  xor     r9d, r9d; msWindowLength
0x180007ec9  xor     r8d, r8d; msPeriod
0x180007ecc  xor     edx, edx; pftDueTime
0x180007ece  mov     rbx, rcx
0x180007ed1  call    cs:__imp_SetThreadpoolTimer
0x180007ed7  mov     edx, 1; fCancelPendingCallbacks
0x180007edc  mov     rcx, rbx; pti
0x180007edf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180007ee5  mov     rcx, rbx
0x180007ee8  add     rsp, 20h
0x180007eec  pop     rbx
0x180007eed  jmp     cs:__imp_CloseThreadpoolTimer
```
