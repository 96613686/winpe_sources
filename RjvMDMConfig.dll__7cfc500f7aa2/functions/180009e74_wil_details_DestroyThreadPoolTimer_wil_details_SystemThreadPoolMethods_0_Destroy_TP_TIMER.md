# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180009e74`
- end: `0x180009eb9`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180007678`
- `0x180011884`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009e85`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009e85`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180009ead`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009e99`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009e99`

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
0x180009e74  push    rbx
0x180009e76  sub     rsp, 20h
0x180009e7a  xor     r9d, r9d; msWindowLength
0x180009e7d  xor     r8d, r8d; msPeriod
0x180009e80  xor     edx, edx; pftDueTime
0x180009e82  mov     rbx, rcx
0x180009e85  call    cs:__imp_SetThreadpoolTimer
0x180009e8c  nop     dword ptr [rax+rax+00h]
0x180009e91  mov     edx, 1; fCancelPendingCallbacks
0x180009e96  mov     rcx, rbx; pti
0x180009e99  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009ea0  nop     dword ptr [rax+rax+00h]
0x180009ea5  mov     rcx, rbx
0x180009ea8  add     rsp, 20h
0x180009eac  pop     rbx
0x180009ead  jmp     cs:__imp_CloseThreadpoolTimer
```
