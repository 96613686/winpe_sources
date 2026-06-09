# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetCachedFeatureEnabledState(void)

- ea: `0x180011dd8`
- end: `0x180011f11`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012388`
- `0x180014094`
- `0x1800140d4`

## callees

- `0x180004e64`
- `0x180005a7c`
- `0x180009f20`
- `0x180011dd8`
- `0x180012058`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011e96`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011e96`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180024B2C
        || (v14[0] = 3,
            v14[1] = Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180024B50, v14, 0x10u)) )
      {
        _InterlockedAnd(
          (volatile signed __int32 *)Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor,
          0xFFFFFFFB);
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
0x180011dd8  mov     [rsp+arg_10], rbx
0x180011ddd  mov     [rsp+arg_18], rbp
0x180011de2  mov     [rsp+arg_0], rcx
0x180011de7  push    rsi
0x180011de8  push    rdi
0x180011de9  push    r14
0x180011deb  sub     rsp, 30h
0x180011def  mov     rsi, cs:Feature_Print_PlatformStabilizationFixes_2026_Wave1__descriptor
0x180011df6  mov     rdi, rdx
0x180011df9  mov     qword ptr [rdx], 0
0x180011e00  mov     eax, [rsi]
0x180011e02  mov     [rdx], eax
0x180011e04  and     eax, 6
0x180011e07  cmp     al, 6
0x180011e09  jz      loc_180011EFB
0x180011e0f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180011e14  lea     r8, [rsp+48h+arg_0]
0x180011e19  mov     dword ptr [rsp+48h+arg_0], 0
0x180011e21  lea     rdx, [rsp+48h+arg_8]
0x180011e26  mov     ebp, eax
0x180011e28  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave1>::GetCurrentFeatureEnabledState(int *)
0x180011e2d  mov     eax, [rdi]
0x180011e2f  mov     rbx, [rsp+48h+arg_8]
0x180011e34  cmp     dword ptr [rsp+48h+arg_0], 0
0x180011e39  mov     edx, eax
0x180011e3b  mov     [rdi], eax
0x180011e3d  mov     ecx, eax
0x180011e3f  jz      short loc_180011E5A
0x180011e41  test    dl, 2
0x180011e44  jnz     short loc_180011E5A
0x180011e46  and     ecx, 0FFFFF63Eh
0x180011e4c  mov     eax, ebx
0x180011e4e  and     eax, 9C1h
0x180011e53  or      ecx, eax
0x180011e55  or      ecx, 2
0x180011e58  mov     [rdi], ecx
0x180011e5a  mov     r8d, edx
0x180011e5d  and     r8d, 4
0x180011e61  jnz     short loc_180011E75
0x180011e63  btr     ecx, 0Ah
0x180011e67  mov     eax, ebx
0x180011e69  and     eax, 400h
0x180011e6e  or      ecx, eax
0x180011e70  or      ecx, 4
0x180011e73  mov     [rdi], ecx
0x180011e75  mov     eax, edx
0x180011e77  lock cmpxchg [rsi], ecx
0x180011e7b  jnz     short loc_180011E34
0x180011e7d  test    r8d, r8d
0x180011e80  jnz     short loc_180011EE6
0x180011e82  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180011e88  test    eax, eax
0x180011e8a  jz      short loc_180011EE6
0x180011e8c  lea     r14, SRWLock
0x180011e93  mov     rcx, r14; SRWLock
0x180011e96  call    cs:__imp_AcquireSRWLockExclusive
0x180011e9c  mov     eax, cs:dword_180024B2C
0x180011ea2  mov     [rsp+48h+arg_8], r14
0x180011ea7  test    ebp, ebp
0x180011ea9  jz      short loc_180011ED8
0x180011eab  cmp     ebp, eax
0x180011ead  jnz     short loc_180011ED8
0x180011eaf  mov     r8d, 10h; unsigned __int64
0x180011eb5  mov     [rsp+48h+var_28], 3
0x180011ebe  lea     rdx, [rsp+48h+var_28]; void *
0x180011ec3  mov     [rsp+48h+var_20], rsi
0x180011ec8  lea     rcx, qword_180024B50; this
0x180011ecf  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180011ed4  test    al, al
0x180011ed6  jnz     short loc_180011EDC
0x180011ed8  lock and dword ptr [rsi], 0FFFFFFFBh
0x180011edc  lea     rcx, [rsp+48h+arg_8]
0x180011ee1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180011ee6  mov     eax, [rdi]
0x180011ee8  test    al, 2
0x180011eea  jnz     short loc_180011EFB
0x180011eec  and     eax, 0FFFFF63Eh
0x180011ef1  and     ebx, 9C1h
0x180011ef7  or      eax, ebx
0x180011ef9  mov     [rdi], eax
0x180011efb  mov     rbx, [rsp+48h+arg_10]
0x180011f00  mov     rax, rdi
0x180011f03  mov     rbp, [rsp+48h+arg_18]
0x180011f08  add     rsp, 30h
0x180011f0c  pop     r14
0x180011f0e  pop     rdi
0x180011f0f  pop     rsi
0x180011f10  retn
```
