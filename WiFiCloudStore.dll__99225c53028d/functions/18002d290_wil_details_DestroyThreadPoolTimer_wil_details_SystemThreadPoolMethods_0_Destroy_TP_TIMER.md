# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18002d290`
- end: `0x18002d2c4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e5e0`
- `0x180028fe4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002d2a1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002d2a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002d2bd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002d2af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002d2af`

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
0x18002d290  push    rbx
0x18002d292  sub     rsp, 20h
0x18002d296  xor     r9d, r9d; msWindowLength
0x18002d299  xor     r8d, r8d; msPeriod
0x18002d29c  xor     edx, edx; pftDueTime
0x18002d29e  mov     rbx, rcx
0x18002d2a1  call    cs:__imp_SetThreadpoolTimer
0x18002d2a7  mov     edx, 1; fCancelPendingCallbacks
0x18002d2ac  mov     rcx, rbx; pti
0x18002d2af  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002d2b5  mov     rcx, rbx
0x18002d2b8  add     rsp, 20h
0x18002d2bc  pop     rbx
0x18002d2bd  jmp     cs:__imp_CloseThreadpoolTimer
```
