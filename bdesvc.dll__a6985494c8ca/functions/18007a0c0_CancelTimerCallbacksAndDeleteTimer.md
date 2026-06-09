# CancelTimerCallbacksAndDeleteTimer

- ea: `0x18007a0c0`
- end: `0x18007a126`
- name: `CancelTimerCallbacksAndDeleteTimer`
- size: `102`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18007a348`
- `0x18007a994`

## callees

- `0x18007a0c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007a0f5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18007a0f5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007a0dd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007a0dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007a108`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18007a108`

## pseudocode

```c
void __fastcall CancelTimerCallbacksAndDeleteTimer(__int64 a1)
{
  struct _TP_TIMER *v2; // rcx

  v2 = *(struct _TP_TIMER **)(a1 + 344);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*(PTP_TIMER *)(a1 + 344), 1);
    CloseThreadpoolTimer(*(PTP_TIMER *)(a1 + 344));
    *(_QWORD *)(a1 + 344) = 0;
  }
}

```

## disassembly

```asm
0x18007a0c0  push    rbx
0x18007a0c2  sub     rsp, 20h
0x18007a0c6  mov     rbx, rcx
0x18007a0c9  mov     rcx, [rcx+158h]; pti
0x18007a0d0  test    rcx, rcx
0x18007a0d3  jz      short loc_18007A11F
0x18007a0d5  xor     r9d, r9d; msWindowLength
0x18007a0d8  xor     r8d, r8d; msPeriod
0x18007a0db  xor     edx, edx; pftDueTime
0x18007a0dd  call    cs:__imp_SetThreadpoolTimer
0x18007a0e4  nop     dword ptr [rax+rax+00h]
0x18007a0e9  mov     rcx, [rbx+158h]; pti
0x18007a0f0  mov     edx, 1; fCancelPendingCallbacks
0x18007a0f5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18007a0fc  nop     dword ptr [rax+rax+00h]
0x18007a101  mov     rcx, [rbx+158h]; pti
0x18007a108  call    cs:__imp_CloseThreadpoolTimer
0x18007a10f  nop     dword ptr [rax+rax+00h]
0x18007a114  mov     qword ptr [rbx+158h], 0
0x18007a11f  add     rsp, 20h
0x18007a123  pop     rbx
0x18007a124  retn
```
