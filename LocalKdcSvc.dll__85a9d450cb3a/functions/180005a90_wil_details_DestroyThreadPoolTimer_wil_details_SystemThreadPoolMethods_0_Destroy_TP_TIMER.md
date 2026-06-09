# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180005a90`
- end: `0x180005ac4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800050ec`
- `0x180009a74`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005abd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005aaf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005aaf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005aa1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005aa1`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x180005a90  push    rbx
0x180005a92  sub     rsp, 20h
0x180005a96  xor     r9d, r9d; msWindowLength
0x180005a99  xor     r8d, r8d; msPeriod
0x180005a9c  xor     edx, edx; pftDueTime
0x180005a9e  mov     rbx, rcx
0x180005aa1  call    cs:__imp_SetThreadpoolTimer
0x180005aa7  mov     edx, 1; fCancelPendingCallbacks
0x180005aac  mov     rcx, rbx; pti
0x180005aaf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005ab5  mov     rcx, rbx
0x180005ab8  add     rsp, 20h
0x180005abc  pop     rbx
0x180005abd  jmp     cs:__imp_CloseThreadpoolTimer
```
