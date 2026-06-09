# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180089740`
- end: `0x180089774`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18005db40`
- `0x180083ed0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18008976d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180089751`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180089751`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008975f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18008975f`

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
0x180089740  push    rbx
0x180089742  sub     rsp, 20h
0x180089746  xor     r9d, r9d; msWindowLength
0x180089749  xor     r8d, r8d; msPeriod
0x18008974c  xor     edx, edx; pftDueTime
0x18008974e  mov     rbx, rcx
0x180089751  call    cs:__imp_SetThreadpoolTimer
0x180089757  mov     edx, 1; fCancelPendingCallbacks
0x18008975c  mov     rcx, rbx; pti
0x18008975f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180089765  mov     rcx, rbx
0x180089768  add     rsp, 20h
0x18008976c  pop     rbx
0x18008976d  jmp     cs:__imp_CloseThreadpoolTimer
```
