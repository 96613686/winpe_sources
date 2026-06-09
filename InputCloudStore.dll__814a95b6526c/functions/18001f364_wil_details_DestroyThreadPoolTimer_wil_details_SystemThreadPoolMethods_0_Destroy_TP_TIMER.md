# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001f364`
- end: `0x18001f398`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001b41c`
- `0x1800251ac`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f375`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001f375`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f383`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001f383`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001f391`

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
0x18001f364  push    rbx
0x18001f366  sub     rsp, 20h
0x18001f36a  xor     r9d, r9d; msWindowLength
0x18001f36d  xor     r8d, r8d; msPeriod
0x18001f370  xor     edx, edx; pftDueTime
0x18001f372  mov     rbx, rcx
0x18001f375  call    cs:__imp_SetThreadpoolTimer
0x18001f37b  mov     edx, 1; fCancelPendingCallbacks
0x18001f380  mov     rcx, rbx; pti
0x18001f383  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001f389  mov     rcx, rbx
0x18001f38c  add     rsp, 20h
0x18001f390  pop     rbx
0x18001f391  jmp     cs:__imp_CloseThreadpoolTimer
```
