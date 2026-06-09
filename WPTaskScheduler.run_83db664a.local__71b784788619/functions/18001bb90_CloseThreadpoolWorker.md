# CloseThreadpoolWorker

- ea: `0x18001bb90`
- end: `0x18001bbcb`
- name: `CloseThreadpoolWorker`
- size: `59`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x18001bb90`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bba8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001bba8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001bbb6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001bbb6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001bbbf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001bbbf`

## pseudocode

```c
void __fastcall CloseThreadpoolWorker(PTP_CALLBACK_INSTANCE Instance, struct _TP_TIMER *Context, PTP_WORK Work)
{
  if ( Context )
  {
    SetThreadpoolTimer(Context, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(Context, 1);
    CloseThreadpoolTimer(Context);
  }
}

```

## disassembly

```asm
0x18001bb90  test    rdx, rdx
0x18001bb93  jz      short locret_18001BBCA
0x18001bb95  push    rbx
0x18001bb96  sub     rsp, 20h
0x18001bb9a  mov     rbx, rdx
0x18001bb9d  xor     r9d, r9d; msWindowLength
0x18001bba0  mov     rcx, rbx; pti
0x18001bba3  xor     r8d, r8d; msPeriod
0x18001bba6  xor     edx, edx; pftDueTime
0x18001bba8  call    cs:__imp_SetThreadpoolTimer
0x18001bbae  mov     edx, 1; fCancelPendingCallbacks
0x18001bbb3  mov     rcx, rbx; pti
0x18001bbb6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001bbbc  mov     rcx, rbx; pti
0x18001bbbf  call    cs:__imp_CloseThreadpoolTimer
0x18001bbc5  add     rsp, 20h
0x18001bbc9  pop     rbx
0x18001bbca  retn
```
