# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x180015ab4`
- end: `0x180015bed`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b5c4`
- `0x18001d024`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180015ab4`
- `0x180017608`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015b72`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015b72`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_TestAccPerf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_TestAccPerf__descriptor, 0xFFFFFFFB);
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
0x180015ab4  mov     [rsp+arg_10], rbx
0x180015ab9  mov     [rsp+arg_18], rbp
0x180015abe  mov     [rsp+arg_0], rcx
0x180015ac3  push    rsi
0x180015ac4  push    rdi
0x180015ac5  push    r14
0x180015ac7  sub     rsp, 30h
0x180015acb  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x180015ad2  mov     rdi, rdx
0x180015ad5  mov     qword ptr [rdx], 0
0x180015adc  mov     eax, [rsi]
0x180015ade  mov     [rdx], eax
0x180015ae0  and     eax, 6
0x180015ae3  cmp     al, 6
0x180015ae5  jz      loc_180015BD7
0x180015aeb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015af0  lea     r8, [rsp+48h+arg_0]
0x180015af5  mov     dword ptr [rsp+48h+arg_0], 0
0x180015afd  lea     rdx, [rsp+48h+arg_8]
0x180015b02  mov     ebp, eax
0x180015b04  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x180015b09  mov     eax, [rdi]
0x180015b0b  mov     rbx, [rsp+48h+arg_8]
0x180015b10  cmp     dword ptr [rsp+48h+arg_0], 0
0x180015b15  mov     edx, eax
0x180015b17  mov     [rdi], eax
0x180015b19  mov     ecx, eax
0x180015b1b  jz      short loc_180015B36
0x180015b1d  test    dl, 2
0x180015b20  jnz     short loc_180015B36
0x180015b22  and     ecx, 0FFFFF63Eh
0x180015b28  mov     eax, ebx
0x180015b2a  and     eax, 9C1h
0x180015b2f  or      ecx, eax
0x180015b31  or      ecx, 2
0x180015b34  mov     [rdi], ecx
0x180015b36  mov     r8d, edx
0x180015b39  and     r8d, 4
0x180015b3d  jnz     short loc_180015B51
0x180015b3f  btr     ecx, 0Ah
0x180015b43  mov     eax, ebx
0x180015b45  and     eax, 400h
0x180015b4a  or      ecx, eax
0x180015b4c  or      ecx, 4
0x180015b4f  mov     [rdi], ecx
0x180015b51  mov     eax, edx
0x180015b53  lock cmpxchg [rsi], ecx
0x180015b57  jnz     short loc_180015B10
0x180015b59  test    r8d, r8d
0x180015b5c  jnz     short loc_180015BC2
0x180015b5e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015b64  test    eax, eax
0x180015b66  jz      short loc_180015BC2
0x180015b68  lea     r14, SRWLock
0x180015b6f  mov     rcx, r14; SRWLock
0x180015b72  call    cs:__imp_AcquireSRWLockExclusive
0x180015b78  mov     eax, cs:dword_18002EED4
0x180015b7e  mov     [rsp+48h+arg_8], r14
0x180015b83  test    ebp, ebp
0x180015b85  jz      short loc_180015BB4
0x180015b87  cmp     ebp, eax
0x180015b89  jnz     short loc_180015BB4
0x180015b8b  mov     r8d, 10h; unsigned __int64
0x180015b91  mov     [rsp+48h+var_28], 3
0x180015b9a  lea     rdx, [rsp+48h+var_28]; void *
0x180015b9f  mov     [rsp+48h+var_20], rsi
0x180015ba4  lea     rcx, qword_18002EEF8; this
0x180015bab  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180015bb0  test    al, al
0x180015bb2  jnz     short loc_180015BB8
0x180015bb4  lock and dword ptr [rsi], 0FFFFFFFBh
0x180015bb8  lea     rcx, [rsp+48h+arg_8]
0x180015bbd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015bc2  mov     eax, [rdi]
0x180015bc4  test    al, 2
0x180015bc6  jnz     short loc_180015BD7
0x180015bc8  and     eax, 0FFFFF63Eh
0x180015bcd  and     ebx, 9C1h
0x180015bd3  or      eax, ebx
0x180015bd5  mov     [rdi], eax
0x180015bd7  mov     rbx, [rsp+48h+arg_10]
0x180015bdc  mov     rax, rdi
0x180015bdf  mov     rbp, [rsp+48h+arg_18]
0x180015be4  add     rsp, 30h
0x180015be8  pop     r14
0x180015bea  pop     rdi
0x180015beb  pop     rsi
0x180015bec  retn
```
