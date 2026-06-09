# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180009220`
- end: `0x180009304`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `228`
- prototype: `bool __fastcall(wil::details *, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180011d70`

## callees

- `0x180009220`
- `0x18000c954`
- `0x18000f974`
- `0x180012ee0`

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
  int v13; // ecx
  bool v14; // di
  char v15; // dl
  int v16; // [rsp+58h] [rbp+20h] BYREF

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
    if ( !v13 && (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        wil::details::g_enabledStateManager,
        v7,
        0,
        v11);
    return v14;
  }
}

```

## disassembly

```asm
0x180009220  mov     [rsp+arg_8], rbx
0x180009225  push    rbp
0x180009226  push    rsi
0x180009227  push    rdi
0x180009228  sub     rsp, 20h
0x18000922c  test    r9d, r9d
0x18000922f  movzx   edi, r8b
0x180009233  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000923a  mov     esi, edx
0x18000923c  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180009243  mov     rbp, rcx
0x180009246  cmovnz  rbx, rax
0x18000924a  mov     r9d, [rbx]
0x18000924d  mov     eax, r9d
0x180009250  and     al, 3
0x180009252  cmp     al, 2
0x180009254  jnz     short loc_180009265
0x180009256  xor     al, al
0x180009258  mov     rbx, [rsp+38h+arg_8]
0x18000925d  add     rsp, 20h
0x180009261  pop     rdi
0x180009262  pop     rsi
0x180009263  pop     rbp
0x180009264  retn
0x180009265  test    r9b, 2
0x180009269  jnz     short loc_1800092DC
0x18000926b  mov     [rsp+38h+arg_0], r14
0x180009270  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180009275  mov     rcx, [rsp+38h+arg_20]
0x18000927a  lea     r9, [rsp+38h+arg_18]
0x18000927f  mov     r8d, edi
0x180009282  mov     [rsp+38h+arg_18], 0
0x18000928a  mov     edx, esi
0x18000928c  mov     r14d, eax
0x18000928f  mov     dword ptr [rcx], 1
0x180009295  mov     rcx, rbp
0x180009298  call    wil_RtlStagingConfig_QueryFeatureState
0x18000929d  mov     ecx, [rsp+38h+arg_18]
0x1800092a1  test    eax, eax
0x1800092a3  setnz   dil
0x1800092a7  xor     edx, edx
0x1800092a9  test    ecx, ecx
0x1800092ab  setnz   dl
0x1800092ae  add     edx, 6
0x1800092b1  xchg    edx, [rbx]
0x1800092b3  test    ecx, ecx
0x1800092b5  jnz     short loc_1800092D1
0x1800092b7  test    dl, 4
0x1800092ba  jnz     short loc_1800092D1
0x1800092bc  mov     r9d, r14d
0x1800092bf  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800092c6  xor     r8d, r8d
0x1800092c9  mov     rdx, rbx
0x1800092cc  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800092d1  mov     r14, [rsp+38h+arg_0]
0x1800092d6  movzx   eax, dil
0x1800092da  jmp     short loc_1800092F7
0x1800092dc  mov     rax, [rsp+38h+arg_20]
0x1800092e1  mov     r8d, edi
0x1800092e4  xor     r9d, r9d
0x1800092e7  mov     dword ptr [rax], 1
0x1800092ed  call    wil_RtlStagingConfig_QueryFeatureState
0x1800092f2  test    eax, eax
0x1800092f4  setnz   al
0x1800092f7  mov     rbx, [rsp+38h+arg_8]
0x1800092fc  add     rsp, 20h
0x180009300  pop     rdi
0x180009301  pop     rsi
0x180009302  pop     rbp
0x180009303  retn
```
