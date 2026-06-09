# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180010b80`
- end: `0x180010bb4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d0e8`
- `0x18000d1c8`
- `0x18000db84`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010b91`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010b91`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010b9f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010b9f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010bad`

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
0x180010b80  push    rbx
0x180010b82  sub     rsp, 20h
0x180010b86  xor     r9d, r9d; msWindowLength
0x180010b89  xor     r8d, r8d; msPeriod
0x180010b8c  xor     edx, edx; pftDueTime
0x180010b8e  mov     rbx, rcx
0x180010b91  call    cs:__imp_SetThreadpoolTimer
0x180010b97  mov     edx, 1; fCancelPendingCallbacks
0x180010b9c  mov     rcx, rbx; pti
0x180010b9f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010ba5  mov     rcx, rbx
0x180010ba8  add     rsp, 20h
0x180010bac  pop     rbx
0x180010bad  jmp     cs:__imp_CloseThreadpoolTimer
```
