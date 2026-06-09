# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18005b55c`
- end: `0x18005b590`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180054e7c`
- `0x180054ecc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18005b589`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005b56d`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18005b56d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005b57b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18005b57b`

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
0x18005b55c  push    rbx
0x18005b55e  sub     rsp, 20h
0x18005b562  xor     r9d, r9d; msWindowLength
0x18005b565  xor     r8d, r8d; msPeriod
0x18005b568  xor     edx, edx; pftDueTime
0x18005b56a  mov     rbx, rcx
0x18005b56d  call    cs:__imp_SetThreadpoolTimer
0x18005b573  mov     edx, 1; fCancelPendingCallbacks
0x18005b578  mov     rcx, rbx; pti
0x18005b57b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18005b581  mov     rcx, rbx
0x18005b584  add     rsp, 20h
0x18005b588  pop     rbx
0x18005b589  jmp     cs:__imp_CloseThreadpoolTimer
```
