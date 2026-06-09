# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18003b548`
- end: `0x18003b5d7`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `143`
- prototype: ``
- caller_count: `10`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18003649c`
- `0x180036590`
- `0x180036704`
- `0x180036878`
- `0x1800369ec`
- `0x180036b60`
- `0x180036c54`
- `0x180036d48`
- `0x180036e3c`
- `0x180036f30`

## callees

- `0x18003368c`
- `0x18003b548`
- `0x18003c060`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x18003b570`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18003b570`

## pseudocode

```c
__int64 __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  __int64 result; // rax
  unsigned __int64 v7; // r8
  RTL_SRWLOCK *v8; // [rsp+20h] [rbp-38h] BYREF
  _DWORD Source[2]; // [rsp+28h] [rbp-30h] BYREF
  volatile signed __int32 *v10; // [rsp+30h] [rbp-28h]

  result = wil::details::g_enabledStateManager;
  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v8 = &SRWLock;
    if ( !a3
      || a3 != dword_18004A554
      || (Source[1] = 0,
          Source[0] = a2,
          v10 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18004A578, Source, v7)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
  return result;
}

```

## disassembly

```asm
0x18003b548  mov     [rsp+arg_10], rbx
0x18003b54d  push    rbp
0x18003b54e  push    rsi
0x18003b54f  push    rdi
0x18003b550  sub     rsp, 40h
0x18003b554  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18003b55a  mov     esi, r8d
0x18003b55d  mov     edi, edx
0x18003b55f  mov     rbx, rcx
0x18003b562  test    eax, eax
0x18003b564  jz      short loc_18003B5CA
0x18003b566  lea     rbp, SRWLock
0x18003b56d  mov     rcx, rbp; SRWLock
0x18003b570  call    cs:__imp_AcquireSRWLockExclusive
0x18003b576  mov     eax, cs:dword_18004A554
0x18003b57c  mov     [rsp+58h+var_38], rbp
0x18003b581  test    esi, esi
0x18003b583  jz      short loc_18003B5AF
0x18003b585  cmp     esi, eax
0x18003b587  jnz     short loc_18003B5AF
0x18003b589  lea     rdx, [rsp+58h+Source]; Source
0x18003b58e  mov     [rsp+58h+var_2C], 0
0x18003b596  lea     rcx, qword_18004A578; this
0x18003b59d  mov     [rsp+58h+Source], edi
0x18003b5a1  mov     [rsp+58h+var_28], rbx
0x18003b5a6  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003b5ab  test    al, al
0x18003b5ad  jnz     short loc_18003B5C0
0x18003b5af  neg     edi
0x18003b5b1  sbb     eax, eax
0x18003b5b3  and     eax, 83Ah
0x18003b5b8  add     eax, 0FFFFF7C1h
0x18003b5bd  lock and [rbx], eax
0x18003b5c0  lea     rcx, [rsp+58h+var_38]
0x18003b5c5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003b5ca  mov     rbx, [rsp+58h+arg_10]
0x18003b5cf  add     rsp, 40h
0x18003b5d3  pop     rdi
0x18003b5d4  pop     rsi
0x18003b5d5  pop     rbp
0x18003b5d6  retn
```
