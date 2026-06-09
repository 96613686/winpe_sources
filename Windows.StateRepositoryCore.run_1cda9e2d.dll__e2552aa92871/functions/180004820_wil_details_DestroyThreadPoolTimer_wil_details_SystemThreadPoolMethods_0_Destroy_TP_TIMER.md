# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180004820`
- end: `0x180004854`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003db8`
- `0x18000ae20`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004831`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004831`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000484d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000483f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000483f`

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
0x180004820  push    rbx
0x180004822  sub     rsp, 20h
0x180004826  xor     r9d, r9d; msWindowLength
0x180004829  xor     r8d, r8d; msPeriod
0x18000482c  xor     edx, edx; pftDueTime
0x18000482e  mov     rbx, rcx
0x180004831  call    cs:__imp_SetThreadpoolTimer
0x180004837  mov     edx, 1; fCancelPendingCallbacks
0x18000483c  mov     rcx, rbx; pti
0x18000483f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004845  mov     rcx, rbx
0x180004848  add     rsp, 20h
0x18000484c  pop     rbx
0x18000484d  jmp     cs:__imp_CloseThreadpoolTimer
```
