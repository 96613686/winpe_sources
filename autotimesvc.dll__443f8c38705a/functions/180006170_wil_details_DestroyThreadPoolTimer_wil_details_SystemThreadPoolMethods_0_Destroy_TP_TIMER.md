# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180006170`
- end: `0x1800061a4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180005860`
- `0x18000aa38`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000618f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000618f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006181`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006181`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000619d`

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
0x180006170  push    rbx
0x180006172  sub     rsp, 20h
0x180006176  xor     r9d, r9d; msWindowLength
0x180006179  xor     r8d, r8d; msPeriod
0x18000617c  xor     edx, edx; pftDueTime
0x18000617e  mov     rbx, rcx
0x180006181  call    cs:__imp_SetThreadpoolTimer
0x180006187  mov     edx, 1; fCancelPendingCallbacks
0x18000618c  mov     rcx, rbx; pti
0x18000618f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006195  mov     rcx, rbx
0x180006198  add     rsp, 20h
0x18000619c  pop     rbx
0x18000619d  jmp     cs:__imp_CloseThreadpoolTimer
```
