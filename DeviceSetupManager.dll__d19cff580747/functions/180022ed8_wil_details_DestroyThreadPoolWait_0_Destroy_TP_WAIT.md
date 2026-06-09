# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x180022ed8`
- end: `0x180022f09`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180022b7c`
- `0x18002acac`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180022ee6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180022ee6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180022ef4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180022ef4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180022f02`

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
0x180022ed8  push    rbx
0x180022eda  sub     rsp, 20h
0x180022ede  xor     r8d, r8d; pftTimeout
0x180022ee1  xor     edx, edx; h
0x180022ee3  mov     rbx, rcx
0x180022ee6  call    cs:__imp_SetThreadpoolWait
0x180022eec  mov     edx, 1; fCancelPendingCallbacks
0x180022ef1  mov     rcx, rbx; pwa
0x180022ef4  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180022efa  mov     rcx, rbx
0x180022efd  add     rsp, 20h
0x180022f01  pop     rbx
0x180022f02  jmp     cs:__imp_CloseThreadpoolWait
```
