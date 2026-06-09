# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x180005a24`
- end: `0x180005b4d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `297`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800090e0`

## callees

- `0x180003d78`
- `0x180004650`
- `0x180004944`
- `0x180005a24`
- `0x1800063fc`
- `0x18000ad18`

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
      wil::AcquireSRWLockExclusive(&v16, (RTL_SRWLOCK *)qword_180018220);
      if ( !v5
        || v5 != dword_180018234
        || (v14[0] = 3,
            v14[1] = Feature_ValLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180018258, v14, 0x10u)) )
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
0x180005a24  mov     [rsp+arg_10], rbx
0x180005a29  mov     [rsp+arg_0], rcx
0x180005a2e  push    rbp
0x180005a2f  push    rsi
0x180005a30  push    rdi
0x180005a31  sub     rsp, 30h
0x180005a35  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180005a3c  mov     rdi, rdx
0x180005a3f  mov     qword ptr [rdx], 0
0x180005a46  mov     eax, [rsi]
0x180005a48  mov     [rdx], eax
0x180005a4a  and     eax, 6
0x180005a4d  cmp     al, 6
0x180005a4f  jz      loc_180005B3D
0x180005a55  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180005a5a  lea     r8, [rsp+48h+arg_0]
0x180005a5f  mov     dword ptr [rsp+48h+arg_0], 0
0x180005a67  lea     rdx, [rsp+48h+arg_8]
0x180005a6c  mov     ebp, eax
0x180005a6e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x180005a73  mov     eax, [rdi]
0x180005a75  mov     rbx, [rsp+48h+arg_8]
0x180005a7a  cmp     dword ptr [rsp+48h+arg_0], 0
0x180005a7f  mov     edx, eax
0x180005a81  mov     [rdi], eax
0x180005a83  mov     ecx, eax
0x180005a85  jz      short loc_180005AA0
0x180005a87  test    dl, 2
0x180005a8a  jnz     short loc_180005AA0
0x180005a8c  and     ecx, 0FFFFF63Eh
0x180005a92  mov     eax, ebx
0x180005a94  and     eax, 9C1h
0x180005a99  or      ecx, eax
0x180005a9b  or      ecx, 2
0x180005a9e  mov     [rdi], ecx
0x180005aa0  mov     r8d, edx
0x180005aa3  and     r8d, 4
0x180005aa7  jnz     short loc_180005ABB
0x180005aa9  btr     ecx, 0Ah
0x180005aad  mov     eax, ebx
0x180005aaf  and     eax, 400h
0x180005ab4  or      ecx, eax
0x180005ab6  or      ecx, 4
0x180005ab9  mov     [rdi], ecx
0x180005abb  mov     eax, edx
0x180005abd  lock cmpxchg [rsi], ecx
0x180005ac1  jnz     short loc_180005A7A
0x180005ac3  test    r8d, r8d
0x180005ac6  jnz     short loc_180005B28
0x180005ac8  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180005ace  test    eax, eax
0x180005ad0  jz      short loc_180005B28
0x180005ad2  lea     rdx, qword_180018220
0x180005ad9  lea     rcx, [rsp+48h+arg_8]
0x180005ade  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180005ae3  mov     eax, cs:dword_180018234
0x180005ae9  test    ebp, ebp
0x180005aeb  jz      short loc_180005B1A
0x180005aed  cmp     ebp, eax
0x180005aef  jnz     short loc_180005B1A
0x180005af1  mov     r8d, 10h; unsigned __int64
0x180005af7  mov     [rsp+48h+var_28], 3
0x180005b00  lea     rdx, [rsp+48h+var_28]; void *
0x180005b05  mov     [rsp+48h+var_20], rsi
0x180005b0a  lea     rcx, qword_180018258; this
0x180005b11  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180005b16  test    al, al
0x180005b18  jnz     short loc_180005B1E
0x180005b1a  lock and dword ptr [rsi], 0FFFFFFFBh
0x180005b1e  lea     rcx, [rsp+48h+arg_8]
0x180005b23  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180005b28  mov     eax, [rdi]
0x180005b2a  test    al, 2
0x180005b2c  jnz     short loc_180005B3D
0x180005b2e  and     eax, 0FFFFF63Eh
0x180005b33  and     ebx, 9C1h
0x180005b39  or      eax, ebx
0x180005b3b  mov     [rdi], eax
0x180005b3d  mov     rbx, [rsp+48h+arg_10]
0x180005b42  mov     rax, rdi
0x180005b45  add     rsp, 30h
0x180005b49  pop     rdi
0x180005b4a  pop     rsi
0x180005b4b  pop     rbp
0x180005b4c  retn
```
