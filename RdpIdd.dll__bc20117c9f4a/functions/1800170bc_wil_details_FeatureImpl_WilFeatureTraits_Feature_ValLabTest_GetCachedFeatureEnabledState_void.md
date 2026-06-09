# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x1800170bc`
- end: `0x1800171fc`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d294`

## callees

- `0x180008fc0`
- `0x180009790`
- `0x18000c1f4`
- `0x1800170bc`
- `0x180017598`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001717a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001717a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800578F4
        || (v14[0] = 3,
            v14[1] = Feature_ValLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180057928, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValLabTest__descriptor, 0xFFFFFFFB);
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
0x1800170bc  mov     [rsp+arg_10], rbx
0x1800170c1  mov     [rsp+arg_18], rbp
0x1800170c6  mov     [rsp+arg_0], rcx
0x1800170cb  push    rsi
0x1800170cc  push    rdi
0x1800170cd  push    r14
0x1800170cf  sub     rsp, 30h
0x1800170d3  mov     rsi, cs:Feature_ValLabTest__descriptor
0x1800170da  mov     rdi, rdx
0x1800170dd  mov     qword ptr [rdx], 0
0x1800170e4  mov     eax, [rsi]
0x1800170e6  mov     [rdx], eax
0x1800170e8  and     eax, 6
0x1800170eb  cmp     al, 6
0x1800170ed  jz      loc_1800171E5
0x1800170f3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800170f8  lea     r8, [rsp+48h+arg_0]
0x1800170fd  mov     dword ptr [rsp+48h+arg_0], 0
0x180017105  lea     rdx, [rsp+48h+arg_8]
0x18001710a  mov     ebp, eax
0x18001710c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x180017111  mov     eax, [rdi]
0x180017113  mov     rbx, [rsp+48h+arg_8]
0x180017118  cmp     dword ptr [rsp+48h+arg_0], 0
0x18001711d  mov     edx, eax
0x18001711f  mov     [rdi], eax
0x180017121  mov     ecx, eax
0x180017123  jz      short loc_18001713E
0x180017125  test    dl, 2
0x180017128  jnz     short loc_18001713E
0x18001712a  and     ecx, 0FFFFF63Eh
0x180017130  mov     eax, ebx
0x180017132  and     eax, 9C1h
0x180017137  or      ecx, eax
0x180017139  or      ecx, 2
0x18001713c  mov     [rdi], ecx
0x18001713e  mov     r8d, edx
0x180017141  and     r8d, 4
0x180017145  jnz     short loc_180017159
0x180017147  btr     ecx, 0Ah
0x18001714b  mov     eax, ebx
0x18001714d  and     eax, 400h
0x180017152  or      ecx, eax
0x180017154  or      ecx, 4
0x180017157  mov     [rdi], ecx
0x180017159  mov     eax, edx
0x18001715b  lock cmpxchg [rsi], ecx
0x18001715f  jnz     short loc_180017118
0x180017161  test    r8d, r8d
0x180017164  jnz     short loc_1800171D0
0x180017166  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001716c  test    eax, eax
0x18001716e  jz      short loc_1800171D0
0x180017170  lea     r14, SRWLock
0x180017177  mov     rcx, r14; SRWLock
0x18001717a  call    cs:__imp_AcquireSRWLockExclusive
0x180017181  nop     dword ptr [rax+rax+00h]
0x180017186  mov     eax, cs:dword_1800578F4
0x18001718c  mov     [rsp+48h+arg_8], r14
0x180017191  test    ebp, ebp
0x180017193  jz      short loc_1800171C2
0x180017195  cmp     ebp, eax
0x180017197  jnz     short loc_1800171C2
0x180017199  mov     r8d, 10h; unsigned __int64
0x18001719f  mov     [rsp+48h+var_28], 3
0x1800171a8  lea     rdx, [rsp+48h+var_28]; void *
0x1800171ad  mov     [rsp+48h+var_20], rsi
0x1800171b2  lea     rcx, qword_180057928; this
0x1800171b9  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800171be  test    al, al
0x1800171c0  jnz     short loc_1800171C6
0x1800171c2  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800171c6  lea     rcx, [rsp+48h+arg_8]
0x1800171cb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800171d0  mov     eax, [rdi]
0x1800171d2  test    al, 2
0x1800171d4  jnz     short loc_1800171E5
0x1800171d6  and     eax, 0FFFFF63Eh
0x1800171db  and     ebx, 9C1h
0x1800171e1  or      eax, ebx
0x1800171e3  mov     [rdi], eax
0x1800171e5  mov     rbx, [rsp+48h+arg_10]
0x1800171ea  mov     rax, rdi
0x1800171ed  mov     rbp, [rsp+48h+arg_18]
0x1800171f2  add     rsp, 30h
0x1800171f6  pop     r14
0x1800171f8  pop     rdi
0x1800171f9  pop     rsi
0x1800171fa  retn
```
