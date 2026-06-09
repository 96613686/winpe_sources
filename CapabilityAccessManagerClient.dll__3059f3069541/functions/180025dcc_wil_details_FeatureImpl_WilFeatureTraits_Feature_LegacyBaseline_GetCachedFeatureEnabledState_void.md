# wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyBaseline>::GetCachedFeatureEnabledState(void)

- ea: `0x180025dcc`
- end: `0x180025f05`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_LegacyBaseline@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027c0c`
- `0x18002848c`
- `0x180034790`

## callees

- `0x18000aa04`
- `0x18000b598`
- `0x18000fc44`
- `0x180025dcc`
- `0x180026e58`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025e8a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025e8a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyBaseline>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_LegacyBaseline__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_LegacyBaseline__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyBaseline>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_LegacyBaseline__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180061260);
      v16 = &stru_180061260;
      if ( !v5
        || v5 != dword_180061274
        || (v14[0] = 1,
            v14[1] = Feature_LegacyBaseline__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180061298, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_LegacyBaseline__descriptor, 0xFFFFFFFB);
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
0x180025dcc  mov     [rsp+arg_10], rbx
0x180025dd1  mov     [rsp+arg_18], rbp
0x180025dd6  mov     [rsp+arg_0], rcx
0x180025ddb  push    rsi
0x180025ddc  push    rdi
0x180025ddd  push    r14
0x180025ddf  sub     rsp, 30h
0x180025de3  mov     rsi, cs:Feature_LegacyBaseline__descriptor
0x180025dea  mov     rdi, rdx
0x180025ded  mov     qword ptr [rdx], 0
0x180025df4  mov     eax, [rsi]
0x180025df6  mov     [rdx], eax
0x180025df8  and     eax, 6
0x180025dfb  cmp     al, 6
0x180025dfd  jz      loc_180025EEF
0x180025e03  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180025e08  lea     r8, [rsp+48h+arg_0]
0x180025e0d  mov     dword ptr [rsp+48h+arg_0], 0
0x180025e15  lea     rdx, [rsp+48h+arg_8]
0x180025e1a  mov     ebp, eax
0x180025e1c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_LegacyBaseline@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_LegacyBaseline>::GetCurrentFeatureEnabledState(int *)
0x180025e21  mov     eax, [rdi]
0x180025e23  mov     rbx, [rsp+48h+arg_8]
0x180025e28  cmp     dword ptr [rsp+48h+arg_0], 0
0x180025e2d  mov     edx, eax
0x180025e2f  mov     [rdi], eax
0x180025e31  mov     ecx, eax
0x180025e33  jz      short loc_180025E4E
0x180025e35  test    dl, 2
0x180025e38  jnz     short loc_180025E4E
0x180025e3a  and     ecx, 0FFFFF63Eh
0x180025e40  mov     eax, ebx
0x180025e42  and     eax, 9C1h
0x180025e47  or      ecx, eax
0x180025e49  or      ecx, 2
0x180025e4c  mov     [rdi], ecx
0x180025e4e  mov     r8d, edx
0x180025e51  and     r8d, 4
0x180025e55  jnz     short loc_180025E69
0x180025e57  btr     ecx, 0Ah
0x180025e5b  mov     eax, ebx
0x180025e5d  and     eax, 400h
0x180025e62  or      ecx, eax
0x180025e64  or      ecx, 4
0x180025e67  mov     [rdi], ecx
0x180025e69  mov     eax, edx
0x180025e6b  lock cmpxchg [rsi], ecx
0x180025e6f  jnz     short loc_180025E28
0x180025e71  test    r8d, r8d
0x180025e74  jnz     short loc_180025EDA
0x180025e76  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180025e7c  test    eax, eax
0x180025e7e  jz      short loc_180025EDA
0x180025e80  lea     r14, stru_180061260
0x180025e87  mov     rcx, r14; SRWLock
0x180025e8a  call    cs:__imp_AcquireSRWLockExclusive
0x180025e90  mov     eax, cs:dword_180061274
0x180025e96  mov     [rsp+48h+arg_8], r14
0x180025e9b  test    ebp, ebp
0x180025e9d  jz      short loc_180025ECC
0x180025e9f  cmp     ebp, eax
0x180025ea1  jnz     short loc_180025ECC
0x180025ea3  mov     r8d, 10h; unsigned __int64
0x180025ea9  mov     [rsp+48h+var_28], 1
0x180025eb2  lea     rdx, [rsp+48h+var_28]; void *
0x180025eb7  mov     [rsp+48h+var_20], rsi
0x180025ebc  lea     rcx, qword_180061298; this
0x180025ec3  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180025ec8  test    al, al
0x180025eca  jnz     short loc_180025ED0
0x180025ecc  lock and dword ptr [rsi], 0FFFFFFFBh
0x180025ed0  lea     rcx, [rsp+48h+arg_8]
0x180025ed5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180025eda  mov     eax, [rdi]
0x180025edc  test    al, 2
0x180025ede  jnz     short loc_180025EEF
0x180025ee0  and     eax, 0FFFFF63Eh
0x180025ee5  and     ebx, 9C1h
0x180025eeb  or      eax, ebx
0x180025eed  mov     [rdi], eax
0x180025eef  mov     rbx, [rsp+48h+arg_10]
0x180025ef4  mov     rax, rdi
0x180025ef7  mov     rbp, [rsp+48h+arg_18]
0x180025efc  add     rsp, 30h
0x180025f00  pop     r14
0x180025f02  pop     rdi
0x180025f03  pop     rsi
0x180025f04  retn
```
