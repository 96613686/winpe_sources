# wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdvancedSystemSettingsPage>::GetCachedFeatureEnabledState(void)

- ea: `0x180035540`
- end: `0x180035679`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AdvancedSystemSettingsPage@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180036f64`
- `0x180037974`

## callees

- `0x18000b508`
- `0x18000c08c`
- `0x18001026c`
- `0x180035540`
- `0x180035cc0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800355fe`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800355fe`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdvancedSystemSettingsPage>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_AdvancedSystemSettingsPage__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_AdvancedSystemSettingsPage__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdvancedSystemSettingsPage>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_AdvancedSystemSettingsPage__descriptor,
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
            v14[1] = Feature_AdvancedSystemSettingsPage__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180066B18, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_AdvancedSystemSettingsPage__descriptor, 0xFFFFFFFB);
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
0x180035540  mov     [rsp+arg_10], rbx
0x180035545  mov     [rsp+arg_18], rbp
0x18003554a  mov     [rsp+arg_0], rcx
0x18003554f  push    rsi
0x180035550  push    rdi
0x180035551  push    r14
0x180035553  sub     rsp, 30h
0x180035557  mov     rsi, cs:Feature_AdvancedSystemSettingsPage__descriptor
0x18003555e  mov     rdi, rdx
0x180035561  mov     qword ptr [rdx], 0
0x180035568  mov     eax, [rsi]
0x18003556a  mov     [rdx], eax
0x18003556c  and     eax, 6
0x18003556f  cmp     al, 6
0x180035571  jz      loc_180035663
0x180035577  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18003557c  lea     r8, [rsp+48h+arg_0]
0x180035581  mov     dword ptr [rsp+48h+arg_0], 0
0x180035589  lea     rdx, [rsp+48h+arg_8]
0x18003558e  mov     ebp, eax
0x180035590  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_AdvancedSystemSettingsPage@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_AdvancedSystemSettingsPage>::GetCurrentFeatureEnabledState(int *)
0x180035595  mov     eax, [rdi]
0x180035597  mov     rbx, [rsp+48h+arg_8]
0x18003559c  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800355a1  mov     edx, eax
0x1800355a3  mov     [rdi], eax
0x1800355a5  mov     ecx, eax
0x1800355a7  jz      short loc_1800355C2
0x1800355a9  test    dl, 2
0x1800355ac  jnz     short loc_1800355C2
0x1800355ae  and     ecx, 0FFFFF63Eh
0x1800355b4  mov     eax, ebx
0x1800355b6  and     eax, 9C1h
0x1800355bb  or      ecx, eax
0x1800355bd  or      ecx, 2
0x1800355c0  mov     [rdi], ecx
0x1800355c2  mov     r8d, edx
0x1800355c5  and     r8d, 4
0x1800355c9  jnz     short loc_1800355DD
0x1800355cb  btr     ecx, 0Ah
0x1800355cf  mov     eax, ebx
0x1800355d1  and     eax, 400h
0x1800355d6  or      ecx, eax
0x1800355d8  or      ecx, 4
0x1800355db  mov     [rdi], ecx
0x1800355dd  mov     eax, edx
0x1800355df  lock cmpxchg [rsi], ecx
0x1800355e3  jnz     short loc_18003559C
0x1800355e5  test    r8d, r8d
0x1800355e8  jnz     short loc_18003564E
0x1800355ea  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800355f0  test    eax, eax
0x1800355f2  jz      short loc_18003564E
0x1800355f4  lea     r14, SRWLock
0x1800355fb  mov     rcx, r14; SRWLock
0x1800355fe  call    cs:__imp_AcquireSRWLockExclusive
0x180035604  mov     eax, cs:dword_180066AF4
0x18003560a  mov     [rsp+48h+arg_8], r14
0x18003560f  test    ebp, ebp
0x180035611  jz      short loc_180035640
0x180035613  cmp     ebp, eax
0x180035615  jnz     short loc_180035640
0x180035617  mov     r8d, 10h; unsigned __int64
0x18003561d  mov     [rsp+48h+var_28], 1
0x180035626  lea     rdx, [rsp+48h+var_28]; void *
0x18003562b  mov     [rsp+48h+var_20], rsi
0x180035630  lea     rcx, qword_180066B18; this
0x180035637  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003563c  test    al, al
0x18003563e  jnz     short loc_180035644
0x180035640  lock and dword ptr [rsi], 0FFFFFFFBh
0x180035644  lea     rcx, [rsp+48h+arg_8]
0x180035649  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003564e  mov     eax, [rdi]
0x180035650  test    al, 2
0x180035652  jnz     short loc_180035663
0x180035654  and     eax, 0FFFFF63Eh
0x180035659  and     ebx, 9C1h
0x18003565f  or      eax, ebx
0x180035661  mov     [rdi], eax
0x180035663  mov     rbx, [rsp+48h+arg_10]
0x180035668  mov     rax, rdi
0x18003566b  mov     rbp, [rsp+48h+arg_18]
0x180035670  add     rsp, 30h
0x180035674  pop     r14
0x180035676  pop     rdi
0x180035677  pop     rsi
0x180035678  retn
```
