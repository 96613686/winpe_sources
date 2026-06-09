# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000d0e4`
- end: `0x18000d179`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `149`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000a1ac`
- `0x18000a2a0`
- `0x18000a87c`

## callees

- `0x180008eb8`
- `0x18000d0e4`
- `0x18000db4c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d10c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d10c`

## pseudocode

```c
void __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  RTL_SRWLOCK *v6; // [rsp+20h] [rbp-38h] BYREF
  _DWORD v7[2]; // [rsp+28h] [rbp-30h] BYREF
  volatile signed __int32 *v8; // [rsp+30h] [rbp-28h]

  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v6 = &SRWLock;
    if ( !a3
      || a3 != dword_180049394
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800493B8, v7, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
  }
}

```

## disassembly

```asm
0x18000d0e4  mov     [rsp+arg_10], rbx
0x18000d0e9  push    rbp
0x18000d0ea  push    rsi
0x18000d0eb  push    rdi
0x18000d0ec  sub     rsp, 40h
0x18000d0f0  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000d0f6  mov     esi, r8d
0x18000d0f9  mov     edi, edx
0x18000d0fb  mov     rbx, rcx
0x18000d0fe  test    eax, eax
0x18000d100  jz      short loc_18000D16C
0x18000d102  lea     rbp, SRWLock
0x18000d109  mov     rcx, rbp; SRWLock
0x18000d10c  call    cs:__imp_AcquireSRWLockExclusive
0x18000d112  mov     eax, cs:dword_180049394
0x18000d118  mov     [rsp+58h+var_38], rbp
0x18000d11d  test    esi, esi
0x18000d11f  jz      short loc_18000D151
0x18000d121  cmp     esi, eax
0x18000d123  jnz     short loc_18000D151
0x18000d125  mov     r8d, 10h; unsigned __int64
0x18000d12b  mov     [rsp+58h+var_2C], 0
0x18000d133  lea     rdx, [rsp+58h+var_30]; void *
0x18000d138  mov     [rsp+58h+var_30], edi
0x18000d13c  lea     rcx, qword_1800493B8; this
0x18000d143  mov     [rsp+58h+var_28], rbx
0x18000d148  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000d14d  test    al, al
0x18000d14f  jnz     short loc_18000D162
0x18000d151  neg     edi
0x18000d153  sbb     eax, eax
0x18000d155  and     eax, 83Ah
0x18000d15a  add     eax, 0FFFFF7C1h
0x18000d15f  lock and [rbx], eax
0x18000d162  lea     rcx, [rsp+58h+var_38]
0x18000d167  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000d16c  mov     rbx, [rsp+58h+arg_10]
0x18000d171  add     rsp, 40h
0x18000d175  pop     rdi
0x18000d176  pop     rsi
0x18000d177  pop     rbp
0x18000d178  retn
```
