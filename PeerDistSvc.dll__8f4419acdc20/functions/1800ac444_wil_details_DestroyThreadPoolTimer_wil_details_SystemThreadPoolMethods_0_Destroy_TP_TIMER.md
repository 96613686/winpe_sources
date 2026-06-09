# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800ac444`
- end: `0x1800ac478`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800a7c84`
- `0x1800c13b8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800ac471`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ac463`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ac463`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ac455`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ac455`

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
0x1800ac444  push    rbx
0x1800ac446  sub     rsp, 20h
0x1800ac44a  xor     r9d, r9d; msWindowLength
0x1800ac44d  xor     r8d, r8d; msPeriod
0x1800ac450  xor     edx, edx; pftDueTime
0x1800ac452  mov     rbx, rcx
0x1800ac455  call    cs:__imp_SetThreadpoolTimer
0x1800ac45b  mov     edx, 1; fCancelPendingCallbacks
0x1800ac460  mov     rcx, rbx; pti
0x1800ac463  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800ac469  mov     rcx, rbx
0x1800ac46c  add     rsp, 20h
0x1800ac470  pop     rbx
0x1800ac471  jmp     cs:__imp_CloseThreadpoolTimer
```
