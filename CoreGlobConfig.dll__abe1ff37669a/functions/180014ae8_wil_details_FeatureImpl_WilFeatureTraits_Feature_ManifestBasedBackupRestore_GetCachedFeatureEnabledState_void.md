# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ManifestBasedBackupRestore>::GetCachedFeatureEnabledState(void)

- ea: `0x180014ae8`
- end: `0x180014c21`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ManifestBasedBackupRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800187e8`

## callees

- `0x180011488`
- `0x1800144a4`
- `0x180014ae8`
- `0x180014e40`
- `0x18001ea10`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014ba6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014ba6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ManifestBasedBackupRestore>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ManifestBasedBackupRestore__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ManifestBasedBackupRestore__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ManifestBasedBackupRestore>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_ManifestBasedBackupRestore__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180032F3C
        || (v14[0] = 3,
            v14[1] = Feature_ManifestBasedBackupRestore__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180032F60, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ManifestBasedBackupRestore__descriptor, 0xFFFFFFFB);
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
0x180014ae8  mov     [rsp+arg_10], rbx
0x180014aed  mov     [rsp+arg_18], rbp
0x180014af2  mov     [rsp+arg_0], rcx
0x180014af7  push    rsi
0x180014af8  push    rdi
0x180014af9  push    r14
0x180014afb  sub     rsp, 30h
0x180014aff  mov     rsi, cs:Feature_ManifestBasedBackupRestore__descriptor
0x180014b06  mov     rdi, rdx
0x180014b09  mov     qword ptr [rdx], 0
0x180014b10  mov     eax, [rsi]
0x180014b12  mov     [rdx], eax
0x180014b14  and     eax, 6
0x180014b17  cmp     al, 6
0x180014b19  jz      loc_180014C0B
0x180014b1f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014b24  lea     r8, [rsp+48h+arg_0]
0x180014b29  mov     dword ptr [rsp+48h+arg_0], 0
0x180014b31  lea     rdx, [rsp+48h+arg_8]
0x180014b36  mov     ebp, eax
0x180014b38  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ManifestBasedBackupRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ManifestBasedBackupRestore>::GetCurrentFeatureEnabledState(int *)
0x180014b3d  mov     eax, [rdi]
0x180014b3f  mov     rbx, [rsp+48h+arg_8]
0x180014b44  cmp     dword ptr [rsp+48h+arg_0], 0
0x180014b49  mov     edx, eax
0x180014b4b  mov     [rdi], eax
0x180014b4d  mov     ecx, eax
0x180014b4f  jz      short loc_180014B6A
0x180014b51  test    dl, 2
0x180014b54  jnz     short loc_180014B6A
0x180014b56  and     ecx, 0FFFFF63Eh
0x180014b5c  mov     eax, ebx
0x180014b5e  and     eax, 9C1h
0x180014b63  or      ecx, eax
0x180014b65  or      ecx, 2
0x180014b68  mov     [rdi], ecx
0x180014b6a  mov     r8d, edx
0x180014b6d  and     r8d, 4
0x180014b71  jnz     short loc_180014B85
0x180014b73  btr     ecx, 0Ah
0x180014b77  mov     eax, ebx
0x180014b79  and     eax, 400h
0x180014b7e  or      ecx, eax
0x180014b80  or      ecx, 4
0x180014b83  mov     [rdi], ecx
0x180014b85  mov     eax, edx
0x180014b87  lock cmpxchg [rsi], ecx
0x180014b8b  jnz     short loc_180014B44
0x180014b8d  test    r8d, r8d
0x180014b90  jnz     short loc_180014BF6
0x180014b92  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180014b98  test    eax, eax
0x180014b9a  jz      short loc_180014BF6
0x180014b9c  lea     r14, SRWLock
0x180014ba3  mov     rcx, r14; SRWLock
0x180014ba6  call    cs:__imp_AcquireSRWLockExclusive
0x180014bac  mov     eax, cs:dword_180032F3C
0x180014bb2  mov     [rsp+48h+arg_8], r14
0x180014bb7  test    ebp, ebp
0x180014bb9  jz      short loc_180014BE8
0x180014bbb  cmp     ebp, eax
0x180014bbd  jnz     short loc_180014BE8
0x180014bbf  mov     r8d, 10h; unsigned __int64
0x180014bc5  mov     [rsp+48h+var_28], 3
0x180014bce  lea     rdx, [rsp+48h+var_28]; void *
0x180014bd3  mov     [rsp+48h+var_20], rsi
0x180014bd8  lea     rcx, qword_180032F60; this
0x180014bdf  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180014be4  test    al, al
0x180014be6  jnz     short loc_180014BEC
0x180014be8  lock and dword ptr [rsi], 0FFFFFFFBh
0x180014bec  lea     rcx, [rsp+48h+arg_8]
0x180014bf1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014bf6  mov     eax, [rdi]
0x180014bf8  test    al, 2
0x180014bfa  jnz     short loc_180014C0B
0x180014bfc  and     eax, 0FFFFF63Eh
0x180014c01  and     ebx, 9C1h
0x180014c07  or      eax, ebx
0x180014c09  mov     [rdi], eax
0x180014c0b  mov     rbx, [rsp+48h+arg_10]
0x180014c10  mov     rax, rdi
0x180014c13  mov     rbp, [rsp+48h+arg_18]
0x180014c18  add     rsp, 30h
0x180014c1c  pop     r14
0x180014c1e  pop     rdi
0x180014c1f  pop     rsi
0x180014c20  retn
```
