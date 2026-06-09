# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x18000d480`
- end: `0x18000d4b1`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000d104`
- `0x18004e0c8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d48e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d48e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000d49c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18000d49c`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18000d4aa`

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
0x18000d480  push    rbx
0x18000d482  sub     rsp, 20h
0x18000d486  xor     r8d, r8d; pftTimeout
0x18000d489  xor     edx, edx; h
0x18000d48b  mov     rbx, rcx
0x18000d48e  call    cs:__imp_SetThreadpoolWait
0x18000d494  mov     edx, 1; fCancelPendingCallbacks
0x18000d499  mov     rcx, rbx; pwa
0x18000d49c  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18000d4a2  mov     rcx, rbx
0x18000d4a5  add     rsp, 20h
0x18000d4a9  pop     rbx
0x18000d4aa  jmp     cs:__imp_CloseThreadpoolWait
```
