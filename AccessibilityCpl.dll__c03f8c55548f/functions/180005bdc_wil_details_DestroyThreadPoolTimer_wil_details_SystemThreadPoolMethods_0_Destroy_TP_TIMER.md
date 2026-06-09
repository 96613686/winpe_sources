# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180005bdc`
- end: `0x180005c10`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004a10`
- `0x18001b888`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005bed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005bed`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005bfb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005bfb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005c09`

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
0x180005bdc  push    rbx
0x180005bde  sub     rsp, 20h
0x180005be2  xor     r9d, r9d; msWindowLength
0x180005be5  xor     r8d, r8d; msPeriod
0x180005be8  xor     edx, edx; pftDueTime
0x180005bea  mov     rbx, rcx
0x180005bed  call    cs:__imp_SetThreadpoolTimer
0x180005bf3  mov     edx, 1; fCancelPendingCallbacks
0x180005bf8  mov     rcx, rbx; pti
0x180005bfb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005c01  mov     rcx, rbx
0x180005c04  add     rsp, 20h
0x180005c08  pop     rbx
0x180005c09  jmp     cs:__imp_CloseThreadpoolTimer
```
