# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18001bd94`
- end: `0x18001bdc8`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001bc6c`
- `0x18002bf80`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001bdb3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001bdb3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001bdc1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bda5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bda5`

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
0x18001bd94  push    rbx
0x18001bd96  sub     rsp, 20h
0x18001bd9a  xor     r9d, r9d; msWindowLength
0x18001bd9d  xor     r8d, r8d; msPeriod
0x18001bda0  xor     edx, edx; pftDueTime
0x18001bda2  mov     rbx, rcx
0x18001bda5  call    cs:__imp_SetThreadpoolTimer
0x18001bdab  mov     edx, 1; fCancelPendingCallbacks
0x18001bdb0  mov     rcx, rbx; pti
0x18001bdb3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001bdb9  mov     rcx, rbx
0x18001bdbc  add     rsp, 20h
0x18001bdc0  pop     rbx
0x18001bdc1  jmp     cs:__imp_CloseThreadpoolTimer
```
