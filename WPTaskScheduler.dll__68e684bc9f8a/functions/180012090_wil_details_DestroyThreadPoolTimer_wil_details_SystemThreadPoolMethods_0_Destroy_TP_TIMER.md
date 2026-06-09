# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180012090`
- end: `0x1800120c4`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `void __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180011834`
- `0x180016cbc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800120a1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800120a1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800120af`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800120af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800120bd`

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
0x180012090  push    rbx
0x180012092  sub     rsp, 20h
0x180012096  xor     r9d, r9d; msWindowLength
0x180012099  xor     r8d, r8d; msPeriod
0x18001209c  xor     edx, edx; pftDueTime
0x18001209e  mov     rbx, rcx
0x1800120a1  call    cs:__imp_SetThreadpoolTimer
0x1800120a7  mov     edx, 1; fCancelPendingCallbacks
0x1800120ac  mov     rcx, rbx; pti
0x1800120af  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800120b5  mov     rcx, rbx
0x1800120b8  add     rsp, 20h
0x1800120bc  pop     rbx
0x1800120bd  jmp     cs:__imp_CloseThreadpoolTimer
```
