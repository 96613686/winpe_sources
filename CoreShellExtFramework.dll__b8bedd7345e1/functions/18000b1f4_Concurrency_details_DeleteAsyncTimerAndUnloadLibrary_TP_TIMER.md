# Concurrency::details::DeleteAsyncTimerAndUnloadLibrary(_TP_TIMER *)

- ea: `0x18000b1f4`
- end: `0x18000b228`
- name: `?DeleteAsyncTimerAndUnloadLibrary@details@Concurrency@@YAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti, struct _TP_TIMER *)`
- caller_count: `2`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000a6e4`
- `0x18000e9f0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b205`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b205`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b221`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b213`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b213`

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
0x18000b1f4  push    rbx
0x18000b1f6  sub     rsp, 20h
0x18000b1fa  xor     r9d, r9d; msWindowLength
0x18000b1fd  xor     r8d, r8d; msPeriod
0x18000b200  xor     edx, edx; pftDueTime
0x18000b202  mov     rbx, rcx
0x18000b205  call    cs:SetThreadpoolTimer
0x18000b20b  mov     edx, 1; fCancelPendingCallbacks
0x18000b210  mov     rcx, rbx; pti
0x18000b213  call    cs:WaitForThreadpoolTimerCallbacks
0x18000b219  mov     rcx, rbx
0x18000b21c  add     rsp, 20h
0x18000b220  pop     rbx
0x18000b221  jmp     cs:CloseThreadpoolTimer
```
