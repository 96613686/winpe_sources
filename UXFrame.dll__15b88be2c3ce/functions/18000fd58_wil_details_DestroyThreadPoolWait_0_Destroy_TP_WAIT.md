# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x18000fd58`
- end: `0x18000fd89`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e2dc`
- `0x18002d484`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000fd82`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000fd74`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000fd74`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000fd66`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000fd66`

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
0x18000fd58  push    rbx
0x18000fd5a  sub     rsp, 20h
0x18000fd5e  xor     r8d, r8d; pftTimeout
0x18000fd61  xor     edx, edx; h
0x18000fd63  mov     rbx, rcx
0x18000fd66  call    cs:__imp_SetThreadpoolWait
0x18000fd6c  mov     edx, 1; fCancelPendingCallbacks
0x18000fd71  mov     rcx, rbx; pwa
0x18000fd74  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000fd7a  mov     rcx, rbx
0x18000fd7d  add     rsp, 20h
0x18000fd81  pop     rbx
0x18000fd82  jmp     cs:__imp_CloseThreadpoolWait
```
