# wil::details::FeatureImpl<__WilFeatureTraits_Feature_SpacesPoolVersion2700>::GetCachedFeatureEnabledState(void)

- ea: `0x140009f38`
- end: `0x14000a071`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SpacesPoolVersion2700@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000a258`
- `0x14000b7ec`

## callees

- `0x140004604`
- `0x14000526c`
- `0x14000949c`
- `0x140009f38`
- `0x14000a078`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140009ff6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140009ff6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_SpacesPoolVersion2700>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_SpacesPoolVersion2700__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_SpacesPoolVersion2700__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_SpacesPoolVersion2700>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_SpacesPoolVersion2700__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_140027ED8);
      v16 = &stru_140027ED8;
      if ( !v5
        || v5 != dword_140027EEC
        || (v14[0] = 3,
            v14[1] = Feature_SpacesPoolVersion2700__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_140027F10, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_SpacesPoolVersion2700__descriptor, 0xFFFFFFFB);
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
0x140009f38  mov     [rsp+arg_10], rbx
0x140009f3d  mov     [rsp+arg_18], rbp
0x140009f42  mov     [rsp+arg_0], rcx
0x140009f47  push    rsi
0x140009f48  push    rdi
0x140009f49  push    r14
0x140009f4b  sub     rsp, 30h
0x140009f4f  mov     rsi, cs:Feature_SpacesPoolVersion2700__descriptor
0x140009f56  mov     rdi, rdx
0x140009f59  mov     qword ptr [rdx], 0
0x140009f60  mov     eax, [rsi]
0x140009f62  mov     [rdx], eax
0x140009f64  and     eax, 6
0x140009f67  cmp     al, 6
0x140009f69  jz      loc_14000A05B
0x140009f6f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140009f74  lea     r8, [rsp+48h+arg_0]
0x140009f79  mov     dword ptr [rsp+48h+arg_0], 0
0x140009f81  lea     rdx, [rsp+48h+arg_8]
0x140009f86  mov     ebp, eax
0x140009f88  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_SpacesPoolVersion2700@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SpacesPoolVersion2700>::GetCurrentFeatureEnabledState(int *)
0x140009f8d  mov     eax, [rdi]
0x140009f8f  mov     rbx, [rsp+48h+arg_8]
0x140009f94  cmp     dword ptr [rsp+48h+arg_0], 0
0x140009f99  mov     edx, eax
0x140009f9b  mov     [rdi], eax
0x140009f9d  mov     ecx, eax
0x140009f9f  jz      short loc_140009FBA
0x140009fa1  test    dl, 2
0x140009fa4  jnz     short loc_140009FBA
0x140009fa6  and     ecx, 0FFFFF63Eh
0x140009fac  mov     eax, ebx
0x140009fae  and     eax, 9C1h
0x140009fb3  or      ecx, eax
0x140009fb5  or      ecx, 2
0x140009fb8  mov     [rdi], ecx
0x140009fba  mov     r8d, edx
0x140009fbd  and     r8d, 4
0x140009fc1  jnz     short loc_140009FD5
0x140009fc3  btr     ecx, 0Ah
0x140009fc7  mov     eax, ebx
0x140009fc9  and     eax, 400h
0x140009fce  or      ecx, eax
0x140009fd0  or      ecx, 4
0x140009fd3  mov     [rdi], ecx
0x140009fd5  mov     eax, edx
0x140009fd7  lock cmpxchg [rsi], ecx
0x140009fdb  jnz     short loc_140009F94
0x140009fdd  test    r8d, r8d
0x140009fe0  jnz     short loc_14000A046
0x140009fe2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x140009fe8  test    eax, eax
0x140009fea  jz      short loc_14000A046
0x140009fec  lea     r14, stru_140027ED8
0x140009ff3  mov     rcx, r14; SRWLock
0x140009ff6  call    cs:__imp_AcquireSRWLockExclusive
0x140009ffc  mov     eax, cs:dword_140027EEC
0x14000a002  mov     [rsp+48h+arg_8], r14
0x14000a007  test    ebp, ebp
0x14000a009  jz      short loc_14000A038
0x14000a00b  cmp     ebp, eax
0x14000a00d  jnz     short loc_14000A038
0x14000a00f  mov     r8d, 10h; unsigned __int64
0x14000a015  mov     [rsp+48h+var_28], 3
0x14000a01e  lea     rdx, [rsp+48h+var_28]; void *
0x14000a023  mov     [rsp+48h+var_20], rsi
0x14000a028  lea     rcx, qword_140027F10; this
0x14000a02f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000a034  test    al, al
0x14000a036  jnz     short loc_14000A03C
0x14000a038  lock and dword ptr [rsi], 0FFFFFFFBh
0x14000a03c  lea     rcx, [rsp+48h+arg_8]
0x14000a041  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000a046  mov     eax, [rdi]
0x14000a048  test    al, 2
0x14000a04a  jnz     short loc_14000A05B
0x14000a04c  and     eax, 0FFFFF63Eh
0x14000a051  and     ebx, 9C1h
0x14000a057  or      eax, ebx
0x14000a059  mov     [rdi], eax
0x14000a05b  mov     rbx, [rsp+48h+arg_10]
0x14000a060  mov     rax, rdi
0x14000a063  mov     rbp, [rsp+48h+arg_18]
0x14000a068  add     rsp, 30h
0x14000a06c  pop     r14
0x14000a06e  pop     rdi
0x14000a06f  pop     rsi
0x14000a070  retn
```
