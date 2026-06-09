# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000b464`
- end: `0x18000b498`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000aa44`
- `0x18000fd4c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000b491`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b475`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000b475`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b483`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000b483`

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
0x18000b464  push    rbx
0x18000b466  sub     rsp, 20h
0x18000b46a  xor     r9d, r9d; msWindowLength
0x18000b46d  xor     r8d, r8d; msPeriod
0x18000b470  xor     edx, edx; pftDueTime
0x18000b472  mov     rbx, rcx
0x18000b475  call    cs:__imp_SetThreadpoolTimer
0x18000b47b  mov     edx, 1; fCancelPendingCallbacks
0x18000b480  mov     rcx, rbx; pti
0x18000b483  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000b489  mov     rcx, rbx
0x18000b48c  add     rsp, 20h
0x18000b490  pop     rbx
0x18000b491  jmp     cs:__imp_CloseThreadpoolTimer
```
