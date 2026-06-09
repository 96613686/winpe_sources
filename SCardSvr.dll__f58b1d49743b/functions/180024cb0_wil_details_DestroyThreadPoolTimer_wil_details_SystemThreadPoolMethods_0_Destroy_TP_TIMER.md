# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180024cb0`
- end: `0x180024ce4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180016ee4`
- `0x180016f34`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180024cc1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180024cc1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180024cdd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180024ccf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180024ccf`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x180024cb0  push    rbx
0x180024cb2  sub     rsp, 20h
0x180024cb6  xor     r9d, r9d; msWindowLength
0x180024cb9  xor     r8d, r8d; msPeriod
0x180024cbc  xor     edx, edx; pftDueTime
0x180024cbe  mov     rbx, rcx
0x180024cc1  call    cs:__imp_SetThreadpoolTimer
0x180024cc7  mov     edx, 1; fCancelPendingCallbacks
0x180024ccc  mov     rcx, rbx; pti
0x180024ccf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180024cd5  mov     rcx, rbx
0x180024cd8  add     rsp, 20h
0x180024cdc  pop     rbx
0x180024cdd  jmp     cs:__imp_CloseThreadpoolTimer
```
