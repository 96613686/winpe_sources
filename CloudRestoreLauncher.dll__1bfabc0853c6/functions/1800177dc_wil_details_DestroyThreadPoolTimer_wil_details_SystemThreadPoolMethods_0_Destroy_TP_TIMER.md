# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800177dc`
- end: `0x180017810`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180016728`
- `0x18001daa0`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800177fb`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800177fb`
- `KERNEL32!CloseThreadpoolTimer` at `0x180017809`
- `KERNEL32!SetThreadpoolTimer` at `0x1800177ed`
- `KERNEL32!SetThreadpoolTimer` at `0x1800177ed`

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
0x1800177dc  push    rbx
0x1800177de  sub     rsp, 20h
0x1800177e2  xor     r9d, r9d; msWindowLength
0x1800177e5  xor     r8d, r8d; msPeriod
0x1800177e8  xor     edx, edx; pftDueTime
0x1800177ea  mov     rbx, rcx
0x1800177ed  call    cs:__imp_SetThreadpoolTimer
0x1800177f3  mov     edx, 1; fCancelPendingCallbacks
0x1800177f8  mov     rcx, rbx; pti
0x1800177fb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180017801  mov     rcx, rbx
0x180017804  add     rsp, 20h
0x180017808  pop     rbx
0x180017809  jmp     cs:__imp_CloseThreadpoolTimer
```
