# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x180035144`
- end: `0x180035175`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180034dfc`
- `0x1800367f8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18003516e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180035160`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180035160`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180035152`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180035152`

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
0x180035144  push    rbx
0x180035146  sub     rsp, 20h
0x18003514a  xor     r8d, r8d; pftTimeout
0x18003514d  xor     edx, edx; h
0x18003514f  mov     rbx, rcx
0x180035152  call    cs:__imp_SetThreadpoolWait
0x180035158  mov     edx, 1; fCancelPendingCallbacks
0x18003515d  mov     rcx, rbx; pwa
0x180035160  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180035166  mov     rcx, rbx
0x180035169  add     rsp, 20h
0x18003516d  pop     rbx
0x18003516e  jmp     cs:__imp_CloseThreadpoolWait
```
