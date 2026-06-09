# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave3>::GetCachedFeatureEnabledState(void)

- ea: `0x1800143c4`
- end: `0x1800144fd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave3@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001acb8`
- `0x18001dd78`

## callees

- `0x1800074a8`
- `0x180008a5c`
- `0x18000e600`
- `0x1800143c4`
- `0x1800145b4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014482`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014482`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave3>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Print_PlatformStabilizationFixes_2026_Wave3__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Print_PlatformStabilizationFixes_2026_Wave3__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave3>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Print_PlatformStabilizationFixes_2026_Wave3__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_18003F440);
      v16 = &stru_18003F440;
      if ( !v5
        || v5 != dword_18003F454
        || (v14[0] = 3,
            v14[1] = Feature_Print_PlatformStabilizationFixes_2026_Wave3__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18003F478, v14, 0x10u)) )
      {
        _InterlockedAnd(
          (volatile signed __int32 *)Feature_Print_PlatformStabilizationFixes_2026_Wave3__descriptor,
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
0x1800143c4  mov     [rsp+arg_10], rbx
0x1800143c9  mov     [rsp+arg_18], rbp
0x1800143ce  mov     [rsp+arg_0], rcx
0x1800143d3  push    rsi
0x1800143d4  push    rdi
0x1800143d5  push    r14
0x1800143d7  sub     rsp, 30h
0x1800143db  mov     rsi, cs:Feature_Print_PlatformStabilizationFixes_2026_Wave3__descriptor
0x1800143e2  mov     rdi, rdx
0x1800143e5  mov     qword ptr [rdx], 0
0x1800143ec  mov     eax, [rsi]
0x1800143ee  mov     [rdx], eax
0x1800143f0  and     eax, 6
0x1800143f3  cmp     al, 6
0x1800143f5  jz      loc_1800144E7
0x1800143fb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014400  lea     r8, [rsp+48h+arg_0]
0x180014405  mov     dword ptr [rsp+48h+arg_0], 0
0x18001440d  lea     rdx, [rsp+48h+arg_8]
0x180014412  mov     ebp, eax
0x180014414  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave3@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Print_PlatformStabilizationFixes_2026_Wave3>::GetCurrentFeatureEnabledState(int *)
0x180014419  mov     eax, [rdi]
0x18001441b  mov     rbx, [rsp+48h+arg_8]
0x180014420  cmp     dword ptr [rsp+48h+arg_0], 0
0x180014425  mov     edx, eax
0x180014427  mov     [rdi], eax
0x180014429  mov     ecx, eax
0x18001442b  jz      short loc_180014446
0x18001442d  test    dl, 2
0x180014430  jnz     short loc_180014446
0x180014432  and     ecx, 0FFFFF63Eh
0x180014438  mov     eax, ebx
0x18001443a  and     eax, 9C1h
0x18001443f  or      ecx, eax
0x180014441  or      ecx, 2
0x180014444  mov     [rdi], ecx
0x180014446  mov     r8d, edx
0x180014449  and     r8d, 4
0x18001444d  jnz     short loc_180014461
0x18001444f  btr     ecx, 0Ah
0x180014453  mov     eax, ebx
0x180014455  and     eax, 400h
0x18001445a  or      ecx, eax
0x18001445c  or      ecx, 4
0x18001445f  mov     [rdi], ecx
0x180014461  mov     eax, edx
0x180014463  lock cmpxchg [rsi], ecx
0x180014467  jnz     short loc_180014420
0x180014469  test    r8d, r8d
0x18001446c  jnz     short loc_1800144D2
0x18001446e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180014474  test    eax, eax
0x180014476  jz      short loc_1800144D2
0x180014478  lea     r14, stru_18003F440
0x18001447f  mov     rcx, r14; SRWLock
0x180014482  call    cs:__imp_AcquireSRWLockExclusive
0x180014488  mov     eax, cs:dword_18003F454
0x18001448e  mov     [rsp+48h+arg_8], r14
0x180014493  test    ebp, ebp
0x180014495  jz      short loc_1800144C4
0x180014497  cmp     ebp, eax
0x180014499  jnz     short loc_1800144C4
0x18001449b  mov     r8d, 10h; unsigned __int64
0x1800144a1  mov     [rsp+48h+var_28], 3
0x1800144aa  lea     rdx, [rsp+48h+var_28]; void *
0x1800144af  mov     [rsp+48h+var_20], rsi
0x1800144b4  lea     rcx, qword_18003F478; this
0x1800144bb  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800144c0  test    al, al
0x1800144c2  jnz     short loc_1800144C8
0x1800144c4  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800144c8  lea     rcx, [rsp+48h+arg_8]
0x1800144cd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800144d2  mov     eax, [rdi]
0x1800144d4  test    al, 2
0x1800144d6  jnz     short loc_1800144E7
0x1800144d8  and     eax, 0FFFFF63Eh
0x1800144dd  and     ebx, 9C1h
0x1800144e3  or      eax, ebx
0x1800144e5  mov     [rdi], eax
0x1800144e7  mov     rbx, [rsp+48h+arg_10]
0x1800144ec  mov     rax, rdi
0x1800144ef  mov     rbp, [rsp+48h+arg_18]
0x1800144f4  add     rsp, 30h
0x1800144f8  pop     r14
0x1800144fa  pop     rdi
0x1800144fb  pop     rsi
0x1800144fc  retn
```
