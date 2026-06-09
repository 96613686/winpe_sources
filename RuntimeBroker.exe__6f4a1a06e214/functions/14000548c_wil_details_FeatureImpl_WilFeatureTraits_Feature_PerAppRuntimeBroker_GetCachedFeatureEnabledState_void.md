# wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerAppRuntimeBroker>::GetCachedFeatureEnabledState(void)

- ea: `0x14000548c`
- end: `0x140005571`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PerAppRuntimeBroker@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `229`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140005164`

## callees

- `0x14000548c`
- `0x140005578`
- `0x1400055a0`
- `0x1400056d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerAppRuntimeBroker>::GetCachedFeatureEnabledState(
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
  wil::details *v13; // [rsp+40h] [rbp+8h] BYREF
  __int64 v14; // [rsp+48h] [rbp+10h] BYREF

  v13 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_PerAppRuntimeBroker__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_PerAppRuntimeBroker__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerAppRuntimeBroker>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_PerAppRuntimeBroker__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        wil::details::g_enabledStateManager,
        Feature_PerAppRuntimeBroker__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x14000548c  mov     [rsp+arg_10], rbx
0x140005491  mov     [rsp+arg_0], rcx
0x140005496  push    rbp
0x140005497  push    rsi
0x140005498  push    rdi
0x140005499  sub     rsp, 20h
0x14000549d  mov     rsi, cs:Feature_PerAppRuntimeBroker__descriptor
0x1400054a4  mov     rdi, rdx
0x1400054a7  mov     qword ptr [rdx], 0
0x1400054ae  mov     eax, [rsi]
0x1400054b0  mov     [rdx], eax
0x1400054b2  and     eax, 6
0x1400054b5  cmp     al, 6
0x1400054b7  jz      short loc_140005507
0x1400054b9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1400054be  lea     r8, [rsp+38h+arg_0]
0x1400054c3  mov     dword ptr [rsp+38h+arg_0], 0
0x1400054cb  lea     rdx, [rsp+38h+arg_8]
0x1400054d0  mov     ebp, eax
0x1400054d2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_PerAppRuntimeBroker@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_PerAppRuntimeBroker>::GetCurrentFeatureEnabledState(int *)
0x1400054d7  mov     eax, [rdi]
0x1400054d9  mov     rbx, [rsp+38h+arg_8]
0x1400054de  cmp     dword ptr [rsp+38h+arg_0], 0
0x1400054e3  mov     edx, eax
0x1400054e5  mov     [rdi], eax
0x1400054e7  mov     ecx, eax
0x1400054e9  jnz     short loc_140005517
0x1400054eb  mov     r8d, edx
0x1400054ee  and     r8d, 4
0x1400054f2  jz      short loc_14000554C
0x1400054f4  mov     eax, edx
0x1400054f6  lock cmpxchg [rsi], ecx
0x1400054fa  jnz     short loc_1400054DE
0x1400054fc  test    r8d, r8d
0x1400054ff  jz      short loc_140005532
0x140005501  mov     eax, [rdi]
0x140005503  test    al, 2
0x140005505  jz      short loc_140005560
0x140005507  mov     rbx, [rsp+38h+arg_10]
0x14000550c  mov     rax, rdi
0x14000550f  add     rsp, 20h
0x140005513  pop     rdi
0x140005514  pop     rsi
0x140005515  pop     rbp
0x140005516  retn
0x140005517  test    dl, 2
0x14000551a  jnz     short loc_1400054EB
0x14000551c  and     ecx, 0FFFFF63Eh
0x140005522  mov     eax, ebx
0x140005524  and     eax, 9C1h
0x140005529  or      ecx, eax
0x14000552b  or      ecx, 2
0x14000552e  mov     [rdi], ecx
0x140005530  jmp     short loc_1400054EB
0x140005532  mov     r9d, ebp
0x140005535  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000553c  mov     r8d, 3
0x140005542  mov     rdx, rsi
0x140005545  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000554a  jmp     short loc_140005501
0x14000554c  btr     ecx, 0Ah
0x140005550  mov     eax, ebx
0x140005552  and     eax, 400h
0x140005557  or      ecx, eax
0x140005559  or      ecx, 4
0x14000555c  mov     [rdi], ecx
0x14000555e  jmp     short loc_1400054F4
0x140005560  and     eax, 0FFFFF63Eh
0x140005565  and     ebx, 9C1h
0x14000556b  or      eax, ebx
0x14000556d  mov     [rdi], eax
0x14000556f  jmp     short loc_140005507
```
