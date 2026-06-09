# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x180013684`
- end: `0x1800136b5`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x1800129d8`
- `0x18001d8ec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180013692`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180013692`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800136a0`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x1800136a0`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800136ae`

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
0x180013684  push    rbx
0x180013686  sub     rsp, 20h
0x18001368a  xor     r8d, r8d; pftTimeout
0x18001368d  xor     edx, edx; h
0x18001368f  mov     rbx, rcx
0x180013692  call    cs:__imp_SetThreadpoolWait
0x180013698  mov     edx, 1; fCancelPendingCallbacks
0x18001369d  mov     rcx, rbx; pwa
0x1800136a0  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x1800136a6  mov     rcx, rbx
0x1800136a9  add     rsp, 20h
0x1800136ad  pop     rbx
0x1800136ae  jmp     cs:__imp_CloseThreadpoolWait
```
