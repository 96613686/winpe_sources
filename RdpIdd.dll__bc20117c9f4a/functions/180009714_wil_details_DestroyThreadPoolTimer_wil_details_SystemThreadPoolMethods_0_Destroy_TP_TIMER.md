# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180009714`
- end: `0x180009759`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180008fe4`
- `0x18000c300`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009739`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009739`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009725`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009725`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000974d`

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
0x180009714  push    rbx
0x180009716  sub     rsp, 20h
0x18000971a  xor     r9d, r9d; msWindowLength
0x18000971d  xor     r8d, r8d; msPeriod
0x180009720  xor     edx, edx; pftDueTime
0x180009722  mov     rbx, rcx
0x180009725  call    cs:__imp_SetThreadpoolTimer
0x18000972c  nop     dword ptr [rax+rax+00h]
0x180009731  mov     edx, 1; fCancelPendingCallbacks
0x180009736  mov     rcx, rbx; pti
0x180009739  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009740  nop     dword ptr [rax+rax+00h]
0x180009745  mov     rcx, rbx
0x180009748  add     rsp, 20h
0x18000974c  pop     rbx
0x18000974d  jmp     cs:__imp_CloseThreadpoolTimer
```
