# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800099b4`
- end: `0x180009a42`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: ``
- caller_count: `8`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000765c`
- `0x180010870`
- `0x180010950`
- `0x180010a30`
- `0x180010b10`
- `0x18001eec0`
- `0x18001efa0`
- `0x18001f080`

## callees

- `0x180005568`
- `0x1800099b4`
- `0x18000ab3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800099d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800099d9`

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
      || a3 != dword_18002F324
      || (v6[1] = 0,
          v6[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002F348, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x1800099b4  push    rbx
0x1800099b6  push    rbp
0x1800099b7  push    rsi
0x1800099b8  push    rdi
0x1800099b9  sub     rsp, 38h
0x1800099bd  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800099c3  mov     esi, r8d
0x1800099c6  mov     ebx, edx
0x1800099c8  mov     rdi, rcx
0x1800099cb  test    eax, eax
0x1800099cd  jz      short loc_180009A39
0x1800099cf  lea     rbp, SRWLock
0x1800099d6  mov     rcx, rbp; SRWLock
0x1800099d9  call    cs:__imp_AcquireSRWLockExclusive
0x1800099df  mov     eax, cs:dword_18002F324
0x1800099e5  mov     [rsp+58h+arg_18], rbp
0x1800099ea  test    esi, esi
0x1800099ec  jz      short loc_180009A1E
0x1800099ee  cmp     esi, eax
0x1800099f0  jnz     short loc_180009A1E
0x1800099f2  mov     r8d, 10h; unsigned __int64
0x1800099f8  mov     [rsp+58h+var_34], 0
0x180009a00  lea     rdx, [rsp+58h+var_38]; void *
0x180009a05  mov     [rsp+58h+var_38], ebx
0x180009a09  lea     rcx, qword_18002F348; this
0x180009a10  mov     [rsp+58h+var_30], rdi
0x180009a15  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180009a1a  test    al, al
0x180009a1c  jnz     short loc_180009A2F
0x180009a1e  neg     ebx
0x180009a20  sbb     eax, eax
0x180009a22  and     eax, 83Ah
0x180009a27  add     eax, 0FFFFF7C1h
0x180009a2c  lock and [rdi], eax
0x180009a2f  lea     rcx, [rsp+58h+arg_18]
0x180009a34  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009a39  add     rsp, 38h
0x180009a3d  pop     rdi
0x180009a3e  pop     rsi
0x180009a3f  pop     rbp
0x180009a40  pop     rbx
0x180009a41  retn
```
