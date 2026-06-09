# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(void)

- ea: `0x180013504`
- end: `0x180013644`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015608`

## callees

- `0x180007630`
- `0x180009fc0`
- `0x18001171c`
- `0x180013504`
- `0x180014280`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800135c2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800135c2`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_Future__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_Future__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180029CA8);
      v16 = &stru_180029CA8;
      if ( !v5
        || v5 != dword_180029CBC
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_Future__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180029CF0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_Future__descriptor, 0xFFFFFFFB);
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
0x180013504  mov     [rsp+arg_10], rbx
0x180013509  mov     [rsp+arg_18], rbp
0x18001350e  mov     [rsp+arg_0], rcx
0x180013513  push    rsi
0x180013514  push    rdi
0x180013515  push    r14
0x180013517  sub     rsp, 30h
0x18001351b  mov     rsi, cs:Feature_Standalone_Future__descriptor
0x180013522  mov     rdi, rdx
0x180013525  mov     qword ptr [rdx], 0
0x18001352c  mov     eax, [rsi]
0x18001352e  mov     [rdx], eax
0x180013530  and     eax, 6
0x180013533  cmp     al, 6
0x180013535  jz      loc_18001362D
0x18001353b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013540  lea     r8, [rsp+48h+arg_0]
0x180013545  mov     dword ptr [rsp+48h+arg_0], 0
0x18001354d  lea     rdx, [rsp+48h+arg_8]
0x180013552  mov     ebp, eax
0x180013554  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_Future@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_Future>::GetCurrentFeatureEnabledState(int *)
0x180013559  mov     eax, [rdi]
0x18001355b  mov     rbx, [rsp+48h+arg_8]
0x180013560  cmp     dword ptr [rsp+48h+arg_0], 0
0x180013565  mov     edx, eax
0x180013567  mov     [rdi], eax
0x180013569  mov     ecx, eax
0x18001356b  jz      short loc_180013586
0x18001356d  test    dl, 2
0x180013570  jnz     short loc_180013586
0x180013572  and     ecx, 0FFFFF63Eh
0x180013578  mov     eax, ebx
0x18001357a  and     eax, 9C1h
0x18001357f  or      ecx, eax
0x180013581  or      ecx, 2
0x180013584  mov     [rdi], ecx
0x180013586  mov     r8d, edx
0x180013589  and     r8d, 4
0x18001358d  jnz     short loc_1800135A1
0x18001358f  btr     ecx, 0Ah
0x180013593  mov     eax, ebx
0x180013595  and     eax, 400h
0x18001359a  or      ecx, eax
0x18001359c  or      ecx, 4
0x18001359f  mov     [rdi], ecx
0x1800135a1  mov     eax, edx
0x1800135a3  lock cmpxchg [rsi], ecx
0x1800135a7  jnz     short loc_180013560
0x1800135a9  test    r8d, r8d
0x1800135ac  jnz     short loc_180013618
0x1800135ae  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800135b4  test    eax, eax
0x1800135b6  jz      short loc_180013618
0x1800135b8  lea     r14, stru_180029CA8
0x1800135bf  mov     rcx, r14; SRWLock
0x1800135c2  call    cs:__imp_AcquireSRWLockExclusive
0x1800135c9  nop     dword ptr [rax+rax+00h]
0x1800135ce  mov     eax, cs:dword_180029CBC
0x1800135d4  mov     [rsp+48h+arg_8], r14
0x1800135d9  test    ebp, ebp
0x1800135db  jz      short loc_18001360A
0x1800135dd  cmp     ebp, eax
0x1800135df  jnz     short loc_18001360A
0x1800135e1  mov     r8d, 10h; unsigned __int64
0x1800135e7  mov     [rsp+48h+var_28], 3
0x1800135f0  lea     rdx, [rsp+48h+var_28]; void *
0x1800135f5  mov     [rsp+48h+var_20], rsi
0x1800135fa  lea     rcx, qword_180029CF0; this
0x180013601  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180013606  test    al, al
0x180013608  jnz     short loc_18001360E
0x18001360a  lock and dword ptr [rsi], 0FFFFFFFBh
0x18001360e  lea     rcx, [rsp+48h+arg_8]
0x180013613  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013618  mov     eax, [rdi]
0x18001361a  test    al, 2
0x18001361c  jnz     short loc_18001362D
0x18001361e  and     eax, 0FFFFF63Eh
0x180013623  and     ebx, 9C1h
0x180013629  or      eax, ebx
0x18001362b  mov     [rdi], eax
0x18001362d  mov     rbx, [rsp+48h+arg_10]
0x180013632  mov     rax, rdi
0x180013635  mov     rbp, [rsp+48h+arg_18]
0x18001363a  add     rsp, 30h
0x18001363e  pop     r14
0x180013640  pop     rdi
0x180013641  pop     rsi
0x180013642  retn
```
