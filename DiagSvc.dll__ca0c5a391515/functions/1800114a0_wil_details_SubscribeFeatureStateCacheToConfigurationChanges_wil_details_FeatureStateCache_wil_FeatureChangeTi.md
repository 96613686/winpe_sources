# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800114a0`
- end: `0x18001152e`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000b584`
- `0x18000b664`
- `0x18000b744`
- `0x18000b824`
- `0x18000b904`
- `0x18000b9e4`
- `0x18000bac4`
- `0x18000bba4`
- `0x18000bc84`
- `0x18000bd64`
- `0x18000be44`
- `0x18000bf24`
- `0x18000d930`

## callees

- `0x180009edc`
- `0x1800114a0`
- `0x180012b98`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800114c5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800114c5`

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
      || a3 != dword_180039744
      || (v6[1] = 0,
          v6[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180039768, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x1800114a0  push    rbx
0x1800114a2  push    rbp
0x1800114a3  push    rsi
0x1800114a4  push    rdi
0x1800114a5  sub     rsp, 38h
0x1800114a9  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800114af  mov     esi, r8d
0x1800114b2  mov     ebx, edx
0x1800114b4  mov     rdi, rcx
0x1800114b7  test    eax, eax
0x1800114b9  jz      short loc_180011525
0x1800114bb  lea     rbp, SRWLock
0x1800114c2  mov     rcx, rbp; SRWLock
0x1800114c5  call    cs:__imp_AcquireSRWLockExclusive
0x1800114cb  mov     eax, cs:dword_180039744
0x1800114d1  mov     [rsp+58h+arg_18], rbp
0x1800114d6  test    esi, esi
0x1800114d8  jz      short loc_18001150A
0x1800114da  cmp     esi, eax
0x1800114dc  jnz     short loc_18001150A
0x1800114de  mov     r8d, 10h; unsigned __int64
0x1800114e4  mov     [rsp+58h+var_34], 0
0x1800114ec  lea     rdx, [rsp+58h+var_38]; void *
0x1800114f1  mov     [rsp+58h+var_38], ebx
0x1800114f5  lea     rcx, qword_180039768; this
0x1800114fc  mov     [rsp+58h+var_30], rdi
0x180011501  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180011506  test    al, al
0x180011508  jnz     short loc_18001151B
0x18001150a  neg     ebx
0x18001150c  sbb     eax, eax
0x18001150e  and     eax, 83Ah
0x180011513  add     eax, 0FFFFF7C1h
0x180011518  lock and [rdi], eax
0x18001151b  lea     rcx, [rsp+58h+arg_18]
0x180011520  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180011525  add     rsp, 38h
0x180011529  pop     rdi
0x18001152a  pop     rsi
0x18001152b  pop     rbp
0x18001152c  pop     rbx
0x18001152d  retn
```
