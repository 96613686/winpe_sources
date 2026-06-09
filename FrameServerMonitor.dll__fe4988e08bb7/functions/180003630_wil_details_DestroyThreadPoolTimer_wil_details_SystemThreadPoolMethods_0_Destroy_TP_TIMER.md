# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180003630`
- end: `0x180003664`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180003178`
- `0x180005654`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000364f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000364f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000365d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003641`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180003641`

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
0x180003630  push    rbx
0x180003632  sub     rsp, 20h
0x180003636  xor     r9d, r9d; msWindowLength
0x180003639  xor     r8d, r8d; msPeriod
0x18000363c  xor     edx, edx; pftDueTime
0x18000363e  mov     rbx, rcx
0x180003641  call    cs:__imp_SetThreadpoolTimer
0x180003647  mov     edx, 1; fCancelPendingCallbacks
0x18000364c  mov     rcx, rbx; pti
0x18000364f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180003655  mov     rcx, rbx
0x180003658  add     rsp, 20h
0x18000365c  pop     rbx
0x18000365d  jmp     cs:__imp_CloseThreadpoolTimer
```
