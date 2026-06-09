# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180011608`
- end: `0x18001163c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004d04`
- `0x180004d58`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011619`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011619`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011627`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011627`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011635`

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
0x180011608  push    rbx
0x18001160a  sub     rsp, 20h
0x18001160e  xor     r9d, r9d; msWindowLength
0x180011611  xor     r8d, r8d; msPeriod
0x180011614  xor     edx, edx; pftDueTime
0x180011616  mov     rbx, rcx
0x180011619  call    cs:__imp_SetThreadpoolTimer
0x18001161f  mov     edx, 1; fCancelPendingCallbacks
0x180011624  mov     rcx, rbx; pti
0x180011627  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001162d  mov     rcx, rbx
0x180011630  add     rsp, 20h
0x180011634  pop     rbx
0x180011635  jmp     cs:__imp_CloseThreadpoolTimer
```
