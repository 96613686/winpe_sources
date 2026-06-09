# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180005910`
- end: `0x180005944`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004ea4`
- `0x18000a028`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000593d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000592f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000592f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005921`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005921`

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
0x180005910  push    rbx
0x180005912  sub     rsp, 20h
0x180005916  xor     r9d, r9d; msWindowLength
0x180005919  xor     r8d, r8d; msPeriod
0x18000591c  xor     edx, edx; pftDueTime
0x18000591e  mov     rbx, rcx
0x180005921  call    cs:__imp_SetThreadpoolTimer
0x180005927  mov     edx, 1; fCancelPendingCallbacks
0x18000592c  mov     rcx, rbx; pti
0x18000592f  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180005935  mov     rcx, rbx
0x180005938  add     rsp, 20h
0x18000593c  pop     rbx
0x18000593d  jmp     cs:__imp_CloseThreadpoolTimer
```
