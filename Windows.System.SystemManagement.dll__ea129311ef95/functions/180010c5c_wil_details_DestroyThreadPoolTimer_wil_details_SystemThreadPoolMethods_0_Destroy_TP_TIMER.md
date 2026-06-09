# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180010c5c`
- end: `0x180010c90`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180010600`
- `0x180012e64`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010c6d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010c6d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010c7b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010c7b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180010c89`

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
0x180010c5c  push    rbx
0x180010c5e  sub     rsp, 20h
0x180010c62  xor     r9d, r9d; msWindowLength
0x180010c65  xor     r8d, r8d; msPeriod
0x180010c68  xor     edx, edx; pftDueTime
0x180010c6a  mov     rbx, rcx
0x180010c6d  call    cs:__imp_SetThreadpoolTimer
0x180010c73  mov     edx, 1; fCancelPendingCallbacks
0x180010c78  mov     rcx, rbx; pti
0x180010c7b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180010c81  mov     rcx, rbx
0x180010c84  add     rsp, 20h
0x180010c88  pop     rbx
0x180010c89  jmp     cs:__imp_CloseThreadpoolTimer
```
