# wil::details::DestroyThreadPoolWait<0>::Destroy(_TP_WAIT *)

- ea: `0x14002222c`
- end: `0x14002225d`
- name: `?Destroy@?$DestroyThreadPoolWait@$0A@@details@wil@@SAXPEAU_TP_WAIT@@@Z`
- size: `49`
- prototype: `__int64 __fastcall(PTP_WAIT pwa)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x14002174c`
- `0x140023e70`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14002223a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x14002223a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140022256`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140022248`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140022248`

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
0x14002222c  push    rbx
0x14002222e  sub     rsp, 20h
0x140022232  xor     r8d, r8d; pftTimeout
0x140022235  xor     edx, edx; h
0x140022237  mov     rbx, rcx
0x14002223a  call    cs:__imp_SetThreadpoolWait
0x140022240  mov     edx, 1; fCancelPendingCallbacks
0x140022245  mov     rcx, rbx; pwa
0x140022248  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x14002224e  mov     rcx, rbx
0x140022251  add     rsp, 20h
0x140022255  pop     rbx
0x140022256  jmp     cs:__imp_CloseThreadpoolWait
```
