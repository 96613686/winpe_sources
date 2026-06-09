# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18002a9e8`
- end: `0x18002ab28`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c7d0`

## callees

- `0x180008fc0`
- `0x180009790`
- `0x18000c1f4`
- `0x18002a9e8`
- `0x18002b2a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002aaa6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002aaa6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800578F4
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_26_01_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180057928, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, 0xFFFFFFFB);
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
0x18002a9e8  mov     [rsp+arg_10], rbx
0x18002a9ed  mov     [rsp+arg_18], rbp
0x18002a9f2  mov     [rsp+arg_0], rcx
0x18002a9f7  push    rsi
0x18002a9f8  push    rdi
0x18002a9f9  push    r14
0x18002a9fb  sub     rsp, 30h
0x18002a9ff  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x18002aa06  mov     rdi, rdx
0x18002aa09  mov     qword ptr [rdx], 0
0x18002aa10  mov     eax, [rsi]
0x18002aa12  mov     [rdx], eax
0x18002aa14  and     eax, 6
0x18002aa17  cmp     al, 6
0x18002aa19  jz      loc_18002AB11
0x18002aa1f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002aa24  lea     r8, [rsp+48h+arg_0]
0x18002aa29  mov     dword ptr [rsp+48h+arg_0], 0
0x18002aa31  lea     rdx, [rsp+48h+arg_8]
0x18002aa36  mov     ebp, eax
0x18002aa38  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18002aa3d  mov     eax, [rdi]
0x18002aa3f  mov     rbx, [rsp+48h+arg_8]
0x18002aa44  cmp     dword ptr [rsp+48h+arg_0], 0
0x18002aa49  mov     edx, eax
0x18002aa4b  mov     [rdi], eax
0x18002aa4d  mov     ecx, eax
0x18002aa4f  jz      short loc_18002AA6A
0x18002aa51  test    dl, 2
0x18002aa54  jnz     short loc_18002AA6A
0x18002aa56  and     ecx, 0FFFFF63Eh
0x18002aa5c  mov     eax, ebx
0x18002aa5e  and     eax, 9C1h
0x18002aa63  or      ecx, eax
0x18002aa65  or      ecx, 2
0x18002aa68  mov     [rdi], ecx
0x18002aa6a  mov     r8d, edx
0x18002aa6d  and     r8d, 4
0x18002aa71  jnz     short loc_18002AA85
0x18002aa73  btr     ecx, 0Ah
0x18002aa77  mov     eax, ebx
0x18002aa79  and     eax, 400h
0x18002aa7e  or      ecx, eax
0x18002aa80  or      ecx, 4
0x18002aa83  mov     [rdi], ecx
0x18002aa85  mov     eax, edx
0x18002aa87  lock cmpxchg [rsi], ecx
0x18002aa8b  jnz     short loc_18002AA44
0x18002aa8d  test    r8d, r8d
0x18002aa90  jnz     short loc_18002AAFC
0x18002aa92  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002aa98  test    eax, eax
0x18002aa9a  jz      short loc_18002AAFC
0x18002aa9c  lea     r14, SRWLock
0x18002aaa3  mov     rcx, r14; SRWLock
0x18002aaa6  call    cs:__imp_AcquireSRWLockExclusive
0x18002aaad  nop     dword ptr [rax+rax+00h]
0x18002aab2  mov     eax, cs:dword_1800578F4
0x18002aab8  mov     [rsp+48h+arg_8], r14
0x18002aabd  test    ebp, ebp
0x18002aabf  jz      short loc_18002AAEE
0x18002aac1  cmp     ebp, eax
0x18002aac3  jnz     short loc_18002AAEE
0x18002aac5  mov     r8d, 10h; unsigned __int64
0x18002aacb  mov     [rsp+48h+var_28], 3
0x18002aad4  lea     rdx, [rsp+48h+var_28]; void *
0x18002aad9  mov     [rsp+48h+var_20], rsi
0x18002aade  lea     rcx, qword_180057928; this
0x18002aae5  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002aaea  test    al, al
0x18002aaec  jnz     short loc_18002AAF2
0x18002aaee  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002aaf2  lea     rcx, [rsp+48h+arg_8]
0x18002aaf7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002aafc  mov     eax, [rdi]
0x18002aafe  test    al, 2
0x18002ab00  jnz     short loc_18002AB11
0x18002ab02  and     eax, 0FFFFF63Eh
0x18002ab07  and     ebx, 9C1h
0x18002ab0d  or      eax, ebx
0x18002ab0f  mov     [rdi], eax
0x18002ab11  mov     rbx, [rsp+48h+arg_10]
0x18002ab16  mov     rax, rdi
0x18002ab19  mov     rbp, [rsp+48h+arg_18]
0x18002ab1e  add     rsp, 30h
0x18002ab22  pop     r14
0x18002ab24  pop     rdi
0x18002ab25  pop     rsi
0x18002ab26  retn
```
