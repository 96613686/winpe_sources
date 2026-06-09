# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180026840`
- end: `0x180026874`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180013064`
- `0x180026494`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002686d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002685f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002685f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026851`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026851`

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
0x180026840  push    rbx
0x180026842  sub     rsp, 20h
0x180026846  xor     r9d, r9d; msWindowLength
0x180026849  xor     r8d, r8d; msPeriod
0x18002684c  xor     edx, edx; pftDueTime
0x18002684e  mov     rbx, rcx
0x180026851  call    cs:__imp_SetThreadpoolTimer
0x180026857  mov     edx, 1; fCancelPendingCallbacks
0x18002685c  mov     rcx, rbx; pti
0x18002685f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180026865  mov     rcx, rbx
0x180026868  add     rsp, 20h
0x18002686c  pop     rbx
0x18002686d  jmp     cs:__imp_CloseThreadpoolTimer
```
