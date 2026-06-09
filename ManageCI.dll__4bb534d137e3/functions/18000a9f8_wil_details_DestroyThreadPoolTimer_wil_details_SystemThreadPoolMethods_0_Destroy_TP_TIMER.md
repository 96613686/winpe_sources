# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000a9f8`
- end: `0x18000aa2c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a3d8`
- `0x18000d6dc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000aa25`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000aa17`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000aa17`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aa09`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aa09`

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
0x18000a9f8  push    rbx
0x18000a9fa  sub     rsp, 20h
0x18000a9fe  xor     r9d, r9d; msWindowLength
0x18000aa01  xor     r8d, r8d; msPeriod
0x18000aa04  xor     edx, edx; pftDueTime
0x18000aa06  mov     rbx, rcx
0x18000aa09  call    cs:__imp_SetThreadpoolTimer
0x18000aa0f  mov     edx, 1; fCancelPendingCallbacks
0x18000aa14  mov     rcx, rbx; pti
0x18000aa17  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000aa1d  mov     rcx, rbx
0x18000aa20  add     rsp, 20h
0x18000aa24  pop     rbx
0x18000aa25  jmp     cs:__imp_CloseThreadpoolTimer
```
