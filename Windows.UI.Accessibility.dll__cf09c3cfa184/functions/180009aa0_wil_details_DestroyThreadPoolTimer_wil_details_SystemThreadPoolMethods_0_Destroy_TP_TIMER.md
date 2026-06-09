# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180009aa0`
- end: `0x180009ad4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180008fe8`
- `0x18000d2b4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009abf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009abf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009ab1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009ab1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009acd`

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
0x180009aa0  push    rbx
0x180009aa2  sub     rsp, 20h
0x180009aa6  xor     r9d, r9d; msWindowLength
0x180009aa9  xor     r8d, r8d; msPeriod
0x180009aac  xor     edx, edx; pftDueTime
0x180009aae  mov     rbx, rcx
0x180009ab1  call    cs:__imp_SetThreadpoolTimer
0x180009ab7  mov     edx, 1; fCancelPendingCallbacks
0x180009abc  mov     rcx, rbx; pti
0x180009abf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009ac5  mov     rcx, rbx
0x180009ac8  add     rsp, 20h
0x180009acc  pop     rbx
0x180009acd  jmp     cs:__imp_CloseThreadpoolTimer
```
