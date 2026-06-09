# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180008440`
- end: `0x180008474`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180007ec0`
- `0x18000aa8c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000845f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000845f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000846d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008451`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008451`

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
0x180008440  push    rbx
0x180008442  sub     rsp, 20h
0x180008446  xor     r9d, r9d; msWindowLength
0x180008449  xor     r8d, r8d; msPeriod
0x18000844c  xor     edx, edx; pftDueTime
0x18000844e  mov     rbx, rcx
0x180008451  call    cs:__imp_SetThreadpoolTimer
0x180008457  mov     edx, 1; fCancelPendingCallbacks
0x18000845c  mov     rcx, rbx; pti
0x18000845f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180008465  mov     rcx, rbx
0x180008468  add     rsp, 20h
0x18000846c  pop     rbx
0x18000846d  jmp     cs:__imp_CloseThreadpoolTimer
```
