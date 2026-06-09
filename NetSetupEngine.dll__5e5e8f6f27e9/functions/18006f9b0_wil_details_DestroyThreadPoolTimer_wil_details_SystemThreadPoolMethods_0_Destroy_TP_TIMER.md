# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18006f9b0`
- end: `0x18006f9e4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18004a394`
- `0x18004a3e4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006f9dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006f9c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006f9c1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006f9cf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006f9cf`

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
0x18006f9b0  push    rbx
0x18006f9b2  sub     rsp, 20h
0x18006f9b6  xor     r9d, r9d; msWindowLength
0x18006f9b9  xor     r8d, r8d; msPeriod
0x18006f9bc  xor     edx, edx; pftDueTime
0x18006f9be  mov     rbx, rcx
0x18006f9c1  call    cs:__imp_SetThreadpoolTimer
0x18006f9c7  mov     edx, 1; fCancelPendingCallbacks
0x18006f9cc  mov     rcx, rbx; pti
0x18006f9cf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006f9d5  mov     rcx, rbx
0x18006f9d8  add     rsp, 20h
0x18006f9dc  pop     rbx
0x18006f9dd  jmp     cs:__imp_CloseThreadpoolTimer
```
