# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18005098c`
- end: `0x1800509c0`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x1800356b0`
- `0x18003577c`
- `0x180044ad8`
- `0x18004846c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800509ab`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800509ab`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005099d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005099d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800509b9`

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
0x18005098c  push    rbx
0x18005098e  sub     rsp, 20h
0x180050992  xor     r9d, r9d; msWindowLength
0x180050995  xor     r8d, r8d; msPeriod
0x180050998  xor     edx, edx; pftDueTime
0x18005099a  mov     rbx, rcx
0x18005099d  call    cs:__imp_SetThreadpoolTimer
0x1800509a3  mov     edx, 1; fCancelPendingCallbacks
0x1800509a8  mov     rcx, rbx; pti
0x1800509ab  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800509b1  mov     rcx, rbx
0x1800509b4  add     rsp, 20h
0x1800509b8  pop     rbx
0x1800509b9  jmp     cs:__imp_CloseThreadpoolTimer
```
