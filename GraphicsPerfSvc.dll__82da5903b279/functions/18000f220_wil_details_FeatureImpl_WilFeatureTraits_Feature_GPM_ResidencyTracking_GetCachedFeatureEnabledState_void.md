# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f220`
- end: `0x18000f359`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000fe04`
- `0x180011274`
- `0x18001599c`

## callees

- `0x180005c8c`
- `0x180006744`
- `0x18000a96c`
- `0x18000f220`
- `0x18000f540`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f2de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f2de`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_GPM_ResidencyTracking__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_GPM_ResidencyTracking__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_GPM_ResidencyTracking__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180042F88);
      v16 = &stru_180042F88;
      if ( !v5
        || v5 != dword_180042F9C
        || (v14[0] = 1,
            v14[1] = Feature_GPM_ResidencyTracking__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180042FC0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_GPM_ResidencyTracking__descriptor, 0xFFFFFFFB);
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
0x18000f220  mov     [rsp+arg_10], rbx
0x18000f225  mov     [rsp+arg_18], rbp
0x18000f22a  mov     [rsp+arg_0], rcx
0x18000f22f  push    rsi
0x18000f230  push    rdi
0x18000f231  push    r14
0x18000f233  sub     rsp, 30h
0x18000f237  mov     rsi, cs:Feature_GPM_ResidencyTracking__descriptor
0x18000f23e  mov     rdi, rdx
0x18000f241  mov     qword ptr [rdx], 0
0x18000f248  mov     eax, [rsi]
0x18000f24a  mov     [rdx], eax
0x18000f24c  and     eax, 6
0x18000f24f  cmp     al, 6
0x18000f251  jz      loc_18000F343
0x18000f257  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f25c  lea     r8, [rsp+48h+arg_0]
0x18000f261  mov     dword ptr [rsp+48h+arg_0], 0
0x18000f269  lea     rdx, [rsp+48h+arg_8]
0x18000f26e  mov     ebp, eax
0x18000f270  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_ResidencyTracking@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_ResidencyTracking>::GetCurrentFeatureEnabledState(int *)
0x18000f275  mov     eax, [rdi]
0x18000f277  mov     rbx, [rsp+48h+arg_8]
0x18000f27c  cmp     dword ptr [rsp+48h+arg_0], 0
0x18000f281  mov     edx, eax
0x18000f283  mov     [rdi], eax
0x18000f285  mov     ecx, eax
0x18000f287  jz      short loc_18000F2A2
0x18000f289  test    dl, 2
0x18000f28c  jnz     short loc_18000F2A2
0x18000f28e  and     ecx, 0FFFFF63Eh
0x18000f294  mov     eax, ebx
0x18000f296  and     eax, 9C1h
0x18000f29b  or      ecx, eax
0x18000f29d  or      ecx, 2
0x18000f2a0  mov     [rdi], ecx
0x18000f2a2  mov     r8d, edx
0x18000f2a5  and     r8d, 4
0x18000f2a9  jnz     short loc_18000F2BD
0x18000f2ab  btr     ecx, 0Ah
0x18000f2af  mov     eax, ebx
0x18000f2b1  and     eax, 400h
0x18000f2b6  or      ecx, eax
0x18000f2b8  or      ecx, 4
0x18000f2bb  mov     [rdi], ecx
0x18000f2bd  mov     eax, edx
0x18000f2bf  lock cmpxchg [rsi], ecx
0x18000f2c3  jnz     short loc_18000F27C
0x18000f2c5  test    r8d, r8d
0x18000f2c8  jnz     short loc_18000F32E
0x18000f2ca  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000f2d0  test    eax, eax
0x18000f2d2  jz      short loc_18000F32E
0x18000f2d4  lea     r14, stru_180042F88
0x18000f2db  mov     rcx, r14; SRWLock
0x18000f2de  call    cs:__imp_AcquireSRWLockExclusive
0x18000f2e4  mov     eax, cs:dword_180042F9C
0x18000f2ea  mov     [rsp+48h+arg_8], r14
0x18000f2ef  test    ebp, ebp
0x18000f2f1  jz      short loc_18000F320
0x18000f2f3  cmp     ebp, eax
0x18000f2f5  jnz     short loc_18000F320
0x18000f2f7  mov     r8d, 10h; unsigned __int64
0x18000f2fd  mov     [rsp+48h+var_28], 1
0x18000f306  lea     rdx, [rsp+48h+var_28]; void *
0x18000f30b  mov     [rsp+48h+var_20], rsi
0x18000f310  lea     rcx, qword_180042FC0; this
0x18000f317  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000f31c  test    al, al
0x18000f31e  jnz     short loc_18000F324
0x18000f320  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000f324  lea     rcx, [rsp+48h+arg_8]
0x18000f329  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f32e  mov     eax, [rdi]
0x18000f330  test    al, 2
0x18000f332  jnz     short loc_18000F343
0x18000f334  and     eax, 0FFFFF63Eh
0x18000f339  and     ebx, 9C1h
0x18000f33f  or      eax, ebx
0x18000f341  mov     [rdi], eax
0x18000f343  mov     rbx, [rsp+48h+arg_10]
0x18000f348  mov     rax, rdi
0x18000f34b  mov     rbp, [rsp+48h+arg_18]
0x18000f350  add     rsp, 30h
0x18000f354  pop     r14
0x18000f356  pop     rdi
0x18000f357  pop     rsi
0x18000f358  retn
```
