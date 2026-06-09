# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140002a40`
- end: `0x140002a74`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1400016b0`
- `0x140001fe0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140002a51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140002a51`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140002a6d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140002a5f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140002a5f`

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
0x140002a40  push    rbx
0x140002a42  sub     rsp, 20h
0x140002a46  xor     r9d, r9d; msWindowLength
0x140002a49  xor     r8d, r8d; msPeriod
0x140002a4c  xor     edx, edx; pftDueTime
0x140002a4e  mov     rbx, rcx
0x140002a51  call    cs:__imp_SetThreadpoolTimer
0x140002a57  mov     edx, 1; fCancelPendingCallbacks
0x140002a5c  mov     rcx, rbx; pti
0x140002a5f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140002a65  mov     rcx, rbx
0x140002a68  add     rsp, 20h
0x140002a6c  pop     rbx
0x140002a6d  jmp     cs:__imp_CloseThreadpoolTimer
```
