# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001fec4`
- end: `0x18001fef8`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180012c80`
- `0x1800130c8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001fef1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fee3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001fee3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fed5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001fed5`

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
0x18001fec4  push    rbx
0x18001fec6  sub     rsp, 20h
0x18001feca  xor     r9d, r9d; msWindowLength
0x18001fecd  xor     r8d, r8d; msPeriod
0x18001fed0  xor     edx, edx; pftDueTime
0x18001fed2  mov     rbx, rcx
0x18001fed5  call    cs:__imp_SetThreadpoolTimer
0x18001fedb  mov     edx, 1; fCancelPendingCallbacks
0x18001fee0  mov     rcx, rbx; pti
0x18001fee3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001fee9  mov     rcx, rbx
0x18001feec  add     rsp, 20h
0x18001fef0  pop     rbx
0x18001fef1  jmp     cs:__imp_CloseThreadpoolTimer
```
