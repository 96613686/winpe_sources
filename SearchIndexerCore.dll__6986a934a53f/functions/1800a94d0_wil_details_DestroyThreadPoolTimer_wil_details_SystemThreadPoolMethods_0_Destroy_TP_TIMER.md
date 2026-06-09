# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800a94d0`
- end: `0x1800a9504`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18006978c`
- `0x1800697e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a94fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800a94ef`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800a94ef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a94e1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a94e1`

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
0x1800a94d0  push    rbx
0x1800a94d2  sub     rsp, 20h
0x1800a94d6  xor     r9d, r9d; msWindowLength
0x1800a94d9  xor     r8d, r8d; msPeriod
0x1800a94dc  xor     edx, edx; pftDueTime
0x1800a94de  mov     rbx, rcx
0x1800a94e1  call    cs:__imp_SetThreadpoolTimer
0x1800a94e7  mov     edx, 1; fCancelPendingCallbacks
0x1800a94ec  mov     rcx, rbx; pti
0x1800a94ef  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800a94f5  mov     rcx, rbx
0x1800a94f8  add     rsp, 20h
0x1800a94fc  pop     rbx
0x1800a94fd  jmp     cs:__imp_CloseThreadpoolTimer
```
