# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180012794`
- end: `0x1800127c8`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180011198`
- `0x18001afac`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800127a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800127a5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800127b3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800127b3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800127c1`

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
0x180012794  push    rbx
0x180012796  sub     rsp, 20h
0x18001279a  xor     r9d, r9d; msWindowLength
0x18001279d  xor     r8d, r8d; msPeriod
0x1800127a0  xor     edx, edx; pftDueTime
0x1800127a2  mov     rbx, rcx
0x1800127a5  call    cs:__imp_SetThreadpoolTimer
0x1800127ab  mov     edx, 1; fCancelPendingCallbacks
0x1800127b0  mov     rcx, rbx; pti
0x1800127b3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800127b9  mov     rcx, rbx
0x1800127bc  add     rsp, 20h
0x1800127c0  pop     rbx
0x1800127c1  jmp     cs:__imp_CloseThreadpoolTimer
```
