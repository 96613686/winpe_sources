# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetCachedFeatureEnabledState(void)

- ea: `0x18000ed78`
- end: `0x18000ee59`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000fbbc`

## callees

- `0x180006744`
- `0x180009a60`
- `0x18000ed78`
- `0x18000f360`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_GPM_BlitModeTracking__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_GPM_BlitModeTracking__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
    v7 = *(_DWORD *)a2;
    v8 = v14;
    do
    {
      v9 = (_DWORD)v13 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_GPM_BlitModeTracking__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (__int64)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_GPM_BlitModeTracking__descriptor,
        1,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000ed78  mov     [rsp+arg_10], rbx
0x18000ed7d  mov     [rsp+arg_0], rcx
0x18000ed82  push    rbp
0x18000ed83  push    rsi
0x18000ed84  push    rdi
0x18000ed85  sub     rsp, 20h
0x18000ed89  mov     rsi, cs:Feature_GPM_BlitModeTracking__descriptor
0x18000ed90  mov     rdi, rdx
0x18000ed93  mov     qword ptr [rdx], 0
0x18000ed9a  mov     eax, [rsi]
0x18000ed9c  mov     [rdx], eax
0x18000ed9e  and     eax, 6
0x18000eda1  cmp     al, 6
0x18000eda3  jz      loc_18000EE49
0x18000eda9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000edae  lea     r8, [rsp+38h+arg_0]
0x18000edb3  mov     dword ptr [rsp+38h+arg_0], 0
0x18000edbb  lea     rdx, [rsp+38h+arg_8]
0x18000edc0  mov     ebp, eax
0x18000edc2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_BlitModeTracking@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_BlitModeTracking>::GetCurrentFeatureEnabledState(int *)
0x18000edc7  mov     eax, [rdi]
0x18000edc9  mov     rbx, [rsp+38h+arg_8]
0x18000edce  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000edd3  mov     edx, eax
0x18000edd5  mov     [rdi], eax
0x18000edd7  mov     ecx, eax
0x18000edd9  jz      short loc_18000EDF4
0x18000eddb  test    dl, 2
0x18000edde  jnz     short loc_18000EDF4
0x18000ede0  and     ecx, 0FFFFF63Eh
0x18000ede6  mov     eax, ebx
0x18000ede8  and     eax, 9C1h
0x18000eded  or      ecx, eax
0x18000edef  or      ecx, 2
0x18000edf2  mov     [rdi], ecx
0x18000edf4  mov     r8d, edx
0x18000edf7  and     r8d, 4
0x18000edfb  jnz     short loc_18000EE0F
0x18000edfd  btr     ecx, 0Ah
0x18000ee01  mov     eax, ebx
0x18000ee03  and     eax, 400h
0x18000ee08  or      ecx, eax
0x18000ee0a  or      ecx, 4
0x18000ee0d  mov     [rdi], ecx
0x18000ee0f  mov     eax, edx
0x18000ee11  lock cmpxchg [rsi], ecx
0x18000ee15  jnz     short loc_18000EDCE
0x18000ee17  test    r8d, r8d
0x18000ee1a  jnz     short loc_18000EE34
0x18000ee1c  mov     r9d, ebp
0x18000ee1f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000ee26  mov     r8d, 1
0x18000ee2c  mov     rdx, rsi
0x18000ee2f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000ee34  mov     eax, [rdi]
0x18000ee36  test    al, 2
0x18000ee38  jnz     short loc_18000EE49
0x18000ee3a  and     eax, 0FFFFF63Eh
0x18000ee3f  and     ebx, 9C1h
0x18000ee45  or      eax, ebx
0x18000ee47  mov     [rdi], eax
0x18000ee49  mov     rbx, [rsp+38h+arg_10]
0x18000ee4e  mov     rax, rdi
0x18000ee51  add     rsp, 20h
0x18000ee55  pop     rdi
0x18000ee56  pop     rsi
0x18000ee57  pop     rbp
0x18000ee58  retn
```
