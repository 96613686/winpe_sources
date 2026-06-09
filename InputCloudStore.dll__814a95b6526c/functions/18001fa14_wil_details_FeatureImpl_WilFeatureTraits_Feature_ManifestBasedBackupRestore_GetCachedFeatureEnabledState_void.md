# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ManifestBasedBackupRestore>::GetCachedFeatureEnabledState(void)

- ea: `0x18001fa14`
- end: `0x18001fb4d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ManifestBasedBackupRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021144`

## callees

- `0x18001b3fc`
- `0x18001f3e4`
- `0x18001fa14`
- `0x18001fe1c`
- `0x180024b94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fad2`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001fad2`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ManifestBasedBackupRestore>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ManifestBasedBackupRestore__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ManifestBasedBackupRestore__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ManifestBasedBackupRestore>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_ManifestBasedBackupRestore__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800439BC
        || (v14[0] = 3,
            v14[1] = Feature_ManifestBasedBackupRestore__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_1800439E0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ManifestBasedBackupRestore__descriptor, 0xFFFFFFFB);
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
0x18001fa14  mov     [rsp+arg_10], rbx
0x18001fa19  mov     [rsp+arg_18], rbp
0x18001fa1e  mov     [rsp+arg_0], rcx
0x18001fa23  push    rsi
0x18001fa24  push    rdi
0x18001fa25  push    r14
0x18001fa27  sub     rsp, 30h
0x18001fa2b  mov     rsi, cs:Feature_ManifestBasedBackupRestore__descriptor
0x18001fa32  mov     rdi, rdx
0x18001fa35  mov     qword ptr [rdx], 0
0x18001fa3c  mov     eax, [rsi]
0x18001fa3e  mov     [rdx], eax
0x18001fa40  and     eax, 6
0x18001fa43  cmp     al, 6
0x18001fa45  jz      loc_18001FB37
0x18001fa4b  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001fa50  lea     r8, [rsp+48h+arg_0]
0x18001fa55  mov     dword ptr [rsp+48h+arg_0], 0
0x18001fa5d  lea     rdx, [rsp+48h+arg_8]
0x18001fa62  mov     ebp, eax
0x18001fa64  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ManifestBasedBackupRestore@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ManifestBasedBackupRestore>::GetCurrentFeatureEnabledState(int *)
0x18001fa69  mov     eax, [rdi]
0x18001fa6b  mov     rbx, [rsp+48h+arg_8]
0x18001fa70  cmp     dword ptr [rsp+48h+arg_0], 0
0x18001fa75  mov     edx, eax
0x18001fa77  mov     [rdi], eax
0x18001fa79  mov     ecx, eax
0x18001fa7b  jz      short loc_18001FA96
0x18001fa7d  test    dl, 2
0x18001fa80  jnz     short loc_18001FA96
0x18001fa82  and     ecx, 0FFFFF63Eh
0x18001fa88  mov     eax, ebx
0x18001fa8a  and     eax, 9C1h
0x18001fa8f  or      ecx, eax
0x18001fa91  or      ecx, 2
0x18001fa94  mov     [rdi], ecx
0x18001fa96  mov     r8d, edx
0x18001fa99  and     r8d, 4
0x18001fa9d  jnz     short loc_18001FAB1
0x18001fa9f  btr     ecx, 0Ah
0x18001faa3  mov     eax, ebx
0x18001faa5  and     eax, 400h
0x18001faaa  or      ecx, eax
0x18001faac  or      ecx, 4
0x18001faaf  mov     [rdi], ecx
0x18001fab1  mov     eax, edx
0x18001fab3  lock cmpxchg [rsi], ecx
0x18001fab7  jnz     short loc_18001FA70
0x18001fab9  test    r8d, r8d
0x18001fabc  jnz     short loc_18001FB22
0x18001fabe  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001fac4  test    eax, eax
0x18001fac6  jz      short loc_18001FB22
0x18001fac8  lea     r14, SRWLock
0x18001facf  mov     rcx, r14; SRWLock
0x18001fad2  call    cs:__imp_AcquireSRWLockExclusive
0x18001fad8  mov     eax, cs:dword_1800439BC
0x18001fade  mov     [rsp+48h+arg_8], r14
0x18001fae3  test    ebp, ebp
0x18001fae5  jz      short loc_18001FB14
0x18001fae7  cmp     ebp, eax
0x18001fae9  jnz     short loc_18001FB14
0x18001faeb  mov     r8d, 10h; unsigned __int64
0x18001faf1  mov     [rsp+48h+var_28], 3
0x18001fafa  lea     rdx, [rsp+48h+var_28]; void *
0x18001faff  mov     [rsp+48h+var_20], rsi
0x18001fb04  lea     rcx, qword_1800439E0; this
0x18001fb0b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18001fb10  test    al, al
0x18001fb12  jnz     short loc_18001FB18
0x18001fb14  lock and dword ptr [rsi], 0FFFFFFFBh
0x18001fb18  lea     rcx, [rsp+48h+arg_8]
0x18001fb1d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001fb22  mov     eax, [rdi]
0x18001fb24  test    al, 2
0x18001fb26  jnz     short loc_18001FB37
0x18001fb28  and     eax, 0FFFFF63Eh
0x18001fb2d  and     ebx, 9C1h
0x18001fb33  or      eax, ebx
0x18001fb35  mov     [rdi], eax
0x18001fb37  mov     rbx, [rsp+48h+arg_10]
0x18001fb3c  mov     rax, rdi
0x18001fb3f  mov     rbp, [rsp+48h+arg_18]
0x18001fb44  add     rsp, 30h
0x18001fb48  pop     r14
0x18001fb4a  pop     rdi
0x18001fb4b  pop     rsi
0x18001fb4c  retn
```
