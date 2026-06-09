# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x18001be1c`
- end: `0x18001be4d`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18001d804`
- `0x180025ca4`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18001be46`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001be38`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18001be38`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001be2a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18001be2a`

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
0x18001be1c  push    rbx
0x18001be1e  sub     rsp, 20h
0x18001be22  xor     r8d, r8d; pftTimeout
0x18001be25  xor     edx, edx; h
0x18001be27  mov     rbx, rcx
0x18001be2a  call    cs:__imp_SetThreadpoolWait
0x18001be30  mov     edx, 1; fCancelPendingCallbacks
0x18001be35  mov     rcx, rbx; pwa
0x18001be38  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18001be3e  mov     rcx, rbx
0x18001be41  add     rsp, 20h
0x18001be45  pop     rbx
0x18001be46  jmp     cs:__imp_CloseThreadpoolWait
```
