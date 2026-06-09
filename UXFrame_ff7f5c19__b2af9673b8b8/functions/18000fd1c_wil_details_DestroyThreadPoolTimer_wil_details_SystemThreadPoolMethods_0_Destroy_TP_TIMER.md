# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000fd1c`
- end: `0x18000fd50`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e2c0`
- `0x18001a824`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000fd3b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000fd3b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000fd49`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fd2d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000fd2d`

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
0x18000fd1c  push    rbx
0x18000fd1e  sub     rsp, 20h
0x18000fd22  xor     r9d, r9d; msWindowLength
0x18000fd25  xor     r8d, r8d; msPeriod
0x18000fd28  xor     edx, edx; pftDueTime
0x18000fd2a  mov     rbx, rcx
0x18000fd2d  call    cs:__imp_SetThreadpoolTimer
0x18000fd33  mov     edx, 1; fCancelPendingCallbacks
0x18000fd38  mov     rcx, rbx; pti
0x18000fd3b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000fd41  mov     rcx, rbx
0x18000fd44  add     rsp, 20h
0x18000fd48  pop     rbx
0x18000fd49  jmp     cs:__imp_CloseThreadpoolTimer
```
