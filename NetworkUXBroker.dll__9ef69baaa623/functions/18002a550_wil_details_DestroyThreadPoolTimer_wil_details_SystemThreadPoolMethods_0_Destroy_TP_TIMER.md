# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18002a550`
- end: `0x18002a584`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180028624`
- `0x18003697c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002a57d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002a56f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002a56f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002a561`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002a561`

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
0x18002a550  push    rbx
0x18002a552  sub     rsp, 20h
0x18002a556  xor     r9d, r9d; msWindowLength
0x18002a559  xor     r8d, r8d; msPeriod
0x18002a55c  xor     edx, edx; pftDueTime
0x18002a55e  mov     rbx, rcx
0x18002a561  call    cs:__imp_SetThreadpoolTimer
0x18002a567  mov     edx, 1; fCancelPendingCallbacks
0x18002a56c  mov     rcx, rbx; pti
0x18002a56f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002a575  mov     rcx, rbx
0x18002a578  add     rsp, 20h
0x18002a57c  pop     rbx
0x18002a57d  jmp     cs:__imp_CloseThreadpoolTimer
```
