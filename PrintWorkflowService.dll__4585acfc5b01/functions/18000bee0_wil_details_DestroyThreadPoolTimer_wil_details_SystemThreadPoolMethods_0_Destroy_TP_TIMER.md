# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000bee0`
- end: `0x18000bf14`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000a0b4`
- `0x180013f58`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000bf0d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000beff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000beff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bef1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bef1`

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
0x18000bee0  push    rbx
0x18000bee2  sub     rsp, 20h
0x18000bee6  xor     r9d, r9d; msWindowLength
0x18000bee9  xor     r8d, r8d; msPeriod
0x18000beec  xor     edx, edx; pftDueTime
0x18000beee  mov     rbx, rcx
0x18000bef1  call    cs:__imp_SetThreadpoolTimer
0x18000bef7  mov     edx, 1; fCancelPendingCallbacks
0x18000befc  mov     rcx, rbx; pti
0x18000beff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000bf05  mov     rcx, rbx
0x18000bf08  add     rsp, 20h
0x18000bf0c  pop     rbx
0x18000bf0d  jmp     cs:__imp_CloseThreadpoolTimer
```
