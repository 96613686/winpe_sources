# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000aea8`
- end: `0x18000aedc`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180009f1c`
- `0x180012cb4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aeb9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000aeb9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000aec7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000aec7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000aed5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(PTP_TIMER pti)
{
  SetThreadpoolTimer(pti, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(pti, 1);
  CloseThreadpoolTimer(pti);
}

```

## disassembly

```asm
0x18000aea8  push    rbx
0x18000aeaa  sub     rsp, 20h
0x18000aeae  xor     r9d, r9d; msWindowLength
0x18000aeb1  xor     r8d, r8d; msPeriod
0x18000aeb4  xor     edx, edx; pftDueTime
0x18000aeb6  mov     rbx, rcx
0x18000aeb9  call    cs:__imp_SetThreadpoolTimer
0x18000aebf  mov     edx, 1; fCancelPendingCallbacks
0x18000aec4  mov     rcx, rbx; pti
0x18000aec7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000aecd  mov     rcx, rbx
0x18000aed0  add     rsp, 20h
0x18000aed4  pop     rbx
0x18000aed5  jmp     cs:__imp_CloseThreadpoolTimer
```
