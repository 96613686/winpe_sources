# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52435335>::GetCachedFeatureEnabledState(void)

- ea: `0x180015104`
- end: `0x180015241`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID52435335@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `317`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b198`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180015104`
- `0x18001716c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800151c8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800151c8`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52435335>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // r14d
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  int v12; // r8d
  _QWORD v14[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details *v15; // [rsp+60h] [rbp+30h] BYREF
  RTL_SRWLOCK *v16; // [rsp+68h] [rbp+38h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ID52435335__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID52435335__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52435335>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
    if ( !v5 )
      LODWORD(v15) = 0;
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID52435335__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 0,
            v14[1] = Feature_ID52435335__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ID52435335__descriptor, 0xFFFFF7C1);
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
0x180015104  mov     [rsp-28h+arg_10], rbx
0x180015109  mov     [rsp-28h+arg_0], rcx
0x18001510e  push    rbp
0x18001510f  push    rsi
0x180015110  push    rdi
0x180015111  push    r14
0x180015113  push    r15
0x180015115  mov     rbp, rsp
0x180015118  sub     rsp, 30h
0x18001511c  mov     rsi, cs:Feature_ID52435335__descriptor
0x180015123  mov     rdi, rdx
0x180015126  mov     qword ptr [rdx], 0
0x18001512d  mov     eax, [rsi]
0x18001512f  mov     [rdx], eax
0x180015131  and     eax, 6
0x180015134  cmp     al, 6
0x180015136  jz      loc_18001522D
0x18001513c  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015141  lea     r8, [rbp+arg_0]
0x180015145  mov     dword ptr [rbp+arg_0], 0
0x18001514c  lea     rdx, [rbp+arg_8]
0x180015150  mov     r14d, eax
0x180015153  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID52435335@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID52435335>::GetCurrentFeatureEnabledState(int *)
0x180015158  test    r14d, r14d
0x18001515b  jnz     short loc_180015161
0x18001515d  mov     dword ptr [rbp+arg_0], r14d
0x180015161  mov     eax, [rdi]
0x180015163  mov     rbx, [rbp+arg_8]
0x180015167  cmp     dword ptr [rbp+arg_0], 0
0x18001516b  mov     edx, eax
0x18001516d  mov     [rdi], eax
0x18001516f  mov     ecx, eax
0x180015171  jz      short loc_18001518C
0x180015173  test    dl, 2
0x180015176  jnz     short loc_18001518C
0x180015178  and     ecx, 0FFFFF63Eh
0x18001517e  mov     eax, ebx
0x180015180  and     eax, 9C1h
0x180015185  or      ecx, eax
0x180015187  or      ecx, 2
0x18001518a  mov     [rdi], ecx
0x18001518c  mov     r8d, edx
0x18001518f  and     r8d, 4
0x180015193  jnz     short loc_1800151A7
0x180015195  btr     ecx, 0Ah
0x180015199  mov     eax, ebx
0x18001519b  and     eax, 400h
0x1800151a0  or      ecx, eax
0x1800151a2  or      ecx, 4
0x1800151a5  mov     [rdi], ecx
0x1800151a7  mov     eax, edx
0x1800151a9  lock cmpxchg [rsi], ecx
0x1800151ad  jnz     short loc_180015167
0x1800151af  test    r8d, r8d
0x1800151b2  jnz     short loc_180015218
0x1800151b4  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800151ba  test    eax, eax
0x1800151bc  jz      short loc_180015218
0x1800151be  lea     r15, SRWLock
0x1800151c5  mov     rcx, r15; SRWLock
0x1800151c8  call    cs:__imp_AcquireSRWLockExclusive
0x1800151ce  mov     eax, cs:dword_18002EED4
0x1800151d4  mov     [rbp+arg_8], r15
0x1800151d8  test    r14d, r14d
0x1800151db  jz      short loc_180015208
0x1800151dd  cmp     r14d, eax
0x1800151e0  jnz     short loc_180015208
0x1800151e2  mov     r8d, 10h; unsigned __int64
0x1800151e8  mov     [rbp+var_10], 0
0x1800151f0  lea     rdx, [rbp+var_10]; void *
0x1800151f4  mov     [rbp+var_8], rsi
0x1800151f8  lea     rcx, qword_18002EEF8; this
0x1800151ff  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180015204  test    al, al
0x180015206  jnz     short loc_18001520F
0x180015208  lock and dword ptr [rsi], 0FFFFF7C1h
0x18001520f  lea     rcx, [rbp+arg_8]
0x180015213  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015218  mov     eax, [rdi]
0x18001521a  test    al, 2
0x18001521c  jnz     short loc_18001522D
0x18001521e  and     eax, 0FFFFF63Eh
0x180015223  and     ebx, 9C1h
0x180015229  or      eax, ebx
0x18001522b  mov     [rdi], eax
0x18001522d  mov     rbx, [rsp+30h+arg_10]
0x180015232  mov     rax, rdi
0x180015235  add     rsp, 30h
0x180015239  pop     r15
0x18001523b  pop     r14
0x18001523d  pop     rdi
0x18001523e  pop     rsi
0x18001523f  pop     rbp
0x180015240  retn
```
