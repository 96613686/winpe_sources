# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18000bc90`
- end: `0x18000bcc4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180008800`
- `0x180008f20`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bca1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000bca1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000bcbd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bcaf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000bcaf`

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
0x18000bc90  push    rbx
0x18000bc92  sub     rsp, 20h
0x18000bc96  xor     r9d, r9d; msWindowLength
0x18000bc99  xor     r8d, r8d; msPeriod
0x18000bc9c  xor     edx, edx; pftDueTime
0x18000bc9e  mov     rbx, rcx
0x18000bca1  call    cs:__imp_SetThreadpoolTimer
0x18000bca7  mov     edx, 1; fCancelPendingCallbacks
0x18000bcac  mov     rcx, rbx; pti
0x18000bcaf  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000bcb5  mov     rcx, rbx
0x18000bcb8  add     rsp, 20h
0x18000bcbc  pop     rbx
0x18000bcbd  jmp     cs:__imp_CloseThreadpoolTimer
```
