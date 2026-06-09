# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180009020`
- end: `0x180009054`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180008740`
- `0x18000ce38`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000904d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009031`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009031`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000903f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000903f`

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
0x180009020  push    rbx
0x180009022  sub     rsp, 20h
0x180009026  xor     r9d, r9d; msWindowLength
0x180009029  xor     r8d, r8d; msPeriod
0x18000902c  xor     edx, edx; pftDueTime
0x18000902e  mov     rbx, rcx
0x180009031  call    cs:__imp_SetThreadpoolTimer
0x180009037  mov     edx, 1; fCancelPendingCallbacks
0x18000903c  mov     rcx, rbx; pti
0x18000903f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009045  mov     rcx, rbx
0x180009048  add     rsp, 20h
0x18000904c  pop     rbx
0x18000904d  jmp     cs:__imp_CloseThreadpoolTimer
```
