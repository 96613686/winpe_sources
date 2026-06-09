# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800ba77c`
- end: `0x1800ba7b0`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18008f098`
- `0x18008f658`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ba79b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ba79b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800ba7a9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ba78d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ba78d`

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
0x1800ba77c  push    rbx
0x1800ba77e  sub     rsp, 20h
0x1800ba782  xor     r9d, r9d; msWindowLength
0x1800ba785  xor     r8d, r8d; msPeriod
0x1800ba788  xor     edx, edx; pftDueTime
0x1800ba78a  mov     rbx, rcx
0x1800ba78d  call    cs:__imp_SetThreadpoolTimer
0x1800ba793  mov     edx, 1; fCancelPendingCallbacks
0x1800ba798  mov     rcx, rbx; pti
0x1800ba79b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800ba7a1  mov     rcx, rbx
0x1800ba7a4  add     rsp, 20h
0x1800ba7a8  pop     rbx
0x1800ba7a9  jmp     cs:__imp_CloseThreadpoolTimer
```
