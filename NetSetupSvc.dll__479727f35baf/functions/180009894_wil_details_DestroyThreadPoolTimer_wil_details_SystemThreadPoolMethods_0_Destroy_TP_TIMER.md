# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180009894`
- end: `0x1800098c8`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180008ef8`
- `0x18000dc54`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800098b3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800098b3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800098a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800098a5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800098c1`

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
0x180009894  push    rbx
0x180009896  sub     rsp, 20h
0x18000989a  xor     r9d, r9d; msWindowLength
0x18000989d  xor     r8d, r8d; msPeriod
0x1800098a0  xor     edx, edx; pftDueTime
0x1800098a2  mov     rbx, rcx
0x1800098a5  call    cs:__imp_SetThreadpoolTimer
0x1800098ab  mov     edx, 1; fCancelPendingCallbacks
0x1800098b0  mov     rcx, rbx; pti
0x1800098b3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800098b9  mov     rcx, rbx
0x1800098bc  add     rsp, 20h
0x1800098c0  pop     rbx
0x1800098c1  jmp     cs:__imp_CloseThreadpoolTimer
```
