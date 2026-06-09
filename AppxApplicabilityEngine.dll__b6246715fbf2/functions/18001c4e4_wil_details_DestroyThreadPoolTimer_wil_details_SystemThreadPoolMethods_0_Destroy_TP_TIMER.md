# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001c4e4`
- end: `0x18001c518`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001c050`
- `0x18001e15c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001c511`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c503`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001c503`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c4f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001c4f5`

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
0x18001c4e4  push    rbx
0x18001c4e6  sub     rsp, 20h
0x18001c4ea  xor     r9d, r9d; msWindowLength
0x18001c4ed  xor     r8d, r8d; msPeriod
0x18001c4f0  xor     edx, edx; pftDueTime
0x18001c4f2  mov     rbx, rcx
0x18001c4f5  call    cs:__imp_SetThreadpoolTimer
0x18001c4fb  mov     edx, 1; fCancelPendingCallbacks
0x18001c500  mov     rcx, rbx; pti
0x18001c503  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001c509  mov     rcx, rbx
0x18001c50c  add     rsp, 20h
0x18001c510  pop     rbx
0x18001c511  jmp     cs:__imp_CloseThreadpoolTimer
```
