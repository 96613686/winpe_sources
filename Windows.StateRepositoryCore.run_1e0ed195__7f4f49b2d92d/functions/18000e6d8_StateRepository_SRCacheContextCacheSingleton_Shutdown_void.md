# StateRepository::SRCacheContextCacheSingleton::Shutdown(void)

- ea: `0x18000e6d8`
- end: `0x18000e757`
- name: `?Shutdown@SRCacheContextCacheSingleton@StateRepository@@SAJXZ`
- size: `127`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000b358`
- `0x18000ca70`
- `0x18000d504`

## callees

- `0x180003d78`
- `0x180004650`
- `0x18000a8d4`
- `0x18000e488`
- `0x18000e4b4`
- `0x18000e6d8`

## string_xrefs

- `0x18000e718`: `onecore\base\appmodel\staterepository\core\lib\srcachecontextcachesingleton.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 StateRepository::SRCacheContextCacheSingleton::Shutdown(void)
{
  int v0; // eax
  unsigned int v1; // edx
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v5; // [rsp+38h] [rbp+10h] BYREF

  wil::AcquireSRWLockExclusive(&v5, &StateRepository::SRCacheContextCacheSingleton::s_lock);
  if ( _InterlockedExchangeAdd(&initializationCount, 0xFFFFFFFF) == 1
    && StateRepository::SRCacheContextCacheSingleton::s_cache )
  {
    v0 = StateRepository::SRCacheContextCacheSingleton::Clear();
    if ( v0 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x81,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontextcachesingleton.cpp",
        (const char *)(unsigned int)v0,
        v3);
    if ( StateRepository::SRCacheContextCacheSingleton::s_cache )
      StateRepository::SRCacheContextCache::`scalar deleting destructor'(
        StateRepository::SRCacheContextCacheSingleton::s_cache,
        v1);
    StateRepository::SRCacheContextCacheSingleton::s_cache = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
  return 0;
}

```

## disassembly

```asm
0x18000e6d8  sub     rsp, 28h
0x18000e6dc  lea     rdx, ?s_lock@SRCacheContextCacheSingleton@StateRepository@@0Vsrwlock@wil@@A; wil::srwlock StateRepository::SRCacheContextCacheSingleton::s_lock
0x18000e6e3  lea     rcx, [rsp+28h+arg_8]
0x18000e6e8  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18000e6ed  or      eax, 0FFFFFFFFh
0x18000e6f0  lock xadd cs:?initializationCount@@3JC, eax; long volatile initializationCount
0x18000e6f8  cmp     eax, 1
0x18000e6fb  jnz     short loc_18000E745
0x18000e6fd  cmp     cs:?s_cache@SRCacheContextCacheSingleton@StateRepository@@0PEAVSRCacheContextCache@2@EA, 0; StateRepository::SRCacheContextCache * StateRepository::SRCacheContextCacheSingleton::s_cache
0x18000e705  jz      short loc_18000E745
0x18000e707  call    ?Clear@SRCacheContextCacheSingleton@StateRepository@@SAJXZ; StateRepository::SRCacheContextCacheSingleton::Clear(void)
0x18000e70c  mov     rcx, [rsp+28h]; this
0x18000e711  test    eax, eax
0x18000e713  jns     short loc_18000E729
0x18000e715  mov     r9d, eax; char *
0x18000e718  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\staterepositor"...
0x18000e71f  mov     edx, 81h; void *
0x18000e724  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e729  mov     rcx, cs:?s_cache@SRCacheContextCacheSingleton@StateRepository@@0PEAVSRCacheContextCache@2@EA; this
0x18000e730  test    rcx, rcx
0x18000e733  jz      short loc_18000E73A
0x18000e735  call    ??_GSRCacheContextCache@StateRepository@@QEAAPEAXI@Z; StateRepository::SRCacheContextCache::`scalar deleting destructor'(uint)
0x18000e73a  mov     cs:?s_cache@SRCacheContextCacheSingleton@StateRepository@@0PEAVSRCacheContextCache@2@EA, 0; StateRepository::SRCacheContextCache * StateRepository::SRCacheContextCacheSingleton::s_cache
0x18000e745  lea     rcx, [rsp+28h+arg_8]
0x18000e74a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e74f  nop
0x18000e750  xor     eax, eax
0x18000e752  add     rsp, 28h
0x18000e756  retn
```
