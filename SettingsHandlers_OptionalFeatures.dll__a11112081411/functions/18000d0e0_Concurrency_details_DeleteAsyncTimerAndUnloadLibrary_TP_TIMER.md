# Concurrency::details::DeleteAsyncTimerAndUnloadLibrary(_TP_TIMER *)

- ea: `0x18000d0e0`
- end: `0x18000d114`
- name: `?DeleteAsyncTimerAndUnloadLibrary@details@Concurrency@@YAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti, struct _TP_TIMER *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000c740`
- `0x180011548`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d0ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d0ff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d10d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d0f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d0f1`

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
0x18000d0e0  push    rbx
0x18000d0e2  sub     rsp, 20h
0x18000d0e6  xor     r9d, r9d; msWindowLength
0x18000d0e9  xor     r8d, r8d; msPeriod
0x18000d0ec  xor     edx, edx; pftDueTime
0x18000d0ee  mov     rbx, rcx
0x18000d0f1  call    cs:SetThreadpoolTimer
0x18000d0f7  mov     edx, 1; fCancelPendingCallbacks
0x18000d0fc  mov     rcx, rbx; pti
0x18000d0ff  call    cs:WaitForThreadpoolTimerCallbacks
0x18000d105  mov     rcx, rbx
0x18000d108  add     rsp, 20h
0x18000d10c  pop     rbx
0x18000d10d  jmp     cs:CloseThreadpoolTimer
```
