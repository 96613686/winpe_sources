# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180006114`
- end: `0x180006159`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000558c`
- `0x18000b03c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006139`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006139`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000614d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006125`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006125`

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
0x180006114  push    rbx
0x180006116  sub     rsp, 20h
0x18000611a  xor     r9d, r9d; msWindowLength
0x18000611d  xor     r8d, r8d; msPeriod
0x180006120  xor     edx, edx; pftDueTime
0x180006122  mov     rbx, rcx
0x180006125  call    cs:__imp_SetThreadpoolTimer
0x18000612c  nop     dword ptr [rax+rax+00h]
0x180006131  mov     edx, 1; fCancelPendingCallbacks
0x180006136  mov     rcx, rbx; pti
0x180006139  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006140  nop     dword ptr [rax+rax+00h]
0x180006145  mov     rcx, rbx
0x180006148  add     rsp, 20h
0x18000614c  pop     rbx
0x18000614d  jmp     cs:__imp_CloseThreadpoolTimer
```
