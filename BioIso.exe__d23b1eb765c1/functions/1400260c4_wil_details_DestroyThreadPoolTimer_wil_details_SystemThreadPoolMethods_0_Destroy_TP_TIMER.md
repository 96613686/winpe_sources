# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1400260c4`
- end: `0x140026109`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14000c69c`
- `0x14000dbc8`
- `0x140013918`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400260d5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400260d5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400260fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400260e9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400260e9`

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
0x1400260c4  push    rbx
0x1400260c6  sub     rsp, 20h
0x1400260ca  xor     r9d, r9d; msWindowLength
0x1400260cd  xor     r8d, r8d; msPeriod
0x1400260d0  xor     edx, edx; pftDueTime
0x1400260d2  mov     rbx, rcx
0x1400260d5  call    cs:__imp_SetThreadpoolTimer
0x1400260dc  nop     dword ptr [rax+rax+00h]
0x1400260e1  mov     edx, 1; fCancelPendingCallbacks
0x1400260e6  mov     rcx, rbx; pti
0x1400260e9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400260f0  nop     dword ptr [rax+rax+00h]
0x1400260f5  mov     rcx, rbx
0x1400260f8  add     rsp, 20h
0x1400260fc  pop     rbx
0x1400260fd  jmp     cs:__imp_CloseThreadpoolTimer
```
