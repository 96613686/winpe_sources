# Concurrency::details::GetSharedTimerQueue(void)

- ea: `0x18030e6b4`
- end: `0x18030e766`
- name: `?GetSharedTimerQueue@details@Concurrency@@YAPEAXXZ`
- size: `178`
- prototype: `void *__fastcall(Concurrency::details *__hidden this)`
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18030d698`
- `0x18030d9c0`
- `0x18030e630`
- `0x18030e830`
- `0x18030e9e0`
- `0x18030ec38`
- `0x18030f354`

## callees

- `0x1800370f0`
- `0x18030dca4`
- `0x18030e6b4`
- `0x180312b78`
- `0x18032b080`

## import_xrefs

- `KERNEL32!CreateTimerQueue` at `0x18030e6dd`
- `KERNEL32!CreateTimerQueue` at `0x18030e6dd`

## pseudocode

```c
void *__fastcall Concurrency::details::GetSharedTimerQueue(Concurrency::details *this, __int64 a2, __int64 a3)
{
  _BYTE v4[8]; // [rsp+20h] [rbp-38h] BYREF
  int v5; // [rsp+28h] [rbp-30h]
  void (__fastcall *v6)(Concurrency::details *__hidden); // [rsp+30h] [rbp-28h]
  _BYTE pExceptionObject[32]; // [rsp+38h] [rbp-20h] BYREF

  if ( (int)Concurrency::GetOSVersion(this, a2, a3) < 3 && !Concurrency::details::g_hTimerQueue )
  {
    if ( _InterlockedCompareExchange(&Concurrency::details::g_TimerQueueDemandInit, 1, 0) )
    {
      v5 = 0;
      v6 = Concurrency::details::_UnderlyingYield;
      while ( !Concurrency::details::g_hTimerQueue && Concurrency::details::g_TimerQueueDemandInit == 1 )
        Concurrency::details::_SpinWait<1>::_SpinOnce(v4);
    }
    else
    {
      Concurrency::details::g_hTimerQueue = CreateTimerQueue();
      if ( !Concurrency::details::g_hTimerQueue )
        _InterlockedExchange(&Concurrency::details::g_TimerQueueDemandInit, 0);
    }
    if ( !Concurrency::details::g_hTimerQueue )
    {
      std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject);
      throw (std::bad_alloc *)pExceptionObject;
    }
  }
  return Concurrency::details::g_hTimerQueue;
}

```

## disassembly

```asm
0x18030e6b4  push    rbx
0x18030e6b6  sub     rsp, 50h
0x18030e6ba  call    ?GetOSVersion@Concurrency@@YA?AW4OSVersion@IResourceManager@1@XZ; Concurrency::GetOSVersion(void)
0x18030e6bf  cmp     eax, 3
0x18030e6c2  jge     short loc_18030E73D
0x18030e6c4  mov     rax, cs:?g_hTimerQueue@details@Concurrency@@3REAXEA; void * Concurrency::details::g_hTimerQueue
0x18030e6cb  test    rax, rax
0x18030e6ce  jnz     short loc_18030E73D
0x18030e6d0  lea     ebx, [rax+1]
0x18030e6d3  lock cmpxchg cs:?g_TimerQueueDemandInit@details@Concurrency@@3JC, ebx; long volatile Concurrency::details::g_TimerQueueDemandInit
0x18030e6db  jnz     short loc_18030E6FE
0x18030e6dd  call    cs:__imp_CreateTimerQueue
0x18030e6e3  mov     cs:?g_hTimerQueue@details@Concurrency@@3REAXEA, rax; void * Concurrency::details::g_hTimerQueue
0x18030e6ea  mov     rax, cs:?g_hTimerQueue@details@Concurrency@@3REAXEA; void * Concurrency::details::g_hTimerQueue
0x18030e6f1  test    rax, rax
0x18030e6f4  jnz     short loc_18030E731
0x18030e6f6  xchg    eax, cs:?g_TimerQueueDemandInit@details@Concurrency@@3JC; long volatile Concurrency::details::g_TimerQueueDemandInit
0x18030e6fc  jmp     short loc_18030E731
0x18030e6fe  and     [rsp+58h+var_30], 0
0x18030e703  lea     rax, ?_UnderlyingYield@details@Concurrency@@YAXXZ; Concurrency::details::_UnderlyingYield(void)
0x18030e70a  mov     [rsp+58h+var_28], rax
0x18030e70f  jmp     short loc_18030E725
0x18030e711  mov     eax, cs:?g_TimerQueueDemandInit@details@Concurrency@@3JC; long volatile Concurrency::details::g_TimerQueueDemandInit
0x18030e717  cmp     eax, ebx
0x18030e719  jnz     short loc_18030E731
0x18030e71b  lea     rcx, [rsp+58h+var_38]
0x18030e720  call    ?_SpinOnce@?$_SpinWait@$00@details@Concurrency@@QEAA_NXZ; Concurrency::details::_SpinWait<1>::_SpinOnce(void)
0x18030e725  mov     rax, cs:?g_hTimerQueue@details@Concurrency@@3REAXEA; void * Concurrency::details::g_hTimerQueue
0x18030e72c  test    rax, rax
0x18030e72f  jz      short loc_18030E711
0x18030e731  mov     rax, cs:?g_hTimerQueue@details@Concurrency@@3REAXEA; void * Concurrency::details::g_hTimerQueue
0x18030e738  test    rax, rax
0x18030e73b  jz      short loc_18030E74A
0x18030e73d  mov     rax, cs:?g_hTimerQueue@details@Concurrency@@3REAXEA; void * Concurrency::details::g_hTimerQueue
0x18030e744  add     rsp, 50h
0x18030e748  pop     rbx
0x18030e749  retn
0x18030e74a  lea     rcx, [rsp+58h+pExceptionObject]; this
0x18030e74f  call    ??0bad_alloc@std@@QEAA@XZ; std::bad_alloc::bad_alloc(void)
0x18030e754  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18030e75b  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x18030e760  call    _CxxThrowException
```
