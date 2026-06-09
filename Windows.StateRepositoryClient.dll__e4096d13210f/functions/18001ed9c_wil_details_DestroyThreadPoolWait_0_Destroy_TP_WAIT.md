# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x18001ed9c`
- end: `0x18001edcd`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `void __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001e644`
- `0x18001fdd0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001edaa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001edaa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001edc6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001edb8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001edb8`

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
0x18001ed9c  push    rbx
0x18001ed9e  sub     rsp, 20h
0x18001eda2  xor     r8d, r8d; pftTimeout
0x18001eda5  xor     edx, edx; h
0x18001eda7  mov     rbx, rcx
0x18001edaa  call    cs:__imp_SetThreadpoolWait
0x18001edb0  mov     edx, 1; fCancelPendingCallbacks
0x18001edb5  mov     rcx, rbx; pwa
0x18001edb8  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18001edbe  mov     rcx, rbx
0x18001edc1  add     rsp, 20h
0x18001edc5  pop     rbx
0x18001edc6  jmp     cs:__imp_CloseThreadpoolWait
```
