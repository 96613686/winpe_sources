# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18004b040`
- end: `0x18004b074`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d9c8`
- `0x180025b18`
- `0x180025bd8`
- `0x180025bf4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004b05f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18004b05f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18004b06d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004b051`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18004b051`

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
0x18004b040  push    rbx
0x18004b042  sub     rsp, 20h
0x18004b046  xor     r9d, r9d; msWindowLength
0x18004b049  xor     r8d, r8d; msPeriod
0x18004b04c  xor     edx, edx; pftDueTime
0x18004b04e  mov     rbx, rcx
0x18004b051  call    cs:__imp_SetThreadpoolTimer
0x18004b057  mov     edx, 1; fCancelPendingCallbacks
0x18004b05c  mov     rcx, rbx; pti
0x18004b05f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004b065  mov     rcx, rbx
0x18004b068  add     rsp, 20h
0x18004b06c  pop     rbx
0x18004b06d  jmp     cs:__imp_CloseThreadpoolTimer
```
