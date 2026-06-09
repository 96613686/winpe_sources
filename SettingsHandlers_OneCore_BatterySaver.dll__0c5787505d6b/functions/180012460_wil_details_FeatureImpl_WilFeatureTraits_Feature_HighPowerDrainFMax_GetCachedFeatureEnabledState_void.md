# wil::details::FeatureImpl<__WilFeatureTraits_Feature_HighPowerDrainFMax>::GetCachedFeatureEnabledState(void)

- ea: `0x180012460`
- end: `0x180012599`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_HighPowerDrainFMax@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800130c0`
- `0x180013ff4`

## callees

- `0x18000b508`
- `0x18000c08c`
- `0x18001026c`
- `0x180012460`
- `0x1800129cc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001251e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001251e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_HighPowerDrainFMax>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_HighPowerDrainFMax__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_HighPowerDrainFMax__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_HighPowerDrainFMax>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_HighPowerDrainFMax__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180066AF4
        || (v14[0] = 3,
            v14[1] = Feature_HighPowerDrainFMax__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180066B18, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_HighPowerDrainFMax__descriptor, 0xFFFFFFFB);
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
0x180012460  mov     [rsp+arg_10], rbx
0x180012465  mov     [rsp+arg_18], rbp
0x18001246a  mov     [rsp+arg_0], rcx
0x18001246f  push    rsi
0x180012470  push    rdi
0x180012471  push    r14
0x180012473  sub     rsp, 30h
0x180012477  mov     rsi, cs:Feature_HighPowerDrainFMax__descriptor
0x18001247e  mov     rdi, rdx
0x180012481  mov     qword ptr [rdx], 0
0x180012488  mov     eax, [rsi]
0x18001248a  mov     [rdx], eax
0x18001248c  and     eax, 6
0x18001248f  cmp     al, 6
0x180012491  jz      loc_180012583
0x180012497  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001249c  lea     r8, [rsp+48h+arg_0]
0x1800124a1  mov     dword ptr [rsp+48h+arg_0], 0
0x1800124a9  lea     rdx, [rsp+48h+arg_8]
0x1800124ae  mov     ebp, eax
0x1800124b0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_HighPowerDrainFMax@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_HighPowerDrainFMax>::GetCurrentFeatureEnabledState(int *)
0x1800124b5  mov     eax, [rdi]
0x1800124b7  mov     rbx, [rsp+48h+arg_8]
0x1800124bc  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800124c1  mov     edx, eax
0x1800124c3  mov     [rdi], eax
0x1800124c5  mov     ecx, eax
0x1800124c7  jz      short loc_1800124E2
0x1800124c9  test    dl, 2
0x1800124cc  jnz     short loc_1800124E2
0x1800124ce  and     ecx, 0FFFFF63Eh
0x1800124d4  mov     eax, ebx
0x1800124d6  and     eax, 9C1h
0x1800124db  or      ecx, eax
0x1800124dd  or      ecx, 2
0x1800124e0  mov     [rdi], ecx
0x1800124e2  mov     r8d, edx
0x1800124e5  and     r8d, 4
0x1800124e9  jnz     short loc_1800124FD
0x1800124eb  btr     ecx, 0Ah
0x1800124ef  mov     eax, ebx
0x1800124f1  and     eax, 400h
0x1800124f6  or      ecx, eax
0x1800124f8  or      ecx, 4
0x1800124fb  mov     [rdi], ecx
0x1800124fd  mov     eax, edx
0x1800124ff  lock cmpxchg [rsi], ecx
0x180012503  jnz     short loc_1800124BC
0x180012505  test    r8d, r8d
0x180012508  jnz     short loc_18001256E
0x18001250a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180012510  test    eax, eax
0x180012512  jz      short loc_18001256E
0x180012514  lea     r14, SRWLock
0x18001251b  mov     rcx, r14; SRWLock
0x18001251e  call    cs:__imp_AcquireSRWLockExclusive
0x180012524  mov     eax, cs:dword_180066AF4
0x18001252a  mov     [rsp+48h+arg_8], r14
0x18001252f  test    ebp, ebp
0x180012531  jz      short loc_180012560
0x180012533  cmp     ebp, eax
0x180012535  jnz     short loc_180012560
0x180012537  mov     r8d, 10h; unsigned __int64
0x18001253d  mov     [rsp+48h+var_28], 3
0x180012546  lea     rdx, [rsp+48h+var_28]; void *
0x18001254b  mov     [rsp+48h+var_20], rsi
0x180012550  lea     rcx, qword_180066B18; this
0x180012557  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001255c  test    al, al
0x18001255e  jnz     short loc_180012564
0x180012560  lock and dword ptr [rsi], 0FFFFFFFBh
0x180012564  lea     rcx, [rsp+48h+arg_8]
0x180012569  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001256e  mov     eax, [rdi]
0x180012570  test    al, 2
0x180012572  jnz     short loc_180012583
0x180012574  and     eax, 0FFFFF63Eh
0x180012579  and     ebx, 9C1h
0x18001257f  or      eax, ebx
0x180012581  mov     [rdi], eax
0x180012583  mov     rbx, [rsp+48h+arg_10]
0x180012588  mov     rax, rdi
0x18001258b  mov     rbp, [rsp+48h+arg_18]
0x180012590  add     rsp, 30h
0x180012594  pop     r14
0x180012596  pop     rdi
0x180012597  pop     rsi
0x180012598  retn
```
