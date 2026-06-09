# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180006058`
- end: `0x18000608c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800057a4`
- `0x18000bcfc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006085`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006077`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006077`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006069`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006069`

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
0x180006058  push    rbx
0x18000605a  sub     rsp, 20h
0x18000605e  xor     r9d, r9d; msWindowLength
0x180006061  xor     r8d, r8d; msPeriod
0x180006064  xor     edx, edx; pftDueTime
0x180006066  mov     rbx, rcx
0x180006069  call    cs:__imp_SetThreadpoolTimer
0x18000606f  mov     edx, 1; fCancelPendingCallbacks
0x180006074  mov     rcx, rbx; pti
0x180006077  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000607d  mov     rcx, rbx
0x180006080  add     rsp, 20h
0x180006084  pop     rbx
0x180006085  jmp     cs:__imp_CloseThreadpoolTimer
```
