# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800858e4`
- end: `0x180085918`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x18003be18`
- `0x180063178`
- `0x18006329c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800858f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800858f5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180085903`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180085903`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180085911`

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
0x1800858e4  push    rbx
0x1800858e6  sub     rsp, 20h
0x1800858ea  xor     r9d, r9d; msWindowLength
0x1800858ed  xor     r8d, r8d; msPeriod
0x1800858f0  xor     edx, edx; pftDueTime
0x1800858f2  mov     rbx, rcx
0x1800858f5  call    cs:__imp_SetThreadpoolTimer
0x1800858fb  mov     edx, 1; fCancelPendingCallbacks
0x180085900  mov     rcx, rbx; pti
0x180085903  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180085909  mov     rcx, rbx
0x18008590c  add     rsp, 20h
0x180085910  pop     rbx
0x180085911  jmp     cs:__imp_CloseThreadpoolTimer
```
