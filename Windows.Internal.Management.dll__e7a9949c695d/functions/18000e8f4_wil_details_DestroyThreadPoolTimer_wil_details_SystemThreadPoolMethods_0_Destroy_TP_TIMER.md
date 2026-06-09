# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000e8f4`
- end: `0x18000e928`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d7fc`
- `0x180012d38`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000e921`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e913`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000e913`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e905`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000e905`

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
0x18000e8f4  push    rbx
0x18000e8f6  sub     rsp, 20h
0x18000e8fa  xor     r9d, r9d; msWindowLength
0x18000e8fd  xor     r8d, r8d; msPeriod
0x18000e900  xor     edx, edx; pftDueTime
0x18000e902  mov     rbx, rcx
0x18000e905  call    cs:__imp_SetThreadpoolTimer
0x18000e90b  mov     edx, 1; fCancelPendingCallbacks
0x18000e910  mov     rcx, rbx; pti
0x18000e913  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000e919  mov     rcx, rbx
0x18000e91c  add     rsp, 20h
0x18000e920  pop     rbx
0x18000e921  jmp     cs:__imp_CloseThreadpoolTimer
```
