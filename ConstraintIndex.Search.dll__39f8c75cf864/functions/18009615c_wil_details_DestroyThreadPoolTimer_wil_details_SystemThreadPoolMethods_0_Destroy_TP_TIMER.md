# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18009615c`
- end: `0x180096190`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800956a0`
- `0x180099f74`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009616d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18009616d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180096189`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18009617b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18009617b`

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
0x18009615c  push    rbx
0x18009615e  sub     rsp, 20h
0x180096162  xor     r9d, r9d; msWindowLength
0x180096165  xor     r8d, r8d; msPeriod
0x180096168  xor     edx, edx; pftDueTime
0x18009616a  mov     rbx, rcx
0x18009616d  call    cs:__imp_SetThreadpoolTimer
0x180096173  mov     edx, 1; fCancelPendingCallbacks
0x180096178  mov     rcx, rbx; pti
0x18009617b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180096181  mov     rcx, rbx
0x180096184  add     rsp, 20h
0x180096188  pop     rbx
0x180096189  jmp     cs:__imp_CloseThreadpoolTimer
```
