# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800049e0`
- end: `0x180004a14`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800040a0`
- `0x180008cb4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800049f1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800049f1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004a0d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800049ff`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800049ff`

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
0x1800049e0  push    rbx
0x1800049e2  sub     rsp, 20h
0x1800049e6  xor     r9d, r9d; msWindowLength
0x1800049e9  xor     r8d, r8d; msPeriod
0x1800049ec  xor     edx, edx; pftDueTime
0x1800049ee  mov     rbx, rcx
0x1800049f1  call    cs:__imp_SetThreadpoolTimer
0x1800049f7  mov     edx, 1; fCancelPendingCallbacks
0x1800049fc  mov     rcx, rbx; pti
0x1800049ff  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004a05  mov     rcx, rbx
0x180004a08  add     rsp, 20h
0x180004a0c  pop     rbx
0x180004a0d  jmp     cs:__imp_CloseThreadpoolTimer
```
