# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1400038f0`
- end: `0x140003924`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140003014`
- `0x1400074b4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003901`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140003901`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000391d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000390f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000390f`

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
0x1400038f0  push    rbx
0x1400038f2  sub     rsp, 20h
0x1400038f6  xor     r9d, r9d; msWindowLength
0x1400038f9  xor     r8d, r8d; msPeriod
0x1400038fc  xor     edx, edx; pftDueTime
0x1400038fe  mov     rbx, rcx
0x140003901  call    cs:__imp_SetThreadpoolTimer
0x140003907  mov     edx, 1; fCancelPendingCallbacks
0x14000390c  mov     rcx, rbx; pti
0x14000390f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140003915  mov     rcx, rbx
0x140003918  add     rsp, 20h
0x14000391c  pop     rbx
0x14000391d  jmp     cs:__imp_CloseThreadpoolTimer
```
