# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000ac58`
- end: `0x18000ac8c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a604`
- `0x18000d014`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ac85`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ac77`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ac77`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ac69`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ac69`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x18000ac58  push    rbx
0x18000ac5a  sub     rsp, 20h
0x18000ac5e  xor     r9d, r9d; msWindowLength
0x18000ac61  xor     r8d, r8d; msPeriod
0x18000ac64  xor     edx, edx; pftDueTime
0x18000ac66  mov     rbx, rcx
0x18000ac69  call    cs:__imp_SetThreadpoolTimer
0x18000ac6f  mov     edx, 1; fCancelPendingCallbacks
0x18000ac74  mov     rcx, rbx; pti
0x18000ac77  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ac7d  mov     rcx, rbx
0x18000ac80  add     rsp, 20h
0x18000ac84  pop     rbx
0x18000ac85  jmp     cs:__imp_CloseThreadpoolTimer
```
