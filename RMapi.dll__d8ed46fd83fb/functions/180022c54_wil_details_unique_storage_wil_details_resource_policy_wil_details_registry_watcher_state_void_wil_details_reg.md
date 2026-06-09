# wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)

- ea: `0x180022c54`
- end: `0x180022cce`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z`
- size: `122`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x18000bc58`
- `0x18001eea8`
- `0x18002056c`

## callees

- `0x180006630`
- `0x180009098`
- `0x18000bdec`
- `0x180011904`
- `0x180022c00`
- `0x180022c54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022c7f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180022c7f`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
        __int64 *a1,
        __int64 a2)
{
  __int64 v2; // rdi
  unsigned int v5; // edx
  __int64 v6; // [rsp+20h] [rbp-38h] BYREF
  _BYTE v7[48]; // [rsp+28h] [rbp-30h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v7);
    AcquireSRWLockExclusive((PSRWLOCK)(v2 + 152));
    v6 = v2 + 152;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 148), 0xFFFFFFFF) == 1 )
    {
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(
        &v6,
        0);
      wil::details::registry_watcher_state::`scalar deleting destructor'((wil::details::registry_watcher_state *)v2, v5);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v7);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180022c54  push    rbx
0x180022c56  push    rbp
0x180022c57  push    rsi
0x180022c58  push    rdi
0x180022c59  sub     rsp, 38h
0x180022c5d  mov     rdi, [rcx]
0x180022c60  mov     rbp, rdx
0x180022c63  mov     rsi, rcx
0x180022c66  test    rdi, rdi
0x180022c69  jz      short loc_180022CC2
0x180022c6b  lea     rcx, [rsp+58h+var_30]; this
0x180022c70  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180022c75  lea     rbx, [rdi+98h]
0x180022c7c  mov     rcx, rbx; SRWLock
0x180022c7f  call    cs:__imp_AcquireSRWLockExclusive
0x180022c85  or      eax, 0FFFFFFFFh
0x180022c88  mov     [rsp+58h+var_38], rbx
0x180022c8d  lock xadd [rdi+94h], eax
0x180022c95  cmp     eax, 1
0x180022c98  jnz     short loc_180022CAE
0x180022c9a  xor     edx, edx
0x180022c9c  lea     rcx, [rsp+58h+var_38]
0x180022ca1  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180022ca6  mov     rcx, rdi; this
0x180022ca9  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180022cae  lea     rcx, [rsp+58h+var_38]
0x180022cb3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180022cb8  lea     rcx, [rsp+58h+var_30]; this
0x180022cbd  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180022cc2  mov     [rsi], rbp
0x180022cc5  add     rsp, 38h
0x180022cc9  pop     rdi
0x180022cca  pop     rsi
0x180022ccb  pop     rbp
0x180022ccc  pop     rbx
0x180022ccd  retn
```
