# wil::details::FeatureImpl<__WilFeatureTraits_Feature_50284773>::GetCachedFeatureEnabledState(void)

- ea: `0x180013d3c`
- end: `0x180013e79`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_50284773@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `317`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a7bc`
- `0x18001cae8`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180013d3c`
- `0x180016324`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013e00`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013e00`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_50284773>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_50284773__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_50284773__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_50284773>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_50284773__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 0,
            v14[1] = Feature_50284773__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_50284773__descriptor, 0xFFFFF7C1);
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
0x180013d3c  mov     [rsp-28h+arg_10], rbx
0x180013d41  mov     [rsp-28h+arg_0], rcx
0x180013d46  push    rbp
0x180013d47  push    rsi
0x180013d48  push    rdi
0x180013d49  push    r14
0x180013d4b  push    r15
0x180013d4d  mov     rbp, rsp
0x180013d50  sub     rsp, 30h
0x180013d54  mov     rsi, cs:Feature_50284773__descriptor
0x180013d5b  mov     rdi, rdx
0x180013d5e  mov     qword ptr [rdx], 0
0x180013d65  mov     eax, [rsi]
0x180013d67  mov     [rdx], eax
0x180013d69  and     eax, 6
0x180013d6c  cmp     al, 6
0x180013d6e  jz      loc_180013E65
0x180013d74  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013d79  lea     r8, [rbp+arg_0]
0x180013d7d  mov     dword ptr [rbp+arg_0], 0
0x180013d84  lea     rdx, [rbp+arg_8]
0x180013d88  mov     r14d, eax
0x180013d8b  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_50284773@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_50284773>::GetCurrentFeatureEnabledState(int *)
0x180013d90  test    r14d, r14d
0x180013d93  jnz     short loc_180013D99
0x180013d95  mov     dword ptr [rbp+arg_0], r14d
0x180013d99  mov     eax, [rdi]
0x180013d9b  mov     rbx, [rbp+arg_8]
0x180013d9f  cmp     dword ptr [rbp+arg_0], 0
0x180013da3  mov     edx, eax
0x180013da5  mov     [rdi], eax
0x180013da7  mov     ecx, eax
0x180013da9  jz      short loc_180013DC4
0x180013dab  test    dl, 2
0x180013dae  jnz     short loc_180013DC4
0x180013db0  and     ecx, 0FFFFF63Eh
0x180013db6  mov     eax, ebx
0x180013db8  and     eax, 9C1h
0x180013dbd  or      ecx, eax
0x180013dbf  or      ecx, 2
0x180013dc2  mov     [rdi], ecx
0x180013dc4  mov     r8d, edx
0x180013dc7  and     r8d, 4
0x180013dcb  jnz     short loc_180013DDF
0x180013dcd  btr     ecx, 0Ah
0x180013dd1  mov     eax, ebx
0x180013dd3  and     eax, 400h
0x180013dd8  or      ecx, eax
0x180013dda  or      ecx, 4
0x180013ddd  mov     [rdi], ecx
0x180013ddf  mov     eax, edx
0x180013de1  lock cmpxchg [rsi], ecx
0x180013de5  jnz     short loc_180013D9F
0x180013de7  test    r8d, r8d
0x180013dea  jnz     short loc_180013E50
0x180013dec  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013df2  test    eax, eax
0x180013df4  jz      short loc_180013E50
0x180013df6  lea     r15, SRWLock
0x180013dfd  mov     rcx, r15; SRWLock
0x180013e00  call    cs:__imp_AcquireSRWLockExclusive
0x180013e06  mov     eax, cs:dword_18002EED4
0x180013e0c  mov     [rbp+arg_8], r15
0x180013e10  test    r14d, r14d
0x180013e13  jz      short loc_180013E40
0x180013e15  cmp     r14d, eax
0x180013e18  jnz     short loc_180013E40
0x180013e1a  mov     r8d, 10h; unsigned __int64
0x180013e20  mov     [rbp+var_10], 0
0x180013e28  lea     rdx, [rbp+var_10]; void *
0x180013e2c  mov     [rbp+var_8], rsi
0x180013e30  lea     rcx, qword_18002EEF8; this
0x180013e37  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180013e3c  test    al, al
0x180013e3e  jnz     short loc_180013E47
0x180013e40  lock and dword ptr [rsi], 0FFFFF7C1h
0x180013e47  lea     rcx, [rbp+arg_8]
0x180013e4b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013e50  mov     eax, [rdi]
0x180013e52  test    al, 2
0x180013e54  jnz     short loc_180013E65
0x180013e56  and     eax, 0FFFFF63Eh
0x180013e5b  and     ebx, 9C1h
0x180013e61  or      eax, ebx
0x180013e63  mov     [rdi], eax
0x180013e65  mov     rbx, [rsp+30h+arg_10]
0x180013e6a  mov     rax, rdi
0x180013e6d  add     rsp, 30h
0x180013e71  pop     r15
0x180013e73  pop     r14
0x180013e75  pop     rdi
0x180013e76  pop     rsi
0x180013e77  pop     rbp
0x180013e78  retn
```
