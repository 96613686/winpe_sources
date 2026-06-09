# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800043e0`
- end: `0x180004414`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800036d8`
- `0x180008d94`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800043f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800043f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000440d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800043ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800043ff`

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
0x1800043e0  push    rbx
0x1800043e2  sub     rsp, 20h
0x1800043e6  xor     r9d, r9d; msWindowLength
0x1800043e9  xor     r8d, r8d; msPeriod
0x1800043ec  xor     edx, edx; pftDueTime
0x1800043ee  mov     rbx, rcx
0x1800043f1  call    cs:__imp_SetThreadpoolTimer
0x1800043f7  mov     edx, 1; fCancelPendingCallbacks
0x1800043fc  mov     rcx, rbx; pti
0x1800043ff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004405  mov     rcx, rbx
0x180004408  add     rsp, 20h
0x18000440c  pop     rbx
0x18000440d  jmp     cs:__imp_CloseThreadpoolTimer
```
