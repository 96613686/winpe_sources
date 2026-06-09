# StateRepository::SRCacheContextCacheSingleton::Get(ushort const *,SRCacheContext &,Common::RegistryKey &)

- ea: `0x18000e4c0`
- end: `0x18000e554`
- name: `?Get@SRCacheContextCacheSingleton@StateRepository@@SAJPEBGAEAUSRCacheContext@@AEAVRegistryKey@Common@@@Z`
- size: `148`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct SRCacheContext *, struct Common::RegistryKey *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c05c`
- `0x18000c430`

## callees

- `0x180003d78`
- `0x180004650`
- `0x18000be00`
- `0x18000e4c0`
- `0x18000f880`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StateRepository::SRCacheContextCacheSingleton::Get(
        const unsigned __int16 *a1,
        struct SRCacheContext *a2,
        HKEY *a3)
{
  StateRepository::SRCacheContextCache *v6; // rcx
  struct SRCacheContext *v7; // rax
  HKEY v8; // rbx
  char v10; // [rsp+48h] [rbp+20h] BYREF

  wil::AcquireSRWLockExclusive(&v10, &StateRepository::SRCacheContextCacheSingleton::s_lock);
  if ( StateRepository::SRCacheContextCacheSingleton::s_cache )
  {
    v7 = StateRepository::SRCacheContextCache::Get(v6, a1, a2);
    if ( v7 )
    {
      v8 = *(HKEY *)v7;
      *(_QWORD *)v7 = 0;
      if ( *a3 != v8 )
      {
        Common::AutoHandleCloseHKEY<HKEY__ *>(*a3);
        *a3 = v8;
      }
    }
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  return 0;
}

```

## disassembly

```asm
0x18000e4c0  mov     [rsp+arg_0], rbx
0x18000e4c5  mov     [rsp+arg_8], rsi
0x18000e4ca  push    rdi
0x18000e4cb  sub     rsp, 20h
0x18000e4cf  mov     rdi, r8
0x18000e4d2  mov     rbx, rdx
0x18000e4d5  mov     rsi, rcx
0x18000e4d8  lea     rdx, ?s_lock@SRCacheContextCacheSingleton@StateRepository@@0Vsrwlock@wil@@A; wil::srwlock StateRepository::SRCacheContextCacheSingleton::s_lock
0x18000e4df  lea     rcx, [rsp+28h+arg_18]
0x18000e4e4  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18000e4e9  cmp     cs:?s_cache@SRCacheContextCacheSingleton@StateRepository@@0PEAVSRCacheContextCache@2@EA, 0; StateRepository::SRCacheContextCache * StateRepository::SRCacheContextCacheSingleton::s_cache
0x18000e4f1  jnz     short loc_18000E500
0x18000e4f3  lea     rcx, [rsp+28h+arg_18]
0x18000e4f8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e4fd  nop
0x18000e4fe  jmp     short loc_18000E542
0x18000e500  mov     r8, rbx; struct SRCacheContext *
0x18000e503  mov     rdx, rsi; unsigned __int16 *
0x18000e506  call    ?Get@SRCacheContextCache@StateRepository@@QEAAPEAUSRCacheContext@@PEBGAEAU3@@Z; StateRepository::SRCacheContextCache::Get(ushort const *,SRCacheContext &)
0x18000e50b  test    rax, rax
0x18000e50e  jnz     short loc_18000E51D
0x18000e510  lea     rcx, [rsp+28h+arg_18]
0x18000e515  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e51a  nop
0x18000e51b  jmp     short loc_18000E542
0x18000e51d  mov     rbx, [rax]
0x18000e520  mov     qword ptr [rax], 0
0x18000e527  cmp     [rdi], rbx
0x18000e52a  jz      short loc_18000E537
0x18000e52c  mov     rcx, [rdi]
0x18000e52f  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000e534  mov     [rdi], rbx
0x18000e537  lea     rcx, [rsp+28h+arg_18]
0x18000e53c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000e541  nop
0x18000e542  xor     eax, eax
0x18000e544  mov     rbx, [rsp+28h+arg_0]
0x18000e549  mov     rsi, [rsp+28h+arg_8]
0x18000e54e  add     rsp, 20h
0x18000e552  pop     rdi
0x18000e553  retn
```
