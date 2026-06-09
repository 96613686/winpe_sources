# wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableIddCx111>::GetCachedFeatureEnabledState(void)

- ea: `0x18000eed4`
- end: `0x18000f014`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableIddCx111@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010440`
- `0x180010830`

## callees

- `0x180008fc0`
- `0x180009790`
- `0x18000c1f4`
- `0x18000eed4`
- `0x18000f01c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ef92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ef92`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableIddCx111>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_EnableIddCx111__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_EnableIddCx111__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableIddCx111>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_EnableIddCx111__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800578F4
        || (v14[0] = 3,
            v14[1] = Feature_EnableIddCx111__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180057928, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_EnableIddCx111__descriptor, 0xFFFFFFFB);
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
0x18000eed4  mov     [rsp+arg_10], rbx
0x18000eed9  mov     [rsp+arg_18], rbp
0x18000eede  mov     [rsp+arg_0], rcx
0x18000eee3  push    rsi
0x18000eee4  push    rdi
0x18000eee5  push    r14
0x18000eee7  sub     rsp, 30h
0x18000eeeb  mov     rsi, cs:Feature_EnableIddCx111__descriptor
0x18000eef2  mov     rdi, rdx
0x18000eef5  mov     qword ptr [rdx], 0
0x18000eefc  mov     eax, [rsi]
0x18000eefe  mov     [rdx], eax
0x18000ef00  and     eax, 6
0x18000ef03  cmp     al, 6
0x18000ef05  jz      loc_18000EFFD
0x18000ef0b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ef10  lea     r8, [rsp+48h+arg_0]
0x18000ef15  mov     dword ptr [rsp+48h+arg_0], 0
0x18000ef1d  lea     rdx, [rsp+48h+arg_8]
0x18000ef22  mov     ebp, eax
0x18000ef24  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_EnableIddCx111@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EnableIddCx111>::GetCurrentFeatureEnabledState(int *)
0x18000ef29  mov     eax, [rdi]
0x18000ef2b  mov     rbx, [rsp+48h+arg_8]
0x18000ef30  cmp     dword ptr [rsp+48h+arg_0], 0
0x18000ef35  mov     edx, eax
0x18000ef37  mov     [rdi], eax
0x18000ef39  mov     ecx, eax
0x18000ef3b  jz      short loc_18000EF56
0x18000ef3d  test    dl, 2
0x18000ef40  jnz     short loc_18000EF56
0x18000ef42  and     ecx, 0FFFFF63Eh
0x18000ef48  mov     eax, ebx
0x18000ef4a  and     eax, 9C1h
0x18000ef4f  or      ecx, eax
0x18000ef51  or      ecx, 2
0x18000ef54  mov     [rdi], ecx
0x18000ef56  mov     r8d, edx
0x18000ef59  and     r8d, 4
0x18000ef5d  jnz     short loc_18000EF71
0x18000ef5f  btr     ecx, 0Ah
0x18000ef63  mov     eax, ebx
0x18000ef65  and     eax, 400h
0x18000ef6a  or      ecx, eax
0x18000ef6c  or      ecx, 4
0x18000ef6f  mov     [rdi], ecx
0x18000ef71  mov     eax, edx
0x18000ef73  lock cmpxchg [rsi], ecx
0x18000ef77  jnz     short loc_18000EF30
0x18000ef79  test    r8d, r8d
0x18000ef7c  jnz     short loc_18000EFE8
0x18000ef7e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ef84  test    eax, eax
0x18000ef86  jz      short loc_18000EFE8
0x18000ef88  lea     r14, SRWLock
0x18000ef8f  mov     rcx, r14; SRWLock
0x18000ef92  call    cs:__imp_AcquireSRWLockExclusive
0x18000ef99  nop     dword ptr [rax+rax+00h]
0x18000ef9e  mov     eax, cs:dword_1800578F4
0x18000efa4  mov     [rsp+48h+arg_8], r14
0x18000efa9  test    ebp, ebp
0x18000efab  jz      short loc_18000EFDA
0x18000efad  cmp     ebp, eax
0x18000efaf  jnz     short loc_18000EFDA
0x18000efb1  mov     r8d, 10h; unsigned __int64
0x18000efb7  mov     [rsp+48h+var_28], 3
0x18000efc0  lea     rdx, [rsp+48h+var_28]; void *
0x18000efc5  mov     [rsp+48h+var_20], rsi
0x18000efca  lea     rcx, qword_180057928; this
0x18000efd1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000efd6  test    al, al
0x18000efd8  jnz     short loc_18000EFDE
0x18000efda  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000efde  lea     rcx, [rsp+48h+arg_8]
0x18000efe3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000efe8  mov     eax, [rdi]
0x18000efea  test    al, 2
0x18000efec  jnz     short loc_18000EFFD
0x18000efee  and     eax, 0FFFFF63Eh
0x18000eff3  and     ebx, 9C1h
0x18000eff9  or      eax, ebx
0x18000effb  mov     [rdi], eax
0x18000effd  mov     rbx, [rsp+48h+arg_10]
0x18000f002  mov     rax, rdi
0x18000f005  mov     rbp, [rsp+48h+arg_18]
0x18000f00a  add     rsp, 30h
0x18000f00e  pop     r14
0x18000f010  pop     rdi
0x18000f011  pop     rsi
0x18000f012  retn
```
