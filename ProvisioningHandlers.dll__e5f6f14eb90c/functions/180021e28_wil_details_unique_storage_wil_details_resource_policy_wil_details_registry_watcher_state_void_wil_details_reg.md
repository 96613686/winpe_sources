# wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(wil::details::registry_watcher_state *)

- ea: `0x180021e28`
- end: `0x180021eb0`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAUregistry_watcher_state@details@wil@@P6AXPEAU123@@Z$1?delete_registry_watcher_state@23@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU123@PEAU123@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUregistry_watcher_state@23@@Z`
- size: `136`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800114a0`
- `0x180020474`

## callees

- `0x180004394`
- `0x18000468c`
- `0x180004a90`
- `0x180011ff0`
- `0x180021dcc`
- `0x180021e28`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021e56`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180021e56`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<wil::details::registry_watcher_state *,void (*)(wil::details::registry_watcher_state *),&void wil::details::delete_registry_watcher_state(wil::details::registry_watcher_state *),wistd::integral_constant<unsigned __int64,2>,wil::details::registry_watcher_state *,wil::details::registry_watcher_state *,0,std::nullptr_t>>::reset(
        __int64 *a1,
        __int64 a2)
{
  __int64 v2; // rdi
  unsigned int v5; // edx
  __int64 v6; // [rsp+40h] [rbp+8h] BYREF
  char v7; // [rsp+48h] [rbp+10h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
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
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v7);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180021e28  mov     [rsp+arg_10], rbx
0x180021e2d  push    rbp
0x180021e2e  push    rsi
0x180021e2f  push    rdi
0x180021e30  sub     rsp, 20h
0x180021e34  mov     rdi, [rcx]
0x180021e37  mov     rbp, rdx
0x180021e3a  mov     rsi, rcx
0x180021e3d  test    rdi, rdi
0x180021e40  jz      short loc_180021E9F
0x180021e42  lea     rcx, [rsp+38h+arg_8]; this
0x180021e47  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180021e4c  lea     rbx, [rdi+98h]
0x180021e53  mov     rcx, rbx; SRWLock
0x180021e56  call    cs:__imp_AcquireSRWLockExclusive
0x180021e5d  nop     dword ptr [rax+rax+00h]
0x180021e62  or      eax, 0FFFFFFFFh
0x180021e65  mov     [rsp+38h+arg_0], rbx
0x180021e6a  lock xadd [rdi+94h], eax
0x180021e72  cmp     eax, 1
0x180021e75  jnz     short loc_180021E8B
0x180021e77  xor     edx, edx
0x180021e79  lea     rcx, [rsp+38h+arg_0]
0x180021e7e  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_RTL_SRWLOCK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::reset(_RTL_SRWLOCK *)
0x180021e83  mov     rcx, rdi; this
0x180021e86  call    ??_Gregistry_watcher_state@details@wil@@QEAAPEAXI@Z; wil::details::registry_watcher_state::`scalar deleting destructor'(uint)
0x180021e8b  lea     rcx, [rsp+38h+arg_0]
0x180021e90  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180021e95  lea     rcx, [rsp+38h+arg_8]; this
0x180021e9a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180021e9f  mov     rbx, [rsp+38h+arg_10]
0x180021ea4  mov     [rsi], rbp
0x180021ea7  add     rsp, 20h
0x180021eab  pop     rdi
0x180021eac  pop     rsi
0x180021ead  pop     rbp
0x180021eae  retn
```
