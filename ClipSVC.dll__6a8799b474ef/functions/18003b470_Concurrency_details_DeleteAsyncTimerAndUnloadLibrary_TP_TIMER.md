# Concurrency::details::DeleteAsyncTimerAndUnloadLibrary(_TP_TIMER *)

- ea: `0x18003b470`
- end: `0x18003b4a4`
- name: `?DeleteAsyncTimerAndUnloadLibrary@details@Concurrency@@YAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti, struct _TP_TIMER *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18002b178`
- `0x18002b1c8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003b49d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003b481`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003b481`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003b48f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003b48f`

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
0x18003b470  push    rbx
0x18003b472  sub     rsp, 20h
0x18003b476  xor     r9d, r9d; msWindowLength
0x18003b479  xor     r8d, r8d; msPeriod
0x18003b47c  xor     edx, edx; pftDueTime
0x18003b47e  mov     rbx, rcx
0x18003b481  call    cs:SetThreadpoolTimer
0x18003b487  mov     edx, 1; fCancelPendingCallbacks
0x18003b48c  mov     rcx, rbx; pti
0x18003b48f  call    cs:WaitForThreadpoolTimerCallbacks
0x18003b495  mov     rcx, rbx
0x18003b498  add     rsp, 20h
0x18003b49c  pop     rbx
0x18003b49d  jmp     cs:CloseThreadpoolTimer
```
