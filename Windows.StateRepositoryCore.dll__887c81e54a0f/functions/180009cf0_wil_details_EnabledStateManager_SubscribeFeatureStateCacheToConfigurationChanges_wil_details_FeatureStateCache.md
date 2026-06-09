# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180009cf0`
- end: `0x180009d71`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `129`
- prototype: `void __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006efc`

## callees

- `0x180003d78`
- `0x180004650`
- `0x180009cf0`
- `0x18000ad18`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  _DWORD v8[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v9; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v10; // [rsp+60h] [rbp+8h] BYREF

  if ( *(_DWORD *)a1 )
  {
    wil::AcquireSRWLockExclusive(&v10, (RTL_SRWLOCK *)(a1 + 8));
    if ( !a4
      || a4 != *(_DWORD *)(a1 + 28)
      || (v8[1] = 0, v8[0] = a3, v9 = a2, !wil::details_abi::heap_buffer::push_back((void **)(a1 + 64), v8, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x180009cf0  push    rbx
0x180009cf2  push    rbp
0x180009cf3  push    rsi
0x180009cf4  push    rdi
0x180009cf5  sub     rsp, 38h
0x180009cf9  mov     eax, [rcx]
0x180009cfb  mov     ebp, r9d
0x180009cfe  mov     ebx, r8d
0x180009d01  mov     rdi, rdx
0x180009d04  mov     rsi, rcx
0x180009d07  test    eax, eax
0x180009d09  jz      short loc_180009D68
0x180009d0b  lea     rdx, [rcx+8]
0x180009d0f  lea     rcx, [rsp+58h+arg_0]
0x180009d14  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180009d19  mov     eax, [rsi+1Ch]
0x180009d1c  test    ebp, ebp
0x180009d1e  jz      short loc_180009D4D
0x180009d20  cmp     ebp, eax
0x180009d22  jnz     short loc_180009D4D
0x180009d24  lea     rcx, [rsi+40h]; this
0x180009d28  mov     [rsp+58h+var_34], 0
0x180009d30  mov     r8d, 10h; unsigned __int64
0x180009d36  mov     [rsp+58h+var_38], ebx
0x180009d3a  lea     rdx, [rsp+58h+var_38]; void *
0x180009d3f  mov     [rsp+58h+var_30], rdi
0x180009d44  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180009d49  test    al, al
0x180009d4b  jnz     short loc_180009D5E
0x180009d4d  neg     ebx
0x180009d4f  sbb     eax, eax
0x180009d51  and     eax, 83Ah
0x180009d56  add     eax, 0FFFFF7C1h
0x180009d5b  lock and [rdi], eax
0x180009d5e  lea     rcx, [rsp+58h+arg_0]
0x180009d63  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009d68  add     rsp, 38h
0x180009d6c  pop     rdi
0x180009d6d  pop     rsi
0x180009d6e  pop     rbp
0x180009d6f  pop     rbx
0x180009d70  retn
```
