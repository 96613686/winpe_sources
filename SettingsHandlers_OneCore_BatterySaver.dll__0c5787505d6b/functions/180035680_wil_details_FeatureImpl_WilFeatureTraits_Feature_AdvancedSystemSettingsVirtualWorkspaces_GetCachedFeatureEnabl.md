# wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdvancedSystemSettingsVirtualWorkspaces>::GetCachedFeatureEnabledState(void)

- ea: `0x180035680`
- end: `0x1800357b9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AdvancedSystemSettingsVirtualWorkspaces@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036fec`
- `0x1800379b0`

## callees

- `0x18000b508`
- `0x18000c08c`
- `0x18001026c`
- `0x180035680`
- `0x180035d88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003573e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003573e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdvancedSystemSettingsVirtualWorkspaces>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_AdvancedSystemSettingsVirtualWorkspaces__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_AdvancedSystemSettingsVirtualWorkspaces__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdvancedSystemSettingsVirtualWorkspaces>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_AdvancedSystemSettingsVirtualWorkspaces__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180066AF4
        || (v14[0] = 1,
            v14[1] = Feature_AdvancedSystemSettingsVirtualWorkspaces__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180066B18, v14, 0x10u)) )
      {
        _InterlockedAnd(
          (volatile signed __int32 *)Feature_AdvancedSystemSettingsVirtualWorkspaces__descriptor,
          0xFFFFFFFB);
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
0x180035680  mov     [rsp+arg_10], rbx
0x180035685  mov     [rsp+arg_18], rbp
0x18003568a  mov     [rsp+arg_0], rcx
0x18003568f  push    rsi
0x180035690  push    rdi
0x180035691  push    r14
0x180035693  sub     rsp, 30h
0x180035697  mov     rsi, cs:Feature_AdvancedSystemSettingsVirtualWorkspaces__descriptor
0x18003569e  mov     rdi, rdx
0x1800356a1  mov     qword ptr [rdx], 0
0x1800356a8  mov     eax, [rsi]
0x1800356aa  mov     [rdx], eax
0x1800356ac  and     eax, 6
0x1800356af  cmp     al, 6
0x1800356b1  jz      loc_1800357A3
0x1800356b7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800356bc  lea     r8, [rsp+48h+arg_0]
0x1800356c1  mov     dword ptr [rsp+48h+arg_0], 0
0x1800356c9  lea     rdx, [rsp+48h+arg_8]
0x1800356ce  mov     ebp, eax
0x1800356d0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AdvancedSystemSettingsVirtualWorkspaces@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdvancedSystemSettingsVirtualWorkspaces>::GetCurrentFeatureEnabledState(int *)
0x1800356d5  mov     eax, [rdi]
0x1800356d7  mov     rbx, [rsp+48h+arg_8]
0x1800356dc  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800356e1  mov     edx, eax
0x1800356e3  mov     [rdi], eax
0x1800356e5  mov     ecx, eax
0x1800356e7  jz      short loc_180035702
0x1800356e9  test    dl, 2
0x1800356ec  jnz     short loc_180035702
0x1800356ee  and     ecx, 0FFFFF63Eh
0x1800356f4  mov     eax, ebx
0x1800356f6  and     eax, 9C1h
0x1800356fb  or      ecx, eax
0x1800356fd  or      ecx, 2
0x180035700  mov     [rdi], ecx
0x180035702  mov     r8d, edx
0x180035705  and     r8d, 4
0x180035709  jnz     short loc_18003571D
0x18003570b  btr     ecx, 0Ah
0x18003570f  mov     eax, ebx
0x180035711  and     eax, 400h
0x180035716  or      ecx, eax
0x180035718  or      ecx, 4
0x18003571b  mov     [rdi], ecx
0x18003571d  mov     eax, edx
0x18003571f  lock cmpxchg [rsi], ecx
0x180035723  jnz     short loc_1800356DC
0x180035725  test    r8d, r8d
0x180035728  jnz     short loc_18003578E
0x18003572a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180035730  test    eax, eax
0x180035732  jz      short loc_18003578E
0x180035734  lea     r14, SRWLock
0x18003573b  mov     rcx, r14; SRWLock
0x18003573e  call    cs:__imp_AcquireSRWLockExclusive
0x180035744  mov     eax, cs:dword_180066AF4
0x18003574a  mov     [rsp+48h+arg_8], r14
0x18003574f  test    ebp, ebp
0x180035751  jz      short loc_180035780
0x180035753  cmp     ebp, eax
0x180035755  jnz     short loc_180035780
0x180035757  mov     r8d, 10h; unsigned __int64
0x18003575d  mov     [rsp+48h+var_28], 1
0x180035766  lea     rdx, [rsp+48h+var_28]; void *
0x18003576b  mov     [rsp+48h+var_20], rsi
0x180035770  lea     rcx, qword_180066B18; this
0x180035777  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003577c  test    al, al
0x18003577e  jnz     short loc_180035784
0x180035780  lock and dword ptr [rsi], 0FFFFFFFBh
0x180035784  lea     rcx, [rsp+48h+arg_8]
0x180035789  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003578e  mov     eax, [rdi]
0x180035790  test    al, 2
0x180035792  jnz     short loc_1800357A3
0x180035794  and     eax, 0FFFFF63Eh
0x180035799  and     ebx, 9C1h
0x18003579f  or      eax, ebx
0x1800357a1  mov     [rdi], eax
0x1800357a3  mov     rbx, [rsp+48h+arg_10]
0x1800357a8  mov     rax, rdi
0x1800357ab  mov     rbp, [rsp+48h+arg_18]
0x1800357b0  add     rsp, 30h
0x1800357b4  pop     r14
0x1800357b6  pop     rdi
0x1800357b7  pop     rsi
0x1800357b8  retn
```
