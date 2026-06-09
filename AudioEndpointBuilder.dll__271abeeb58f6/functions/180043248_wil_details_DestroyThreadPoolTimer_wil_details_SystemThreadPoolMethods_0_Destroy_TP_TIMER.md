# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x180043248`
- end: `0x18004327c`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180035170`
- `0x1800373e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180043275`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180043267`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180043267`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180043259`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180043259`

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
0x180043248  push    rbx
0x18004324a  sub     rsp, 20h
0x18004324e  xor     r9d, r9d; msWindowLength
0x180043251  xor     r8d, r8d; msPeriod
0x180043254  xor     edx, edx; pftDueTime
0x180043256  mov     rbx, rcx
0x180043259  call    cs:__imp_SetThreadpoolTimer
0x18004325f  mov     edx, 1; fCancelPendingCallbacks
0x180043264  mov     rcx, rbx; pti
0x180043267  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18004326d  mov     rcx, rbx
0x180043270  add     rsp, 20h
0x180043274  pop     rbx
0x180043275  jmp     cs:__imp_CloseThreadpoolTimer
```
