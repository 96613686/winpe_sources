# FSStream::CloseFirstFrameTimer(void)

- ea: `0x1800a79a8`
- end: `0x1800a79fb`
- name: `?CloseFirstFrameTimer@FSStream@@IEAAXXZ`
- size: `83`
- prototype: `void __fastcall(FSStream *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800a6f78`

## callees

- `0x1800a79a8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a79e4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800a79e4`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800a79d7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800a79d7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a79c5`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800a79c5`

## pseudocode

```c
void __fastcall FSStream::CloseFirstFrameTimer(FSStream *this)
{
  struct _TP_TIMER *v2; // rcx

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 97);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 97), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 97));
    *((_QWORD *)this + 97) = 0;
  }
}

```

## disassembly

```asm
0x1800a79a8  push    rbx
0x1800a79aa  sub     rsp, 20h
0x1800a79ae  mov     rbx, rcx
0x1800a79b1  mov     rcx, [rcx+308h]; pti
0x1800a79b8  test    rcx, rcx
0x1800a79bb  jz      short loc_1800A79F5
0x1800a79bd  xor     r9d, r9d; msWindowLength
0x1800a79c0  xor     r8d, r8d; msPeriod
0x1800a79c3  xor     edx, edx; pftDueTime
0x1800a79c5  call    cs:__imp_SetThreadpoolTimer
0x1800a79cb  mov     rcx, [rbx+308h]; pti
0x1800a79d2  mov     edx, 1; fCancelPendingCallbacks
0x1800a79d7  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800a79dd  mov     rcx, [rbx+308h]; pti
0x1800a79e4  call    cs:__imp_CloseThreadpoolTimer
0x1800a79ea  mov     qword ptr [rbx+308h], 0
0x1800a79f5  add     rsp, 20h
0x1800a79f9  pop     rbx
0x1800a79fa  retn
```
