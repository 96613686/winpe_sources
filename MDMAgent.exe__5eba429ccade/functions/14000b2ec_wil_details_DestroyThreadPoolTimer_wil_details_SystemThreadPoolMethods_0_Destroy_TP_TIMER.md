# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x14000b2ec`
- end: `0x14000b320`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000909c`
- `0x1400115d8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000b319`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b2fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000b2fd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b30b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000b30b`

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
0x14000b2ec  push    rbx
0x14000b2ee  sub     rsp, 20h
0x14000b2f2  xor     r9d, r9d; msWindowLength
0x14000b2f5  xor     r8d, r8d; msPeriod
0x14000b2f8  xor     edx, edx; pftDueTime
0x14000b2fa  mov     rbx, rcx
0x14000b2fd  call    cs:__imp_SetThreadpoolTimer
0x14000b303  mov     edx, 1; fCancelPendingCallbacks
0x14000b308  mov     rcx, rbx; pti
0x14000b30b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000b311  mov     rcx, rbx
0x14000b314  add     rsp, 20h
0x14000b318  pop     rbx
0x14000b319  jmp     cs:__imp_CloseThreadpoolTimer
```
