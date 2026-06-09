# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001e900`
- end: `0x18001e945`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180019ae0`
- `0x180019bb0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001e911`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001e911`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001e939`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001e925`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001e925`

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
0x18001e900  push    rbx
0x18001e902  sub     rsp, 20h
0x18001e906  xor     r9d, r9d; msWindowLength
0x18001e909  xor     r8d, r8d; msPeriod
0x18001e90c  xor     edx, edx; pftDueTime
0x18001e90e  mov     rbx, rcx
0x18001e911  call    cs:__imp_SetThreadpoolTimer
0x18001e918  nop     dword ptr [rax+rax+00h]
0x18001e91d  mov     edx, 1; fCancelPendingCallbacks
0x18001e922  mov     rcx, rbx; pti
0x18001e925  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001e92c  nop     dword ptr [rax+rax+00h]
0x18001e931  mov     rcx, rbx
0x18001e934  add     rsp, 20h
0x18001e938  pop     rbx
0x18001e939  jmp     cs:__imp_CloseThreadpoolTimer
```
