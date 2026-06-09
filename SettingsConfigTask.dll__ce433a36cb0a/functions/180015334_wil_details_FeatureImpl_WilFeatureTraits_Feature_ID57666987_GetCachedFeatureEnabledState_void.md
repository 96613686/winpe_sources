# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57666987>::GetCachedFeatureEnabledState(void)

- ea: `0x180015334`
- end: `0x18001546d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID57666987@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b2a0`
- `0x18001cfac`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180015334`
- `0x18001725c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800153f2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800153f2`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57666987>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ID57666987__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID57666987__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57666987>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID57666987__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_ID57666987__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ID57666987__descriptor, 0xFFFFFFFB);
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
0x180015334  mov     [rsp+arg_10], rbx
0x180015339  mov     [rsp+arg_18], rbp
0x18001533e  mov     [rsp+arg_0], rcx
0x180015343  push    rsi
0x180015344  push    rdi
0x180015345  push    r14
0x180015347  sub     rsp, 30h
0x18001534b  mov     rsi, cs:Feature_ID57666987__descriptor
0x180015352  mov     rdi, rdx
0x180015355  mov     qword ptr [rdx], 0
0x18001535c  mov     eax, [rsi]
0x18001535e  mov     [rdx], eax
0x180015360  and     eax, 6
0x180015363  cmp     al, 6
0x180015365  jz      loc_180015457
0x18001536b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015370  lea     r8, [rsp+48h+arg_0]
0x180015375  mov     dword ptr [rsp+48h+arg_0], 0
0x18001537d  lea     rdx, [rsp+48h+arg_8]
0x180015382  mov     ebp, eax
0x180015384  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID57666987@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID57666987>::GetCurrentFeatureEnabledState(int *)
0x180015389  mov     eax, [rdi]
0x18001538b  mov     rbx, [rsp+48h+arg_8]
0x180015390  cmp     dword ptr [rsp+48h+arg_0], 0
0x180015395  mov     edx, eax
0x180015397  mov     [rdi], eax
0x180015399  mov     ecx, eax
0x18001539b  jz      short loc_1800153B6
0x18001539d  test    dl, 2
0x1800153a0  jnz     short loc_1800153B6
0x1800153a2  and     ecx, 0FFFFF63Eh
0x1800153a8  mov     eax, ebx
0x1800153aa  and     eax, 9C1h
0x1800153af  or      ecx, eax
0x1800153b1  or      ecx, 2
0x1800153b4  mov     [rdi], ecx
0x1800153b6  mov     r8d, edx
0x1800153b9  and     r8d, 4
0x1800153bd  jnz     short loc_1800153D1
0x1800153bf  btr     ecx, 0Ah
0x1800153c3  mov     eax, ebx
0x1800153c5  and     eax, 400h
0x1800153ca  or      ecx, eax
0x1800153cc  or      ecx, 4
0x1800153cf  mov     [rdi], ecx
0x1800153d1  mov     eax, edx
0x1800153d3  lock cmpxchg [rsi], ecx
0x1800153d7  jnz     short loc_180015390
0x1800153d9  test    r8d, r8d
0x1800153dc  jnz     short loc_180015442
0x1800153de  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800153e4  test    eax, eax
0x1800153e6  jz      short loc_180015442
0x1800153e8  lea     r14, SRWLock
0x1800153ef  mov     rcx, r14; SRWLock
0x1800153f2  call    cs:__imp_AcquireSRWLockExclusive
0x1800153f8  mov     eax, cs:dword_18002EED4
0x1800153fe  mov     [rsp+48h+arg_8], r14
0x180015403  test    ebp, ebp
0x180015405  jz      short loc_180015434
0x180015407  cmp     ebp, eax
0x180015409  jnz     short loc_180015434
0x18001540b  mov     r8d, 10h; unsigned __int64
0x180015411  mov     [rsp+48h+var_28], 3
0x18001541a  lea     rdx, [rsp+48h+var_28]; void *
0x18001541f  mov     [rsp+48h+var_20], rsi
0x180015424  lea     rcx, qword_18002EEF8; this
0x18001542b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180015430  test    al, al
0x180015432  jnz     short loc_180015438
0x180015434  lock and dword ptr [rsi], 0FFFFFFFBh
0x180015438  lea     rcx, [rsp+48h+arg_8]
0x18001543d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015442  mov     eax, [rdi]
0x180015444  test    al, 2
0x180015446  jnz     short loc_180015457
0x180015448  and     eax, 0FFFFF63Eh
0x18001544d  and     ebx, 9C1h
0x180015453  or      eax, ebx
0x180015455  mov     [rdi], eax
0x180015457  mov     rbx, [rsp+48h+arg_10]
0x18001545c  mov     rax, rdi
0x18001545f  mov     rbp, [rsp+48h+arg_18]
0x180015464  add     rsp, 30h
0x180015468  pop     r14
0x18001546a  pop     rdi
0x18001546b  pop     rsi
0x18001546c  retn
```
