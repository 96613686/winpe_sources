# wil::details::FeatureImpl<__WilFeatureTraits_Feature_61214098>::GetCachedFeatureEnabledState(void)

- ea: `0x180014d44`
- end: `0x180014e7d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_61214098@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001aff8`
- `0x18001cef8`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180014d44`
- `0x180016ef4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014e02`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014e02`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_61214098>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_61214098__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_61214098__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_61214098>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_61214098__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_61214098__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_61214098__descriptor, 0xFFFFFFFB);
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
0x180014d44  mov     [rsp+arg_10], rbx
0x180014d49  mov     [rsp+arg_18], rbp
0x180014d4e  mov     [rsp+arg_0], rcx
0x180014d53  push    rsi
0x180014d54  push    rdi
0x180014d55  push    r14
0x180014d57  sub     rsp, 30h
0x180014d5b  mov     rsi, cs:Feature_61214098__descriptor
0x180014d62  mov     rdi, rdx
0x180014d65  mov     qword ptr [rdx], 0
0x180014d6c  mov     eax, [rsi]
0x180014d6e  mov     [rdx], eax
0x180014d70  and     eax, 6
0x180014d73  cmp     al, 6
0x180014d75  jz      loc_180014E67
0x180014d7b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014d80  lea     r8, [rsp+48h+arg_0]
0x180014d85  mov     dword ptr [rsp+48h+arg_0], 0
0x180014d8d  lea     rdx, [rsp+48h+arg_8]
0x180014d92  mov     ebp, eax
0x180014d94  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_61214098@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_61214098>::GetCurrentFeatureEnabledState(int *)
0x180014d99  mov     eax, [rdi]
0x180014d9b  mov     rbx, [rsp+48h+arg_8]
0x180014da0  cmp     dword ptr [rsp+48h+arg_0], 0
0x180014da5  mov     edx, eax
0x180014da7  mov     [rdi], eax
0x180014da9  mov     ecx, eax
0x180014dab  jz      short loc_180014DC6
0x180014dad  test    dl, 2
0x180014db0  jnz     short loc_180014DC6
0x180014db2  and     ecx, 0FFFFF63Eh
0x180014db8  mov     eax, ebx
0x180014dba  and     eax, 9C1h
0x180014dbf  or      ecx, eax
0x180014dc1  or      ecx, 2
0x180014dc4  mov     [rdi], ecx
0x180014dc6  mov     r8d, edx
0x180014dc9  and     r8d, 4
0x180014dcd  jnz     short loc_180014DE1
0x180014dcf  btr     ecx, 0Ah
0x180014dd3  mov     eax, ebx
0x180014dd5  and     eax, 400h
0x180014dda  or      ecx, eax
0x180014ddc  or      ecx, 4
0x180014ddf  mov     [rdi], ecx
0x180014de1  mov     eax, edx
0x180014de3  lock cmpxchg [rsi], ecx
0x180014de7  jnz     short loc_180014DA0
0x180014de9  test    r8d, r8d
0x180014dec  jnz     short loc_180014E52
0x180014dee  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180014df4  test    eax, eax
0x180014df6  jz      short loc_180014E52
0x180014df8  lea     r14, SRWLock
0x180014dff  mov     rcx, r14; SRWLock
0x180014e02  call    cs:__imp_AcquireSRWLockExclusive
0x180014e08  mov     eax, cs:dword_18002EED4
0x180014e0e  mov     [rsp+48h+arg_8], r14
0x180014e13  test    ebp, ebp
0x180014e15  jz      short loc_180014E44
0x180014e17  cmp     ebp, eax
0x180014e19  jnz     short loc_180014E44
0x180014e1b  mov     r8d, 10h; unsigned __int64
0x180014e21  mov     [rsp+48h+var_28], 3
0x180014e2a  lea     rdx, [rsp+48h+var_28]; void *
0x180014e2f  mov     [rsp+48h+var_20], rsi
0x180014e34  lea     rcx, qword_18002EEF8; this
0x180014e3b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180014e40  test    al, al
0x180014e42  jnz     short loc_180014E48
0x180014e44  lock and dword ptr [rsi], 0FFFFFFFBh
0x180014e48  lea     rcx, [rsp+48h+arg_8]
0x180014e4d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014e52  mov     eax, [rdi]
0x180014e54  test    al, 2
0x180014e56  jnz     short loc_180014E67
0x180014e58  and     eax, 0FFFFF63Eh
0x180014e5d  and     ebx, 9C1h
0x180014e63  or      eax, ebx
0x180014e65  mov     [rdi], eax
0x180014e67  mov     rbx, [rsp+48h+arg_10]
0x180014e6c  mov     rax, rdi
0x180014e6f  mov     rbp, [rsp+48h+arg_18]
0x180014e74  add     rsp, 30h
0x180014e78  pop     r14
0x180014e7a  pop     rdi
0x180014e7b  pop     rsi
0x180014e7c  retn
```
