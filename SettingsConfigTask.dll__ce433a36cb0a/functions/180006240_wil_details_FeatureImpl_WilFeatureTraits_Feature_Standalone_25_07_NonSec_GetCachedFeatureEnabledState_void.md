# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_07_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180006240`
- end: `0x180006321`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_07_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000921c`

## callees

- `0x180005ac4`
- `0x180006240`
- `0x1800065a8`
- `0x18000a09c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_07_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_07_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_07_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_07_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_07_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_Standalone_25_07_NonSec__descriptor,
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
0x180006240  mov     [rsp+arg_10], rbx
0x180006245  mov     [rsp+arg_0], rcx
0x18000624a  push    rbp
0x18000624b  push    rsi
0x18000624c  push    rdi
0x18000624d  sub     rsp, 20h
0x180006251  mov     rsi, cs:Feature_Standalone_25_07_NonSec__descriptor
0x180006258  mov     rdi, rdx
0x18000625b  mov     qword ptr [rdx], 0
0x180006262  mov     eax, [rsi]
0x180006264  mov     [rdx], eax
0x180006266  and     eax, 6
0x180006269  cmp     al, 6
0x18000626b  jz      loc_180006311
0x180006271  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180006276  lea     r8, [rsp+38h+arg_0]
0x18000627b  mov     dword ptr [rsp+38h+arg_0], 0
0x180006283  lea     rdx, [rsp+38h+arg_8]
0x180006288  mov     ebp, eax
0x18000628a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_07_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_07_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18000628f  mov     eax, [rdi]
0x180006291  mov     rbx, [rsp+38h+arg_8]
0x180006296  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000629b  mov     edx, eax
0x18000629d  mov     [rdi], eax
0x18000629f  mov     ecx, eax
0x1800062a1  jz      short loc_1800062BC
0x1800062a3  test    dl, 2
0x1800062a6  jnz     short loc_1800062BC
0x1800062a8  and     ecx, 0FFFFF63Eh
0x1800062ae  mov     eax, ebx
0x1800062b0  and     eax, 9C1h
0x1800062b5  or      ecx, eax
0x1800062b7  or      ecx, 2
0x1800062ba  mov     [rdi], ecx
0x1800062bc  mov     r8d, edx
0x1800062bf  and     r8d, 4
0x1800062c3  jnz     short loc_1800062D7
0x1800062c5  btr     ecx, 0Ah
0x1800062c9  mov     eax, ebx
0x1800062cb  and     eax, 400h
0x1800062d0  or      ecx, eax
0x1800062d2  or      ecx, 4
0x1800062d5  mov     [rdi], ecx
0x1800062d7  mov     eax, edx
0x1800062d9  lock cmpxchg [rsi], ecx
0x1800062dd  jnz     short loc_180006296
0x1800062df  test    r8d, r8d
0x1800062e2  jnz     short loc_1800062FC
0x1800062e4  mov     r9d, ebp
0x1800062e7  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800062ee  mov     r8d, 3
0x1800062f4  mov     rdx, rsi
0x1800062f7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800062fc  mov     eax, [rdi]
0x1800062fe  test    al, 2
0x180006300  jnz     short loc_180006311
0x180006302  and     eax, 0FFFFF63Eh
0x180006307  and     ebx, 9C1h
0x18000630d  or      eax, ebx
0x18000630f  mov     [rdi], eax
0x180006311  mov     rbx, [rsp+38h+arg_10]
0x180006316  mov     rax, rdi
0x180006319  add     rsp, 20h
0x18000631d  pop     rdi
0x18000631e  pop     rsi
0x18000631f  pop     rbp
0x180006320  retn
```
