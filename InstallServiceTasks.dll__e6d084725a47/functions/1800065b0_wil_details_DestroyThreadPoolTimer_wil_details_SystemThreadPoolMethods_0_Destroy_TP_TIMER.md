# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800065b0`
- end: `0x1800065e4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180005c3c`
- `0x18000a904`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800065c1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800065c1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800065cf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800065cf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800065dd`

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
0x1800065b0  push    rbx
0x1800065b2  sub     rsp, 20h
0x1800065b6  xor     r9d, r9d; msWindowLength
0x1800065b9  xor     r8d, r8d; msPeriod
0x1800065bc  xor     edx, edx; pftDueTime
0x1800065be  mov     rbx, rcx
0x1800065c1  call    cs:__imp_SetThreadpoolTimer
0x1800065c7  mov     edx, 1; fCancelPendingCallbacks
0x1800065cc  mov     rcx, rbx; pti
0x1800065cf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800065d5  mov     rcx, rbx
0x1800065d8  add     rsp, 20h
0x1800065dc  pop     rbx
0x1800065dd  jmp     cs:__imp_CloseThreadpoolTimer
```
