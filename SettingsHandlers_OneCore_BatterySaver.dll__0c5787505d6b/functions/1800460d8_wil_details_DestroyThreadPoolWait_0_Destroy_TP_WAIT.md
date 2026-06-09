# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x1800460d8`
- end: `0x180046109`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180045ed0`
- `0x1800465c8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800460e6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x1800460e6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800460f4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800460f4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180046102`

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
0x1800460d8  push    rbx
0x1800460da  sub     rsp, 20h
0x1800460de  xor     r8d, r8d; pftTimeout
0x1800460e1  xor     edx, edx; h
0x1800460e3  mov     rbx, rcx
0x1800460e6  call    cs:__imp_SetThreadpoolWait
0x1800460ec  mov     edx, 1; fCancelPendingCallbacks
0x1800460f1  mov     rcx, rbx; pwa
0x1800460f4  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800460fa  mov     rcx, rbx
0x1800460fd  add     rsp, 20h
0x180046101  pop     rbx
0x180046102  jmp     cs:__imp_CloseThreadpoolWait
```
