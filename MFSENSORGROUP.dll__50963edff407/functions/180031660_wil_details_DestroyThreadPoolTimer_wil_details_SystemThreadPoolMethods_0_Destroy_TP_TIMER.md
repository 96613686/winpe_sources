# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180031660`
- end: `0x180031694`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18003161c`
- `0x180031c30`
- `0x180031ca4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180031671`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180031671`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003168d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003167f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18003167f`

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
0x180031660  push    rbx
0x180031662  sub     rsp, 20h
0x180031666  xor     r9d, r9d; msWindowLength
0x180031669  xor     r8d, r8d; msPeriod
0x18003166c  xor     edx, edx; pftDueTime
0x18003166e  mov     rbx, rcx
0x180031671  call    cs:__imp_SetThreadpoolTimer
0x180031677  mov     edx, 1; fCancelPendingCallbacks
0x18003167c  mov     rcx, rbx; pti
0x18003167f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180031685  mov     rcx, rbx
0x180031688  add     rsp, 20h
0x18003168c  pop     rbx
0x18003168d  jmp     cs:__imp_CloseThreadpoolTimer
```
