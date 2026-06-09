# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800119f4`
- end: `0x180011a28`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800112c4`
- `0x180013ff8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011a13`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011a13`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011a05`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011a05`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011a21`

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
0x1800119f4  push    rbx
0x1800119f6  sub     rsp, 20h
0x1800119fa  xor     r9d, r9d; msWindowLength
0x1800119fd  xor     r8d, r8d; msPeriod
0x180011a00  xor     edx, edx; pftDueTime
0x180011a02  mov     rbx, rcx
0x180011a05  call    cs:__imp_SetThreadpoolTimer
0x180011a0b  mov     edx, 1; fCancelPendingCallbacks
0x180011a10  mov     rcx, rbx; pti
0x180011a13  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011a19  mov     rcx, rbx
0x180011a1c  add     rsp, 20h
0x180011a20  pop     rbx
0x180011a21  jmp     cs:__imp_CloseThreadpoolTimer
```
