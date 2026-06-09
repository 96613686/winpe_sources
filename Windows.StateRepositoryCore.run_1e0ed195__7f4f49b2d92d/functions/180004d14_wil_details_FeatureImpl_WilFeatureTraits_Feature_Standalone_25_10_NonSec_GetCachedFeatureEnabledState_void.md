# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180004d14`
- end: `0x180004e3d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008b18`

## callees

- `0x180003d78`
- `0x180004650`
- `0x180004944`
- `0x180004d14`
- `0x180005c8c`
- `0x18000ad18`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
      v6,
      &v16,
      &v15);
    v7 = *(_DWORD *)a2;
    v8 = v16;
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      wil::AcquireSRWLockExclusive(&v16, qword_180018220);
      if ( !v5
        || v5 != dword_180018234
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_10_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180018258, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, 0xFFFFFFFB);
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
0x180004d14  mov     [rsp+arg_10], rbx
0x180004d19  mov     [rsp+arg_0], rcx
0x180004d1e  push    rbp
0x180004d1f  push    rsi
0x180004d20  push    rdi
0x180004d21  sub     rsp, 30h
0x180004d25  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180004d2c  mov     rdi, rdx
0x180004d2f  mov     qword ptr [rdx], 0
0x180004d36  mov     eax, [rsi]
0x180004d38  mov     [rdx], eax
0x180004d3a  and     eax, 6
0x180004d3d  cmp     al, 6
0x180004d3f  jz      loc_180004E2D
0x180004d45  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180004d4a  lea     r8, [rsp+48h+arg_0]
0x180004d4f  mov     dword ptr [rsp+48h+arg_0], 0
0x180004d57  lea     rdx, [rsp+48h+arg_8]
0x180004d5c  mov     ebp, eax
0x180004d5e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180004d63  mov     eax, [rdi]
0x180004d65  mov     rbx, [rsp+48h+arg_8]
0x180004d6a  cmp     dword ptr [rsp+48h+arg_0], 0
0x180004d6f  mov     edx, eax
0x180004d71  mov     [rdi], eax
0x180004d73  mov     ecx, eax
0x180004d75  jz      short loc_180004D90
0x180004d77  test    dl, 2
0x180004d7a  jnz     short loc_180004D90
0x180004d7c  and     ecx, 0FFFFF63Eh
0x180004d82  mov     eax, ebx
0x180004d84  and     eax, 9C1h
0x180004d89  or      ecx, eax
0x180004d8b  or      ecx, 2
0x180004d8e  mov     [rdi], ecx
0x180004d90  mov     r8d, edx
0x180004d93  and     r8d, 4
0x180004d97  jnz     short loc_180004DAB
0x180004d99  btr     ecx, 0Ah
0x180004d9d  mov     eax, ebx
0x180004d9f  and     eax, 400h
0x180004da4  or      ecx, eax
0x180004da6  or      ecx, 4
0x180004da9  mov     [rdi], ecx
0x180004dab  mov     eax, edx
0x180004dad  lock cmpxchg [rsi], ecx
0x180004db1  jnz     short loc_180004D6A
0x180004db3  test    r8d, r8d
0x180004db6  jnz     short loc_180004E18
0x180004db8  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004dbe  test    eax, eax
0x180004dc0  jz      short loc_180004E18
0x180004dc2  lea     rdx, qword_180018220
0x180004dc9  lea     rcx, [rsp+48h+arg_8]
0x180004dce  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180004dd3  mov     eax, cs:dword_180018234
0x180004dd9  test    ebp, ebp
0x180004ddb  jz      short loc_180004E0A
0x180004ddd  cmp     ebp, eax
0x180004ddf  jnz     short loc_180004E0A
0x180004de1  mov     r8d, 10h; unsigned __int64
0x180004de7  mov     [rsp+48h+var_28], 3
0x180004df0  lea     rdx, [rsp+48h+var_28]; void *
0x180004df5  mov     [rsp+48h+var_20], rsi
0x180004dfa  lea     rcx, qword_180018258; this
0x180004e01  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180004e06  test    al, al
0x180004e08  jnz     short loc_180004E0E
0x180004e0a  lock and dword ptr [rsi], 0FFFFFFFBh
0x180004e0e  lea     rcx, [rsp+48h+arg_8]
0x180004e13  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180004e18  mov     eax, [rdi]
0x180004e1a  test    al, 2
0x180004e1c  jnz     short loc_180004E2D
0x180004e1e  and     eax, 0FFFFF63Eh
0x180004e23  and     ebx, 9C1h
0x180004e29  or      eax, ebx
0x180004e2b  mov     [rdi], eax
0x180004e2d  mov     rbx, [rsp+48h+arg_10]
0x180004e32  mov     rax, rdi
0x180004e35  add     rsp, 30h
0x180004e39  pop     rdi
0x180004e3a  pop     rsi
0x180004e3b  pop     rbp
0x180004e3c  retn
```
