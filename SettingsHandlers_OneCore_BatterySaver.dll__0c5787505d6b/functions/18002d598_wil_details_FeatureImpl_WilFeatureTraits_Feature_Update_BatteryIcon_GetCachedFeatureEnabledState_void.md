# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_BatteryIcon>::GetCachedFeatureEnabledState(void)

- ea: `0x18002d598`
- end: `0x18002d6d1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Update_BatteryIcon@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18002f794`
- `0x18002fa04`
- `0x180044ef8`

## callees

- `0x18000b508`
- `0x18000c08c`
- `0x18001026c`
- `0x18002d598`
- `0x18002d7d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d656`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002d656`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_BatteryIcon>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Update_BatteryIcon__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Update_BatteryIcon__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_BatteryIcon>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Update_BatteryIcon__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180066AF4
        || (v14[0] = 3,
            v14[1] = Feature_Update_BatteryIcon__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180066B18, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Update_BatteryIcon__descriptor, 0xFFFFFFFB);
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
0x18002d598  mov     [rsp+arg_10], rbx
0x18002d59d  mov     [rsp+arg_18], rbp
0x18002d5a2  mov     [rsp+arg_0], rcx
0x18002d5a7  push    rsi
0x18002d5a8  push    rdi
0x18002d5a9  push    r14
0x18002d5ab  sub     rsp, 30h
0x18002d5af  mov     rsi, cs:Feature_Update_BatteryIcon__descriptor
0x18002d5b6  mov     rdi, rdx
0x18002d5b9  mov     qword ptr [rdx], 0
0x18002d5c0  mov     eax, [rsi]
0x18002d5c2  mov     [rdx], eax
0x18002d5c4  and     eax, 6
0x18002d5c7  cmp     al, 6
0x18002d5c9  jz      loc_18002D6BB
0x18002d5cf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002d5d4  lea     r8, [rsp+48h+arg_0]
0x18002d5d9  mov     dword ptr [rsp+48h+arg_0], 0
0x18002d5e1  lea     rdx, [rsp+48h+arg_8]
0x18002d5e6  mov     ebp, eax
0x18002d5e8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Update_BatteryIcon@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Update_BatteryIcon>::GetCurrentFeatureEnabledState(int *)
0x18002d5ed  mov     eax, [rdi]
0x18002d5ef  mov     rbx, [rsp+48h+arg_8]
0x18002d5f4  cmp     dword ptr [rsp+48h+arg_0], 0
0x18002d5f9  mov     edx, eax
0x18002d5fb  mov     [rdi], eax
0x18002d5fd  mov     ecx, eax
0x18002d5ff  jz      short loc_18002D61A
0x18002d601  test    dl, 2
0x18002d604  jnz     short loc_18002D61A
0x18002d606  and     ecx, 0FFFFF63Eh
0x18002d60c  mov     eax, ebx
0x18002d60e  and     eax, 9C1h
0x18002d613  or      ecx, eax
0x18002d615  or      ecx, 2
0x18002d618  mov     [rdi], ecx
0x18002d61a  mov     r8d, edx
0x18002d61d  and     r8d, 4
0x18002d621  jnz     short loc_18002D635
0x18002d623  btr     ecx, 0Ah
0x18002d627  mov     eax, ebx
0x18002d629  and     eax, 400h
0x18002d62e  or      ecx, eax
0x18002d630  or      ecx, 4
0x18002d633  mov     [rdi], ecx
0x18002d635  mov     eax, edx
0x18002d637  lock cmpxchg [rsi], ecx
0x18002d63b  jnz     short loc_18002D5F4
0x18002d63d  test    r8d, r8d
0x18002d640  jnz     short loc_18002D6A6
0x18002d642  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002d648  test    eax, eax
0x18002d64a  jz      short loc_18002D6A6
0x18002d64c  lea     r14, SRWLock
0x18002d653  mov     rcx, r14; SRWLock
0x18002d656  call    cs:__imp_AcquireSRWLockExclusive
0x18002d65c  mov     eax, cs:dword_180066AF4
0x18002d662  mov     [rsp+48h+arg_8], r14
0x18002d667  test    ebp, ebp
0x18002d669  jz      short loc_18002D698
0x18002d66b  cmp     ebp, eax
0x18002d66d  jnz     short loc_18002D698
0x18002d66f  mov     r8d, 10h; unsigned __int64
0x18002d675  mov     [rsp+48h+var_28], 3
0x18002d67e  lea     rdx, [rsp+48h+var_28]; void *
0x18002d683  mov     [rsp+48h+var_20], rsi
0x18002d688  lea     rcx, qword_180066B18; this
0x18002d68f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002d694  test    al, al
0x18002d696  jnz     short loc_18002D69C
0x18002d698  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002d69c  lea     rcx, [rsp+48h+arg_8]
0x18002d6a1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002d6a6  mov     eax, [rdi]
0x18002d6a8  test    al, 2
0x18002d6aa  jnz     short loc_18002D6BB
0x18002d6ac  and     eax, 0FFFFF63Eh
0x18002d6b1  and     ebx, 9C1h
0x18002d6b7  or      eax, ebx
0x18002d6b9  mov     [rdi], eax
0x18002d6bb  mov     rbx, [rsp+48h+arg_10]
0x18002d6c0  mov     rax, rdi
0x18002d6c3  mov     rbp, [rsp+48h+arg_18]
0x18002d6c8  add     rsp, 30h
0x18002d6cc  pop     r14
0x18002d6ce  pop     rdi
0x18002d6cf  pop     rsi
0x18002d6d0  retn
```
