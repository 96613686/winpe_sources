# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000ae14`
- end: `0x18000aea2`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006578`
- `0x180006658`
- `0x180006738`
- `0x180006818`
- `0x1800068f8`
- `0x1800069d8`
- `0x180006ab8`
- `0x180006b98`
- `0x180006c78`
- `0x180006d58`
- `0x180006e38`
- `0x180006f18`
- `0x180008324`

## callees

- `0x180005764`
- `0x18000ae14`
- `0x18000bbb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ae39`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ae39`

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
    AcquireSRWLockExclusive(&stru_18006B450);
    v8 = &stru_18006B450;
    if ( !a3
      || a3 != dword_18006B464
      || (v6[1] = 0,
          v6[0] = a2,
          v7 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18006B488, v6, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  }
}

```

## disassembly

```asm
0x18000ae14  push    rbx
0x18000ae16  push    rbp
0x18000ae17  push    rsi
0x18000ae18  push    rdi
0x18000ae19  sub     rsp, 38h
0x18000ae1d  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ae23  mov     esi, r8d
0x18000ae26  mov     ebx, edx
0x18000ae28  mov     rdi, rcx
0x18000ae2b  test    eax, eax
0x18000ae2d  jz      short loc_18000AE99
0x18000ae2f  lea     rbp, stru_18006B450
0x18000ae36  mov     rcx, rbp; SRWLock
0x18000ae39  call    cs:__imp_AcquireSRWLockExclusive
0x18000ae3f  mov     eax, cs:dword_18006B464
0x18000ae45  mov     [rsp+58h+arg_18], rbp
0x18000ae4a  test    esi, esi
0x18000ae4c  jz      short loc_18000AE7E
0x18000ae4e  cmp     esi, eax
0x18000ae50  jnz     short loc_18000AE7E
0x18000ae52  mov     r8d, 10h; unsigned __int64
0x18000ae58  mov     [rsp+58h+var_34], 0
0x18000ae60  lea     rdx, [rsp+58h+var_38]; void *
0x18000ae65  mov     [rsp+58h+var_38], ebx
0x18000ae69  lea     rcx, qword_18006B488; this
0x18000ae70  mov     [rsp+58h+var_30], rdi
0x18000ae75  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000ae7a  test    al, al
0x18000ae7c  jnz     short loc_18000AE8F
0x18000ae7e  neg     ebx
0x18000ae80  sbb     eax, eax
0x18000ae82  and     eax, 83Ah
0x18000ae87  add     eax, 0FFFFF7C1h
0x18000ae8c  lock and [rdi], eax
0x18000ae8f  lea     rcx, [rsp+58h+arg_18]
0x18000ae94  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ae99  add     rsp, 38h
0x18000ae9d  pop     rdi
0x18000ae9e  pop     rsi
0x18000ae9f  pop     rbp
0x18000aea0  pop     rbx
0x18000aea1  retn
```
