# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ee60`
- end: `0x18000ef99`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fc54`

## callees

- `0x180005c8c`
- `0x180006744`
- `0x18000a96c`
- `0x18000ee60`
- `0x18000f3d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ef1e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000ef1e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_GPM_CreatePSOTracking__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_GPM_CreatePSOTracking__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_GPM_CreatePSOTracking__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180042F88);
      v16 = &stru_180042F88;
      if ( !v5
        || v5 != dword_180042F9C
        || (v14[0] = 1,
            v14[1] = Feature_GPM_CreatePSOTracking__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180042FC0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_GPM_CreatePSOTracking__descriptor, 0xFFFFFFFB);
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
0x18000ee60  mov     [rsp+arg_10], rbx
0x18000ee65  mov     [rsp+arg_18], rbp
0x18000ee6a  mov     [rsp+arg_0], rcx
0x18000ee6f  push    rsi
0x18000ee70  push    rdi
0x18000ee71  push    r14
0x18000ee73  sub     rsp, 30h
0x18000ee77  mov     rsi, cs:Feature_GPM_CreatePSOTracking__descriptor
0x18000ee7e  mov     rdi, rdx
0x18000ee81  mov     qword ptr [rdx], 0
0x18000ee88  mov     eax, [rsi]
0x18000ee8a  mov     [rdx], eax
0x18000ee8c  and     eax, 6
0x18000ee8f  cmp     al, 6
0x18000ee91  jz      loc_18000EF83
0x18000ee97  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ee9c  lea     r8, [rsp+48h+arg_0]
0x18000eea1  mov     dword ptr [rsp+48h+arg_0], 0
0x18000eea9  lea     rdx, [rsp+48h+arg_8]
0x18000eeae  mov     ebp, eax
0x18000eeb0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_CreatePSOTracking@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_CreatePSOTracking>::GetCurrentFeatureEnabledState(int *)
0x18000eeb5  mov     eax, [rdi]
0x18000eeb7  mov     rbx, [rsp+48h+arg_8]
0x18000eebc  cmp     dword ptr [rsp+48h+arg_0], 0
0x18000eec1  mov     edx, eax
0x18000eec3  mov     [rdi], eax
0x18000eec5  mov     ecx, eax
0x18000eec7  jz      short loc_18000EEE2
0x18000eec9  test    dl, 2
0x18000eecc  jnz     short loc_18000EEE2
0x18000eece  and     ecx, 0FFFFF63Eh
0x18000eed4  mov     eax, ebx
0x18000eed6  and     eax, 9C1h
0x18000eedb  or      ecx, eax
0x18000eedd  or      ecx, 2
0x18000eee0  mov     [rdi], ecx
0x18000eee2  mov     r8d, edx
0x18000eee5  and     r8d, 4
0x18000eee9  jnz     short loc_18000EEFD
0x18000eeeb  btr     ecx, 0Ah
0x18000eeef  mov     eax, ebx
0x18000eef1  and     eax, 400h
0x18000eef6  or      ecx, eax
0x18000eef8  or      ecx, 4
0x18000eefb  mov     [rdi], ecx
0x18000eefd  mov     eax, edx
0x18000eeff  lock cmpxchg [rsi], ecx
0x18000ef03  jnz     short loc_18000EEBC
0x18000ef05  test    r8d, r8d
0x18000ef08  jnz     short loc_18000EF6E
0x18000ef0a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ef10  test    eax, eax
0x18000ef12  jz      short loc_18000EF6E
0x18000ef14  lea     r14, stru_180042F88
0x18000ef1b  mov     rcx, r14; SRWLock
0x18000ef1e  call    cs:__imp_AcquireSRWLockExclusive
0x18000ef24  mov     eax, cs:dword_180042F9C
0x18000ef2a  mov     [rsp+48h+arg_8], r14
0x18000ef2f  test    ebp, ebp
0x18000ef31  jz      short loc_18000EF60
0x18000ef33  cmp     ebp, eax
0x18000ef35  jnz     short loc_18000EF60
0x18000ef37  mov     r8d, 10h; unsigned __int64
0x18000ef3d  mov     [rsp+48h+var_28], 1
0x18000ef46  lea     rdx, [rsp+48h+var_28]; void *
0x18000ef4b  mov     [rsp+48h+var_20], rsi
0x18000ef50  lea     rcx, qword_180042FC0; this
0x18000ef57  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000ef5c  test    al, al
0x18000ef5e  jnz     short loc_18000EF64
0x18000ef60  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000ef64  lea     rcx, [rsp+48h+arg_8]
0x18000ef69  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000ef6e  mov     eax, [rdi]
0x18000ef70  test    al, 2
0x18000ef72  jnz     short loc_18000EF83
0x18000ef74  and     eax, 0FFFFF63Eh
0x18000ef79  and     ebx, 9C1h
0x18000ef7f  or      eax, ebx
0x18000ef81  mov     [rdi], eax
0x18000ef83  mov     rbx, [rsp+48h+arg_10]
0x18000ef88  mov     rax, rdi
0x18000ef8b  mov     rbp, [rsp+48h+arg_18]
0x18000ef90  add     rsp, 30h
0x18000ef94  pop     r14
0x18000ef96  pop     rdi
0x18000ef97  pop     rsi
0x18000ef98  retn
```
