# wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_59009491>::GetCachedFeatureEnabledState(void)

- ea: `0x18003bb84`
- end: `0x18003bcbd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_59009491@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003bd4c`
- `0x18003bdf0`

## callees

- `0x18000f0e0`
- `0x18001acd0`
- `0x180026938`
- `0x18003bb84`
- `0x18003bcc4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bc42`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003bc42`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_59009491>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_NetworkUX_BugFix_59009491__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_NetworkUX_BugFix_59009491__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_59009491>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_NetworkUX_BugFix_59009491__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_1800529D8);
      v16 = &stru_1800529D8;
      if ( !v5
        || v5 != dword_1800529EC
        || (v14[0] = 3,
            v14[1] = Feature_NetworkUX_BugFix_59009491__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180052A10, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_NetworkUX_BugFix_59009491__descriptor, 0xFFFFFFFB);
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
0x18003bb84  mov     [rsp+arg_10], rbx
0x18003bb89  mov     [rsp+arg_18], rbp
0x18003bb8e  mov     [rsp+arg_0], rcx
0x18003bb93  push    rsi
0x18003bb94  push    rdi
0x18003bb95  push    r14
0x18003bb97  sub     rsp, 30h
0x18003bb9b  mov     rsi, cs:Feature_NetworkUX_BugFix_59009491__descriptor
0x18003bba2  mov     rdi, rdx
0x18003bba5  mov     qword ptr [rdx], 0
0x18003bbac  mov     eax, [rsi]
0x18003bbae  mov     [rdx], eax
0x18003bbb0  and     eax, 6
0x18003bbb3  cmp     al, 6
0x18003bbb5  jz      loc_18003BCA7
0x18003bbbb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18003bbc0  lea     r8, [rsp+48h+arg_0]
0x18003bbc5  mov     dword ptr [rsp+48h+arg_0], 0
0x18003bbcd  lea     rdx, [rsp+48h+arg_8]
0x18003bbd2  mov     ebp, eax
0x18003bbd4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_NetworkUX_BugFix_59009491@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_NetworkUX_BugFix_59009491>::GetCurrentFeatureEnabledState(int *)
0x18003bbd9  mov     eax, [rdi]
0x18003bbdb  mov     rbx, [rsp+48h+arg_8]
0x18003bbe0  cmp     dword ptr [rsp+48h+arg_0], 0
0x18003bbe5  mov     edx, eax
0x18003bbe7  mov     [rdi], eax
0x18003bbe9  mov     ecx, eax
0x18003bbeb  jz      short loc_18003BC06
0x18003bbed  test    dl, 2
0x18003bbf0  jnz     short loc_18003BC06
0x18003bbf2  and     ecx, 0FFFFF63Eh
0x18003bbf8  mov     eax, ebx
0x18003bbfa  and     eax, 9C1h
0x18003bbff  or      ecx, eax
0x18003bc01  or      ecx, 2
0x18003bc04  mov     [rdi], ecx
0x18003bc06  mov     r8d, edx
0x18003bc09  and     r8d, 4
0x18003bc0d  jnz     short loc_18003BC21
0x18003bc0f  btr     ecx, 0Ah
0x18003bc13  mov     eax, ebx
0x18003bc15  and     eax, 400h
0x18003bc1a  or      ecx, eax
0x18003bc1c  or      ecx, 4
0x18003bc1f  mov     [rdi], ecx
0x18003bc21  mov     eax, edx
0x18003bc23  lock cmpxchg [rsi], ecx
0x18003bc27  jnz     short loc_18003BBE0
0x18003bc29  test    r8d, r8d
0x18003bc2c  jnz     short loc_18003BC92
0x18003bc2e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18003bc34  test    eax, eax
0x18003bc36  jz      short loc_18003BC92
0x18003bc38  lea     r14, stru_1800529D8
0x18003bc3f  mov     rcx, r14; SRWLock
0x18003bc42  call    cs:__imp_AcquireSRWLockExclusive
0x18003bc48  mov     eax, cs:dword_1800529EC
0x18003bc4e  mov     [rsp+48h+arg_8], r14
0x18003bc53  test    ebp, ebp
0x18003bc55  jz      short loc_18003BC84
0x18003bc57  cmp     ebp, eax
0x18003bc59  jnz     short loc_18003BC84
0x18003bc5b  mov     r8d, 10h; unsigned __int64
0x18003bc61  mov     [rsp+48h+var_28], 3
0x18003bc6a  lea     rdx, [rsp+48h+var_28]; void *
0x18003bc6f  mov     [rsp+48h+var_20], rsi
0x18003bc74  lea     rcx, qword_180052A10; this
0x18003bc7b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003bc80  test    al, al
0x18003bc82  jnz     short loc_18003BC88
0x18003bc84  lock and dword ptr [rsi], 0FFFFFFFBh
0x18003bc88  lea     rcx, [rsp+48h+arg_8]
0x18003bc8d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003bc92  mov     eax, [rdi]
0x18003bc94  test    al, 2
0x18003bc96  jnz     short loc_18003BCA7
0x18003bc98  and     eax, 0FFFFF63Eh
0x18003bc9d  and     ebx, 9C1h
0x18003bca3  or      eax, ebx
0x18003bca5  mov     [rdi], eax
0x18003bca7  mov     rbx, [rsp+48h+arg_10]
0x18003bcac  mov     rax, rdi
0x18003bcaf  mov     rbp, [rsp+48h+arg_18]
0x18003bcb4  add     rsp, 30h
0x18003bcb8  pop     r14
0x18003bcba  pop     rdi
0x18003bcbb  pop     rsi
0x18003bcbc  retn
```
