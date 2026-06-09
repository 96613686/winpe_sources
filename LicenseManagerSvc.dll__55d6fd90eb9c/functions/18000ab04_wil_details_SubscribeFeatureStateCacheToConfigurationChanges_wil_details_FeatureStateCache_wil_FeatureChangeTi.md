# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000ab04`
- end: `0x18000ab92`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180008918`
- `0x1800089f8`
- `0x180008ad8`
- `0x180008bb8`
- `0x180008c98`
- `0x1800090fc`
- `0x18000c7b8`
- `0x18000c898`

## callees

- `0x180007f88`
- `0x18000ab04`
- `0x18000b418`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ab29`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ab29`

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
    AcquireSRWLockExclusive(&SRWLock);
    v9 = &SRWLock;
    if ( !a3
      || a3 != dword_18002159C
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800215C0, v7, 0x10u)) )
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
0x18000ab04  push    rbx
0x18000ab06  push    rbp
0x18000ab07  push    rsi
0x18000ab08  push    rdi
0x18000ab09  sub     rsp, 38h
0x18000ab0d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ab13  mov     esi, r8d
0x18000ab16  mov     ebx, edx
0x18000ab18  mov     rdi, rcx
0x18000ab1b  test    eax, eax
0x18000ab1d  jz      short loc_18000AB89
0x18000ab1f  lea     rbp, SRWLock
0x18000ab26  mov     rcx, rbp; SRWLock
0x18000ab29  call    cs:__imp_AcquireSRWLockExclusive
0x18000ab2f  mov     eax, cs:dword_18002159C
0x18000ab35  mov     [rsp+58h+arg_18], rbp
0x18000ab3a  test    esi, esi
0x18000ab3c  jz      short loc_18000AB6E
0x18000ab3e  cmp     esi, eax
0x18000ab40  jnz     short loc_18000AB6E
0x18000ab42  mov     r8d, 10h; unsigned __int64
0x18000ab48  mov     [rsp+58h+var_34], 0
0x18000ab50  lea     rdx, [rsp+58h+var_38]; void *
0x18000ab55  mov     [rsp+58h+var_38], ebx
0x18000ab59  lea     rcx, qword_1800215C0; this
0x18000ab60  mov     [rsp+58h+var_30], rdi
0x18000ab65  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000ab6a  test    al, al
0x18000ab6c  jnz     short loc_18000AB7F
0x18000ab6e  neg     ebx
0x18000ab70  sbb     eax, eax
0x18000ab72  and     eax, 83Ah
0x18000ab77  add     eax, 0FFFFF7C1h
0x18000ab7c  lock and [rdi], eax
0x18000ab7f  lea     rcx, [rsp+58h+arg_18]
0x18000ab84  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ab89  add     rsp, 38h
0x18000ab8d  pop     rdi
0x18000ab8e  pop     rsi
0x18000ab8f  pop     rbp
0x18000ab90  pop     rbx
0x18000ab91  retn
```
