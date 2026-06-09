# SRCacheContext_CacheReset

- ea: `0x18000ca10`
- end: `0x18000ca69`
- name: `SRCacheContext_CacheReset`
- size: `89`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x180003d78`
- `0x180004650`
- `0x18000a8d4`
- `0x18000ca10`
- `0x18000e4b4`
- `0x18000e69c`

## string_xrefs

- `0x18000ca40`: `onecore\base\appmodel\staterepository\core\lib\srcachecontextcachesingleton.cpp`

## pseudocode

```c
__int64 SRCacheContext_CacheReset()
{
  HKEY *v0; // rcx
  int v1; // eax
  StateRepository::Time *v2; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v5; // [rsp+30h] [rbp+8h] BYREF

  wil::AcquireSRWLockExclusive(&v5, (RTL_SRWLOCK *)&StateRepository::SRCacheContextCacheSingleton::s_lock);
  if ( StateRepository::SRCacheContextCacheSingleton::s_cache )
  {
    v1 = StateRepository::SRCacheContextCacheSingleton::Clear(v0);
    v2 = retaddr;
    if ( v1 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x91,
        (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontextcachesingleton.cpp",
        (const char *)(unsigned int)v1);
    StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v2);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
  return 0;
}

```

## disassembly

```asm
0x18000ca10  sub     rsp, 28h
0x18000ca14  lea     rdx, ?s_lock@SRCacheContextCacheSingleton@StateRepository@@0Vsrwlock@wil@@A; wil::srwlock StateRepository::SRCacheContextCacheSingleton::s_lock
0x18000ca1b  lea     rcx, [rsp+28h+arg_0]
0x18000ca20  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18000ca25  cmp     cs:?s_cache@SRCacheContextCacheSingleton@StateRepository@@0PEAVSRCacheContextCache@2@EA, 0; StateRepository::SRCacheContextCache * StateRepository::SRCacheContextCacheSingleton::s_cache
0x18000ca2d  jz      short loc_18000CA57
0x18000ca2f  call    ?Clear@SRCacheContextCacheSingleton@StateRepository@@SAJXZ; StateRepository::SRCacheContextCacheSingleton::Clear(void)
0x18000ca34  mov     rcx, [rsp+28h]; this
0x18000ca39  test    eax, eax
0x18000ca3b  jns     short loc_18000CA51
0x18000ca3d  mov     r9d, eax; char *
0x18000ca40  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\staterepositor"...
0x18000ca47  mov     edx, 91h; void *
0x18000ca4c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000ca51  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x18000ca56  nop
0x18000ca57  lea     rcx, [rsp+28h+arg_0]
0x18000ca5c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ca61  nop
0x18000ca62  xor     eax, eax
0x18000ca64  add     rsp, 28h
0x18000ca68  retn
```
