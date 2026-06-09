# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000aac0`
- end: `0x18000aaf4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180009ae4`
- `0x18000ff8c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000aaed`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000aadf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000aadf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aad1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aad1`

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
0x18000aac0  push    rbx
0x18000aac2  sub     rsp, 20h
0x18000aac6  xor     r9d, r9d; msWindowLength
0x18000aac9  xor     r8d, r8d; msPeriod
0x18000aacc  xor     edx, edx; pftDueTime
0x18000aace  mov     rbx, rcx
0x18000aad1  call    cs:__imp_SetThreadpoolTimer
0x18000aad7  mov     edx, 1; fCancelPendingCallbacks
0x18000aadc  mov     rcx, rbx; pti
0x18000aadf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000aae5  mov     rcx, rbx
0x18000aae8  add     rsp, 20h
0x18000aaec  pop     rbx
0x18000aaed  jmp     cs:__imp_CloseThreadpoolTimer
```
