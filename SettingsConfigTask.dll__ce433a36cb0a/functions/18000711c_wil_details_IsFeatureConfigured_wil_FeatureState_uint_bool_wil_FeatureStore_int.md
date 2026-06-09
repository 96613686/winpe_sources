# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000711c`
- end: `0x1800071fa`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18000a8e0`

## callees

- `0x180005ac4`
- `0x18000711c`
- `0x18000a09c`
- `0x18000ba2c`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(
        wil::details *a1,
        unsigned int a2,
        unsigned __int8 a3,
        int a4,
        _DWORD *a5)
{
  int v5; // edi
  __int64 *v7; // rbx
  unsigned int v10; // eax
  int v11; // r14d
  int v12; // eax
  int v13; // r8d
  bool v14; // di
  char v15; // dl
  int v16; // [rsp+58h] [rbp+20h] BYREF

  v5 = a3;
  v7 = &`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  if ( a4 )
    v7 = &`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  if ( (*(_DWORD *)v7 & 3) == 2 )
    return 0;
  if ( (*(_DWORD *)v7 & 2) != 0 )
  {
    *a5 = 1;
    return (unsigned int)wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, a3, 0) != 0;
  }
  else
  {
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v16 = 0;
    v11 = v10;
    *a5 = 1;
    v12 = wil_RtlStagingConfig_QueryFeatureState((__int64)a1, a2, v5, &v16);
    v13 = v16;
    v14 = v12 != 0;
    v15 = _InterlockedExchange((volatile __int32 *)v7, (v16 != 0) + 6);
    if ( !v13 && (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (__int64)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)v7,
        0,
        v11);
    return v14;
  }
}

```

## disassembly

```asm
0x18000711c  mov     [rsp+arg_0], rbx
0x180007121  mov     [rsp+arg_8], rbp
0x180007126  push    rsi
0x180007127  push    rdi
0x180007128  push    r14
0x18000712a  sub     rsp, 20h
0x18000712e  test    r9d, r9d
0x180007131  movzx   edi, r8b
0x180007135  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000713c  mov     esi, edx
0x18000713e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180007145  mov     rbp, rcx
0x180007148  cmovnz  rbx, rax
0x18000714c  mov     r9d, [rbx]
0x18000714f  mov     eax, r9d
0x180007152  and     al, 3
0x180007154  cmp     al, 2
0x180007156  jnz     short loc_18000715F
0x180007158  xor     al, al
0x18000715a  jmp     loc_1800071E7
0x18000715f  test    r9b, 2
0x180007163  jnz     short loc_1800071CC
0x180007165  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000716a  mov     rcx, [rsp+38h+arg_20]
0x18000716f  lea     r9, [rsp+38h+arg_18]
0x180007174  mov     r8d, edi
0x180007177  mov     [rsp+38h+arg_18], 0
0x18000717f  mov     edx, esi
0x180007181  mov     r14d, eax
0x180007184  mov     dword ptr [rcx], 1
0x18000718a  mov     rcx, rbp
0x18000718d  call    wil_RtlStagingConfig_QueryFeatureState
0x180007192  mov     r8d, [rsp+38h+arg_18]
0x180007197  test    eax, eax
0x180007199  mov     ecx, r8d
0x18000719c  setnz   dil
0x1800071a0  neg     ecx
0x1800071a2  sbb     edx, edx
0x1800071a4  neg     edx
0x1800071a6  add     edx, 6
0x1800071a9  xchg    edx, [rbx]
0x1800071ab  test    r8d, r8d
0x1800071ae  jnz     short loc_1800071C7
0x1800071b0  test    dl, 4
0x1800071b3  jnz     short loc_1800071C7
0x1800071b5  mov     r9d, r14d
0x1800071b8  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800071bf  mov     rdx, rbx
0x1800071c2  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800071c7  mov     al, dil
0x1800071ca  jmp     short loc_1800071E7
0x1800071cc  mov     rax, [rsp+38h+arg_20]
0x1800071d1  mov     r8d, edi
0x1800071d4  xor     r9d, r9d
0x1800071d7  mov     dword ptr [rax], 1
0x1800071dd  call    wil_RtlStagingConfig_QueryFeatureState
0x1800071e2  test    eax, eax
0x1800071e4  setnz   al
0x1800071e7  mov     rbx, [rsp+38h+arg_0]
0x1800071ec  mov     rbp, [rsp+38h+arg_8]
0x1800071f1  add     rsp, 20h
0x1800071f5  pop     r14
0x1800071f7  pop     rdi
0x1800071f8  pop     rsi
0x1800071f9  retn
```
