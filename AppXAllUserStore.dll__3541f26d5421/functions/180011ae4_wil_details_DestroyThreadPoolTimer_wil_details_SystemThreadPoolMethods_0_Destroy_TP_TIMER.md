# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180011ae4`
- end: `0x180011b18`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180011aa0`
- `0x18001b1e4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011b11`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011af5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011af5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011b03`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011b03`

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
0x180011ae4  push    rbx
0x180011ae6  sub     rsp, 20h
0x180011aea  xor     r9d, r9d; msWindowLength
0x180011aed  xor     r8d, r8d; msPeriod
0x180011af0  xor     edx, edx; pftDueTime
0x180011af2  mov     rbx, rcx
0x180011af5  call    cs:__imp_SetThreadpoolTimer
0x180011afb  mov     edx, 1; fCancelPendingCallbacks
0x180011b00  mov     rcx, rbx; pti
0x180011b03  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011b09  mov     rcx, rbx
0x180011b0c  add     rsp, 20h
0x180011b10  pop     rbx
0x180011b11  jmp     cs:__imp_CloseThreadpoolTimer
```
