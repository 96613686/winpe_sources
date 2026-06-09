# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x180013a24`
- end: `0x180013b64`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015830`
- `0x180015bb0`

## callees

- `0x180007630`
- `0x180009fc0`
- `0x18001171c`
- `0x180013a24`
- `0x1800145c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013ae2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013ae2`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180029CA8);
      v16 = &stru_180029CA8;
      if ( !v5
        || v5 != dword_180029CBC
        || (v14[0] = 3,
            v14[1] = Feature_UxAccOptimization__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180029CF0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, 0xFFFFFFFB);
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
0x180013a24  mov     [rsp+arg_10], rbx
0x180013a29  mov     [rsp+arg_18], rbp
0x180013a2e  mov     [rsp+arg_0], rcx
0x180013a33  push    rsi
0x180013a34  push    rdi
0x180013a35  push    r14
0x180013a37  sub     rsp, 30h
0x180013a3b  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x180013a42  mov     rdi, rdx
0x180013a45  mov     qword ptr [rdx], 0
0x180013a4c  mov     eax, [rsi]
0x180013a4e  mov     [rdx], eax
0x180013a50  and     eax, 6
0x180013a53  cmp     al, 6
0x180013a55  jz      loc_180013B4D
0x180013a5b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013a60  lea     r8, [rsp+48h+arg_0]
0x180013a65  mov     dword ptr [rsp+48h+arg_0], 0
0x180013a6d  lea     rdx, [rsp+48h+arg_8]
0x180013a72  mov     ebp, eax
0x180013a74  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x180013a79  mov     eax, [rdi]
0x180013a7b  mov     rbx, [rsp+48h+arg_8]
0x180013a80  cmp     dword ptr [rsp+48h+arg_0], 0
0x180013a85  mov     edx, eax
0x180013a87  mov     [rdi], eax
0x180013a89  mov     ecx, eax
0x180013a8b  jz      short loc_180013AA6
0x180013a8d  test    dl, 2
0x180013a90  jnz     short loc_180013AA6
0x180013a92  and     ecx, 0FFFFF63Eh
0x180013a98  mov     eax, ebx
0x180013a9a  and     eax, 9C1h
0x180013a9f  or      ecx, eax
0x180013aa1  or      ecx, 2
0x180013aa4  mov     [rdi], ecx
0x180013aa6  mov     r8d, edx
0x180013aa9  and     r8d, 4
0x180013aad  jnz     short loc_180013AC1
0x180013aaf  btr     ecx, 0Ah
0x180013ab3  mov     eax, ebx
0x180013ab5  and     eax, 400h
0x180013aba  or      ecx, eax
0x180013abc  or      ecx, 4
0x180013abf  mov     [rdi], ecx
0x180013ac1  mov     eax, edx
0x180013ac3  lock cmpxchg [rsi], ecx
0x180013ac7  jnz     short loc_180013A80
0x180013ac9  test    r8d, r8d
0x180013acc  jnz     short loc_180013B38
0x180013ace  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013ad4  test    eax, eax
0x180013ad6  jz      short loc_180013B38
0x180013ad8  lea     r14, stru_180029CA8
0x180013adf  mov     rcx, r14; SRWLock
0x180013ae2  call    cs:__imp_AcquireSRWLockExclusive
0x180013ae9  nop     dword ptr [rax+rax+00h]
0x180013aee  mov     eax, cs:dword_180029CBC
0x180013af4  mov     [rsp+48h+arg_8], r14
0x180013af9  test    ebp, ebp
0x180013afb  jz      short loc_180013B2A
0x180013afd  cmp     ebp, eax
0x180013aff  jnz     short loc_180013B2A
0x180013b01  mov     r8d, 10h; unsigned __int64
0x180013b07  mov     [rsp+48h+var_28], 3
0x180013b10  lea     rdx, [rsp+48h+var_28]; void *
0x180013b15  mov     [rsp+48h+var_20], rsi
0x180013b1a  lea     rcx, qword_180029CF0; this
0x180013b21  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180013b26  test    al, al
0x180013b28  jnz     short loc_180013B2E
0x180013b2a  lock and dword ptr [rsi], 0FFFFFFFBh
0x180013b2e  lea     rcx, [rsp+48h+arg_8]
0x180013b33  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013b38  mov     eax, [rdi]
0x180013b3a  test    al, 2
0x180013b3c  jnz     short loc_180013B4D
0x180013b3e  and     eax, 0FFFFF63Eh
0x180013b43  and     ebx, 9C1h
0x180013b49  or      eax, ebx
0x180013b4b  mov     [rdi], eax
0x180013b4d  mov     rbx, [rsp+48h+arg_10]
0x180013b52  mov     rax, rdi
0x180013b55  mov     rbp, [rsp+48h+arg_18]
0x180013b5a  add     rsp, 30h
0x180013b5e  pop     r14
0x180013b60  pop     rdi
0x180013b61  pop     rsi
0x180013b62  retn
```
