# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180013b6c`
- end: `0x180013cac`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800158bc`
- `0x180015bec`

## callees

- `0x180007630`
- `0x180009fc0`
- `0x18001171c`
- `0x180013b6c`
- `0x180014690`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013c2a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013c2a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180029CA8);
      v16 = &stru_180029CA8;
      if ( !v5
        || v5 != dword_180029CBC
        || (v14[0] = 3,
            v14[1] = Feature_ValAccTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180029CF0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValAccTest__descriptor, 0xFFFFFFFB);
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
0x180013b6c  mov     [rsp+arg_10], rbx
0x180013b71  mov     [rsp+arg_18], rbp
0x180013b76  mov     [rsp+arg_0], rcx
0x180013b7b  push    rsi
0x180013b7c  push    rdi
0x180013b7d  push    r14
0x180013b7f  sub     rsp, 30h
0x180013b83  mov     rsi, cs:Feature_ValAccTest__descriptor
0x180013b8a  mov     rdi, rdx
0x180013b8d  mov     qword ptr [rdx], 0
0x180013b94  mov     eax, [rsi]
0x180013b96  mov     [rdx], eax
0x180013b98  and     eax, 6
0x180013b9b  cmp     al, 6
0x180013b9d  jz      loc_180013C95
0x180013ba3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013ba8  lea     r8, [rsp+48h+arg_0]
0x180013bad  mov     dword ptr [rsp+48h+arg_0], 0
0x180013bb5  lea     rdx, [rsp+48h+arg_8]
0x180013bba  mov     ebp, eax
0x180013bbc  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180013bc1  mov     eax, [rdi]
0x180013bc3  mov     rbx, [rsp+48h+arg_8]
0x180013bc8  cmp     dword ptr [rsp+48h+arg_0], 0
0x180013bcd  mov     edx, eax
0x180013bcf  mov     [rdi], eax
0x180013bd1  mov     ecx, eax
0x180013bd3  jz      short loc_180013BEE
0x180013bd5  test    dl, 2
0x180013bd8  jnz     short loc_180013BEE
0x180013bda  and     ecx, 0FFFFF63Eh
0x180013be0  mov     eax, ebx
0x180013be2  and     eax, 9C1h
0x180013be7  or      ecx, eax
0x180013be9  or      ecx, 2
0x180013bec  mov     [rdi], ecx
0x180013bee  mov     r8d, edx
0x180013bf1  and     r8d, 4
0x180013bf5  jnz     short loc_180013C09
0x180013bf7  btr     ecx, 0Ah
0x180013bfb  mov     eax, ebx
0x180013bfd  and     eax, 400h
0x180013c02  or      ecx, eax
0x180013c04  or      ecx, 4
0x180013c07  mov     [rdi], ecx
0x180013c09  mov     eax, edx
0x180013c0b  lock cmpxchg [rsi], ecx
0x180013c0f  jnz     short loc_180013BC8
0x180013c11  test    r8d, r8d
0x180013c14  jnz     short loc_180013C80
0x180013c16  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013c1c  test    eax, eax
0x180013c1e  jz      short loc_180013C80
0x180013c20  lea     r14, stru_180029CA8
0x180013c27  mov     rcx, r14; SRWLock
0x180013c2a  call    cs:__imp_AcquireSRWLockExclusive
0x180013c31  nop     dword ptr [rax+rax+00h]
0x180013c36  mov     eax, cs:dword_180029CBC
0x180013c3c  mov     [rsp+48h+arg_8], r14
0x180013c41  test    ebp, ebp
0x180013c43  jz      short loc_180013C72
0x180013c45  cmp     ebp, eax
0x180013c47  jnz     short loc_180013C72
0x180013c49  mov     r8d, 10h; unsigned __int64
0x180013c4f  mov     [rsp+48h+var_28], 3
0x180013c58  lea     rdx, [rsp+48h+var_28]; void *
0x180013c5d  mov     [rsp+48h+var_20], rsi
0x180013c62  lea     rcx, qword_180029CF0; this
0x180013c69  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180013c6e  test    al, al
0x180013c70  jnz     short loc_180013C76
0x180013c72  lock and dword ptr [rsi], 0FFFFFFFBh
0x180013c76  lea     rcx, [rsp+48h+arg_8]
0x180013c7b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013c80  mov     eax, [rdi]
0x180013c82  test    al, 2
0x180013c84  jnz     short loc_180013C95
0x180013c86  and     eax, 0FFFFF63Eh
0x180013c8b  and     ebx, 9C1h
0x180013c91  or      eax, ebx
0x180013c93  mov     [rdi], eax
0x180013c95  mov     rbx, [rsp+48h+arg_10]
0x180013c9a  mov     rax, rdi
0x180013c9d  mov     rbp, [rsp+48h+arg_18]
0x180013ca2  add     rsp, 30h
0x180013ca6  pop     r14
0x180013ca8  pop     rdi
0x180013ca9  pop     rsi
0x180013caa  retn
```
