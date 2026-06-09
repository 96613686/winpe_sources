# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800240b4`
- end: `0x1800240f9`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000f90c`
- `0x1800145e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800240c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800240c5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800240d9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800240d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800240ed`

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
0x1800240b4  push    rbx
0x1800240b6  sub     rsp, 20h
0x1800240ba  xor     r9d, r9d; msWindowLength
0x1800240bd  xor     r8d, r8d; msPeriod
0x1800240c0  xor     edx, edx; pftDueTime
0x1800240c2  mov     rbx, rcx
0x1800240c5  call    cs:__imp_SetThreadpoolTimer
0x1800240cc  nop     dword ptr [rax+rax+00h]
0x1800240d1  mov     edx, 1; fCancelPendingCallbacks
0x1800240d6  mov     rcx, rbx; pti
0x1800240d9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800240e0  nop     dword ptr [rax+rax+00h]
0x1800240e5  mov     rcx, rbx
0x1800240e8  add     rsp, 20h
0x1800240ec  pop     rbx
0x1800240ed  jmp     cs:__imp_CloseThreadpoolTimer
```
