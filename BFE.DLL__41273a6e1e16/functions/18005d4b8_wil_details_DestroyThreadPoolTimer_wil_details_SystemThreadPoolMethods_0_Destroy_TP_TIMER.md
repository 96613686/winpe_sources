# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18005d4b8`
- end: `0x18005d4fd`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180056d10`
- `0x180056d6c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005d4f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005d4c9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005d4c9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005d4dd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005d4dd`

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
0x18005d4b8  push    rbx
0x18005d4ba  sub     rsp, 20h
0x18005d4be  xor     r9d, r9d; msWindowLength
0x18005d4c1  xor     r8d, r8d; msPeriod
0x18005d4c4  xor     edx, edx; pftDueTime
0x18005d4c6  mov     rbx, rcx
0x18005d4c9  call    cs:__imp_SetThreadpoolTimer
0x18005d4d0  nop     dword ptr [rax+rax+00h]
0x18005d4d5  mov     edx, 1; fCancelPendingCallbacks
0x18005d4da  mov     rcx, rbx; pti
0x18005d4dd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005d4e4  nop     dword ptr [rax+rax+00h]
0x18005d4e9  mov     rcx, rbx
0x18005d4ec  add     rsp, 20h
0x18005d4f0  pop     rbx
0x18005d4f1  jmp     cs:__imp_CloseThreadpoolTimer
```
