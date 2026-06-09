# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000f9d4`
- end: `0x18000fa08`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f4a0`
- `0x18001238c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f9e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f9e5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f9f3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f9f3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000fa01`

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
0x18000f9d4  push    rbx
0x18000f9d6  sub     rsp, 20h
0x18000f9da  xor     r9d, r9d; msWindowLength
0x18000f9dd  xor     r8d, r8d; msPeriod
0x18000f9e0  xor     edx, edx; pftDueTime
0x18000f9e2  mov     rbx, rcx
0x18000f9e5  call    cs:__imp_SetThreadpoolTimer
0x18000f9eb  mov     edx, 1; fCancelPendingCallbacks
0x18000f9f0  mov     rcx, rbx; pti
0x18000f9f3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f9f9  mov     rcx, rbx
0x18000f9fc  add     rsp, 20h
0x18000fa00  pop     rbx
0x18000fa01  jmp     cs:__imp_CloseThreadpoolTimer
```
