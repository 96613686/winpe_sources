# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000d854`
- end: `0x18000d888`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000bf18`
- `0x180014e2c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d881`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d873`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d873`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d865`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d865`

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
0x18000d854  push    rbx
0x18000d856  sub     rsp, 20h
0x18000d85a  xor     r9d, r9d; msWindowLength
0x18000d85d  xor     r8d, r8d; msPeriod
0x18000d860  xor     edx, edx; pftDueTime
0x18000d862  mov     rbx, rcx
0x18000d865  call    cs:__imp_SetThreadpoolTimer
0x18000d86b  mov     edx, 1; fCancelPendingCallbacks
0x18000d870  mov     rcx, rbx; pti
0x18000d873  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d879  mov     rcx, rbx
0x18000d87c  add     rsp, 20h
0x18000d880  pop     rbx
0x18000d881  jmp     cs:__imp_CloseThreadpoolTimer
```
