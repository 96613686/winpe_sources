# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000f4b0`
- end: `0x18000f4e4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000eac8`
- `0x180013fdc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f4c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f4c1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f4dd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f4cf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f4cf`

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
0x18000f4b0  push    rbx
0x18000f4b2  sub     rsp, 20h
0x18000f4b6  xor     r9d, r9d; msWindowLength
0x18000f4b9  xor     r8d, r8d; msPeriod
0x18000f4bc  xor     edx, edx; pftDueTime
0x18000f4be  mov     rbx, rcx
0x18000f4c1  call    cs:__imp_SetThreadpoolTimer
0x18000f4c7  mov     edx, 1; fCancelPendingCallbacks
0x18000f4cc  mov     rcx, rbx; pti
0x18000f4cf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f4d5  mov     rcx, rbx
0x18000f4d8  add     rsp, 20h
0x18000f4dc  pop     rbx
0x18000f4dd  jmp     cs:__imp_CloseThreadpoolTimer
```
