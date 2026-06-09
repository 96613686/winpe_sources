# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001ae44`
- end: `0x18001ae78`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001ad78`
- `0x18001adc8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001ae71`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ae63`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ae63`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ae55`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ae55`

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
0x18001ae44  push    rbx
0x18001ae46  sub     rsp, 20h
0x18001ae4a  xor     r9d, r9d; msWindowLength
0x18001ae4d  xor     r8d, r8d; msPeriod
0x18001ae50  xor     edx, edx; pftDueTime
0x18001ae52  mov     rbx, rcx
0x18001ae55  call    cs:__imp_SetThreadpoolTimer
0x18001ae5b  mov     edx, 1; fCancelPendingCallbacks
0x18001ae60  mov     rcx, rbx; pti
0x18001ae63  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001ae69  mov     rcx, rbx
0x18001ae6c  add     rsp, 20h
0x18001ae70  pop     rbx
0x18001ae71  jmp     cs:__imp_CloseThreadpoolTimer
```
