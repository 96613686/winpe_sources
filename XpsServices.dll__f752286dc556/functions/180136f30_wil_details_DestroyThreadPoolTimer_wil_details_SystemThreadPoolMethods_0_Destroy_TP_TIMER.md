# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180136f30`
- end: `0x180136f64`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800fa1b0`
- `0x1800fa200`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180136f5d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180136f4f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180136f4f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180136f41`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180136f41`

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
0x180136f30  push    rbx
0x180136f32  sub     rsp, 20h
0x180136f36  xor     r9d, r9d; msWindowLength
0x180136f39  xor     r8d, r8d; msPeriod
0x180136f3c  xor     edx, edx; pftDueTime
0x180136f3e  mov     rbx, rcx
0x180136f41  call    cs:__imp_SetThreadpoolTimer
0x180136f47  mov     edx, 1; fCancelPendingCallbacks
0x180136f4c  mov     rcx, rbx; pti
0x180136f4f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180136f55  mov     rcx, rbx
0x180136f58  add     rsp, 20h
0x180136f5c  pop     rbx
0x180136f5d  jmp     cs:__imp_CloseThreadpoolTimer
```
