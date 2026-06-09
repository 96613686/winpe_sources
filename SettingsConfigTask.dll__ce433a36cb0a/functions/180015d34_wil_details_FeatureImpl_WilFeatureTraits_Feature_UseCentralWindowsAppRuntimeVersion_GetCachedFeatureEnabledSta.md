# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::GetCachedFeatureEnabledState(void)

- ea: `0x180015d34`
- end: `0x180015e6d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b6d4`
- `0x18001d09c`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180015d34`
- `0x1800177e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015df2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015df2`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UseCentralWindowsAppRuntimeVersion__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UseCentralWindowsAppRuntimeVersion__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_UseCentralWindowsAppRuntimeVersion__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_UseCentralWindowsAppRuntimeVersion__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_UseCentralWindowsAppRuntimeVersion__descriptor, 0xFFFFFFFB);
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
0x180015d34  mov     [rsp+arg_10], rbx
0x180015d39  mov     [rsp+arg_18], rbp
0x180015d3e  mov     [rsp+arg_0], rcx
0x180015d43  push    rsi
0x180015d44  push    rdi
0x180015d45  push    r14
0x180015d47  sub     rsp, 30h
0x180015d4b  mov     rsi, cs:Feature_UseCentralWindowsAppRuntimeVersion__descriptor
0x180015d52  mov     rdi, rdx
0x180015d55  mov     qword ptr [rdx], 0
0x180015d5c  mov     eax, [rsi]
0x180015d5e  mov     [rdx], eax
0x180015d60  and     eax, 6
0x180015d63  cmp     al, 6
0x180015d65  jz      loc_180015E57
0x180015d6b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180015d70  lea     r8, [rsp+48h+arg_0]
0x180015d75  mov     dword ptr [rsp+48h+arg_0], 0
0x180015d7d  lea     rdx, [rsp+48h+arg_8]
0x180015d82  mov     ebp, eax
0x180015d84  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::GetCurrentFeatureEnabledState(int *)
0x180015d89  mov     eax, [rdi]
0x180015d8b  mov     rbx, [rsp+48h+arg_8]
0x180015d90  cmp     dword ptr [rsp+48h+arg_0], 0
0x180015d95  mov     edx, eax
0x180015d97  mov     [rdi], eax
0x180015d99  mov     ecx, eax
0x180015d9b  jz      short loc_180015DB6
0x180015d9d  test    dl, 2
0x180015da0  jnz     short loc_180015DB6
0x180015da2  and     ecx, 0FFFFF63Eh
0x180015da8  mov     eax, ebx
0x180015daa  and     eax, 9C1h
0x180015daf  or      ecx, eax
0x180015db1  or      ecx, 2
0x180015db4  mov     [rdi], ecx
0x180015db6  mov     r8d, edx
0x180015db9  and     r8d, 4
0x180015dbd  jnz     short loc_180015DD1
0x180015dbf  btr     ecx, 0Ah
0x180015dc3  mov     eax, ebx
0x180015dc5  and     eax, 400h
0x180015dca  or      ecx, eax
0x180015dcc  or      ecx, 4
0x180015dcf  mov     [rdi], ecx
0x180015dd1  mov     eax, edx
0x180015dd3  lock cmpxchg [rsi], ecx
0x180015dd7  jnz     short loc_180015D90
0x180015dd9  test    r8d, r8d
0x180015ddc  jnz     short loc_180015E42
0x180015dde  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015de4  test    eax, eax
0x180015de6  jz      short loc_180015E42
0x180015de8  lea     r14, SRWLock
0x180015def  mov     rcx, r14; SRWLock
0x180015df2  call    cs:__imp_AcquireSRWLockExclusive
0x180015df8  mov     eax, cs:dword_18002EED4
0x180015dfe  mov     [rsp+48h+arg_8], r14
0x180015e03  test    ebp, ebp
0x180015e05  jz      short loc_180015E34
0x180015e07  cmp     ebp, eax
0x180015e09  jnz     short loc_180015E34
0x180015e0b  mov     r8d, 10h; unsigned __int64
0x180015e11  mov     [rsp+48h+var_28], 3
0x180015e1a  lea     rdx, [rsp+48h+var_28]; void *
0x180015e1f  mov     [rsp+48h+var_20], rsi
0x180015e24  lea     rcx, qword_18002EEF8; this
0x180015e2b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180015e30  test    al, al
0x180015e32  jnz     short loc_180015E38
0x180015e34  lock and dword ptr [rsi], 0FFFFFFFBh
0x180015e38  lea     rcx, [rsp+48h+arg_8]
0x180015e3d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015e42  mov     eax, [rdi]
0x180015e44  test    al, 2
0x180015e46  jnz     short loc_180015E57
0x180015e48  and     eax, 0FFFFF63Eh
0x180015e4d  and     ebx, 9C1h
0x180015e53  or      eax, ebx
0x180015e55  mov     [rdi], eax
0x180015e57  mov     rbx, [rsp+48h+arg_10]
0x180015e5c  mov     rax, rdi
0x180015e5f  mov     rbp, [rsp+48h+arg_18]
0x180015e64  add     rsp, 30h
0x180015e68  pop     r14
0x180015e6a  pop     rdi
0x180015e6b  pop     rsi
0x180015e6c  retn
```
