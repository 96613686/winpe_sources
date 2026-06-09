# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000ee68`
- end: `0x18000eead`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000dd04`
- `0x180013370`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000eea1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ee8d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ee8d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ee79`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ee79`

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
0x18000ee68  push    rbx
0x18000ee6a  sub     rsp, 20h
0x18000ee6e  xor     r9d, r9d; msWindowLength
0x18000ee71  xor     r8d, r8d; msPeriod
0x18000ee74  xor     edx, edx; pftDueTime
0x18000ee76  mov     rbx, rcx
0x18000ee79  call    cs:__imp_SetThreadpoolTimer
0x18000ee80  nop     dword ptr [rax+rax+00h]
0x18000ee85  mov     edx, 1; fCancelPendingCallbacks
0x18000ee8a  mov     rcx, rbx; pti
0x18000ee8d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ee94  nop     dword ptr [rax+rax+00h]
0x18000ee99  mov     rcx, rbx
0x18000ee9c  add     rsp, 20h
0x18000eea0  pop     rbx
0x18000eea1  jmp     cs:__imp_CloseThreadpoolTimer
```
