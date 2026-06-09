# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180051e20`
- end: `0x180051e54`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180035e98`
- `0x1800422a8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180051e31`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180051e31`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180051e4d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180051e3f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180051e3f`

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
0x180051e20  push    rbx
0x180051e22  sub     rsp, 20h
0x180051e26  xor     r9d, r9d; msWindowLength
0x180051e29  xor     r8d, r8d; msPeriod
0x180051e2c  xor     edx, edx; pftDueTime
0x180051e2e  mov     rbx, rcx
0x180051e31  call    cs:__imp_SetThreadpoolTimer
0x180051e37  mov     edx, 1; fCancelPendingCallbacks
0x180051e3c  mov     rcx, rbx; pti
0x180051e3f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180051e45  mov     rcx, rbx
0x180051e48  add     rsp, 20h
0x180051e4c  pop     rbx
0x180051e4d  jmp     cs:__imp_CloseThreadpoolTimer
```
