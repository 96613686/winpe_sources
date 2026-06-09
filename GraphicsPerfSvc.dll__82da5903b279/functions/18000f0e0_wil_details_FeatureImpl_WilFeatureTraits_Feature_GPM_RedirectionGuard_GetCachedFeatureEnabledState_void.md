# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_RedirectionGuard>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f0e0`
- end: `0x18000f219`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_RedirectionGuard@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fd78`
- `0x180011238`

## callees

- `0x180005c8c`
- `0x180006744`
- `0x18000a96c`
- `0x18000f0e0`
- `0x18000f4bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f19e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f19e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_RedirectionGuard>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_GPM_RedirectionGuard__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_GPM_RedirectionGuard__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_RedirectionGuard>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_GPM_RedirectionGuard__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180042F88);
      v16 = &stru_180042F88;
      if ( !v5
        || v5 != dword_180042F9C
        || (v14[0] = 1,
            v14[1] = Feature_GPM_RedirectionGuard__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180042FC0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_GPM_RedirectionGuard__descriptor, 0xFFFFFFFB);
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
0x18000f0e0  mov     [rsp+arg_10], rbx
0x18000f0e5  mov     [rsp+arg_18], rbp
0x18000f0ea  mov     [rsp+arg_0], rcx
0x18000f0ef  push    rsi
0x18000f0f0  push    rdi
0x18000f0f1  push    r14
0x18000f0f3  sub     rsp, 30h
0x18000f0f7  mov     rsi, cs:Feature_GPM_RedirectionGuard__descriptor
0x18000f0fe  mov     rdi, rdx
0x18000f101  mov     qword ptr [rdx], 0
0x18000f108  mov     eax, [rsi]
0x18000f10a  mov     [rdx], eax
0x18000f10c  and     eax, 6
0x18000f10f  cmp     al, 6
0x18000f111  jz      loc_18000F203
0x18000f117  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f11c  lea     r8, [rsp+48h+arg_0]
0x18000f121  mov     dword ptr [rsp+48h+arg_0], 0
0x18000f129  lea     rdx, [rsp+48h+arg_8]
0x18000f12e  mov     ebp, eax
0x18000f130  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_RedirectionGuard@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_RedirectionGuard>::GetCurrentFeatureEnabledState(int *)
0x18000f135  mov     eax, [rdi]
0x18000f137  mov     rbx, [rsp+48h+arg_8]
0x18000f13c  cmp     dword ptr [rsp+48h+arg_0], 0
0x18000f141  mov     edx, eax
0x18000f143  mov     [rdi], eax
0x18000f145  mov     ecx, eax
0x18000f147  jz      short loc_18000F162
0x18000f149  test    dl, 2
0x18000f14c  jnz     short loc_18000F162
0x18000f14e  and     ecx, 0FFFFF63Eh
0x18000f154  mov     eax, ebx
0x18000f156  and     eax, 9C1h
0x18000f15b  or      ecx, eax
0x18000f15d  or      ecx, 2
0x18000f160  mov     [rdi], ecx
0x18000f162  mov     r8d, edx
0x18000f165  and     r8d, 4
0x18000f169  jnz     short loc_18000F17D
0x18000f16b  btr     ecx, 0Ah
0x18000f16f  mov     eax, ebx
0x18000f171  and     eax, 400h
0x18000f176  or      ecx, eax
0x18000f178  or      ecx, 4
0x18000f17b  mov     [rdi], ecx
0x18000f17d  mov     eax, edx
0x18000f17f  lock cmpxchg [rsi], ecx
0x18000f183  jnz     short loc_18000F13C
0x18000f185  test    r8d, r8d
0x18000f188  jnz     short loc_18000F1EE
0x18000f18a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000f190  test    eax, eax
0x18000f192  jz      short loc_18000F1EE
0x18000f194  lea     r14, stru_180042F88
0x18000f19b  mov     rcx, r14; SRWLock
0x18000f19e  call    cs:__imp_AcquireSRWLockExclusive
0x18000f1a4  mov     eax, cs:dword_180042F9C
0x18000f1aa  mov     [rsp+48h+arg_8], r14
0x18000f1af  test    ebp, ebp
0x18000f1b1  jz      short loc_18000F1E0
0x18000f1b3  cmp     ebp, eax
0x18000f1b5  jnz     short loc_18000F1E0
0x18000f1b7  mov     r8d, 10h; unsigned __int64
0x18000f1bd  mov     [rsp+48h+var_28], 1
0x18000f1c6  lea     rdx, [rsp+48h+var_28]; void *
0x18000f1cb  mov     [rsp+48h+var_20], rsi
0x18000f1d0  lea     rcx, qword_180042FC0; this
0x18000f1d7  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000f1dc  test    al, al
0x18000f1de  jnz     short loc_18000F1E4
0x18000f1e0  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000f1e4  lea     rcx, [rsp+48h+arg_8]
0x18000f1e9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f1ee  mov     eax, [rdi]
0x18000f1f0  test    al, 2
0x18000f1f2  jnz     short loc_18000F203
0x18000f1f4  and     eax, 0FFFFF63Eh
0x18000f1f9  and     ebx, 9C1h
0x18000f1ff  or      eax, ebx
0x18000f201  mov     [rdi], eax
0x18000f203  mov     rbx, [rsp+48h+arg_10]
0x18000f208  mov     rax, rdi
0x18000f20b  mov     rbp, [rsp+48h+arg_18]
0x18000f210  add     rsp, 30h
0x18000f214  pop     r14
0x18000f216  pop     rdi
0x18000f217  pop     rsi
0x18000f218  retn
```
