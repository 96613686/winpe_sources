# SRCacheContext::AddToCache(SRCacheContext &,ushort const *)

- ea: `0x18000bfac`
- end: `0x18000c055`
- name: `?AddToCache@SRCacheContext@@QEAAJAEAU1@PEBG@Z`
- size: `169`
- prototype: `int(SRCacheContext *__hidden this, struct SRCacheContext *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18000c950`

## callees

- `0x180003d78`
- `0x180004650`
- `0x18000940c`
- `0x18000bfac`
- `0x18000f5c8`

## string_xrefs

- `0x18000bfd1`: `onecore\base\appmodel\staterepository\core\lib\srcachecontext.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SRCacheContext::AddToCache(
        SRCacheContext *this,
        struct SRCacheContext *a2,
        const unsigned __int16 *a3)
{
  int v5; // ebx
  __int64 v6; // rdx
  StateRepository::SRCacheContextCache *v8; // rcx
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  SRCacheContext *v11; // [rsp+30h] [rbp+8h] BYREF

  v11 = this;
  if ( !*(_QWORD *)a2 )
  {
    v5 = -2147024809;
    v6 = 49;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontext.cpp",
      (const char *)(unsigned int)v5,
      v9);
    return (unsigned int)v5;
  }
  wil::AcquireSRWLockExclusive(&v11, &StateRepository::SRCacheContextCacheSingleton::s_lock);
  if ( StateRepository::SRCacheContextCacheSingleton::s_cache && *(_QWORD *)a2 )
  {
    v5 = StateRepository::SRCacheContextCache::Add(v8, a3, a2);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
    if ( v5 < 0 )
    {
      v6 = 51;
      goto LABEL_3;
    }
  }
  else
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
  return 0;
}

```

## disassembly

```asm
0x18000bfac  mov     [rsp+arg_8], rbx
0x18000bfb1  mov     [rsp+arg_0], rcx
0x18000bfb6  push    rdi; int
0x18000bfb7  sub     rsp, 20h
0x18000bfbb  mov     rdi, r8
0x18000bfbe  mov     rbx, rdx
0x18000bfc1  cmp     qword ptr [rdx], 0
0x18000bfc5  jnz     short loc_18000BFE9
0x18000bfc7  mov     ebx, 80070057h
0x18000bfcc  mov     edx, 31h ; '1'; void *
0x18000bfd1  lea     r8, aOnecoreBaseApp_11; "onecore\\base\\appmodel\\staterepositor"...
0x18000bfd8  mov     r9d, ebx; char *
0x18000bfdb  mov     rcx, [rsp+28h]; this
0x18000bfe0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000bfe5  mov     eax, ebx
0x18000bfe7  jmp     short loc_18000C011
0x18000bfe9  lea     rdx, ?s_lock@SRCacheContextCacheSingleton@StateRepository@@0Vsrwlock@wil@@A; wil::srwlock StateRepository::SRCacheContextCacheSingleton::s_lock
0x18000bff0  lea     rcx, [rsp+28h+arg_0]
0x18000bff5  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18000bffa  cmp     cs:?s_cache@SRCacheContextCacheSingleton@StateRepository@@0PEAVSRCacheContextCache@2@EA, 0; StateRepository::SRCacheContextCache * StateRepository::SRCacheContextCacheSingleton::s_cache
0x18000c002  jnz     short loc_18000C01C
0x18000c004  lea     rcx, [rsp+28h+arg_0]
0x18000c009  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000c00e  nop
0x18000c00f  xor     eax, eax
0x18000c011  mov     rbx, [rsp+28h+arg_8]
0x18000c016  add     rsp, 20h
0x18000c01a  pop     rdi
0x18000c01b  retn
0x18000c01c  cmp     qword ptr [rbx], 0
0x18000c020  jnz     short loc_18000C02F
0x18000c022  lea     rcx, [rsp+28h+arg_0]
0x18000c027  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000c02c  nop
0x18000c02d  jmp     short loc_18000C00F
0x18000c02f  mov     r8, rbx; struct SRCacheContext *
0x18000c032  mov     rdx, rdi; unsigned __int16 *
0x18000c035  call    ?Add@SRCacheContextCache@StateRepository@@QEAAJPEBGAEAUSRCacheContext@@@Z; StateRepository::SRCacheContextCache::Add(ushort const *,SRCacheContext &)
0x18000c03a  mov     ebx, eax
0x18000c03c  lea     rcx, [rsp+28h+arg_0]
0x18000c041  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000c046  nop
0x18000c047  test    ebx, ebx
0x18000c049  jns     short loc_18000C00F
0x18000c04b  mov     edx, 33h ; '3'
0x18000c050  jmp     loc_18000BFD1
```
