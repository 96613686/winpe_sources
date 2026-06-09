# wil::details::FeatureImpl<__WilFeatureTraits_Feature_SustainabilityFixes_Q1>::GetCachedFeatureEnabledState(void)

- ea: `0x180041954`
- end: `0x180041a8d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SustainabilityFixes_Q1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800434f4`
- `0x180044e44`

## callees

- `0x18000b508`
- `0x18000c08c`
- `0x18001026c`
- `0x180041954`
- `0x1800421d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041a12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180041a12`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_SustainabilityFixes_Q1>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_SustainabilityFixes_Q1__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_SustainabilityFixes_Q1__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SustainabilityFixes_Q1>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_SustainabilityFixes_Q1__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180066AF4
        || (v14[0] = 3,
            v14[1] = Feature_SustainabilityFixes_Q1__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180066B18, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_SustainabilityFixes_Q1__descriptor, 0xFFFFFFFB);
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
0x180041954  mov     [rsp+arg_10], rbx
0x180041959  mov     [rsp+arg_18], rbp
0x18004195e  mov     [rsp+arg_0], rcx
0x180041963  push    rsi
0x180041964  push    rdi
0x180041965  push    r14
0x180041967  sub     rsp, 30h
0x18004196b  mov     rsi, cs:Feature_SustainabilityFixes_Q1__descriptor
0x180041972  mov     rdi, rdx
0x180041975  mov     qword ptr [rdx], 0
0x18004197c  mov     eax, [rsi]
0x18004197e  mov     [rdx], eax
0x180041980  and     eax, 6
0x180041983  cmp     al, 6
0x180041985  jz      loc_180041A77
0x18004198b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180041990  lea     r8, [rsp+48h+arg_0]
0x180041995  mov     dword ptr [rsp+48h+arg_0], 0
0x18004199d  lea     rdx, [rsp+48h+arg_8]
0x1800419a2  mov     ebp, eax
0x1800419a4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SustainabilityFixes_Q1@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SustainabilityFixes_Q1>::GetCurrentFeatureEnabledState(int *)
0x1800419a9  mov     eax, [rdi]
0x1800419ab  mov     rbx, [rsp+48h+arg_8]
0x1800419b0  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800419b5  mov     edx, eax
0x1800419b7  mov     [rdi], eax
0x1800419b9  mov     ecx, eax
0x1800419bb  jz      short loc_1800419D6
0x1800419bd  test    dl, 2
0x1800419c0  jnz     short loc_1800419D6
0x1800419c2  and     ecx, 0FFFFF63Eh
0x1800419c8  mov     eax, ebx
0x1800419ca  and     eax, 9C1h
0x1800419cf  or      ecx, eax
0x1800419d1  or      ecx, 2
0x1800419d4  mov     [rdi], ecx
0x1800419d6  mov     r8d, edx
0x1800419d9  and     r8d, 4
0x1800419dd  jnz     short loc_1800419F1
0x1800419df  btr     ecx, 0Ah
0x1800419e3  mov     eax, ebx
0x1800419e5  and     eax, 400h
0x1800419ea  or      ecx, eax
0x1800419ec  or      ecx, 4
0x1800419ef  mov     [rdi], ecx
0x1800419f1  mov     eax, edx
0x1800419f3  lock cmpxchg [rsi], ecx
0x1800419f7  jnz     short loc_1800419B0
0x1800419f9  test    r8d, r8d
0x1800419fc  jnz     short loc_180041A62
0x1800419fe  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180041a04  test    eax, eax
0x180041a06  jz      short loc_180041A62
0x180041a08  lea     r14, SRWLock
0x180041a0f  mov     rcx, r14; SRWLock
0x180041a12  call    cs:__imp_AcquireSRWLockExclusive
0x180041a18  mov     eax, cs:dword_180066AF4
0x180041a1e  mov     [rsp+48h+arg_8], r14
0x180041a23  test    ebp, ebp
0x180041a25  jz      short loc_180041A54
0x180041a27  cmp     ebp, eax
0x180041a29  jnz     short loc_180041A54
0x180041a2b  mov     r8d, 10h; unsigned __int64
0x180041a31  mov     [rsp+48h+var_28], 3
0x180041a3a  lea     rdx, [rsp+48h+var_28]; void *
0x180041a3f  mov     [rsp+48h+var_20], rsi
0x180041a44  lea     rcx, qword_180066B18; this
0x180041a4b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180041a50  test    al, al
0x180041a52  jnz     short loc_180041A58
0x180041a54  lock and dword ptr [rsi], 0FFFFFFFBh
0x180041a58  lea     rcx, [rsp+48h+arg_8]
0x180041a5d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180041a62  mov     eax, [rdi]
0x180041a64  test    al, 2
0x180041a66  jnz     short loc_180041A77
0x180041a68  and     eax, 0FFFFF63Eh
0x180041a6d  and     ebx, 9C1h
0x180041a73  or      eax, ebx
0x180041a75  mov     [rdi], eax
0x180041a77  mov     rbx, [rsp+48h+arg_10]
0x180041a7c  mov     rax, rdi
0x180041a7f  mov     rbp, [rsp+48h+arg_18]
0x180041a84  add     rsp, 30h
0x180041a88  pop     r14
0x180041a8a  pop     rdi
0x180041a8b  pop     rsi
0x180041a8c  retn
```
