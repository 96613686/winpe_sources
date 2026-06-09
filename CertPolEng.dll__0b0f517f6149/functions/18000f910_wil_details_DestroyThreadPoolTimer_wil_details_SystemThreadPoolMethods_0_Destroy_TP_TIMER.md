# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000f910`
- end: `0x18000f944`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b4d0`
- `0x18000bb44`
- `0x18000c918`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000f93d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f92f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000f92f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f921`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000f921`

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
0x18000f910  push    rbx
0x18000f912  sub     rsp, 20h
0x18000f916  xor     r9d, r9d; msWindowLength
0x18000f919  xor     r8d, r8d; msPeriod
0x18000f91c  xor     edx, edx; pftDueTime
0x18000f91e  mov     rbx, rcx
0x18000f921  call    cs:__imp_SetThreadpoolTimer
0x18000f927  mov     edx, 1; fCancelPendingCallbacks
0x18000f92c  mov     rcx, rbx; pti
0x18000f92f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000f935  mov     rcx, rbx
0x18000f938  add     rsp, 20h
0x18000f93c  pop     rbx
0x18000f93d  jmp     cs:__imp_CloseThreadpoolTimer
```
