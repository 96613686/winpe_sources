# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180026f0c`
- end: `0x180026f51`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001b110`
- `0x180026eec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026f1d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026f1d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180026f45`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180026f31`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180026f31`

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
0x180026f0c  push    rbx
0x180026f0e  sub     rsp, 20h
0x180026f12  xor     r9d, r9d; msWindowLength
0x180026f15  xor     r8d, r8d; msPeriod
0x180026f18  xor     edx, edx; pftDueTime
0x180026f1a  mov     rbx, rcx
0x180026f1d  call    cs:__imp_SetThreadpoolTimer
0x180026f24  nop     dword ptr [rax+rax+00h]
0x180026f29  mov     edx, 1; fCancelPendingCallbacks
0x180026f2e  mov     rcx, rbx; pti
0x180026f31  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180026f38  nop     dword ptr [rax+rax+00h]
0x180026f3d  mov     rcx, rbx
0x180026f40  add     rsp, 20h
0x180026f44  pop     rbx
0x180026f45  jmp     cs:__imp_CloseThreadpoolTimer
```
