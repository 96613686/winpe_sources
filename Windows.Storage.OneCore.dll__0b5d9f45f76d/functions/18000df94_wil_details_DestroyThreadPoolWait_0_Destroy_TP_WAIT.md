# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x18000df94`
- end: `0x18000dfc5`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d584`
- `0x180010910`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000dfbe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000dfb0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000dfb0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000dfa2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000dfa2`

## pseudocode

```c
void __fastcall wil::details::DestroyThreadPoolWait<0>::Destroy(PTP_WAIT pwa)
{
  SetThreadpoolWait(pwa, 0, 0);
  WaitForThreadpoolWaitCallbacks(pwa, 1);
  CloseThreadpoolWait(pwa);
}

```

## disassembly

```asm
0x18000df94  push    rbx
0x18000df96  sub     rsp, 20h
0x18000df9a  xor     r8d, r8d; pftTimeout
0x18000df9d  xor     edx, edx; h
0x18000df9f  mov     rbx, rcx
0x18000dfa2  call    cs:__imp_SetThreadpoolWait
0x18000dfa8  mov     edx, 1; fCancelPendingCallbacks
0x18000dfad  mov     rcx, rbx; pwa
0x18000dfb0  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000dfb6  mov     rcx, rbx
0x18000dfb9  add     rsp, 20h
0x18000dfbd  pop     rbx
0x18000dfbe  jmp     cs:__imp_CloseThreadpoolWait
```
