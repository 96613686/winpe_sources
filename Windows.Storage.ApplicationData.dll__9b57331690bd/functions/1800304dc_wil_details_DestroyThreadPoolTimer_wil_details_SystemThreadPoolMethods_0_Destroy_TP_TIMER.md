# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800304dc`
- end: `0x180030510`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(_TP_TIMER *threadpoolTimer)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002f950`
- `0x180033dd0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180030509`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800304fb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800304fb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800304ed`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800304ed`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(
        _TP_TIMER *threadpoolTimer)
{
  SetThreadpoolTimer(threadpoolTimer, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(threadpoolTimer, 1);
  CloseThreadpoolTimer(threadpoolTimer);
}

```

## disassembly

```asm
0x1800304dc  push    rbx
0x1800304de  sub     rsp, 20h
0x1800304e2  xor     r9d, r9d; msWindowLength
0x1800304e5  xor     r8d, r8d; msPeriod
0x1800304e8  xor     edx, edx; pftDueTime
0x1800304ea  mov     rbx, threadpoolTimer
0x1800304ed  call    cs:__imp_SetThreadpoolTimer
0x1800304f3  mov     edx, 1; fCancelPendingCallbacks
0x1800304f8  mov     threadpoolTimer, rbx; pti
0x1800304fb  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180030501  mov     threadpoolTimer, rbx
0x180030504  add     rsp, 20h
0x180030508  pop     rbx
0x180030509  jmp     cs:__imp_CloseThreadpoolTimer
```
