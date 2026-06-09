# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800054d4`
- end: `0x180005508`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000464c`
- `0x18000b338`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180005501`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800054f3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800054f3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800054e5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800054e5`

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
0x1800054d4  push    rbx
0x1800054d6  sub     rsp, 20h
0x1800054da  xor     r9d, r9d; msWindowLength
0x1800054dd  xor     r8d, r8d; msPeriod
0x1800054e0  xor     edx, edx; pftDueTime
0x1800054e2  mov     rbx, rcx
0x1800054e5  call    cs:__imp_SetThreadpoolTimer
0x1800054eb  mov     edx, 1; fCancelPendingCallbacks
0x1800054f0  mov     rcx, rbx; pti
0x1800054f3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800054f9  mov     rcx, rbx
0x1800054fc  add     rsp, 20h
0x180005500  pop     rbx
0x180005501  jmp     cs:__imp_CloseThreadpoolTimer
```
