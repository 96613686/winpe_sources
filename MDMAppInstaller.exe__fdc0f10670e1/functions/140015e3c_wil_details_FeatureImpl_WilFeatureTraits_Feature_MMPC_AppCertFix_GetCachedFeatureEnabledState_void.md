# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MMPC_AppCertFix>::GetCachedFeatureEnabledState(void)

- ea: `0x140015e3c`
- end: `0x140015f79`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MMPC_AppCertFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `317`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400180b4`

## callees

- `0x1400092f0`
- `0x14000b36c`
- `0x140012af8`
- `0x140015e3c`
- `0x140015f80`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140015f00`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140015f00`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MMPC_AppCertFix>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_MMPC_AppCertFix__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MMPC_AppCertFix__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_MMPC_AppCertFix>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MMPC_AppCertFix__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_14002BCD0);
      v16 = &stru_14002BCD0;
      if ( !v5
        || v5 != dword_14002BCE4
        || (v14[0] = 0,
            v14[1] = Feature_MMPC_AppCertFix__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_14002BD08, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_MMPC_AppCertFix__descriptor, 0xFFFFF7C1);
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
0x140015e3c  mov     [rsp-28h+arg_10], rbx
0x140015e41  mov     [rsp-28h+arg_0], rcx
0x140015e46  push    rbp
0x140015e47  push    rsi
0x140015e48  push    rdi
0x140015e49  push    r14
0x140015e4b  push    r15
0x140015e4d  mov     rbp, rsp
0x140015e50  sub     rsp, 30h
0x140015e54  mov     rsi, cs:Feature_MMPC_AppCertFix__descriptor
0x140015e5b  mov     rdi, rdx
0x140015e5e  mov     qword ptr [rdx], 0
0x140015e65  mov     eax, [rsi]
0x140015e67  mov     [rdx], eax
0x140015e69  and     eax, 6
0x140015e6c  cmp     al, 6
0x140015e6e  jz      loc_140015F65
0x140015e74  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140015e79  lea     r8, [rbp+arg_0]
0x140015e7d  mov     dword ptr [rbp+arg_0], 0
0x140015e84  lea     rdx, [rbp+arg_8]
0x140015e88  mov     r14d, eax
0x140015e8b  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MMPC_AppCertFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MMPC_AppCertFix>::GetCurrentFeatureEnabledState(int *)
0x140015e90  test    r14d, r14d
0x140015e93  jnz     short loc_140015E99
0x140015e95  mov     dword ptr [rbp+arg_0], r14d
0x140015e99  mov     eax, [rdi]
0x140015e9b  mov     rbx, [rbp+arg_8]
0x140015e9f  cmp     dword ptr [rbp+arg_0], 0
0x140015ea3  mov     edx, eax
0x140015ea5  mov     [rdi], eax
0x140015ea7  mov     ecx, eax
0x140015ea9  jz      short loc_140015EC4
0x140015eab  test    dl, 2
0x140015eae  jnz     short loc_140015EC4
0x140015eb0  and     ecx, 0FFFFF63Eh
0x140015eb6  mov     eax, ebx
0x140015eb8  and     eax, 9C1h
0x140015ebd  or      ecx, eax
0x140015ebf  or      ecx, 2
0x140015ec2  mov     [rdi], ecx
0x140015ec4  mov     r8d, edx
0x140015ec7  and     r8d, 4
0x140015ecb  jnz     short loc_140015EDF
0x140015ecd  btr     ecx, 0Ah
0x140015ed1  mov     eax, ebx
0x140015ed3  and     eax, 400h
0x140015ed8  or      ecx, eax
0x140015eda  or      ecx, 4
0x140015edd  mov     [rdi], ecx
0x140015edf  mov     eax, edx
0x140015ee1  lock cmpxchg [rsi], ecx
0x140015ee5  jnz     short loc_140015E9F
0x140015ee7  test    r8d, r8d
0x140015eea  jnz     short loc_140015F50
0x140015eec  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140015ef2  test    eax, eax
0x140015ef4  jz      short loc_140015F50
0x140015ef6  lea     r15, stru_14002BCD0
0x140015efd  mov     rcx, r15; SRWLock
0x140015f00  call    cs:__imp_AcquireSRWLockExclusive
0x140015f06  mov     eax, cs:dword_14002BCE4
0x140015f0c  mov     [rbp+arg_8], r15
0x140015f10  test    r14d, r14d
0x140015f13  jz      short loc_140015F40
0x140015f15  cmp     r14d, eax
0x140015f18  jnz     short loc_140015F40
0x140015f1a  mov     r8d, 10h; unsigned __int64
0x140015f20  mov     [rbp+var_10], 0
0x140015f28  lea     rdx, [rbp+var_10]; void *
0x140015f2c  mov     [rbp+var_8], rsi
0x140015f30  lea     rcx, qword_14002BD08; this
0x140015f37  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140015f3c  test    al, al
0x140015f3e  jnz     short loc_140015F47
0x140015f40  lock and dword ptr [rsi], 0FFFFF7C1h
0x140015f47  lea     rcx, [rbp+arg_8]
0x140015f4b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140015f50  mov     eax, [rdi]
0x140015f52  test    al, 2
0x140015f54  jnz     short loc_140015F65
0x140015f56  and     eax, 0FFFFF63Eh
0x140015f5b  and     ebx, 9C1h
0x140015f61  or      eax, ebx
0x140015f63  mov     [rdi], eax
0x140015f65  mov     rbx, [rsp+30h+arg_10]
0x140015f6a  mov     rax, rdi
0x140015f6d  add     rsp, 30h
0x140015f71  pop     r15
0x140015f73  pop     r14
0x140015f75  pop     rdi
0x140015f76  pop     rsi
0x140015f77  pop     rbp
0x140015f78  retn
```
