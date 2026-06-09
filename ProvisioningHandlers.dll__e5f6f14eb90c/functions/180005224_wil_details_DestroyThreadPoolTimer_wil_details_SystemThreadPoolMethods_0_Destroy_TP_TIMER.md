# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180005224`
- end: `0x180005269`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800046d4`
- `0x18000a5c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005235`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005235`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005249`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180005249`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000525d`

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
0x180005224  push    rbx
0x180005226  sub     rsp, 20h
0x18000522a  xor     r9d, r9d; msWindowLength
0x18000522d  xor     r8d, r8d; msPeriod
0x180005230  xor     edx, edx; pftDueTime
0x180005232  mov     rbx, rcx
0x180005235  call    cs:__imp_SetThreadpoolTimer
0x18000523c  nop     dword ptr [rax+rax+00h]
0x180005241  mov     edx, 1; fCancelPendingCallbacks
0x180005246  mov     rcx, rbx; pti
0x180005249  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005250  nop     dword ptr [rax+rax+00h]
0x180005255  mov     rcx, rbx
0x180005258  add     rsp, 20h
0x18000525c  pop     rbx
0x18000525d  jmp     cs:__imp_CloseThreadpoolTimer
```
