# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_03_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180006158`
- end: `0x180006239`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009198`

## callees

- `0x180005ac4`
- `0x180006158`
- `0x18000652c`
- `0x18000a09c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_03_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_03_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_03_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_03_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_03_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_Standalone_25_03_NonSec__descriptor,
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
0x180006158  mov     [rsp+arg_10], rbx
0x18000615d  mov     [rsp+arg_0], rcx
0x180006162  push    rbp
0x180006163  push    rsi
0x180006164  push    rdi
0x180006165  sub     rsp, 20h
0x180006169  mov     rsi, cs:Feature_Standalone_25_03_NonSec__descriptor
0x180006170  mov     rdi, rdx
0x180006173  mov     qword ptr [rdx], 0
0x18000617a  mov     eax, [rsi]
0x18000617c  mov     [rdx], eax
0x18000617e  and     eax, 6
0x180006181  cmp     al, 6
0x180006183  jz      loc_180006229
0x180006189  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000618e  lea     r8, [rsp+38h+arg_0]
0x180006193  mov     dword ptr [rsp+38h+arg_0], 0
0x18000619b  lea     rdx, [rsp+38h+arg_8]
0x1800061a0  mov     ebp, eax
0x1800061a2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_03_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_03_NonSec>::GetCurrentFeatureEnabledState(int *)
0x1800061a7  mov     eax, [rdi]
0x1800061a9  mov     rbx, [rsp+38h+arg_8]
0x1800061ae  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800061b3  mov     edx, eax
0x1800061b5  mov     [rdi], eax
0x1800061b7  mov     ecx, eax
0x1800061b9  jz      short loc_1800061D4
0x1800061bb  test    dl, 2
0x1800061be  jnz     short loc_1800061D4
0x1800061c0  and     ecx, 0FFFFF63Eh
0x1800061c6  mov     eax, ebx
0x1800061c8  and     eax, 9C1h
0x1800061cd  or      ecx, eax
0x1800061cf  or      ecx, 2
0x1800061d2  mov     [rdi], ecx
0x1800061d4  mov     r8d, edx
0x1800061d7  and     r8d, 4
0x1800061db  jnz     short loc_1800061EF
0x1800061dd  btr     ecx, 0Ah
0x1800061e1  mov     eax, ebx
0x1800061e3  and     eax, 400h
0x1800061e8  or      ecx, eax
0x1800061ea  or      ecx, 4
0x1800061ed  mov     [rdi], ecx
0x1800061ef  mov     eax, edx
0x1800061f1  lock cmpxchg [rsi], ecx
0x1800061f5  jnz     short loc_1800061AE
0x1800061f7  test    r8d, r8d
0x1800061fa  jnz     short loc_180006214
0x1800061fc  mov     r9d, ebp
0x1800061ff  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180006206  mov     r8d, 3
0x18000620c  mov     rdx, rsi
0x18000620f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006214  mov     eax, [rdi]
0x180006216  test    al, 2
0x180006218  jnz     short loc_180006229
0x18000621a  and     eax, 0FFFFF63Eh
0x18000621f  and     ebx, 9C1h
0x180006225  or      eax, ebx
0x180006227  mov     [rdi], eax
0x180006229  mov     rbx, [rsp+38h+arg_10]
0x18000622e  mov     rax, rdi
0x180006231  add     rsp, 20h
0x180006235  pop     rdi
0x180006236  pop     rsi
0x180006237  pop     rbp
0x180006238  retn
```
