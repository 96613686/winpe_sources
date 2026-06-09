# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x14000e984`
- end: `0x14000e9c9`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000dee8`
- `0x1400134ec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e9a9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000e9a9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000e9bd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e995`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000e995`

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
0x14000e984  push    rbx
0x14000e986  sub     rsp, 20h
0x14000e98a  xor     r9d, r9d; msWindowLength
0x14000e98d  xor     r8d, r8d; msPeriod
0x14000e990  xor     edx, edx; pftDueTime
0x14000e992  mov     rbx, rcx
0x14000e995  call    cs:__imp_SetThreadpoolTimer
0x14000e99c  nop     dword ptr [rax+rax+00h]
0x14000e9a1  mov     edx, 1; fCancelPendingCallbacks
0x14000e9a6  mov     rcx, rbx; pti
0x14000e9a9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000e9b0  nop     dword ptr [rax+rax+00h]
0x14000e9b5  mov     rcx, rbx
0x14000e9b8  add     rsp, 20h
0x14000e9bc  pop     rbx
0x14000e9bd  jmp     cs:__imp_CloseThreadpoolTimer
```
