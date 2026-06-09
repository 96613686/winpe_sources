# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180011bc0`
- end: `0x180011bf4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e9fc`
- `0x18001d3d8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011bed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011bd1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011bd1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011bdf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011bdf`

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
0x180011bc0  push    rbx
0x180011bc2  sub     rsp, 20h
0x180011bc6  xor     r9d, r9d; msWindowLength
0x180011bc9  xor     r8d, r8d; msPeriod
0x180011bcc  xor     edx, edx; pftDueTime
0x180011bce  mov     rbx, rcx
0x180011bd1  call    cs:__imp_SetThreadpoolTimer
0x180011bd7  mov     edx, 1; fCancelPendingCallbacks
0x180011bdc  mov     rcx, rbx; pti
0x180011bdf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011be5  mov     rcx, rbx
0x180011be8  add     rsp, 20h
0x180011bec  pop     rbx
0x180011bed  jmp     cs:__imp_CloseThreadpoolTimer
```
