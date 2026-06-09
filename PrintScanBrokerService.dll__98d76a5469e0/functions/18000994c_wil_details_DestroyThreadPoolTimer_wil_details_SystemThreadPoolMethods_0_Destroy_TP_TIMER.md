# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000994c`
- end: `0x180009980`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180008228`
- `0x180010d48`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000996b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000996b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009979`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000995d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000995d`

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
0x18000994c  push    rbx
0x18000994e  sub     rsp, 20h
0x180009952  xor     r9d, r9d; msWindowLength
0x180009955  xor     r8d, r8d; msPeriod
0x180009958  xor     edx, edx; pftDueTime
0x18000995a  mov     rbx, rcx
0x18000995d  call    cs:__imp_SetThreadpoolTimer
0x180009963  mov     edx, 1; fCancelPendingCallbacks
0x180009968  mov     rcx, rbx; pti
0x18000996b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009971  mov     rcx, rbx
0x180009974  add     rsp, 20h
0x180009978  pop     rbx
0x180009979  jmp     cs:__imp_CloseThreadpoolTimer
```
