# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000bb18`
- end: `0x18000bb4c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000389c`
- `0x1800038ec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000bb45`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bb29`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bb29`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bb37`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bb37`

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
0x18000bb18  push    rbx
0x18000bb1a  sub     rsp, 20h
0x18000bb1e  xor     r9d, r9d; msWindowLength
0x18000bb21  xor     r8d, r8d; msPeriod
0x18000bb24  xor     edx, edx; pftDueTime
0x18000bb26  mov     rbx, rcx
0x18000bb29  call    cs:__imp_SetThreadpoolTimer
0x18000bb2f  mov     edx, 1; fCancelPendingCallbacks
0x18000bb34  mov     rcx, rbx; pti
0x18000bb37  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000bb3d  mov     rcx, rbx
0x18000bb40  add     rsp, 20h
0x18000bb44  pop     rbx
0x18000bb45  jmp     cs:__imp_CloseThreadpoolTimer
```
