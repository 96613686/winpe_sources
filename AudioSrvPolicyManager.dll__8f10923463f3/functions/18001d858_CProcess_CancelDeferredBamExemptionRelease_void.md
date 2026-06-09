# CProcess::CancelDeferredBamExemptionRelease(void)

- ea: `0x18001d858`
- end: `0x18001d893`
- name: `?CancelDeferredBamExemptionRelease@CProcess@@IEAAXXZ`
- size: `59`
- prototype: `void __fastcall(CProcess *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ecb0`

## callees

- `0x18001d858`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d875`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d875`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001d887`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001d887`

## pseudocode

```c
void __fastcall CProcess::CancelDeferredBamExemptionRelease(CProcess *this)
{
  struct _TP_TIMER *v2; // rcx

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 73);
  if ( v2 )
  {
    SetThreadpoolTimer(v2, 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 73), 1);
  }
}

```

## disassembly

```asm
0x18001d858  push    rbx
0x18001d85a  sub     rsp, 20h
0x18001d85e  mov     rbx, rcx
0x18001d861  mov     rcx, [rcx+248h]; pti
0x18001d868  test    rcx, rcx
0x18001d86b  jz      short loc_18001D88D
0x18001d86d  xor     r9d, r9d; msWindowLength
0x18001d870  xor     r8d, r8d; msPeriod
0x18001d873  xor     edx, edx; pftDueTime
0x18001d875  call    cs:__imp_SetThreadpoolTimer
0x18001d87b  mov     rcx, [rbx+248h]; pti
0x18001d882  mov     edx, 1; fCancelPendingCallbacks
0x18001d887  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001d88d  add     rsp, 20h
0x18001d891  pop     rbx
0x18001d892  retn
```
