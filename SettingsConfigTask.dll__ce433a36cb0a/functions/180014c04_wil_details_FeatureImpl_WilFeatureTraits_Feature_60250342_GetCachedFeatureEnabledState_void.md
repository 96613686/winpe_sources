# wil::details::FeatureImpl<__WilFeatureTraits_Feature_60250342>::GetCachedFeatureEnabledState(void)

- ea: `0x180014c04`
- end: `0x180014d3d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_60250342@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001af6c`
- `0x18001cebc`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180014c04`
- `0x180016e0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014cc2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014cc2`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_60250342>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_60250342__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_60250342__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_60250342>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_60250342__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 1,
            v14[1] = Feature_60250342__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_60250342__descriptor, 0xFFFFFFFB);
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
0x180014c04  mov     [rsp+arg_10], rbx
0x180014c09  mov     [rsp+arg_18], rbp
0x180014c0e  mov     [rsp+arg_0], rcx
0x180014c13  push    rsi
0x180014c14  push    rdi
0x180014c15  push    r14
0x180014c17  sub     rsp, 30h
0x180014c1b  mov     rsi, cs:Feature_60250342__descriptor
0x180014c22  mov     rdi, rdx
0x180014c25  mov     qword ptr [rdx], 0
0x180014c2c  mov     eax, [rsi]
0x180014c2e  mov     [rdx], eax
0x180014c30  and     eax, 6
0x180014c33  cmp     al, 6
0x180014c35  jz      loc_180014D27
0x180014c3b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014c40  lea     r8, [rsp+48h+arg_0]
0x180014c45  mov     dword ptr [rsp+48h+arg_0], 0
0x180014c4d  lea     rdx, [rsp+48h+arg_8]
0x180014c52  mov     ebp, eax
0x180014c54  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_60250342@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_60250342>::GetCurrentFeatureEnabledState(int *)
0x180014c59  mov     eax, [rdi]
0x180014c5b  mov     rbx, [rsp+48h+arg_8]
0x180014c60  cmp     dword ptr [rsp+48h+arg_0], 0
0x180014c65  mov     edx, eax
0x180014c67  mov     [rdi], eax
0x180014c69  mov     ecx, eax
0x180014c6b  jz      short loc_180014C86
0x180014c6d  test    dl, 2
0x180014c70  jnz     short loc_180014C86
0x180014c72  and     ecx, 0FFFFF63Eh
0x180014c78  mov     eax, ebx
0x180014c7a  and     eax, 9C1h
0x180014c7f  or      ecx, eax
0x180014c81  or      ecx, 2
0x180014c84  mov     [rdi], ecx
0x180014c86  mov     r8d, edx
0x180014c89  and     r8d, 4
0x180014c8d  jnz     short loc_180014CA1
0x180014c8f  btr     ecx, 0Ah
0x180014c93  mov     eax, ebx
0x180014c95  and     eax, 400h
0x180014c9a  or      ecx, eax
0x180014c9c  or      ecx, 4
0x180014c9f  mov     [rdi], ecx
0x180014ca1  mov     eax, edx
0x180014ca3  lock cmpxchg [rsi], ecx
0x180014ca7  jnz     short loc_180014C60
0x180014ca9  test    r8d, r8d
0x180014cac  jnz     short loc_180014D12
0x180014cae  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180014cb4  test    eax, eax
0x180014cb6  jz      short loc_180014D12
0x180014cb8  lea     r14, SRWLock
0x180014cbf  mov     rcx, r14; SRWLock
0x180014cc2  call    cs:__imp_AcquireSRWLockExclusive
0x180014cc8  mov     eax, cs:dword_18002EED4
0x180014cce  mov     [rsp+48h+arg_8], r14
0x180014cd3  test    ebp, ebp
0x180014cd5  jz      short loc_180014D04
0x180014cd7  cmp     ebp, eax
0x180014cd9  jnz     short loc_180014D04
0x180014cdb  mov     r8d, 10h; unsigned __int64
0x180014ce1  mov     [rsp+48h+var_28], 1
0x180014cea  lea     rdx, [rsp+48h+var_28]; void *
0x180014cef  mov     [rsp+48h+var_20], rsi
0x180014cf4  lea     rcx, qword_18002EEF8; this
0x180014cfb  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180014d00  test    al, al
0x180014d02  jnz     short loc_180014D08
0x180014d04  lock and dword ptr [rsi], 0FFFFFFFBh
0x180014d08  lea     rcx, [rsp+48h+arg_8]
0x180014d0d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014d12  mov     eax, [rdi]
0x180014d14  test    al, 2
0x180014d16  jnz     short loc_180014D27
0x180014d18  and     eax, 0FFFFF63Eh
0x180014d1d  and     ebx, 9C1h
0x180014d23  or      eax, ebx
0x180014d25  mov     [rdi], eax
0x180014d27  mov     rbx, [rsp+48h+arg_10]
0x180014d2c  mov     rax, rdi
0x180014d2f  mov     rbp, [rsp+48h+arg_18]
0x180014d34  add     rsp, 30h
0x180014d38  pop     r14
0x180014d3a  pop     rdi
0x180014d3b  pop     rsi
0x180014d3c  retn
```
