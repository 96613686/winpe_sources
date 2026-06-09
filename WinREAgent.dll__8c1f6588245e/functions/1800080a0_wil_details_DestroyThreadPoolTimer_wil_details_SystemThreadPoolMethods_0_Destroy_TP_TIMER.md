# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800080a0`
- end: `0x1800080d4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800055ec`
- `0x1800145cc`

## import_xrefs

- `KERNEL32!CloseThreadpoolTimer` at `0x1800080cd`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800080bf`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x1800080bf`
- `KERNEL32!SetThreadpoolTimer` at `0x1800080b1`
- `KERNEL32!SetThreadpoolTimer` at `0x1800080b1`

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
0x1800080a0  push    rbx
0x1800080a2  sub     rsp, 20h
0x1800080a6  xor     r9d, r9d; msWindowLength
0x1800080a9  xor     r8d, r8d; msPeriod
0x1800080ac  xor     edx, edx; pftDueTime
0x1800080ae  mov     rbx, rcx
0x1800080b1  call    cs:__imp_SetThreadpoolTimer
0x1800080b7  mov     edx, 1; fCancelPendingCallbacks
0x1800080bc  mov     rcx, rbx; pti
0x1800080bf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800080c5  mov     rcx, rbx
0x1800080c8  add     rsp, 20h
0x1800080cc  pop     rbx
0x1800080cd  jmp     cs:__imp_CloseThreadpoolTimer
```
