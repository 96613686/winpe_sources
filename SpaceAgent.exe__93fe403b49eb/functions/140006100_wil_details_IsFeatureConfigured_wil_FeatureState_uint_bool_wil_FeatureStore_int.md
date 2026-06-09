# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x140006100`
- end: `0x1400061de`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `222`
- prototype: `bool __fastcall(wil::details *, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140008e50`

## callees

- `0x14000526c`
- `0x140006100`
- `0x140008798`
- `0x140009a1c`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(wil::details *a1, __int64 a2, unsigned __int8 a3, int a4, _DWORD *a5)
{
  unsigned int v5; // edi
  unsigned int v6; // esi
  __int64 *v7; // rbx
  unsigned int v10; // eax
  unsigned int v11; // r14d
  int v12; // eax
  __int64 v13; // r8
  bool v14; // di
  char v15; // dl
  unsigned int v16; // [rsp+58h] [rbp+20h] BYREF

  v5 = a3;
  v6 = a2;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState(a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v16 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState(a1, v6, v5, &v16);
    v13 = v16;
    v14 = v12 != 0;
    v15 = _InterlockedExchange((volatile __int32 *)v7, (v16 != 0) + 6);
    if ( !(_DWORD)v13 && (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        v7,
        v13,
        v11);
    return v14;
  }
}

```

## disassembly

```asm
0x140006100  mov     [rsp+arg_0], rbx
0x140006105  mov     [rsp+arg_8], rbp
0x14000610a  push    rsi
0x14000610b  push    rdi
0x14000610c  push    r14
0x14000610e  sub     rsp, 20h
0x140006112  test    r9d, r9d
0x140006115  movzx   edi, r8b
0x140006119  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x140006120  mov     esi, edx
0x140006122  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x140006129  mov     rbp, rcx
0x14000612c  cmovnz  rbx, rax
0x140006130  mov     r9d, [rbx]
0x140006133  mov     eax, r9d
0x140006136  and     al, 3
0x140006138  cmp     al, 2
0x14000613a  jnz     short loc_140006143
0x14000613c  xor     al, al
0x14000613e  jmp     loc_1400061CB
0x140006143  test    r9b, 2
0x140006147  jnz     short loc_1400061B0
0x140006149  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000614e  mov     rcx, [rsp+38h+arg_20]
0x140006153  lea     r9, [rsp+38h+arg_18]
0x140006158  mov     r8d, edi
0x14000615b  mov     [rsp+38h+arg_18], 0
0x140006163  mov     edx, esi
0x140006165  mov     r14d, eax
0x140006168  mov     dword ptr [rcx], 1
0x14000616e  mov     rcx, rbp
0x140006171  call    wil_RtlStagingConfig_QueryFeatureState
0x140006176  mov     r8d, [rsp+38h+arg_18]
0x14000617b  test    eax, eax
0x14000617d  mov     ecx, r8d
0x140006180  setnz   dil
0x140006184  neg     ecx
0x140006186  sbb     edx, edx
0x140006188  neg     edx
0x14000618a  add     edx, 6
0x14000618d  xchg    edx, [rbx]
0x14000618f  test    r8d, r8d
0x140006192  jnz     short loc_1400061AB
0x140006194  test    dl, 4
0x140006197  jnz     short loc_1400061AB
0x140006199  mov     r9d, r14d
0x14000619c  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1400061a3  mov     rdx, rbx
0x1400061a6  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1400061ab  mov     al, dil
0x1400061ae  jmp     short loc_1400061CB
0x1400061b0  mov     rax, [rsp+38h+arg_20]
0x1400061b5  mov     r8d, edi
0x1400061b8  xor     r9d, r9d
0x1400061bb  mov     dword ptr [rax], 1
0x1400061c1  call    wil_RtlStagingConfig_QueryFeatureState
0x1400061c6  test    eax, eax
0x1400061c8  setnz   al
0x1400061cb  mov     rbx, [rsp+38h+arg_0]
0x1400061d0  mov     rbp, [rsp+38h+arg_8]
0x1400061d5  add     rsp, 20h
0x1400061d9  pop     r14
0x1400061db  pop     rdi
0x1400061dc  pop     rsi
0x1400061dd  retn
```
