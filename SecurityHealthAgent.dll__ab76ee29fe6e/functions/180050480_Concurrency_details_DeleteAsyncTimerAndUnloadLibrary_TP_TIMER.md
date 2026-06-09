# Concurrency::details::DeleteAsyncTimerAndUnloadLibrary(_TP_TIMER *)

- ea: `0x180050480`
- end: `0x1800504b4`
- name: `?DeleteAsyncTimerAndUnloadLibrary@details@Concurrency@@YAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti, struct _TP_TIMER *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18004fb30`
- `0x180054584`

## import_xrefs

- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18005049f`
- `KERNEL32!WaitForThreadpoolTimerCallbacks` at `0x18005049f`
- `KERNEL32!CloseThreadpoolTimer` at `0x1800504ad`
- `KERNEL32!SetThreadpoolTimer` at `0x180050491`
- `KERNEL32!SetThreadpoolTimer` at `0x180050491`

## pseudocode

```c
void __fastcall Concurrency::details::DeleteAsyncTimerAndUnloadLibrary(PTP_TIMER pti, struct _TP_TIMER *a2)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x180050480  push    rbx
0x180050482  sub     rsp, 20h
0x180050486  xor     r9d, r9d; msWindowLength
0x180050489  xor     r8d, r8d; msPeriod
0x18005048c  xor     edx, edx; pftDueTime
0x18005048e  mov     rbx, rcx
0x180050491  call    cs:SetThreadpoolTimer
0x180050497  mov     edx, 1; fCancelPendingCallbacks
0x18005049c  mov     rcx, rbx; pti
0x18005049f  call    cs:WaitForThreadpoolTimerCallbacks
0x1800504a5  mov     rcx, rbx
0x1800504a8  add     rsp, 20h
0x1800504ac  pop     rbx
0x1800504ad  jmp     cs:CloseThreadpoolTimer
```
