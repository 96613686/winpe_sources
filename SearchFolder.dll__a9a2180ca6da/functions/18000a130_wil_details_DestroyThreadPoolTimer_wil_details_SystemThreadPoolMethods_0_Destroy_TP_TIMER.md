# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000a130`
- end: `0x18000a164`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004d90`
- `0x180050910`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a15d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a141`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a141`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a14f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a14f`

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
0x18000a130  push    rbx
0x18000a132  sub     rsp, 20h
0x18000a136  xor     r9d, r9d; msWindowLength
0x18000a139  xor     r8d, r8d; msPeriod
0x18000a13c  xor     edx, edx; pftDueTime
0x18000a13e  mov     rbx, rcx
0x18000a141  call    cs:__imp_SetThreadpoolTimer
0x18000a147  mov     edx, 1; fCancelPendingCallbacks
0x18000a14c  mov     rcx, rbx; pti
0x18000a14f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a155  mov     rcx, rbx
0x18000a158  add     rsp, 20h
0x18000a15c  pop     rbx
0x18000a15d  jmp     cs:__imp_CloseThreadpoolTimer
```
