# CTimer::_DestroyThreadPoolTimer(bool)

- ea: `0x18006ae70`
- end: `0x18006aede`
- name: `?_DestroyThreadPoolTimer@CTimer@@AEAAX_N@Z`
- size: `110`
- prototype: `void __fastcall(CTimer *__hidden this, bool)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180026e3c`
- `0x18006ae2c`

## callees

- `0x18006ae70`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006aec3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18006aec3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006aea7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18006aea7`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18006ae9a`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18006ae9a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006aed6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18006aed6`

## pseudocode

```c
void __fastcall CTimer::_DestroyThreadPoolTimer(CTimer *this, char a2)
{
  struct _TP_TIMER *v2; // rbx

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( v2
    && v2 == (struct _TP_TIMER *)_InterlockedCompareExchange64(
                                   (volatile signed __int64 *)this + 7,
                                   0,
                                   (signed __int64)v2) )
  {
    if ( IsThreadpoolTimerSet(v2) )
    {
      SetThreadpoolTimer(v2, 0, 0, 0);
      if ( a2 )
        WaitForThreadpoolTimerCallbacks(v2, 1);
    }
    CloseThreadpoolTimer(v2);
  }
}

```

## disassembly

```asm
0x18006ae70  mov     [rsp+arg_0], rbx
0x18006ae75  push    rdi
0x18006ae76  sub     rsp, 20h
0x18006ae7a  mov     rbx, [rcx+38h]
0x18006ae7e  mov     dil, dl
0x18006ae81  test    rbx, rbx
0x18006ae84  jz      short loc_18006AEAD
0x18006ae86  xor     r8d, r8d
0x18006ae89  mov     rax, rbx
0x18006ae8c  lock cmpxchg [rcx+38h], r8
0x18006ae92  cmp     rbx, rax
0x18006ae95  jnz     short loc_18006AEAD
0x18006ae97  mov     rcx, rbx; pti
0x18006ae9a  call    cs:__imp_IsThreadpoolTimerSet
0x18006aea0  test    eax, eax
0x18006aea2  jnz     short loc_18006AEB8
0x18006aea4  mov     rcx, rbx; pti
0x18006aea7  call    cs:__imp_CloseThreadpoolTimer
0x18006aead  mov     rbx, [rsp+28h+arg_0]
0x18006aeb2  add     rsp, 20h
0x18006aeb6  pop     rdi
0x18006aeb7  retn
0x18006aeb8  xor     r9d, r9d; msWindowLength
0x18006aebb  xor     r8d, r8d; msPeriod
0x18006aebe  xor     edx, edx; pftDueTime
0x18006aec0  mov     rcx, rbx; pti
0x18006aec3  call    cs:__imp_SetThreadpoolTimer
0x18006aec9  test    dil, dil
0x18006aecc  jz      short loc_18006AEA4
0x18006aece  mov     edx, 1; fCancelPendingCallbacks
0x18006aed3  mov     rcx, rbx; pti
0x18006aed6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18006aedc  jmp     short loc_18006AEA4
```
