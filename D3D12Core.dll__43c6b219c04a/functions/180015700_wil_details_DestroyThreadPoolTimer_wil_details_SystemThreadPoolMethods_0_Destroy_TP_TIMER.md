# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180015700`
- end: `0x180015734`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800156bc`
- `0x18001573c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015711`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180015711`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001572d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001571f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001571f`

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
0x180015700  push    rbx
0x180015702  sub     rsp, 20h
0x180015706  xor     r9d, r9d; msWindowLength
0x180015709  xor     r8d, r8d; msPeriod
0x18001570c  xor     edx, edx; pftDueTime
0x18001570e  mov     rbx, rcx
0x180015711  call    cs:__imp_SetThreadpoolTimer
0x180015717  mov     edx, 1; fCancelPendingCallbacks
0x18001571c  mov     rcx, rbx; pti
0x18001571f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180015725  mov     rcx, rbx
0x180015728  add     rsp, 20h
0x18001572c  pop     rbx
0x18001572d  jmp     cs:__imp_CloseThreadpoolTimer
```
