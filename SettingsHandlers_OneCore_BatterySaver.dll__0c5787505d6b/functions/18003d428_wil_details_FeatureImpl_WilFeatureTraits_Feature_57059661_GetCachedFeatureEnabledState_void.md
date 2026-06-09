# wil::details::FeatureImpl<__WilFeatureTraits_Feature_57059661>::GetCachedFeatureEnabledState(void)

- ea: `0x18003d428`
- end: `0x18003d561`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57059661@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003e170`
- `0x18003e8f8`

## callees

- `0x18000b508`
- `0x18000c08c`
- `0x18001026c`
- `0x18003d428`
- `0x18003d6a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d4e6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d4e6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_57059661>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_57059661__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_57059661__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_57059661>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_57059661__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180066AF4
        || (v14[0] = 1,
            v14[1] = Feature_57059661__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180066B18, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_57059661__descriptor, 0xFFFFFFFB);
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
0x18003d428  mov     [rsp+arg_10], rbx
0x18003d42d  mov     [rsp+arg_18], rbp
0x18003d432  mov     [rsp+arg_0], rcx
0x18003d437  push    rsi
0x18003d438  push    rdi
0x18003d439  push    r14
0x18003d43b  sub     rsp, 30h
0x18003d43f  mov     rsi, cs:Feature_57059661__descriptor
0x18003d446  mov     rdi, rdx
0x18003d449  mov     qword ptr [rdx], 0
0x18003d450  mov     eax, [rsi]
0x18003d452  mov     [rdx], eax
0x18003d454  and     eax, 6
0x18003d457  cmp     al, 6
0x18003d459  jz      loc_18003D54B
0x18003d45f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18003d464  lea     r8, [rsp+48h+arg_0]
0x18003d469  mov     dword ptr [rsp+48h+arg_0], 0
0x18003d471  lea     rdx, [rsp+48h+arg_8]
0x18003d476  mov     ebp, eax
0x18003d478  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57059661@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57059661>::GetCurrentFeatureEnabledState(int *)
0x18003d47d  mov     eax, [rdi]
0x18003d47f  mov     rbx, [rsp+48h+arg_8]
0x18003d484  cmp     dword ptr [rsp+48h+arg_0], 0
0x18003d489  mov     edx, eax
0x18003d48b  mov     [rdi], eax
0x18003d48d  mov     ecx, eax
0x18003d48f  jz      short loc_18003D4AA
0x18003d491  test    dl, 2
0x18003d494  jnz     short loc_18003D4AA
0x18003d496  and     ecx, 0FFFFF63Eh
0x18003d49c  mov     eax, ebx
0x18003d49e  and     eax, 9C1h
0x18003d4a3  or      ecx, eax
0x18003d4a5  or      ecx, 2
0x18003d4a8  mov     [rdi], ecx
0x18003d4aa  mov     r8d, edx
0x18003d4ad  and     r8d, 4
0x18003d4b1  jnz     short loc_18003D4C5
0x18003d4b3  btr     ecx, 0Ah
0x18003d4b7  mov     eax, ebx
0x18003d4b9  and     eax, 400h
0x18003d4be  or      ecx, eax
0x18003d4c0  or      ecx, 4
0x18003d4c3  mov     [rdi], ecx
0x18003d4c5  mov     eax, edx
0x18003d4c7  lock cmpxchg [rsi], ecx
0x18003d4cb  jnz     short loc_18003D484
0x18003d4cd  test    r8d, r8d
0x18003d4d0  jnz     short loc_18003D536
0x18003d4d2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18003d4d8  test    eax, eax
0x18003d4da  jz      short loc_18003D536
0x18003d4dc  lea     r14, SRWLock
0x18003d4e3  mov     rcx, r14; SRWLock
0x18003d4e6  call    cs:__imp_AcquireSRWLockExclusive
0x18003d4ec  mov     eax, cs:dword_180066AF4
0x18003d4f2  mov     [rsp+48h+arg_8], r14
0x18003d4f7  test    ebp, ebp
0x18003d4f9  jz      short loc_18003D528
0x18003d4fb  cmp     ebp, eax
0x18003d4fd  jnz     short loc_18003D528
0x18003d4ff  mov     r8d, 10h; unsigned __int64
0x18003d505  mov     [rsp+48h+var_28], 1
0x18003d50e  lea     rdx, [rsp+48h+var_28]; void *
0x18003d513  mov     [rsp+48h+var_20], rsi
0x18003d518  lea     rcx, qword_180066B18; this
0x18003d51f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003d524  test    al, al
0x18003d526  jnz     short loc_18003D52C
0x18003d528  lock and dword ptr [rsi], 0FFFFFFFBh
0x18003d52c  lea     rcx, [rsp+48h+arg_8]
0x18003d531  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003d536  mov     eax, [rdi]
0x18003d538  test    al, 2
0x18003d53a  jnz     short loc_18003D54B
0x18003d53c  and     eax, 0FFFFF63Eh
0x18003d541  and     ebx, 9C1h
0x18003d547  or      eax, ebx
0x18003d549  mov     [rdi], eax
0x18003d54b  mov     rbx, [rsp+48h+arg_10]
0x18003d550  mov     rax, rdi
0x18003d553  mov     rbp, [rsp+48h+arg_18]
0x18003d558  add     rsp, 30h
0x18003d55c  pop     r14
0x18003d55e  pop     rdi
0x18003d55f  pop     rsi
0x18003d560  retn
```
