# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180015e74`
- end: `0x180015fad`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b760`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180015e74`
- `0x1800178ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015f32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015f32`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UxLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxLabTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_UxLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_UxLabTest__descriptor, 0xFFFFFFFB);
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
0x180015e74  mov     [rsp+arg_10], rbx
0x180015e79  mov     [rsp+arg_18], rbp
0x180015e7e  mov     [rsp+arg_0], rcx
0x180015e83  push    rsi
0x180015e84  push    rdi
0x180015e85  push    r14
0x180015e87  sub     rsp, 30h
0x180015e8b  mov     rsi, cs:Feature_UxLabTest__descriptor
0x180015e92  mov     rdi, rdx
0x180015e95  mov     qword ptr [rdx], 0
0x180015e9c  mov     eax, [rsi]
0x180015e9e  mov     [rdx], eax
0x180015ea0  and     eax, 6
0x180015ea3  cmp     al, 6
0x180015ea5  jz      loc_180015F97
0x180015eab  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015eb0  lea     r8, [rsp+48h+arg_0]
0x180015eb5  mov     dword ptr [rsp+48h+arg_0], 0
0x180015ebd  lea     rdx, [rsp+48h+arg_8]
0x180015ec2  mov     ebp, eax
0x180015ec4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxLabTest>::GetCurrentFeatureEnabledState(int *)
0x180015ec9  mov     eax, [rdi]
0x180015ecb  mov     rbx, [rsp+48h+arg_8]
0x180015ed0  cmp     dword ptr [rsp+48h+arg_0], 0
0x180015ed5  mov     edx, eax
0x180015ed7  mov     [rdi], eax
0x180015ed9  mov     ecx, eax
0x180015edb  jz      short loc_180015EF6
0x180015edd  test    dl, 2
0x180015ee0  jnz     short loc_180015EF6
0x180015ee2  and     ecx, 0FFFFF63Eh
0x180015ee8  mov     eax, ebx
0x180015eea  and     eax, 9C1h
0x180015eef  or      ecx, eax
0x180015ef1  or      ecx, 2
0x180015ef4  mov     [rdi], ecx
0x180015ef6  mov     r8d, edx
0x180015ef9  and     r8d, 4
0x180015efd  jnz     short loc_180015F11
0x180015eff  btr     ecx, 0Ah
0x180015f03  mov     eax, ebx
0x180015f05  and     eax, 400h
0x180015f0a  or      ecx, eax
0x180015f0c  or      ecx, 4
0x180015f0f  mov     [rdi], ecx
0x180015f11  mov     eax, edx
0x180015f13  lock cmpxchg [rsi], ecx
0x180015f17  jnz     short loc_180015ED0
0x180015f19  test    r8d, r8d
0x180015f1c  jnz     short loc_180015F82
0x180015f1e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015f24  test    eax, eax
0x180015f26  jz      short loc_180015F82
0x180015f28  lea     r14, SRWLock
0x180015f2f  mov     rcx, r14; SRWLock
0x180015f32  call    cs:__imp_AcquireSRWLockExclusive
0x180015f38  mov     eax, cs:dword_18002EED4
0x180015f3e  mov     [rsp+48h+arg_8], r14
0x180015f43  test    ebp, ebp
0x180015f45  jz      short loc_180015F74
0x180015f47  cmp     ebp, eax
0x180015f49  jnz     short loc_180015F74
0x180015f4b  mov     r8d, 10h; unsigned __int64
0x180015f51  mov     [rsp+48h+var_28], 3
0x180015f5a  lea     rdx, [rsp+48h+var_28]; void *
0x180015f5f  mov     [rsp+48h+var_20], rsi
0x180015f64  lea     rcx, qword_18002EEF8; this
0x180015f6b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180015f70  test    al, al
0x180015f72  jnz     short loc_180015F78
0x180015f74  lock and dword ptr [rsi], 0FFFFFFFBh
0x180015f78  lea     rcx, [rsp+48h+arg_8]
0x180015f7d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015f82  mov     eax, [rdi]
0x180015f84  test    al, 2
0x180015f86  jnz     short loc_180015F97
0x180015f88  and     eax, 0FFFFF63Eh
0x180015f8d  and     ebx, 9C1h
0x180015f93  or      eax, ebx
0x180015f95  mov     [rdi], eax
0x180015f97  mov     rbx, [rsp+48h+arg_10]
0x180015f9c  mov     rax, rdi
0x180015f9f  mov     rbp, [rsp+48h+arg_18]
0x180015fa4  add     rsp, 30h
0x180015fa8  pop     r14
0x180015faa  pop     rdi
0x180015fab  pop     rsi
0x180015fac  retn
```
