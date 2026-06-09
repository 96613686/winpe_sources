# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180011f64`
- end: `0x180011f98`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000b744`
- `0x180011944`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011f91`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011f83`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011f83`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011f75`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011f75`

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
0x180011f64  push    rbx
0x180011f66  sub     rsp, 20h
0x180011f6a  xor     r9d, r9d; msWindowLength
0x180011f6d  xor     r8d, r8d; msPeriod
0x180011f70  xor     edx, edx; pftDueTime
0x180011f72  mov     rbx, rcx
0x180011f75  call    cs:__imp_SetThreadpoolTimer
0x180011f7b  mov     edx, 1; fCancelPendingCallbacks
0x180011f80  mov     rcx, rbx; pti
0x180011f83  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011f89  mov     rcx, rbx
0x180011f8c  add     rsp, 20h
0x180011f90  pop     rbx
0x180011f91  jmp     cs:__imp_CloseThreadpoolTimer
```
