# ProcessRefCount::AddRef(void)

- ea: `0x180001230`
- end: `0x18000128d`
- name: `?AddRef@ProcessRefCount@@UEAAKXZ`
- size: `93`
- prototype: `unsigned int __fastcall(ProcessRefCount *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180001230`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180001250`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x180001250`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180001285`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180001285`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180001279`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180001279`

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
0x180001230  mov     [rsp+arg_0], rbx
0x180001235  push    rdi
0x180001236  sub     rsp, 20h
0x18000123a  xor     eax, eax
0x18000123c  mov     rdi, rcx
0x18000123f  xchg    eax, [rcx+8]
0x180001242  mov     rcx, [rcx+20h]; pti
0x180001246  mov     ebx, 1
0x18000124b  test    rcx, rcx
0x18000124e  jz      short loc_18000125A
0x180001250  call    cs:__imp_IsThreadpoolTimerSet
0x180001256  test    eax, eax
0x180001258  jnz     short loc_18000126D
0x18000125a  lock xadd [rdi+10h], ebx
0x18000125f  lea     eax, [rbx+1]
0x180001262  mov     rbx, [rsp+28h+arg_0]
0x180001267  add     rsp, 20h
0x18000126b  pop     rdi
0x18000126c  retn
0x18000126d  mov     rcx, [rdi+20h]; pti
0x180001271  xor     r9d, r9d; msWindowLength
0x180001274  xor     r8d, r8d; msPeriod
0x180001277  xor     edx, edx; pftDueTime
0x180001279  call    cs:__imp_SetThreadpoolTimer
0x18000127f  mov     rcx, [rdi+20h]; pti
0x180001283  mov     edx, ebx; fCancelPendingCallbacks
0x180001285  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000128b  jmp     short loc_18000125A
```
