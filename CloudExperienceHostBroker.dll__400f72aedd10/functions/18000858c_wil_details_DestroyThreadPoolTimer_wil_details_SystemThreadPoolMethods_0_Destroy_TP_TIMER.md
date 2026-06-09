# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000858c`
- end: `0x1800085c0`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1800051b0`
- `0x180005bb0`
- `0x180008508`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800085ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800085ab`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800085b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000859d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000859d`

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
0x18000858c  push    rbx
0x18000858e  sub     rsp, 20h
0x180008592  xor     r9d, r9d; msWindowLength
0x180008595  xor     r8d, r8d; msPeriod
0x180008598  xor     edx, edx; pftDueTime
0x18000859a  mov     rbx, rcx
0x18000859d  call    cs:__imp_SetThreadpoolTimer
0x1800085a3  mov     edx, 1; fCancelPendingCallbacks
0x1800085a8  mov     rcx, rbx; pti
0x1800085ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800085b1  mov     rcx, rbx
0x1800085b4  add     rsp, 20h
0x1800085b8  pop     rbx
0x1800085b9  jmp     cs:__imp_CloseThreadpoolTimer
```
