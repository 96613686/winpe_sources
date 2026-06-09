# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandMultilingualSupport>::GetCachedFeatureEnabledState(void)

- ea: `0x180014e84`
- end: `0x180014fbd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CommandMultilingualSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b084`
- `0x18001cf34`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180014e84`
- `0x180016fb8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014f42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014f42`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandMultilingualSupport>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  int v12; // r8d
  _QWORD v14[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_CommandMultilingualSupport__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CommandMultilingualSupport__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandMultilingualSupport>::GetCurrentFeatureEnabledState(
      v6,
      &v16,
      &v15);
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
             (volatile signed __int32 *)Feature_CommandMultilingualSupport__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_CommandMultilingualSupport__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_CommandMultilingualSupport__descriptor, 0xFFFFFFFB);
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
0x180014e84  mov     [rsp+arg_10], rbx
0x180014e89  mov     [rsp+arg_18], rbp
0x180014e8e  mov     [rsp+arg_0], rcx
0x180014e93  push    rsi
0x180014e94  push    rdi
0x180014e95  push    r14
0x180014e97  sub     rsp, 30h
0x180014e9b  mov     rsi, cs:Feature_CommandMultilingualSupport__descriptor
0x180014ea2  mov     rdi, rdx
0x180014ea5  mov     qword ptr [rdx], 0
0x180014eac  mov     eax, [rsi]
0x180014eae  mov     [rdx], eax
0x180014eb0  and     eax, 6
0x180014eb3  cmp     al, 6
0x180014eb5  jz      loc_180014FA7
0x180014ebb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014ec0  lea     r8, [rsp+48h+arg_0]
0x180014ec5  mov     dword ptr [rsp+48h+arg_0], 0
0x180014ecd  lea     rdx, [rsp+48h+arg_8]
0x180014ed2  mov     ebp, eax
0x180014ed4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CommandMultilingualSupport@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CommandMultilingualSupport>::GetCurrentFeatureEnabledState(int *)
0x180014ed9  mov     eax, [rdi]
0x180014edb  mov     rbx, [rsp+48h+arg_8]
0x180014ee0  cmp     dword ptr [rsp+48h+arg_0], 0
0x180014ee5  mov     edx, eax
0x180014ee7  mov     [rdi], eax
0x180014ee9  mov     ecx, eax
0x180014eeb  jz      short loc_180014F06
0x180014eed  test    dl, 2
0x180014ef0  jnz     short loc_180014F06
0x180014ef2  and     ecx, 0FFFFF63Eh
0x180014ef8  mov     eax, ebx
0x180014efa  and     eax, 9C1h
0x180014eff  or      ecx, eax
0x180014f01  or      ecx, 2
0x180014f04  mov     [rdi], ecx
0x180014f06  mov     r8d, edx
0x180014f09  and     r8d, 4
0x180014f0d  jnz     short loc_180014F21
0x180014f0f  btr     ecx, 0Ah
0x180014f13  mov     eax, ebx
0x180014f15  and     eax, 400h
0x180014f1a  or      ecx, eax
0x180014f1c  or      ecx, 4
0x180014f1f  mov     [rdi], ecx
0x180014f21  mov     eax, edx
0x180014f23  lock cmpxchg [rsi], ecx
0x180014f27  jnz     short loc_180014EE0
0x180014f29  test    r8d, r8d
0x180014f2c  jnz     short loc_180014F92
0x180014f2e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180014f34  test    eax, eax
0x180014f36  jz      short loc_180014F92
0x180014f38  lea     r14, SRWLock
0x180014f3f  mov     rcx, r14; SRWLock
0x180014f42  call    cs:__imp_AcquireSRWLockExclusive
0x180014f48  mov     eax, cs:dword_18002EED4
0x180014f4e  mov     [rsp+48h+arg_8], r14
0x180014f53  test    ebp, ebp
0x180014f55  jz      short loc_180014F84
0x180014f57  cmp     ebp, eax
0x180014f59  jnz     short loc_180014F84
0x180014f5b  mov     r8d, 10h; unsigned __int64
0x180014f61  mov     [rsp+48h+var_28], 3
0x180014f6a  lea     rdx, [rsp+48h+var_28]; void *
0x180014f6f  mov     [rsp+48h+var_20], rsi
0x180014f74  lea     rcx, qword_18002EEF8; this
0x180014f7b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180014f80  test    al, al
0x180014f82  jnz     short loc_180014F88
0x180014f84  lock and dword ptr [rsi], 0FFFFFFFBh
0x180014f88  lea     rcx, [rsp+48h+arg_8]
0x180014f8d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014f92  mov     eax, [rdi]
0x180014f94  test    al, 2
0x180014f96  jnz     short loc_180014FA7
0x180014f98  and     eax, 0FFFFF63Eh
0x180014f9d  and     ebx, 9C1h
0x180014fa3  or      eax, ebx
0x180014fa5  mov     [rdi], eax
0x180014fa7  mov     rbx, [rsp+48h+arg_10]
0x180014fac  mov     rax, rdi
0x180014faf  mov     rbp, [rsp+48h+arg_18]
0x180014fb4  add     rsp, 30h
0x180014fb8  pop     r14
0x180014fba  pop     rdi
0x180014fbb  pop     rsi
0x180014fbc  retn
```
