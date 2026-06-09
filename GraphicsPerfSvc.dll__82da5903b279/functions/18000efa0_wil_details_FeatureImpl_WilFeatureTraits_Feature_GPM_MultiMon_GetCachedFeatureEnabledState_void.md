# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::GetCachedFeatureEnabledState(void)

- ea: `0x18000efa0`
- end: `0x18000f0d9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MultiMon@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fcec`

## callees

- `0x180005c8c`
- `0x180006744`
- `0x18000a96c`
- `0x18000efa0`
- `0x18000f448`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f05e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000f05e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_GPM_MultiMon__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_GPM_MultiMon__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_GPM_MultiMon__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180042F88);
      v16 = &stru_180042F88;
      if ( !v5
        || v5 != dword_180042F9C
        || (v14[0] = 1,
            v14[1] = Feature_GPM_MultiMon__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180042FC0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_GPM_MultiMon__descriptor, 0xFFFFFFFB);
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
0x18000efa0  mov     [rsp+arg_10], rbx
0x18000efa5  mov     [rsp+arg_18], rbp
0x18000efaa  mov     [rsp+arg_0], rcx
0x18000efaf  push    rsi
0x18000efb0  push    rdi
0x18000efb1  push    r14
0x18000efb3  sub     rsp, 30h
0x18000efb7  mov     rsi, cs:Feature_GPM_MultiMon__descriptor
0x18000efbe  mov     rdi, rdx
0x18000efc1  mov     qword ptr [rdx], 0
0x18000efc8  mov     eax, [rsi]
0x18000efca  mov     [rdx], eax
0x18000efcc  and     eax, 6
0x18000efcf  cmp     al, 6
0x18000efd1  jz      loc_18000F0C3
0x18000efd7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000efdc  lea     r8, [rsp+48h+arg_0]
0x18000efe1  mov     dword ptr [rsp+48h+arg_0], 0
0x18000efe9  lea     rdx, [rsp+48h+arg_8]
0x18000efee  mov     ebp, eax
0x18000eff0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_MultiMon@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_MultiMon>::GetCurrentFeatureEnabledState(int *)
0x18000eff5  mov     eax, [rdi]
0x18000eff7  mov     rbx, [rsp+48h+arg_8]
0x18000effc  cmp     dword ptr [rsp+48h+arg_0], 0
0x18000f001  mov     edx, eax
0x18000f003  mov     [rdi], eax
0x18000f005  mov     ecx, eax
0x18000f007  jz      short loc_18000F022
0x18000f009  test    dl, 2
0x18000f00c  jnz     short loc_18000F022
0x18000f00e  and     ecx, 0FFFFF63Eh
0x18000f014  mov     eax, ebx
0x18000f016  and     eax, 9C1h
0x18000f01b  or      ecx, eax
0x18000f01d  or      ecx, 2
0x18000f020  mov     [rdi], ecx
0x18000f022  mov     r8d, edx
0x18000f025  and     r8d, 4
0x18000f029  jnz     short loc_18000F03D
0x18000f02b  btr     ecx, 0Ah
0x18000f02f  mov     eax, ebx
0x18000f031  and     eax, 400h
0x18000f036  or      ecx, eax
0x18000f038  or      ecx, 4
0x18000f03b  mov     [rdi], ecx
0x18000f03d  mov     eax, edx
0x18000f03f  lock cmpxchg [rsi], ecx
0x18000f043  jnz     short loc_18000EFFC
0x18000f045  test    r8d, r8d
0x18000f048  jnz     short loc_18000F0AE
0x18000f04a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000f050  test    eax, eax
0x18000f052  jz      short loc_18000F0AE
0x18000f054  lea     r14, stru_180042F88
0x18000f05b  mov     rcx, r14; SRWLock
0x18000f05e  call    cs:__imp_AcquireSRWLockExclusive
0x18000f064  mov     eax, cs:dword_180042F9C
0x18000f06a  mov     [rsp+48h+arg_8], r14
0x18000f06f  test    ebp, ebp
0x18000f071  jz      short loc_18000F0A0
0x18000f073  cmp     ebp, eax
0x18000f075  jnz     short loc_18000F0A0
0x18000f077  mov     r8d, 10h; unsigned __int64
0x18000f07d  mov     [rsp+48h+var_28], 1
0x18000f086  lea     rdx, [rsp+48h+var_28]; void *
0x18000f08b  mov     [rsp+48h+var_20], rsi
0x18000f090  lea     rcx, qword_180042FC0; this
0x18000f097  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000f09c  test    al, al
0x18000f09e  jnz     short loc_18000F0A4
0x18000f0a0  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000f0a4  lea     rcx, [rsp+48h+arg_8]
0x18000f0a9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000f0ae  mov     eax, [rdi]
0x18000f0b0  test    al, 2
0x18000f0b2  jnz     short loc_18000F0C3
0x18000f0b4  and     eax, 0FFFFF63Eh
0x18000f0b9  and     ebx, 9C1h
0x18000f0bf  or      eax, ebx
0x18000f0c1  mov     [rdi], eax
0x18000f0c3  mov     rbx, [rsp+48h+arg_10]
0x18000f0c8  mov     rax, rdi
0x18000f0cb  mov     rbp, [rsp+48h+arg_18]
0x18000f0d0  add     rsp, 30h
0x18000f0d4  pop     r14
0x18000f0d6  pop     rdi
0x18000f0d7  pop     rsi
0x18000f0d8  retn
```
