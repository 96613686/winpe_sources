# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180008794`
- end: `0x180008822`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: `void __fastcall(volatile signed __int32 *, int, int)`
- caller_count: `19`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006350`
- `0x18000c088`
- `0x18000c1dc`
- `0x18000c2bc`
- `0x18001172c`
- `0x1800149ac`
- `0x180014a8c`
- `0x180014b6c`
- `0x180014c4c`
- `0x180014da8`
- `0x180014f04`
- `0x180015060`
- `0x1800151bc`
- `0x180015318`
- `0x1800153f8`
- `0x1800154d8`
- `0x1800155b8`
- `0x180015698`
- `0x180015778`

## callees

- `0x18000490c`
- `0x180008794`
- `0x180009944`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800087b9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800087b9`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  _DWORD v6[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v7; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v8; // [rsp+78h] [rbp+20h] BYREF

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v8 = &SRWLock;
    if ( !a3
      || a3 != dword_180027694
      || (v6[1] = 0,
          v6[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800276B8, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x180008794  push    rbx
0x180008796  push    rbp
0x180008797  push    rsi
0x180008798  push    rdi
0x180008799  sub     rsp, 38h
0x18000879d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800087a3  mov     esi, r8d
0x1800087a6  mov     ebx, edx
0x1800087a8  mov     rdi, rcx
0x1800087ab  test    eax, eax
0x1800087ad  jz      short loc_180008819
0x1800087af  lea     rbp, SRWLock
0x1800087b6  mov     rcx, rbp; SRWLock
0x1800087b9  call    cs:__imp_AcquireSRWLockExclusive
0x1800087bf  mov     eax, cs:dword_180027694
0x1800087c5  mov     [rsp+58h+arg_18], rbp
0x1800087ca  test    esi, esi
0x1800087cc  jz      short loc_1800087FE
0x1800087ce  cmp     esi, eax
0x1800087d0  jnz     short loc_1800087FE
0x1800087d2  mov     r8d, 10h; unsigned __int64
0x1800087d8  mov     [rsp+58h+var_34], 0
0x1800087e0  lea     rdx, [rsp+58h+var_38]; void *
0x1800087e5  mov     [rsp+58h+var_38], ebx
0x1800087e9  lea     rcx, qword_1800276B8; this
0x1800087f0  mov     [rsp+58h+var_30], rdi
0x1800087f5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800087fa  test    al, al
0x1800087fc  jnz     short loc_18000880F
0x1800087fe  neg     ebx
0x180008800  sbb     eax, eax
0x180008802  and     eax, 83Ah
0x180008807  add     eax, 0FFFFF7C1h
0x18000880c  lock and [rdi], eax
0x18000880f  lea     rcx, [rsp+58h+arg_18]
0x180008814  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180008819  add     rsp, 38h
0x18000881d  pop     rdi
0x18000881e  pop     rsi
0x18000881f  pop     rbp
0x180008820  pop     rbx
0x180008821  retn
```
