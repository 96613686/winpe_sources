# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x140015054`
- end: `0x140015088`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140013d38`
- `0x140018c68`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140015073`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x140015073`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140015081`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140015065`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140015065`

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
0x140015054  push    rbx
0x140015056  sub     rsp, 20h
0x14001505a  xor     r9d, r9d; msWindowLength
0x14001505d  xor     r8d, r8d; msPeriod
0x140015060  xor     edx, edx; pftDueTime
0x140015062  mov     rbx, rcx
0x140015065  call    cs:__imp_SetThreadpoolTimer
0x14001506b  mov     edx, 1; fCancelPendingCallbacks
0x140015070  mov     rcx, rbx; pti
0x140015073  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140015079  mov     rcx, rbx
0x14001507c  add     rsp, 20h
0x140015080  pop     rbx
0x140015081  jmp     cs:__imp_CloseThreadpoolTimer
```
