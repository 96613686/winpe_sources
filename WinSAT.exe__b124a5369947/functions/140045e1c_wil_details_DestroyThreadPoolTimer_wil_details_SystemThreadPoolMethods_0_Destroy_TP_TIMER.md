# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140045e1c`
- end: `0x140045e50`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140045190`
- `0x14004b27c`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x140045e2d`
- `KERNEL32!SetThreadpoolTimer` at `0x140045e2d`
- `KERNEL32!CloseThreadpoolTimer` at `0x140045e49`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140045e3b`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x140045e3b`

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
0x140045e1c  push    rbx
0x140045e1e  sub     rsp, 20h
0x140045e22  xor     r9d, r9d; msWindowLength
0x140045e25  xor     r8d, r8d; msPeriod
0x140045e28  xor     edx, edx; pftDueTime
0x140045e2a  mov     rbx, rcx
0x140045e2d  call    cs:__imp_SetThreadpoolTimer
0x140045e33  mov     edx, 1; fCancelPendingCallbacks
0x140045e38  mov     rcx, rbx; pti
0x140045e3b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140045e41  mov     rcx, rbx
0x140045e44  add     rsp, 20h
0x140045e48  pop     rbx
0x140045e49  jmp     cs:__imp_CloseThreadpoolTimer
```
