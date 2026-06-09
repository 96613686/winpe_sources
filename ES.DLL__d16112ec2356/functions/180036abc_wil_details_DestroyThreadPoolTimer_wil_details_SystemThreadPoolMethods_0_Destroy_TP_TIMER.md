# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180036abc`
- end: `0x180036af0`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002b658`
- `0x18002b6a8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180036ae9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036acd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036acd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180036adb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180036adb`

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
0x180036abc  push    rbx
0x180036abe  sub     rsp, 20h
0x180036ac2  xor     r9d, r9d; msWindowLength
0x180036ac5  xor     r8d, r8d; msPeriod
0x180036ac8  xor     edx, edx; pftDueTime
0x180036aca  mov     rbx, rcx
0x180036acd  call    cs:__imp_SetThreadpoolTimer
0x180036ad3  mov     edx, 1; fCancelPendingCallbacks
0x180036ad8  mov     rcx, rbx; pti
0x180036adb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180036ae1  mov     rcx, rbx
0x180036ae4  add     rsp, 20h
0x180036ae8  pop     rbx
0x180036ae9  jmp     cs:__imp_CloseThreadpoolTimer
```
