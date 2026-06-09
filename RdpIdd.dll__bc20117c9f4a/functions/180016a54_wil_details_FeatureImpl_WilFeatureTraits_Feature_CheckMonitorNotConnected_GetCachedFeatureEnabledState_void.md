# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CheckMonitorNotConnected>::GetCachedFeatureEnabledState(void)

- ea: `0x180016a54`
- end: `0x180016b94`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CheckMonitorNotConnected@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001cfe4`
- `0x180020f24`

## callees

- `0x180008fc0`
- `0x180009790`
- `0x18000c1f4`
- `0x180016a54`
- `0x180017220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016b12`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016b12`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CheckMonitorNotConnected>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CheckMonitorNotConnected__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CheckMonitorNotConnected__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CheckMonitorNotConnected>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CheckMonitorNotConnected__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800578F4
        || (v14[0] = 3,
            v14[1] = Feature_CheckMonitorNotConnected__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180057928, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_CheckMonitorNotConnected__descriptor, 0xFFFFFFFB);
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
0x180016a54  mov     [rsp+arg_10], rbx
0x180016a59  mov     [rsp+arg_18], rbp
0x180016a5e  mov     [rsp+arg_0], rcx
0x180016a63  push    rsi
0x180016a64  push    rdi
0x180016a65  push    r14
0x180016a67  sub     rsp, 30h
0x180016a6b  mov     rsi, cs:Feature_CheckMonitorNotConnected__descriptor
0x180016a72  mov     rdi, rdx
0x180016a75  mov     qword ptr [rdx], 0
0x180016a7c  mov     eax, [rsi]
0x180016a7e  mov     [rdx], eax
0x180016a80  and     eax, 6
0x180016a83  cmp     al, 6
0x180016a85  jz      loc_180016B7D
0x180016a8b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180016a90  lea     r8, [rsp+48h+arg_0]
0x180016a95  mov     dword ptr [rsp+48h+arg_0], 0
0x180016a9d  lea     rdx, [rsp+48h+arg_8]
0x180016aa2  mov     ebp, eax
0x180016aa4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CheckMonitorNotConnected@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CheckMonitorNotConnected>::GetCurrentFeatureEnabledState(int *)
0x180016aa9  mov     eax, [rdi]
0x180016aab  mov     rbx, [rsp+48h+arg_8]
0x180016ab0  cmp     dword ptr [rsp+48h+arg_0], 0
0x180016ab5  mov     edx, eax
0x180016ab7  mov     [rdi], eax
0x180016ab9  mov     ecx, eax
0x180016abb  jz      short loc_180016AD6
0x180016abd  test    dl, 2
0x180016ac0  jnz     short loc_180016AD6
0x180016ac2  and     ecx, 0FFFFF63Eh
0x180016ac8  mov     eax, ebx
0x180016aca  and     eax, 9C1h
0x180016acf  or      ecx, eax
0x180016ad1  or      ecx, 2
0x180016ad4  mov     [rdi], ecx
0x180016ad6  mov     r8d, edx
0x180016ad9  and     r8d, 4
0x180016add  jnz     short loc_180016AF1
0x180016adf  btr     ecx, 0Ah
0x180016ae3  mov     eax, ebx
0x180016ae5  and     eax, 400h
0x180016aea  or      ecx, eax
0x180016aec  or      ecx, 4
0x180016aef  mov     [rdi], ecx
0x180016af1  mov     eax, edx
0x180016af3  lock cmpxchg [rsi], ecx
0x180016af7  jnz     short loc_180016AB0
0x180016af9  test    r8d, r8d
0x180016afc  jnz     short loc_180016B68
0x180016afe  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180016b04  test    eax, eax
0x180016b06  jz      short loc_180016B68
0x180016b08  lea     r14, SRWLock
0x180016b0f  mov     rcx, r14; SRWLock
0x180016b12  call    cs:__imp_AcquireSRWLockExclusive
0x180016b19  nop     dword ptr [rax+rax+00h]
0x180016b1e  mov     eax, cs:dword_1800578F4
0x180016b24  mov     [rsp+48h+arg_8], r14
0x180016b29  test    ebp, ebp
0x180016b2b  jz      short loc_180016B5A
0x180016b2d  cmp     ebp, eax
0x180016b2f  jnz     short loc_180016B5A
0x180016b31  mov     r8d, 10h; unsigned __int64
0x180016b37  mov     [rsp+48h+var_28], 3
0x180016b40  lea     rdx, [rsp+48h+var_28]; void *
0x180016b45  mov     [rsp+48h+var_20], rsi
0x180016b4a  lea     rcx, qword_180057928; this
0x180016b51  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180016b56  test    al, al
0x180016b58  jnz     short loc_180016B5E
0x180016b5a  lock and dword ptr [rsi], 0FFFFFFFBh
0x180016b5e  lea     rcx, [rsp+48h+arg_8]
0x180016b63  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016b68  mov     eax, [rdi]
0x180016b6a  test    al, 2
0x180016b6c  jnz     short loc_180016B7D
0x180016b6e  and     eax, 0FFFFF63Eh
0x180016b73  and     ebx, 9C1h
0x180016b79  or      eax, ebx
0x180016b7b  mov     [rdi], eax
0x180016b7d  mov     rbx, [rsp+48h+arg_10]
0x180016b82  mov     rax, rdi
0x180016b85  mov     rbp, [rsp+48h+arg_18]
0x180016b8a  add     rsp, 30h
0x180016b8e  pop     r14
0x180016b90  pop     rdi
0x180016b91  pop     rsi
0x180016b92  retn
```
