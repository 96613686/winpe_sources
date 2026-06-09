# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180019930`
- end: `0x1800199be`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `24`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800110e0`
- `0x180011ae0`
- `0x180013240`
- `0x180013410`
- `0x180019f98`
- `0x18002062c`
- `0x18002070c`
- `0x1800208ac`
- `0x180020a58`
- `0x180020bb8`
- `0x180020d18`
- `0x180020e78`
- `0x180020fd8`
- `0x1800210b8`
- `0x180021210`
- `0x1800212f0`
- `0x1800213d0`
- `0x1800214b0`
- `0x180021590`
- `0x180021670`
- `0x180021750`
- `0x180021830`
- `0x18002caec`
- `0x18002dd4c`

## callees

- `0x1800138cc`
- `0x180018434`
- `0x180019930`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019955`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019955`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD Source[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v8; // [rsp+78h] [rbp+20h] BYREF

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v8 = &SRWLock;
    if ( !a3
      || a3 != dword_180041864
      || (Source[1] = 0,
          Source[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180041888, Source, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x180019930  push    rbx
0x180019932  push    rbp
0x180019933  push    rsi
0x180019934  push    rdi
0x180019935  sub     rsp, 38h
0x180019939  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001993f  mov     esi, r8d
0x180019942  mov     ebx, edx
0x180019944  mov     rdi, rcx
0x180019947  test    eax, eax
0x180019949  jz      short loc_1800199B5
0x18001994b  lea     rbp, SRWLock
0x180019952  mov     rcx, rbp; SRWLock
0x180019955  call    cs:__imp_AcquireSRWLockExclusive
0x18001995b  mov     eax, cs:dword_180041864
0x180019961  mov     [rsp+58h+arg_18], rbp
0x180019966  test    esi, esi
0x180019968  jz      short loc_18001999A
0x18001996a  cmp     esi, eax
0x18001996c  jnz     short loc_18001999A
0x18001996e  mov     r8d, 10h; SourceSize
0x180019974  mov     [rsp+58h+var_34], 0
0x18001997c  lea     rdx, [rsp+58h+Source]; Source
0x180019981  mov     [rsp+58h+Source], ebx
0x180019985  lea     rcx, qword_180041888; this
0x18001998c  mov     [rsp+58h+var_30], rdi
0x180019991  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180019996  test    al, al
0x180019998  jnz     short loc_1800199AB
0x18001999a  neg     ebx
0x18001999c  sbb     eax, eax
0x18001999e  and     eax, 83Ah
0x1800199a3  add     eax, 0FFFFF7C1h
0x1800199a8  lock and [rdi], eax
0x1800199ab  lea     rcx, [rsp+58h+arg_18]
0x1800199b0  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800199b5  add     rsp, 38h
0x1800199b9  pop     rdi
0x1800199ba  pop     rsi
0x1800199bb  pop     rbp
0x1800199bc  pop     rbx
0x1800199bd  retn
```
