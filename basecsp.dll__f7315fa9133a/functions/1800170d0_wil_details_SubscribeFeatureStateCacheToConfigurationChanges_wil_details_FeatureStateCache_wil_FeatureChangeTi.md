# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800170d0`
- end: `0x18001715e`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: ``
- caller_count: `18`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000df60`
- `0x18000e040`
- `0x18000e120`
- `0x18000e200`
- `0x18000e2e0`
- `0x18000e3c0`
- `0x18000e4a0`
- `0x18000e580`
- `0x18000e660`
- `0x18000e740`
- `0x18000e820`
- `0x18000e900`
- `0x18000e9e0`
- `0x18000eac0`
- `0x18001054c`
- `0x18001f444`
- `0x18001f524`
- `0x18001f67c`

## callees

- `0x18000bc80`
- `0x1800170d0`
- `0x180018d34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800170f5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800170f5`

## pseudocode

```c
__int64 __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  __int64 result; // rax
  _DWORD v7[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v8; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v9; // [rsp+78h] [rbp+20h] BYREF

  result = wil::details::g_enabledStateManager;
  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&stru_18003B5D8);
    v9 = &stru_18003B5D8;
    if ( !a3
      || a3 != dword_18003B5EC
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18003B610, v7, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
  return result;
}

```

## disassembly

```asm
0x1800170d0  push    rbx
0x1800170d2  push    rbp
0x1800170d3  push    rsi
0x1800170d4  push    rdi
0x1800170d5  sub     rsp, 38h
0x1800170d9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800170df  mov     esi, r8d
0x1800170e2  mov     ebx, edx
0x1800170e4  mov     rdi, rcx
0x1800170e7  test    eax, eax
0x1800170e9  jz      short loc_180017155
0x1800170eb  lea     rbp, stru_18003B5D8
0x1800170f2  mov     rcx, rbp; SRWLock
0x1800170f5  call    cs:__imp_AcquireSRWLockExclusive
0x1800170fb  mov     eax, cs:dword_18003B5EC
0x180017101  mov     [rsp+58h+arg_18], rbp
0x180017106  test    esi, esi
0x180017108  jz      short loc_18001713A
0x18001710a  cmp     esi, eax
0x18001710c  jnz     short loc_18001713A
0x18001710e  mov     r8d, 10h; unsigned __int64
0x180017114  mov     [rsp+58h+var_34], 0
0x18001711c  lea     rdx, [rsp+58h+var_38]; void *
0x180017121  mov     [rsp+58h+var_38], ebx
0x180017125  lea     rcx, qword_18003B610; this
0x18001712c  mov     [rsp+58h+var_30], rdi
0x180017131  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180017136  test    al, al
0x180017138  jnz     short loc_18001714B
0x18001713a  neg     ebx
0x18001713c  sbb     eax, eax
0x18001713e  and     eax, 83Ah
0x180017143  add     eax, 0FFFFF7C1h
0x180017148  lock and [rdi], eax
0x18001714b  lea     rcx, [rsp+58h+arg_18]
0x180017150  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180017155  add     rsp, 38h
0x180017159  pop     rdi
0x18001715a  pop     rsi
0x18001715b  pop     rbp
0x18001715c  pop     rbx
0x18001715d  retn
```
