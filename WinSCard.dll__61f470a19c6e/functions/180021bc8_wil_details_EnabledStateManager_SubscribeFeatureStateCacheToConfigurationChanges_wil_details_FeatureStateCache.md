# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180021bc8`
- end: `0x180021c4b`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `131`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180017c48`
- `0x180018170`
- `0x18001f528`

## callees

- `0x180018504`
- `0x18001b964`
- `0x180021bc8`
- `0x1800227b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        unsigned int *a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  __int64 result; // rax
  _DWORD v9[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v10; // [rsp+28h] [rbp-30h]
  char v11; // [rsp+60h] [rbp+8h] BYREF

  result = *a1;
  if ( (_DWORD)result )
  {
    wil::srwlock::lock_exclusive(a1 + 2, &v11);
    if ( !a4
      || a4 != a1[7]
      || (v9[1] = 0,
          v9[0] = a3,
          v10 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(a1 + 16), v9, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v11);
  }
  return result;
}

```

## disassembly

```asm
0x180021bc8  push    rbx
0x180021bca  push    rbp
0x180021bcb  push    rsi
0x180021bcc  push    rdi
0x180021bcd  sub     rsp, 38h
0x180021bd1  mov     ebp, r9d
0x180021bd4  mov     ebx, r8d
0x180021bd7  mov     rdi, rdx
0x180021bda  mov     rsi, rcx
0x180021bdd  mov     eax, [rcx]
0x180021bdf  test    eax, eax
0x180021be1  jz      short loc_180021C42
0x180021be3  add     rcx, 8
0x180021be7  lea     rdx, [rsp+58h+arg_0]
0x180021bec  call    ?lock_exclusive@srwlock@wil@@QEAA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@XZ; wil::srwlock::lock_exclusive(void)
0x180021bf1  nop
0x180021bf2  mov     eax, [rsi+1Ch]
0x180021bf5  test    ebp, ebp
0x180021bf7  jz      short loc_180021C26
0x180021bf9  cmp     ebp, eax
0x180021bfb  jnz     short loc_180021C26
0x180021bfd  mov     [rsp+58h+var_34], 0
0x180021c05  mov     [rsp+58h+var_38], ebx
0x180021c09  mov     [rsp+58h+var_30], rdi
0x180021c0e  lea     rcx, [rsi+40h]; this
0x180021c12  mov     r8d, 10h; unsigned __int64
0x180021c18  lea     rdx, [rsp+58h+var_38]; void *
0x180021c1d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180021c22  test    al, al
0x180021c24  jnz     short loc_180021C37
0x180021c26  neg     ebx
0x180021c28  sbb     eax, eax
0x180021c2a  and     eax, 83Ah
0x180021c2f  add     eax, 0FFFFF7C1h
0x180021c34  lock and [rdi], eax
0x180021c37  lea     rcx, [rsp+58h+arg_0]
0x180021c3c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180021c41  nop
0x180021c42  add     rsp, 38h
0x180021c46  pop     rdi
0x180021c47  pop     rsi
0x180021c48  pop     rbp
0x180021c49  pop     rbx
0x180021c4a  retn
```
