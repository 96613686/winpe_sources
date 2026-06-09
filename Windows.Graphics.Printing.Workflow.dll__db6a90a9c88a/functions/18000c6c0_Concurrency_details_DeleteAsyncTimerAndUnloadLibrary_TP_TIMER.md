# Concurrency::details::DeleteAsyncTimerAndUnloadLibrary(_TP_TIMER *)

- ea: `0x18000c6c0`
- end: `0x18000c6f4`
- name: `?DeleteAsyncTimerAndUnloadLibrary@details@Concurrency@@YAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti, struct _TP_TIMER *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000bcd0`
- `0x180010f5c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c6ed`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c6df`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c6df`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c6d1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c6d1`

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
0x18000c6c0  push    rbx
0x18000c6c2  sub     rsp, 20h
0x18000c6c6  xor     r9d, r9d; msWindowLength
0x18000c6c9  xor     r8d, r8d; msPeriod
0x18000c6cc  xor     edx, edx; pftDueTime
0x18000c6ce  mov     rbx, rcx
0x18000c6d1  call    cs:SetThreadpoolTimer
0x18000c6d7  mov     edx, 1; fCancelPendingCallbacks
0x18000c6dc  mov     rcx, rbx; pti
0x18000c6df  call    cs:WaitForThreadpoolTimerCallbacks
0x18000c6e5  mov     rcx, rbx
0x18000c6e8  add     rsp, 20h
0x18000c6ec  pop     rbx
0x18000c6ed  jmp     cs:CloseThreadpoolTimer
```
