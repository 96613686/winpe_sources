# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140007f50`
- end: `0x140007f84`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140004330`
- `0x140004734`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007f61`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140007f61`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140007f7d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140007f6f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140007f6f`

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
0x140007f50  push    rbx
0x140007f52  sub     rsp, 20h
0x140007f56  xor     r9d, r9d; msWindowLength
0x140007f59  xor     r8d, r8d; msPeriod
0x140007f5c  xor     edx, edx; pftDueTime
0x140007f5e  mov     rbx, rcx
0x140007f61  call    cs:__imp_SetThreadpoolTimer
0x140007f67  mov     edx, 1; fCancelPendingCallbacks
0x140007f6c  mov     rcx, rbx; pti
0x140007f6f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140007f75  mov     rcx, rbx
0x140007f78  add     rsp, 20h
0x140007f7c  pop     rbx
0x140007f7d  jmp     cs:__imp_CloseThreadpoolTimer
```
