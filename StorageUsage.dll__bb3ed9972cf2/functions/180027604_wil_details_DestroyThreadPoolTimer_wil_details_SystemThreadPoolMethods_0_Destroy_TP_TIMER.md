# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180027604`
- end: `0x180027638`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180026fd0`
- `0x18002a6b8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180027631`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180027623`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180027623`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180027615`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180027615`

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
0x180027604  push    rbx
0x180027606  sub     rsp, 20h
0x18002760a  xor     r9d, r9d; msWindowLength
0x18002760d  xor     r8d, r8d; msPeriod
0x180027610  xor     edx, edx; pftDueTime
0x180027612  mov     rbx, rcx
0x180027615  call    cs:__imp_SetThreadpoolTimer
0x18002761b  mov     edx, 1; fCancelPendingCallbacks
0x180027620  mov     rcx, rbx; pti
0x180027623  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180027629  mov     rcx, rbx
0x18002762c  add     rsp, 20h
0x180027630  pop     rbx
0x180027631  jmp     cs:__imp_CloseThreadpoolTimer
```
