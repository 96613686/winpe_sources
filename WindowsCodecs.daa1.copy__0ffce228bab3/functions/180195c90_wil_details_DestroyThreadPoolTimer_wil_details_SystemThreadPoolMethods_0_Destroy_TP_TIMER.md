# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180195c90`
- end: `0x180195cd5`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800b866c`
- `0x1800c3070`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180195cb5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180195cb5`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180195cc9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180195ca1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180195ca1`

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
0x180195c90  push    rbx
0x180195c92  sub     rsp, 20h
0x180195c96  xor     r9d, r9d; msWindowLength
0x180195c99  xor     r8d, r8d; msPeriod
0x180195c9c  xor     edx, edx; pftDueTime
0x180195c9e  mov     rbx, rcx
0x180195ca1  call    cs:__imp_SetThreadpoolTimer
0x180195ca8  nop     dword ptr [rax+rax+00h]
0x180195cad  mov     edx, 1; fCancelPendingCallbacks
0x180195cb2  mov     rcx, rbx; pti
0x180195cb5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180195cbc  nop     dword ptr [rax+rax+00h]
0x180195cc1  mov     rcx, rbx
0x180195cc4  add     rsp, 20h
0x180195cc8  pop     rbx
0x180195cc9  jmp     cs:__imp_CloseThreadpoolTimer
```
