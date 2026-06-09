# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1400148a8`
- end: `0x1400148dc`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14000f34c`
- `0x140037d88`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400148d5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400148c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400148c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400148b9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400148b9`

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
0x1400148a8  push    rbx
0x1400148aa  sub     rsp, 20h
0x1400148ae  xor     r9d, r9d; msWindowLength
0x1400148b1  xor     r8d, r8d; msPeriod
0x1400148b4  xor     edx, edx; pftDueTime
0x1400148b6  mov     rbx, rcx
0x1400148b9  call    cs:__imp_SetThreadpoolTimer
0x1400148bf  mov     edx, 1; fCancelPendingCallbacks
0x1400148c4  mov     rcx, rbx; pti
0x1400148c7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400148cd  mov     rcx, rbx
0x1400148d0  add     rsp, 20h
0x1400148d4  pop     rbx
0x1400148d5  jmp     cs:__imp_CloseThreadpoolTimer
```
