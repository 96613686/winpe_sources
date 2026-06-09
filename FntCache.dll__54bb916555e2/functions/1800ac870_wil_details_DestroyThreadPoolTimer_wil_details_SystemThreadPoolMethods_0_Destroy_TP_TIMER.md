# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800ac870`
- end: `0x1800ac8a4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18009938c`
- `0x1800a536c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800ac89d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ac88f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800ac88f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ac881`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800ac881`

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
0x1800ac870  push    rbx
0x1800ac872  sub     rsp, 20h
0x1800ac876  xor     r9d, r9d; msWindowLength
0x1800ac879  xor     r8d, r8d; msPeriod
0x1800ac87c  xor     edx, edx; pftDueTime
0x1800ac87e  mov     rbx, rcx
0x1800ac881  call    cs:__imp_SetThreadpoolTimer
0x1800ac887  mov     edx, 1; fCancelPendingCallbacks
0x1800ac88c  mov     rcx, rbx; pti
0x1800ac88f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800ac895  mov     rcx, rbx
0x1800ac898  add     rsp, 20h
0x1800ac89c  pop     rbx
0x1800ac89d  jmp     cs:__imp_CloseThreadpoolTimer
```
