# TelemetryOperationWatchdog::`vector deleting destructor'(uint)

- ea: `0x180020ff0`
- end: `0x180021074`
- name: `??_ETelemetryOperationWatchdog@@UEAAPEAXI@Z`
- size: `132`
- prototype: `PTP_TIMER *__fastcall(PTP_TIMER *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180005654`
- `0x180020ff0`
- `0x180025ae4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002101c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002101c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180021036`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180021036`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002104d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18002104d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180021044`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180021044`

## pseudocode

```c
PTP_TIMER *__fastcall TelemetryOperationWatchdog::`vector deleting destructor'(PTP_TIMER *this, char a2)
{
  PTP_TIMER v4; // rcx
  struct _TP_TIMER *v5; // rdi

  *this = (PTP_TIMER)&OperationWatchdog::`vftable';
  OperationWatchdog::End((OperationWatchdog *)this);
  v4 = this[4];
  if ( v4 )
    LocalFree(v4);
  v5 = this[2];
  if ( v5 )
  {
    SetThreadpoolTimer(this[2], 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(v5, 1);
    CloseThreadpoolTimer(v5);
  }
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180020ff0  mov     [rsp+arg_0], rbx
0x180020ff5  mov     [rsp+arg_8], rsi
0x180020ffa  push    rdi
0x180020ffb  sub     rsp, 20h
0x180020fff  lea     rax, ??_7OperationWatchdog@@6B@; const OperationWatchdog::`vftable'
0x180021006  mov     esi, edx
0x180021008  mov     [rcx], rax
0x18002100b  mov     rbx, rcx
0x18002100e  call    ?End@OperationWatchdog@@QEAAXXZ; OperationWatchdog::End(void)
0x180021013  mov     rcx, [rbx+20h]; hMem
0x180021017  test    rcx, rcx
0x18002101a  jz      short loc_180021022
0x18002101c  call    cs:__imp_LocalFree
0x180021022  mov     rdi, [rbx+10h]
0x180021026  test    rdi, rdi
0x180021029  jz      short loc_180021053
0x18002102b  xor     r9d, r9d; msWindowLength
0x18002102e  xor     r8d, r8d; msPeriod
0x180021031  xor     edx, edx; pftDueTime
0x180021033  mov     rcx, rdi; pti
0x180021036  call    cs:__imp_SetThreadpoolTimer
0x18002103c  mov     edx, 1; fCancelPendingCallbacks
0x180021041  mov     rcx, rdi; pti
0x180021044  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18002104a  mov     rcx, rdi; pti
0x18002104d  call    cs:__imp_CloseThreadpoolTimer
0x180021053  test    sil, 1
0x180021057  jz      short loc_180021061
0x180021059  mov     rcx, rbx; Block
0x18002105c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180021061  mov     rsi, [rsp+28h+arg_8]
0x180021066  mov     rax, rbx
0x180021069  mov     rbx, [rsp+28h+arg_0]
0x18002106e  add     rsp, 20h
0x180021072  pop     rdi
0x180021073  retn
```
