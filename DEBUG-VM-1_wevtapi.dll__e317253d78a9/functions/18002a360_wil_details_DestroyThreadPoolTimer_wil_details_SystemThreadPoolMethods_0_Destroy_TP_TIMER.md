# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18002a360`
- end: `0x18002a394`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x180020714`
- `0x180020838`
- `0x180020888`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002a38d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002a371`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002a371`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002a37f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002a37f`

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
0x18002a360  push    rbx
0x18002a362  sub     rsp, 20h
0x18002a366  xor     r9d, r9d; msWindowLength
0x18002a369  xor     r8d, r8d; msPeriod
0x18002a36c  xor     edx, edx; pftDueTime
0x18002a36e  mov     rbx, rcx
0x18002a371  call    cs:__imp_SetThreadpoolTimer
0x18002a377  mov     edx, 1; fCancelPendingCallbacks
0x18002a37c  mov     rcx, rbx; pti
0x18002a37f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002a385  mov     rcx, rbx
0x18002a388  add     rsp, 20h
0x18002a38c  pop     rbx
0x18002a38d  jmp     cs:__imp_CloseThreadpoolTimer
```
