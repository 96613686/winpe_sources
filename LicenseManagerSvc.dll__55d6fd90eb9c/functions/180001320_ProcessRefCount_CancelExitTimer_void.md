# ProcessRefCount::CancelExitTimer(void)

- ea: `0x180001320`
- end: `0x18000136a`
- name: `?CancelExitTimer@ProcessRefCount@@AEAAXXZ`
- size: `74`
- prototype: `void __fastcall(ProcessRefCount *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b50`

## callees

- `0x180001320`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180001337`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180001337`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180001362`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180001362`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180001353`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180001353`

## pseudocode

```c
void __fastcall ProcessRefCount::CancelExitTimer(ProcessRefCount *this)
{
  struct _TP_TIMER *v2; // rcx

  _InterlockedExchange((volatile __int32 *)this + 2, 0);
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 4);
  if ( v2 )
  {
    if ( IsThreadpoolTimerSet(v2) )
    {
      SetThreadpoolTimer(*((PTP_TIMER *)this + 4), 0, 0, 0);
      WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 4), 1);
    }
  }
}

```

## disassembly

```asm
0x180001320  push    rbx
0x180001322  sub     rsp, 20h
0x180001326  xor     eax, eax
0x180001328  mov     rbx, rcx
0x18000132b  xchg    eax, [rcx+8]
0x18000132e  mov     rcx, [rcx+20h]; pti
0x180001332  test    rcx, rcx
0x180001335  jz      short loc_180001341
0x180001337  call    cs:__imp_IsThreadpoolTimerSet
0x18000133d  test    eax, eax
0x18000133f  jnz     short loc_180001347
0x180001341  add     rsp, 20h
0x180001345  pop     rbx
0x180001346  retn
0x180001347  mov     rcx, [rbx+20h]; pti
0x18000134b  xor     r9d, r9d; msWindowLength
0x18000134e  xor     r8d, r8d; msPeriod
0x180001351  xor     edx, edx; pftDueTime
0x180001353  call    cs:__imp_SetThreadpoolTimer
0x180001359  mov     rcx, [rbx+20h]; pti
0x18000135d  mov     edx, 1; fCancelPendingCallbacks
0x180001362  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180001368  jmp     short loc_180001341
```
