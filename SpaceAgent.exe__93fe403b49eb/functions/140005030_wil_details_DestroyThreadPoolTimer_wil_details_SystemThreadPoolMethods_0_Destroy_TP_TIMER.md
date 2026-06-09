# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140005030`
- end: `0x140005064`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140004644`
- `0x1400095a8`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000504f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x14000504f`
- `KERNEL32!CloseThreadpoolTimer` at `0x14000505d`
- `KERNEL32!SetThreadpoolTimer` at `0x140005041`
- `KERNEL32!SetThreadpoolTimer` at `0x140005041`

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
0x140005030  push    rbx
0x140005032  sub     rsp, 20h
0x140005036  xor     r9d, r9d; msWindowLength
0x140005039  xor     r8d, r8d; msPeriod
0x14000503c  xor     edx, edx; pftDueTime
0x14000503e  mov     rbx, rcx
0x140005041  call    cs:__imp_SetThreadpoolTimer
0x140005047  mov     edx, 1; fCancelPendingCallbacks
0x14000504c  mov     rcx, rbx; pti
0x14000504f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140005055  mov     rcx, rbx
0x140005058  add     rsp, 20h
0x14000505c  pop     rbx
0x14000505d  jmp     cs:__imp_CloseThreadpoolTimer
```
