# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x1800160f4`
- end: `0x18001622d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b86c`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x1800160f4`
- `0x180017a04`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800161b2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800161b2`

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
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_ValLabTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
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
0x1800160f4  mov     [rsp+arg_10], rbx
0x1800160f9  mov     [rsp+arg_18], rbp
0x1800160fe  mov     [rsp+arg_0], rcx
0x180016103  push    rsi
0x180016104  push    rdi
0x180016105  push    r14
0x180016107  sub     rsp, 30h
0x18001610b  mov     rsi, cs:Feature_ValLabTest__descriptor
0x180016112  mov     rdi, rdx
0x180016115  mov     qword ptr [rdx], 0
0x18001611c  mov     eax, [rsi]
0x18001611e  mov     [rdx], eax
0x180016120  and     eax, 6
0x180016123  cmp     al, 6
0x180016125  jz      loc_180016217
0x18001612b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180016130  lea     r8, [rsp+48h+arg_0]
0x180016135  mov     dword ptr [rsp+48h+arg_0], 0
0x18001613d  lea     rdx, [rsp+48h+arg_8]
0x180016142  mov     ebp, eax
0x180016144  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x180016149  mov     eax, [rdi]
0x18001614b  mov     rbx, [rsp+48h+arg_8]
0x180016150  cmp     dword ptr [rsp+48h+arg_0], 0
0x180016155  mov     edx, eax
0x180016157  mov     [rdi], eax
0x180016159  mov     ecx, eax
0x18001615b  jz      short loc_180016176
0x18001615d  test    dl, 2
0x180016160  jnz     short loc_180016176
0x180016162  and     ecx, 0FFFFF63Eh
0x180016168  mov     eax, ebx
0x18001616a  and     eax, 9C1h
0x18001616f  or      ecx, eax
0x180016171  or      ecx, 2
0x180016174  mov     [rdi], ecx
0x180016176  mov     r8d, edx
0x180016179  and     r8d, 4
0x18001617d  jnz     short loc_180016191
0x18001617f  btr     ecx, 0Ah
0x180016183  mov     eax, ebx
0x180016185  and     eax, 400h
0x18001618a  or      ecx, eax
0x18001618c  or      ecx, 4
0x18001618f  mov     [rdi], ecx
0x180016191  mov     eax, edx
0x180016193  lock cmpxchg [rsi], ecx
0x180016197  jnz     short loc_180016150
0x180016199  test    r8d, r8d
0x18001619c  jnz     short loc_180016202
0x18001619e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800161a4  test    eax, eax
0x1800161a6  jz      short loc_180016202
0x1800161a8  lea     r14, SRWLock
0x1800161af  mov     rcx, r14; SRWLock
0x1800161b2  call    cs:__imp_AcquireSRWLockExclusive
0x1800161b8  mov     eax, cs:dword_18002EED4
0x1800161be  mov     [rsp+48h+arg_8], r14
0x1800161c3  test    ebp, ebp
0x1800161c5  jz      short loc_1800161F4
0x1800161c7  cmp     ebp, eax
0x1800161c9  jnz     short loc_1800161F4
0x1800161cb  mov     r8d, 10h; unsigned __int64
0x1800161d1  mov     [rsp+48h+var_28], 3
0x1800161da  lea     rdx, [rsp+48h+var_28]; void *
0x1800161df  mov     [rsp+48h+var_20], rsi
0x1800161e4  lea     rcx, qword_18002EEF8; this
0x1800161eb  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800161f0  test    al, al
0x1800161f2  jnz     short loc_1800161F8
0x1800161f4  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800161f8  lea     rcx, [rsp+48h+arg_8]
0x1800161fd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016202  mov     eax, [rdi]
0x180016204  test    al, 2
0x180016206  jnz     short loc_180016217
0x180016208  and     eax, 0FFFFF63Eh
0x18001620d  and     ebx, 9C1h
0x180016213  or      eax, ebx
0x180016215  mov     [rdi], eax
0x180016217  mov     rbx, [rsp+48h+arg_10]
0x18001621c  mov     rax, rdi
0x18001621f  mov     rbp, [rsp+48h+arg_18]
0x180016224  add     rsp, 30h
0x180016228  pop     r14
0x18001622a  pop     rdi
0x18001622b  pop     rsi
0x18001622c  retn
```
