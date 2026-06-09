# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18005cc8c`
- end: `0x18005ccc3`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `55`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18005b5b8`
- `0x1800640c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005cc9d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005cc9d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005ccac`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005ccac`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005ccb6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005ccb6`

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
0x18005cc8c  push    rbx
0x18005cc8e  sub     rsp, 20h
0x18005cc92  mov     rbx, rcx
0x18005cc95  xor     r9d, r9d; msWindowLength
0x18005cc98  xor     r8d, r8d; msPeriod
0x18005cc9b  xor     edx, edx; pftDueTime
0x18005cc9d  call    cs:__imp_SetThreadpoolTimer
0x18005cca3  nop
0x18005cca4  mov     edx, 1; fCancelPendingCallbacks
0x18005cca9  mov     rcx, rbx; pti
0x18005ccac  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005ccb2  nop
0x18005ccb3  mov     rcx, rbx; pti
0x18005ccb6  call    cs:__imp_CloseThreadpoolTimer
0x18005ccbc  nop
0x18005ccbd  add     rsp, 20h
0x18005ccc1  pop     rbx
0x18005ccc2  retn
```
