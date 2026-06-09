# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x1800664cc`
- end: `0x18006650a`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `62`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180065ad4`
- `0x1800693b8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800664e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800664e6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800664f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800664f4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800664fd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800664fd`

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
0x1800664cc  push    rbx
0x1800664ce  sub     rsp, 30h
0x1800664d2  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x1800664db  mov     rbx, rcx
0x1800664de  xor     r9d, r9d; msWindowLength
0x1800664e1  xor     r8d, r8d; msPeriod
0x1800664e4  xor     edx, edx; pftDueTime
0x1800664e6  call    cs:__imp_SetThreadpoolTimer
0x1800664ec  mov     edx, 1; fCancelPendingCallbacks
0x1800664f1  mov     rcx, rbx; pti
0x1800664f4  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800664fa  mov     rcx, rbx; pti
0x1800664fd  call    cs:__imp_CloseThreadpoolTimer
0x180066503  nop
0x180066504  add     rsp, 30h
0x180066508  pop     rbx
0x180066509  retn
```
