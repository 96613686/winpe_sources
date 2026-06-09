# StateRepository::SRCacheContextCacheSingleton::Initialize(void)

- ea: `0x18000e55c`
- end: `0x18000e668`
- name: `?Initialize@SRCacheContextCacheSingleton@StateRepository@@SAJXZ`
- size: `268`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000b358`
- `0x18000ca00`
- `0x18000d560`

## callees

- `0x1800029dc`
- `0x180003d78`
- `0x180004650`
- `0x18000940c`
- `0x18000a8d4`
- `0x18000e488`
- `0x18000e4b4`
- `0x18000e55c`
- `0x18000e69c`

## string_xrefs

- `0x18000e5a4`: `onecore\base\appmodel\staterepository\core\lib\srcachecontextcachesingleton.cpp`
- `0x18000e644`: `onecore\base\appmodel\staterepository\core\lib\srcachecontextcachesingleton.cpp`

## pseudocode

```c
__int64 StateRepository::SRCacheContextCacheSingleton::Initialize(void)
{
  HKEY *v0; // rcx
  int v1; // eax
  unsigned int v2; // edx
  _QWORD *v3; // rax
  StateRepository::Time *v4; // rcx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v8; // [rsp+30h] [rbp+8h] BYREF

  wil::AcquireSRWLockExclusive(&v8, (RTL_SRWLOCK *)&StateRepository::SRCacheContextCacheSingleton::s_lock);
  if ( _InterlockedIncrement(&initializationCount) != 1 )
    goto LABEL_10;
  if ( StateRepository::SRCacheContextCacheSingleton::s_cache )
  {
    v1 = StateRepository::SRCacheContextCacheSingleton::Clear(v0);
    if ( v1 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x66,
        (int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontextcachesingleton.cpp",
        (const char *)(unsigned int)v1);
    if ( StateRepository::SRCacheContextCacheSingleton::s_cache )
      StateRepository::SRCacheContextCache::`scalar deleting destructor'(
        StateRepository::SRCacheContextCacheSingleton::s_cache,
        v2);
    StateRepository::SRCacheContextCacheSingleton::s_cache = 0;
  }
  v3 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v3 )
  {
    *v3 = 0;
    v3[1] = 0;
    v3[2] = 0;
    *((_BYTE *)v3 + 24) = 1;
    v3[4] = 0;
    v3[5] = 0;
    v3[6] = 0;
    StateRepository::SRCacheContextCacheSingleton::s_cache = (StateRepository::SRCacheContextCache *)v3;
    StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(v4);
LABEL_10:
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x6C,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontextcachesingleton.cpp",
    (const char *)0x8007000ELL,
    v6);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000e55c  sub     rsp, 28h
0x18000e560  lea     rdx, ?s_lock@SRCacheContextCacheSingleton@StateRepository@@0Vsrwlock@wil@@A; wil::srwlock StateRepository::SRCacheContextCacheSingleton::s_lock
0x18000e567  lea     rcx, [rsp+28h+arg_0]
0x18000e56c  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18000e571  mov     eax, 1
0x18000e576  lock xadd cs:?initializationCount@@3JC, eax; long volatile initializationCount
0x18000e57e  inc     eax
0x18000e580  cmp     eax, 1
0x18000e583  jnz     loc_18000E627
0x18000e589  cmp     cs:?s_cache@SRCacheContextCacheSingleton@StateRepository@@0PEAVSRCacheContextCache@2@EA, 0; StateRepository::SRCacheContextCache * StateRepository::SRCacheContextCacheSingleton::s_cache
0x18000e591  jz      short loc_18000E5D1
0x18000e593  call    ?Clear@SRCacheContextCacheSingleton@StateRepository@@SAJXZ; StateRepository::SRCacheContextCacheSingleton::Clear(void)
0x18000e598  mov     rcx, [rsp+28h]; this
0x18000e59d  test    eax, eax
0x18000e59f  jns     short loc_18000E5B5
0x18000e5a1  mov     r9d, eax; char *
0x18000e5a4  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\staterepositor"...
0x18000e5ab  mov     edx, 66h ; 'f'; void *
0x18000e5b0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000e5b5  mov     rcx, cs:?s_cache@SRCacheContextCacheSingleton@StateRepository@@0PEAVSRCacheContextCache@2@EA; this
0x18000e5bc  test    rcx, rcx
0x18000e5bf  jz      short loc_18000E5C6
0x18000e5c1  call    ??_GSRCacheContextCache@StateRepository@@QEAAPEAXI@Z; StateRepository::SRCacheContextCache::`scalar deleting destructor'(uint)
0x18000e5c6  mov     cs:?s_cache@SRCacheContextCacheSingleton@StateRepository@@0PEAVSRCacheContextCache@2@EA, 0; StateRepository::SRCacheContextCache * StateRepository::SRCacheContextCacheSingleton::s_cache
0x18000e5d1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000e5d8  mov     ecx, 38h ; '8'; unsigned __int64
0x18000e5dd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000e5e2  test    rax, rax
0x18000e5e5  jz      short loc_18000E639
0x18000e5e7  mov     qword ptr [rax], 0
0x18000e5ee  mov     qword ptr [rax+8], 0
0x18000e5f6  mov     qword ptr [rax+10h], 0
0x18000e5fe  mov     byte ptr [rax+18h], 1
0x18000e602  mov     qword ptr [rax+20h], 0
0x18000e60a  mov     qword ptr [rax+28h], 0
0x18000e612  mov     qword ptr [rax+30h], 0
0x18000e61a  mov     cs:?s_cache@SRCacheContextCacheSingleton@StateRepository@@0PEAVSRCacheContextCache@2@EA, rax; StateRepository::SRCacheContextCache * StateRepository::SRCacheContextCacheSingleton::s_cache
0x18000e621  call    ?QueryUnbiasedInterruptTimeAsMSec@Time@StateRepository@@YA_KXZ; StateRepository::Time::QueryUnbiasedInterruptTimeAsMSec(void)
0x18000e626  nop
0x18000e627  lea     rcx, [rsp+28h+arg_0]
0x18000e62c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e631  nop
0x18000e632  xor     eax, eax
0x18000e634  add     rsp, 28h
0x18000e638  retn
0x18000e639  mov     rcx, [rsp+28h]; this
0x18000e63e  mov     r9d, 8007000Eh; char *
0x18000e644  lea     r8, aOnecoreBaseApp_9; "onecore\\base\\appmodel\\staterepositor"...
0x18000e64b  mov     edx, 6Ch ; 'l'; void *
0x18000e650  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e655  nop
0x18000e656  lea     rcx, [rsp+28h+arg_0]
0x18000e65b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e660  nop
0x18000e661  mov     eax, 8007000Eh
0x18000e666  jmp     short loc_18000E634
```
