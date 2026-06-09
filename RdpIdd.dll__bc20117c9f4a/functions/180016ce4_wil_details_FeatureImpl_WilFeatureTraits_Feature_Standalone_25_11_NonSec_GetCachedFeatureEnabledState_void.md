# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180016ce4`
- end: `0x180016e24`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d0f8`

## callees

- `0x180008fc0`
- `0x180009790`
- `0x18000c1f4`
- `0x180016ce4`
- `0x180017360`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016da2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016da2`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800578F4
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_11_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180057928, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, 0xFFFFFFFB);
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
0x180016ce4  mov     [rsp+arg_10], rbx
0x180016ce9  mov     [rsp+arg_18], rbp
0x180016cee  mov     [rsp+arg_0], rcx
0x180016cf3  push    rsi
0x180016cf4  push    rdi
0x180016cf5  push    r14
0x180016cf7  sub     rsp, 30h
0x180016cfb  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180016d02  mov     rdi, rdx
0x180016d05  mov     qword ptr [rdx], 0
0x180016d0c  mov     eax, [rsi]
0x180016d0e  mov     [rdx], eax
0x180016d10  and     eax, 6
0x180016d13  cmp     al, 6
0x180016d15  jz      loc_180016E0D
0x180016d1b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180016d20  lea     r8, [rsp+48h+arg_0]
0x180016d25  mov     dword ptr [rsp+48h+arg_0], 0
0x180016d2d  lea     rdx, [rsp+48h+arg_8]
0x180016d32  mov     ebp, eax
0x180016d34  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180016d39  mov     eax, [rdi]
0x180016d3b  mov     rbx, [rsp+48h+arg_8]
0x180016d40  cmp     dword ptr [rsp+48h+arg_0], 0
0x180016d45  mov     edx, eax
0x180016d47  mov     [rdi], eax
0x180016d49  mov     ecx, eax
0x180016d4b  jz      short loc_180016D66
0x180016d4d  test    dl, 2
0x180016d50  jnz     short loc_180016D66
0x180016d52  and     ecx, 0FFFFF63Eh
0x180016d58  mov     eax, ebx
0x180016d5a  and     eax, 9C1h
0x180016d5f  or      ecx, eax
0x180016d61  or      ecx, 2
0x180016d64  mov     [rdi], ecx
0x180016d66  mov     r8d, edx
0x180016d69  and     r8d, 4
0x180016d6d  jnz     short loc_180016D81
0x180016d6f  btr     ecx, 0Ah
0x180016d73  mov     eax, ebx
0x180016d75  and     eax, 400h
0x180016d7a  or      ecx, eax
0x180016d7c  or      ecx, 4
0x180016d7f  mov     [rdi], ecx
0x180016d81  mov     eax, edx
0x180016d83  lock cmpxchg [rsi], ecx
0x180016d87  jnz     short loc_180016D40
0x180016d89  test    r8d, r8d
0x180016d8c  jnz     short loc_180016DF8
0x180016d8e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180016d94  test    eax, eax
0x180016d96  jz      short loc_180016DF8
0x180016d98  lea     r14, SRWLock
0x180016d9f  mov     rcx, r14; SRWLock
0x180016da2  call    cs:__imp_AcquireSRWLockExclusive
0x180016da9  nop     dword ptr [rax+rax+00h]
0x180016dae  mov     eax, cs:dword_1800578F4
0x180016db4  mov     [rsp+48h+arg_8], r14
0x180016db9  test    ebp, ebp
0x180016dbb  jz      short loc_180016DEA
0x180016dbd  cmp     ebp, eax
0x180016dbf  jnz     short loc_180016DEA
0x180016dc1  mov     r8d, 10h; unsigned __int64
0x180016dc7  mov     [rsp+48h+var_28], 3
0x180016dd0  lea     rdx, [rsp+48h+var_28]; void *
0x180016dd5  mov     [rsp+48h+var_20], rsi
0x180016dda  lea     rcx, qword_180057928; this
0x180016de1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180016de6  test    al, al
0x180016de8  jnz     short loc_180016DEE
0x180016dea  lock and dword ptr [rsi], 0FFFFFFFBh
0x180016dee  lea     rcx, [rsp+48h+arg_8]
0x180016df3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016df8  mov     eax, [rdi]
0x180016dfa  test    al, 2
0x180016dfc  jnz     short loc_180016E0D
0x180016dfe  and     eax, 0FFFFF63Eh
0x180016e03  and     ebx, 9C1h
0x180016e09  or      eax, ebx
0x180016e0b  mov     [rdi], eax
0x180016e0d  mov     rbx, [rsp+48h+arg_10]
0x180016e12  mov     rax, rdi
0x180016e15  mov     rbp, [rsp+48h+arg_18]
0x180016e1a  add     rsp, 30h
0x180016e1e  pop     r14
0x180016e20  pop     rdi
0x180016e21  pop     rsi
0x180016e22  retn
```
