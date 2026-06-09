# ProcessRefCount::AddRef(void)

- ea: `0x1800201d0`
- end: `0x180020224`
- name: `?AddRef@ProcessRefCount@@UEAAKXZ`
- size: `84`
- prototype: `__int64 __fastcall(ProcessRefCount *this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1800201d0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002020c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18002020c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800201fd`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800201fd`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1800201e7`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x1800201e7`

## pseudocode

```c
__int64 __fastcall ProcessRefCount::AddRef(ProcessRefCount *this)
{
  struct _TP_TIMER *v2; // rcx

  _InterlockedExchange((volatile __int32 *)this + 2, 0);
  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 4);
  if ( v2 && IsThreadpoolTimerSet(v2) )
  {
    SetThreadpoolTimer(*((PTP_TIMER *)this + 4), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 4), 1);
  }
  return (unsigned int)_InterlockedIncrement((volatile signed __int32 *)this + 4);
}

```

## disassembly

```asm
0x1800201d0  push    rbx
0x1800201d2  sub     rsp, 20h
0x1800201d6  xor     eax, eax
0x1800201d8  mov     rbx, rcx
0x1800201db  xchg    eax, [rcx+8]
0x1800201de  mov     rcx, [rcx+20h]; pti
0x1800201e2  test    rcx, rcx
0x1800201e5  jz      short loc_180020212
0x1800201e7  call    cs:__imp_IsThreadpoolTimerSet
0x1800201ed  test    eax, eax
0x1800201ef  jz      short loc_180020212
0x1800201f1  mov     rcx, [rbx+20h]; pti
0x1800201f5  xor     r9d, r9d; msWindowLength
0x1800201f8  xor     r8d, r8d; msPeriod
0x1800201fb  xor     edx, edx; pftDueTime
0x1800201fd  call    cs:__imp_SetThreadpoolTimer
0x180020203  mov     rcx, [rbx+20h]; pti
0x180020207  mov     edx, 1; fCancelPendingCallbacks
0x18002020c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180020212  mov     eax, 1
0x180020217  lock xadd [rbx+10h], eax
0x18002021c  inc     eax
0x18002021e  add     rsp, 20h
0x180020222  pop     rbx
0x180020223  retn
```
