# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18005b748`
- end: `0x18005b77c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800488a8`
- `0x1800488f8`

## import_xrefs

- `KERNEL32!SetThreadpoolTimer` at `0x18005b759`
- `KERNEL32!SetThreadpoolTimer` at `0x18005b759`
- `KERNEL32!CloseThreadpoolTimer` at `0x18005b775`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18005b767`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18005b767`

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
0x18005b748  push    rbx
0x18005b74a  sub     rsp, 20h
0x18005b74e  xor     r9d, r9d; msWindowLength
0x18005b751  xor     r8d, r8d; msPeriod
0x18005b754  xor     edx, edx; pftDueTime
0x18005b756  mov     rbx, rcx
0x18005b759  call    cs:__imp_SetThreadpoolTimer
0x18005b75f  mov     edx, 1; fCancelPendingCallbacks
0x18005b764  mov     rcx, rbx; pti
0x18005b767  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005b76d  mov     rcx, rbx
0x18005b770  add     rsp, 20h
0x18005b774  pop     rbx
0x18005b775  jmp     cs:__imp_CloseThreadpoolTimer
```
