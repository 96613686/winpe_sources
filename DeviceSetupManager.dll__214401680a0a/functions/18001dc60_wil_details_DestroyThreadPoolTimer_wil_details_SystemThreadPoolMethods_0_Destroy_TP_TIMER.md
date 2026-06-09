# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001dc60`
- end: `0x18001dc94`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180015590`
- `0x1800155e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001dc8d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001dc7f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001dc7f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001dc71`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001dc71`

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
0x18001dc60  push    rbx
0x18001dc62  sub     rsp, 20h
0x18001dc66  xor     r9d, r9d; msWindowLength
0x18001dc69  xor     r8d, r8d; msPeriod
0x18001dc6c  xor     edx, edx; pftDueTime
0x18001dc6e  mov     rbx, rcx
0x18001dc71  call    cs:__imp_SetThreadpoolTimer
0x18001dc77  mov     edx, 1; fCancelPendingCallbacks
0x18001dc7c  mov     rcx, rbx; pti
0x18001dc7f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001dc85  mov     rcx, rbx
0x18001dc88  add     rsp, 20h
0x18001dc8c  pop     rbx
0x18001dc8d  jmp     cs:__imp_CloseThreadpoolTimer
```
