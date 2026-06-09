# wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetCachedFeatureEnabledState(void)

- ea: `0x18000f178`
- end: `0x18000f2b1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f6c4`

## callees

- `0x180004e64`
- `0x180005a7c`
- `0x180009f20`
- `0x18000f178`
- `0x18000f2b8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f236`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f236`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_IppPsaEnterprise_Api__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_IppPsaEnterprise_Api__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_IppPsaEnterprise_Api__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180024B2C
        || (v14[0] = 3,
            v14[1] = Feature_IppPsaEnterprise_Api__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180024B50, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_IppPsaEnterprise_Api__descriptor, 0xFFFFFFFB);
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
0x18000f178  mov     [rsp+arg_10], rbx
0x18000f17d  mov     [rsp+arg_18], rbp
0x18000f182  mov     [rsp+arg_0], rcx
0x18000f187  push    rsi
0x18000f188  push    rdi
0x18000f189  push    r14
0x18000f18b  sub     rsp, 30h
0x18000f18f  mov     rsi, cs:Feature_IppPsaEnterprise_Api__descriptor
0x18000f196  mov     rdi, rdx
0x18000f199  mov     qword ptr [rdx], 0
0x18000f1a0  mov     eax, [rsi]
0x18000f1a2  mov     [rdx], eax
0x18000f1a4  and     eax, 6
0x18000f1a7  cmp     al, 6
0x18000f1a9  jz      loc_18000F29B
0x18000f1af  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000f1b4  lea     r8, [rsp+48h+arg_0]
0x18000f1b9  mov     dword ptr [rsp+48h+arg_0], 0
0x18000f1c1  lea     rdx, [rsp+48h+arg_8]
0x18000f1c6  mov     ebp, eax
0x18000f1c8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_IppPsaEnterprise_Api@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_IppPsaEnterprise_Api>::GetCurrentFeatureEnabledState(int *)
0x18000f1cd  mov     eax, [rdi]
0x18000f1cf  mov     rbx, [rsp+48h+arg_8]
0x18000f1d4  cmp     dword ptr [rsp+48h+arg_0], 0
0x18000f1d9  mov     edx, eax
0x18000f1db  mov     [rdi], eax
0x18000f1dd  mov     ecx, eax
0x18000f1df  jz      short loc_18000F1FA
0x18000f1e1  test    dl, 2
0x18000f1e4  jnz     short loc_18000F1FA
0x18000f1e6  and     ecx, 0FFFFF63Eh
0x18000f1ec  mov     eax, ebx
0x18000f1ee  and     eax, 9C1h
0x18000f1f3  or      ecx, eax
0x18000f1f5  or      ecx, 2
0x18000f1f8  mov     [rdi], ecx
0x18000f1fa  mov     r8d, edx
0x18000f1fd  and     r8d, 4
0x18000f201  jnz     short loc_18000F215
0x18000f203  btr     ecx, 0Ah
0x18000f207  mov     eax, ebx
0x18000f209  and     eax, 400h
0x18000f20e  or      ecx, eax
0x18000f210  or      ecx, 4
0x18000f213  mov     [rdi], ecx
0x18000f215  mov     eax, edx
0x18000f217  lock cmpxchg [rsi], ecx
0x18000f21b  jnz     short loc_18000F1D4
0x18000f21d  test    r8d, r8d
0x18000f220  jnz     short loc_18000F286
0x18000f222  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000f228  test    eax, eax
0x18000f22a  jz      short loc_18000F286
0x18000f22c  lea     r14, SRWLock
0x18000f233  mov     rcx, r14; SRWLock
0x18000f236  call    cs:__imp_AcquireSRWLockExclusive
0x18000f23c  mov     eax, cs:dword_180024B2C
0x18000f242  mov     [rsp+48h+arg_8], r14
0x18000f247  test    ebp, ebp
0x18000f249  jz      short loc_18000F278
0x18000f24b  cmp     ebp, eax
0x18000f24d  jnz     short loc_18000F278
0x18000f24f  mov     r8d, 10h; unsigned __int64
0x18000f255  mov     [rsp+48h+var_28], 3
0x18000f25e  lea     rdx, [rsp+48h+var_28]; void *
0x18000f263  mov     [rsp+48h+var_20], rsi
0x18000f268  lea     rcx, qword_180024B50; this
0x18000f26f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000f274  test    al, al
0x18000f276  jnz     short loc_18000F27C
0x18000f278  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000f27c  lea     rcx, [rsp+48h+arg_8]
0x18000f281  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f286  mov     eax, [rdi]
0x18000f288  test    al, 2
0x18000f28a  jnz     short loc_18000F29B
0x18000f28c  and     eax, 0FFFFF63Eh
0x18000f291  and     ebx, 9C1h
0x18000f297  or      eax, ebx
0x18000f299  mov     [rdi], eax
0x18000f29b  mov     rbx, [rsp+48h+arg_10]
0x18000f2a0  mov     rax, rdi
0x18000f2a3  mov     rbp, [rsp+48h+arg_18]
0x18000f2a8  add     rsp, 30h
0x18000f2ac  pop     r14
0x18000f2ae  pop     rdi
0x18000f2af  pop     rsi
0x18000f2b0  retn
```
