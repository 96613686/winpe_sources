# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudEyeControlSettingsRestore>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f7e8`
- end: `0x18001f925`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudEyeControlSettingsRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021034`

## callees

- `0x18001b3fc`
- `0x18001f3e4`
- `0x18001f7e8`
- `0x18001fcf8`
- `0x180024b94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f8ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001f8ac`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudEyeControlSettingsRestore>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // r14d
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  int v12; // r8d
  _QWORD v14[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details *v15; // [rsp+60h] [rbp+30h] BYREF
  RTL_SRWLOCK *v16; // [rsp+68h] [rbp+38h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_CloudEyeControlSettingsRestore__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CloudEyeControlSettingsRestore__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudEyeControlSettingsRestore>::GetCurrentFeatureEnabledState(
      v6,
      &v16,
      &v15);
    if ( !v5 )
      LODWORD(v15) = 0;
    v7 = *(_DWORD *)a2;
    v8 = (__int16)v16;
    do
    {
      v9 = (_DWORD)v15 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      v12 = v7 & 4;
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_CloudEyeControlSettingsRestore__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800439BC
        || (v14[0] = 0,
            v14[1] = Feature_CloudEyeControlSettingsRestore__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800439E0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_CloudEyeControlSettingsRestore__descriptor, 0xFFFFF7C1);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001f7e8  mov     [rsp-28h+arg_10], rbx
0x18001f7ed  mov     [rsp-28h+arg_0], rcx
0x18001f7f2  push    rbp
0x18001f7f3  push    rsi
0x18001f7f4  push    rdi
0x18001f7f5  push    r14
0x18001f7f7  push    r15
0x18001f7f9  mov     rbp, rsp
0x18001f7fc  sub     rsp, 30h
0x18001f800  mov     rsi, cs:Feature_CloudEyeControlSettingsRestore__descriptor
0x18001f807  mov     rdi, rdx
0x18001f80a  mov     qword ptr [rdx], 0
0x18001f811  mov     eax, [rsi]
0x18001f813  mov     [rdx], eax
0x18001f815  and     eax, 6
0x18001f818  cmp     al, 6
0x18001f81a  jz      loc_18001F911
0x18001f820  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f825  lea     r8, [rbp+arg_0]
0x18001f829  mov     dword ptr [rbp+arg_0], 0
0x18001f830  lea     rdx, [rbp+arg_8]
0x18001f834  mov     r14d, eax
0x18001f837  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CloudEyeControlSettingsRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CloudEyeControlSettingsRestore>::GetCurrentFeatureEnabledState(int *)
0x18001f83c  test    r14d, r14d
0x18001f83f  jnz     short loc_18001F845
0x18001f841  mov     dword ptr [rbp+arg_0], r14d
0x18001f845  mov     eax, [rdi]
0x18001f847  mov     rbx, [rbp+arg_8]
0x18001f84b  cmp     dword ptr [rbp+arg_0], 0
0x18001f84f  mov     edx, eax
0x18001f851  mov     [rdi], eax
0x18001f853  mov     ecx, eax
0x18001f855  jz      short loc_18001F870
0x18001f857  test    dl, 2
0x18001f85a  jnz     short loc_18001F870
0x18001f85c  and     ecx, 0FFFFF63Eh
0x18001f862  mov     eax, ebx
0x18001f864  and     eax, 9C1h
0x18001f869  or      ecx, eax
0x18001f86b  or      ecx, 2
0x18001f86e  mov     [rdi], ecx
0x18001f870  mov     r8d, edx
0x18001f873  and     r8d, 4
0x18001f877  jnz     short loc_18001F88B
0x18001f879  btr     ecx, 0Ah
0x18001f87d  mov     eax, ebx
0x18001f87f  and     eax, 400h
0x18001f884  or      ecx, eax
0x18001f886  or      ecx, 4
0x18001f889  mov     [rdi], ecx
0x18001f88b  mov     eax, edx
0x18001f88d  lock cmpxchg [rsi], ecx
0x18001f891  jnz     short loc_18001F84B
0x18001f893  test    r8d, r8d
0x18001f896  jnz     short loc_18001F8FC
0x18001f898  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001f89e  test    eax, eax
0x18001f8a0  jz      short loc_18001F8FC
0x18001f8a2  lea     r15, SRWLock
0x18001f8a9  mov     rcx, r15; SRWLock
0x18001f8ac  call    cs:__imp_AcquireSRWLockExclusive
0x18001f8b2  mov     eax, cs:dword_1800439BC
0x18001f8b8  mov     [rbp+arg_8], r15
0x18001f8bc  test    r14d, r14d
0x18001f8bf  jz      short loc_18001F8EC
0x18001f8c1  cmp     r14d, eax
0x18001f8c4  jnz     short loc_18001F8EC
0x18001f8c6  mov     r8d, 10h; unsigned __int64
0x18001f8cc  mov     [rbp+var_10], 0
0x18001f8d4  lea     rdx, [rbp+var_10]; void *
0x18001f8d8  mov     [rbp+var_8], rsi
0x18001f8dc  lea     rcx, qword_1800439E0; this
0x18001f8e3  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001f8e8  test    al, al
0x18001f8ea  jnz     short loc_18001F8F3
0x18001f8ec  lock and dword ptr [rsi], 0FFFFF7C1h
0x18001f8f3  lea     rcx, [rbp+arg_8]
0x18001f8f7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001f8fc  mov     eax, [rdi]
0x18001f8fe  test    al, 2
0x18001f900  jnz     short loc_18001F911
0x18001f902  and     eax, 0FFFFF63Eh
0x18001f907  and     ebx, 9C1h
0x18001f90d  or      eax, ebx
0x18001f90f  mov     [rdi], eax
0x18001f911  mov     rbx, [rsp+30h+arg_10]
0x18001f916  mov     rax, rdi
0x18001f919  add     rsp, 30h
0x18001f91d  pop     r15
0x18001f91f  pop     r14
0x18001f921  pop     rdi
0x18001f922  pop     rsi
0x18001f923  pop     rbp
0x18001f924  retn
```
