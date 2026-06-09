# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_LightWeightDxgKrnlETWKeyword>::GetCachedFeatureEnabledState(void)

- ea: `0x180019a1c`
- end: `0x180019afd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_LightWeightDxgKrnlETWKeyword@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001adac`

## callees

- `0x180006744`
- `0x180009a60`
- `0x180019a1c`
- `0x180019ddc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_LightWeightDxgKrnlETWKeyword>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_GPM_LightWeightDxgKrnlETWKeyword__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_GPM_LightWeightDxgKrnlETWKeyword__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_LightWeightDxgKrnlETWKeyword>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_GPM_LightWeightDxgKrnlETWKeyword__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (__int64)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_GPM_LightWeightDxgKrnlETWKeyword__descriptor,
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
0x180019a1c  mov     [rsp+arg_10], rbx
0x180019a21  mov     [rsp+arg_0], rcx
0x180019a26  push    rbp
0x180019a27  push    rsi
0x180019a28  push    rdi
0x180019a29  sub     rsp, 20h
0x180019a2d  mov     rsi, cs:Feature_GPM_LightWeightDxgKrnlETWKeyword__descriptor
0x180019a34  mov     rdi, rdx
0x180019a37  mov     qword ptr [rdx], 0
0x180019a3e  mov     eax, [rsi]
0x180019a40  mov     [rdx], eax
0x180019a42  and     eax, 6
0x180019a45  cmp     al, 6
0x180019a47  jz      loc_180019AED
0x180019a4d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180019a52  lea     r8, [rsp+38h+arg_0]
0x180019a57  mov     dword ptr [rsp+38h+arg_0], 0
0x180019a5f  lea     rdx, [rsp+38h+arg_8]
0x180019a64  mov     ebp, eax
0x180019a66  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_LightWeightDxgKrnlETWKeyword@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_LightWeightDxgKrnlETWKeyword>::GetCurrentFeatureEnabledState(int *)
0x180019a6b  mov     eax, [rdi]
0x180019a6d  mov     rbx, [rsp+38h+arg_8]
0x180019a72  cmp     dword ptr [rsp+38h+arg_0], 0
0x180019a77  mov     edx, eax
0x180019a79  mov     [rdi], eax
0x180019a7b  mov     ecx, eax
0x180019a7d  jz      short loc_180019A98
0x180019a7f  test    dl, 2
0x180019a82  jnz     short loc_180019A98
0x180019a84  and     ecx, 0FFFFF63Eh
0x180019a8a  mov     eax, ebx
0x180019a8c  and     eax, 9C1h
0x180019a91  or      ecx, eax
0x180019a93  or      ecx, 2
0x180019a96  mov     [rdi], ecx
0x180019a98  mov     r8d, edx
0x180019a9b  and     r8d, 4
0x180019a9f  jnz     short loc_180019AB3
0x180019aa1  btr     ecx, 0Ah
0x180019aa5  mov     eax, ebx
0x180019aa7  and     eax, 400h
0x180019aac  or      ecx, eax
0x180019aae  or      ecx, 4
0x180019ab1  mov     [rdi], ecx
0x180019ab3  mov     eax, edx
0x180019ab5  lock cmpxchg [rsi], ecx
0x180019ab9  jnz     short loc_180019A72
0x180019abb  test    r8d, r8d
0x180019abe  jnz     short loc_180019AD8
0x180019ac0  mov     r9d, ebp
0x180019ac3  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180019aca  mov     r8d, 1
0x180019ad0  mov     rdx, rsi
0x180019ad3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180019ad8  mov     eax, [rdi]
0x180019ada  test    al, 2
0x180019adc  jnz     short loc_180019AED
0x180019ade  and     eax, 0FFFFF63Eh
0x180019ae3  and     ebx, 9C1h
0x180019ae9  or      eax, ebx
0x180019aeb  mov     [rdi], eax
0x180019aed  mov     rbx, [rsp+38h+arg_10]
0x180019af2  mov     rax, rdi
0x180019af5  add     rsp, 20h
0x180019af9  pop     rdi
0x180019afa  pop     rsi
0x180019afb  pop     rbp
0x180019afc  retn
```
