# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180036104`
- end: `0x180036149`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002bfa0`
- `0x18002bffc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180036129`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180036129`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036115`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036115`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003613d`

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
0x180036104  push    rbx
0x180036106  sub     rsp, 20h
0x18003610a  xor     r9d, r9d; msWindowLength
0x18003610d  xor     r8d, r8d; msPeriod
0x180036110  xor     edx, edx; pftDueTime
0x180036112  mov     rbx, rcx
0x180036115  call    cs:__imp_SetThreadpoolTimer
0x18003611c  nop     dword ptr [rax+rax+00h]
0x180036121  mov     edx, 1; fCancelPendingCallbacks
0x180036126  mov     rcx, rbx; pti
0x180036129  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180036130  nop     dword ptr [rax+rax+00h]
0x180036135  mov     rcx, rbx
0x180036138  add     rsp, 20h
0x18003613c  pop     rbx
0x18003613d  jmp     cs:__imp_CloseThreadpoolTimer
```
