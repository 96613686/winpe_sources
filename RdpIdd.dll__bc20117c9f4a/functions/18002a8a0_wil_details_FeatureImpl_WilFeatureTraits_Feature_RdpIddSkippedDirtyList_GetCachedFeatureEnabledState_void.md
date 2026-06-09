# wil::details::FeatureImpl<__WilFeatureTraits_Feature_RdpIddSkippedDirtyList>::GetCachedFeatureEnabledState(void)

- ea: `0x18002a8a0`
- end: `0x18002a9e0`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_RdpIddSkippedDirtyList@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c740`
- `0x18002d474`

## callees

- `0x180008fc0`
- `0x180009790`
- `0x18000c1f4`
- `0x18002a8a0`
- `0x18002b1e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a95e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002a95e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_RdpIddSkippedDirtyList>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_RdpIddSkippedDirtyList__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_RdpIddSkippedDirtyList__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_RdpIddSkippedDirtyList>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_RdpIddSkippedDirtyList__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800578F4
        || (v14[0] = 3,
            v14[1] = Feature_RdpIddSkippedDirtyList__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180057928, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_RdpIddSkippedDirtyList__descriptor, 0xFFFFFFFB);
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
0x18002a8a0  mov     [rsp+arg_10], rbx
0x18002a8a5  mov     [rsp+arg_18], rbp
0x18002a8aa  mov     [rsp+arg_0], rcx
0x18002a8af  push    rsi
0x18002a8b0  push    rdi
0x18002a8b1  push    r14
0x18002a8b3  sub     rsp, 30h
0x18002a8b7  mov     rsi, cs:Feature_RdpIddSkippedDirtyList__descriptor
0x18002a8be  mov     rdi, rdx
0x18002a8c1  mov     qword ptr [rdx], 0
0x18002a8c8  mov     eax, [rsi]
0x18002a8ca  mov     [rdx], eax
0x18002a8cc  and     eax, 6
0x18002a8cf  cmp     al, 6
0x18002a8d1  jz      loc_18002A9C9
0x18002a8d7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002a8dc  lea     r8, [rsp+48h+arg_0]
0x18002a8e1  mov     dword ptr [rsp+48h+arg_0], 0
0x18002a8e9  lea     rdx, [rsp+48h+arg_8]
0x18002a8ee  mov     ebp, eax
0x18002a8f0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_RdpIddSkippedDirtyList@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RdpIddSkippedDirtyList>::GetCurrentFeatureEnabledState(int *)
0x18002a8f5  mov     eax, [rdi]
0x18002a8f7  mov     rbx, [rsp+48h+arg_8]
0x18002a8fc  cmp     dword ptr [rsp+48h+arg_0], 0
0x18002a901  mov     edx, eax
0x18002a903  mov     [rdi], eax
0x18002a905  mov     ecx, eax
0x18002a907  jz      short loc_18002A922
0x18002a909  test    dl, 2
0x18002a90c  jnz     short loc_18002A922
0x18002a90e  and     ecx, 0FFFFF63Eh
0x18002a914  mov     eax, ebx
0x18002a916  and     eax, 9C1h
0x18002a91b  or      ecx, eax
0x18002a91d  or      ecx, 2
0x18002a920  mov     [rdi], ecx
0x18002a922  mov     r8d, edx
0x18002a925  and     r8d, 4
0x18002a929  jnz     short loc_18002A93D
0x18002a92b  btr     ecx, 0Ah
0x18002a92f  mov     eax, ebx
0x18002a931  and     eax, 400h
0x18002a936  or      ecx, eax
0x18002a938  or      ecx, 4
0x18002a93b  mov     [rdi], ecx
0x18002a93d  mov     eax, edx
0x18002a93f  lock cmpxchg [rsi], ecx
0x18002a943  jnz     short loc_18002A8FC
0x18002a945  test    r8d, r8d
0x18002a948  jnz     short loc_18002A9B4
0x18002a94a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002a950  test    eax, eax
0x18002a952  jz      short loc_18002A9B4
0x18002a954  lea     r14, SRWLock
0x18002a95b  mov     rcx, r14; SRWLock
0x18002a95e  call    cs:__imp_AcquireSRWLockExclusive
0x18002a965  nop     dword ptr [rax+rax+00h]
0x18002a96a  mov     eax, cs:dword_1800578F4
0x18002a970  mov     [rsp+48h+arg_8], r14
0x18002a975  test    ebp, ebp
0x18002a977  jz      short loc_18002A9A6
0x18002a979  cmp     ebp, eax
0x18002a97b  jnz     short loc_18002A9A6
0x18002a97d  mov     r8d, 10h; unsigned __int64
0x18002a983  mov     [rsp+48h+var_28], 3
0x18002a98c  lea     rdx, [rsp+48h+var_28]; void *
0x18002a991  mov     [rsp+48h+var_20], rsi
0x18002a996  lea     rcx, qword_180057928; this
0x18002a99d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002a9a2  test    al, al
0x18002a9a4  jnz     short loc_18002A9AA
0x18002a9a6  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002a9aa  lea     rcx, [rsp+48h+arg_8]
0x18002a9af  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002a9b4  mov     eax, [rdi]
0x18002a9b6  test    al, 2
0x18002a9b8  jnz     short loc_18002A9C9
0x18002a9ba  and     eax, 0FFFFF63Eh
0x18002a9bf  and     ebx, 9C1h
0x18002a9c5  or      eax, ebx
0x18002a9c7  mov     [rdi], eax
0x18002a9c9  mov     rbx, [rsp+48h+arg_10]
0x18002a9ce  mov     rax, rdi
0x18002a9d1  mov     rbp, [rsp+48h+arg_18]
0x18002a9d6  add     rsp, 30h
0x18002a9da  pop     r14
0x18002a9dc  pop     rdi
0x18002a9dd  pop     rsi
0x18002a9de  retn
```
