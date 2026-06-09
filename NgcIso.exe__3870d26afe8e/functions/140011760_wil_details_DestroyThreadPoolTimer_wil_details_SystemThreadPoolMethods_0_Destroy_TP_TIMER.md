# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140011760`
- end: `0x140011794`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000cc30`
- `0x14006f840`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14001178d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001177f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14001177f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140011771`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140011771`

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
0x140011760  push    rbx
0x140011762  sub     rsp, 20h
0x140011766  xor     r9d, r9d; msWindowLength
0x140011769  xor     r8d, r8d; msPeriod
0x14001176c  xor     edx, edx; pftDueTime
0x14001176e  mov     rbx, rcx
0x140011771  call    cs:__imp_SetThreadpoolTimer
0x140011777  mov     edx, 1; fCancelPendingCallbacks
0x14001177c  mov     rcx, rbx; pti
0x14001177f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140011785  mov     rcx, rbx
0x140011788  add     rsp, 20h
0x14001178c  pop     rbx
0x14001178d  jmp     cs:__imp_CloseThreadpoolTimer
```
