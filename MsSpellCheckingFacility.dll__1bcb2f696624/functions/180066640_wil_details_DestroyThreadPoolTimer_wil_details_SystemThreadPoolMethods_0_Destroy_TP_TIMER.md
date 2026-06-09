# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180066640`
- end: `0x180066674`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x180044b80`
- `0x180044c0c`
- `0x180044c28`
- `0x1800bf430`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006665f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006665f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006666d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180066651`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180066651`

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
0x180066640  push    rbx
0x180066642  sub     rsp, 20h
0x180066646  xor     r9d, r9d; msWindowLength
0x180066649  xor     r8d, r8d; msPeriod
0x18006664c  xor     edx, edx; pftDueTime
0x18006664e  mov     rbx, rcx
0x180066651  call    cs:__imp_SetThreadpoolTimer
0x180066657  mov     edx, 1; fCancelPendingCallbacks
0x18006665c  mov     rcx, rbx; pti
0x18006665f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180066665  mov     rcx, rbx
0x180066668  add     rsp, 20h
0x18006666c  pop     rbx
0x18006666d  jmp     cs:__imp_CloseThreadpoolTimer
```
