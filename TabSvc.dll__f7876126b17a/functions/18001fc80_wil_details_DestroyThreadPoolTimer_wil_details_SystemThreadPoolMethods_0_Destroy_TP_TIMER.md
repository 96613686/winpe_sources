# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001fc80`
- end: `0x18001fcb4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180013e6c`
- `0x1800186e4`
- `0x180018b2c`
- `0x180018bf8`
- `0x180018cb8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fc9f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fc9f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001fcad`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fc91`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fc91`

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
0x18001fc80  push    rbx
0x18001fc82  sub     rsp, 20h
0x18001fc86  xor     r9d, r9d; msWindowLength
0x18001fc89  xor     r8d, r8d; msPeriod
0x18001fc8c  xor     edx, edx; pftDueTime
0x18001fc8e  mov     rbx, rcx
0x18001fc91  call    cs:__imp_SetThreadpoolTimer
0x18001fc97  mov     edx, 1; fCancelPendingCallbacks
0x18001fc9c  mov     rcx, rbx; pti
0x18001fc9f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001fca5  mov     rcx, rbx
0x18001fca8  add     rsp, 20h
0x18001fcac  pop     rbx
0x18001fcad  jmp     cs:__imp_CloseThreadpoolTimer
```
