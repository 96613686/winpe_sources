# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001ed40`
- end: `0x18001ed85`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180019eb0`
- `0x180019f80`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ed65`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001ed65`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ed51`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ed51`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001ed79`

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
0x18001ed40  push    rbx
0x18001ed42  sub     rsp, 20h
0x18001ed46  xor     r9d, r9d; msWindowLength
0x18001ed49  xor     r8d, r8d; msPeriod
0x18001ed4c  xor     edx, edx; pftDueTime
0x18001ed4e  mov     rbx, rcx
0x18001ed51  call    cs:__imp_SetThreadpoolTimer
0x18001ed58  nop     dword ptr [rax+rax+00h]
0x18001ed5d  mov     edx, 1; fCancelPendingCallbacks
0x18001ed62  mov     rcx, rbx; pti
0x18001ed65  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001ed6c  nop     dword ptr [rax+rax+00h]
0x18001ed71  mov     rcx, rbx
0x18001ed74  add     rsp, 20h
0x18001ed78  pop     rbx
0x18001ed79  jmp     cs:__imp_CloseThreadpoolTimer
```
