# wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)

- ea: `0x18002c484`
- end: `0x18002c4b8`
- name: `?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z`
- size: `52`
- prototype: `__int64 __fastcall(PTP_TIMER pti)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18002bf58`
- `0x18002e5c8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c495`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18002c495`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002c4b1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002c4a3`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002c4a3`

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
0x18002c484  push    rbx
0x18002c486  sub     rsp, 20h
0x18002c48a  xor     r9d, r9d; msWindowLength
0x18002c48d  xor     r8d, r8d; msPeriod
0x18002c490  xor     edx, edx; pftDueTime
0x18002c492  mov     rbx, rcx
0x18002c495  call    cs:__imp_SetThreadpoolTimer
0x18002c49b  mov     edx, 1; fCancelPendingCallbacks
0x18002c4a0  mov     rcx, rbx; pti
0x18002c4a3  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002c4a9  mov     rcx, rbx
0x18002c4ac  add     rsp, 20h
0x18002c4b0  pop     rbx
0x18002c4b1  jmp     cs:__imp_CloseThreadpoolTimer
```
