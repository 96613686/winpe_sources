# ProcessorStatisticsBase::Stop(void)

- ea: `0x1402964ec`
- end: `0x140296546`
- name: `?Stop@ProcessorStatisticsBase@@QEAAXXZ`
- size: `90`
- prototype: `void __fastcall(ProcessorStatisticsBase *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x14026d6a0`
- `0x140296458`

## callees

- `0x1402964ec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14029652b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14029652b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140296506`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140296506`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14029651b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14029651b`

## pseudocode

```c
void __fastcall ProcessorStatisticsBase::Stop(ProcessorStatisticsBase *this)
{
  struct _TP_TIMER *v2; // rcx

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 12);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 12), 1);
    CloseThreadpoolTimer(*((PTP_TIMER *)this + 12));
    *((_QWORD *)this + 12) = 0;
  }
}

```

## disassembly

```asm
0x1402964ec  push    rbx
0x1402964ee  sub     rsp, 20h
0x1402964f2  mov     rbx, rcx
0x1402964f5  mov     rcx, [rcx+60h]; pti
0x1402964f9  test    rcx, rcx
0x1402964fc  jz      short loc_14029653F
0x1402964fe  xor     r9d, r9d; msWindowLength
0x140296501  xor     r8d, r8d; msPeriod
0x140296504  xor     edx, edx; pftDueTime
0x140296506  call    cs:__imp_SetThreadpoolTimer
0x14029650d  nop     dword ptr [rax+rax+00h]
0x140296512  mov     rcx, [rbx+60h]; pti
0x140296516  mov     edx, 1; fCancelPendingCallbacks
0x14029651b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140296522  nop     dword ptr [rax+rax+00h]
0x140296527  mov     rcx, [rbx+60h]; pti
0x14029652b  call    cs:__imp_CloseThreadpoolTimer
0x140296532  nop     dword ptr [rax+rax+00h]
0x140296537  mov     qword ptr [rbx+60h], 0
0x14029653f  add     rsp, 20h
0x140296543  pop     rbx
0x140296544  retn
```
