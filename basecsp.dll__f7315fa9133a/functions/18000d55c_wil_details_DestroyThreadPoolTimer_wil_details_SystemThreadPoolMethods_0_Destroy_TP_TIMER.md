# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000d55c`
- end: `0x18000d590`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000bcc0`
- `0x180018f10`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d589`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d57b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d57b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d56d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d56d`

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
0x18000d55c  push    rbx
0x18000d55e  sub     rsp, 20h
0x18000d562  xor     r9d, r9d; msWindowLength
0x18000d565  xor     r8d, r8d; msPeriod
0x18000d568  xor     edx, edx; pftDueTime
0x18000d56a  mov     rbx, rcx
0x18000d56d  call    cs:__imp_SetThreadpoolTimer
0x18000d573  mov     edx, 1; fCancelPendingCallbacks
0x18000d578  mov     rcx, rbx; pti
0x18000d57b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d581  mov     rcx, rbx
0x18000d584  add     rsp, 20h
0x18000d588  pop     rbx
0x18000d589  jmp     cs:__imp_CloseThreadpoolTimer
```
