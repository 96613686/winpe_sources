# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180078994`
- end: `0x1800789d9`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180053e50`
- `0x180054024`
- `0x180065eec`
- `0x18006d060`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800789b9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800789b9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800789cd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800789a5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800789a5`

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
0x180078994  push    rbx
0x180078996  sub     rsp, 20h
0x18007899a  xor     r9d, r9d; msWindowLength
0x18007899d  xor     r8d, r8d; msPeriod
0x1800789a0  xor     edx, edx; pftDueTime
0x1800789a2  mov     rbx, rcx
0x1800789a5  call    cs:__imp_SetThreadpoolTimer
0x1800789ac  nop     dword ptr [rax+rax+00h]
0x1800789b1  mov     edx, 1; fCancelPendingCallbacks
0x1800789b6  mov     rcx, rbx; pti
0x1800789b9  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800789c0  nop     dword ptr [rax+rax+00h]
0x1800789c5  mov     rcx, rbx
0x1800789c8  add     rsp, 20h
0x1800789cc  pop     rbx
0x1800789cd  jmp     cs:__imp_CloseThreadpoolTimer
```
