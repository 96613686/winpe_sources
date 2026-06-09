# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180025368`
- end: `0x18002539c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001ad0c`
- `0x18002534c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025379`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180025379`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180025395`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025387`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180025387`

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
0x180025368  push    rbx
0x18002536a  sub     rsp, 20h
0x18002536e  xor     r9d, r9d; msWindowLength
0x180025371  xor     r8d, r8d; msPeriod
0x180025374  xor     edx, edx; pftDueTime
0x180025376  mov     rbx, rcx
0x180025379  call    cs:__imp_SetThreadpoolTimer
0x18002537f  mov     edx, 1; fCancelPendingCallbacks
0x180025384  mov     rcx, rbx; pti
0x180025387  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002538d  mov     rcx, rbx
0x180025390  add     rsp, 20h
0x180025394  pop     rbx
0x180025395  jmp     cs:__imp_CloseThreadpoolTimer
```
