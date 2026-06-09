# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x18000697c`
- end: `0x180006a5a`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `222`
- prototype: `bool __fastcall(wil::details *, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800097e0`

## callees

- `0x180005a7c`
- `0x18000697c`
- `0x1800090a4`
- `0x18000a5e8`

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
0x18000697c  mov     [rsp+arg_0], rbx
0x180006981  mov     [rsp+arg_8], rbp
0x180006986  push    rsi
0x180006987  push    rdi
0x180006988  push    r14
0x18000698a  sub     rsp, 20h
0x18000698e  test    r9d, r9d
0x180006991  movzx   edi, r8b
0x180006995  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x18000699c  mov     esi, edx
0x18000699e  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1800069a5  mov     rbp, rcx
0x1800069a8  cmovnz  rbx, rax
0x1800069ac  mov     r9d, [rbx]
0x1800069af  mov     eax, r9d
0x1800069b2  and     al, 3
0x1800069b4  cmp     al, 2
0x1800069b6  jnz     short loc_1800069BF
0x1800069b8  xor     al, al
0x1800069ba  jmp     loc_180006A47
0x1800069bf  test    r9b, 2
0x1800069c3  jnz     short loc_180006A2C
0x1800069c5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800069ca  mov     rcx, [rsp+38h+arg_20]
0x1800069cf  lea     r9, [rsp+38h+arg_18]
0x1800069d4  mov     r8d, edi
0x1800069d7  mov     [rsp+38h+arg_18], 0
0x1800069df  mov     edx, esi
0x1800069e1  mov     r14d, eax
0x1800069e4  mov     dword ptr [rcx], 1
0x1800069ea  mov     rcx, rbp
0x1800069ed  call    wil_RtlStagingConfig_QueryFeatureState
0x1800069f2  mov     r8d, [rsp+38h+arg_18]
0x1800069f7  test    eax, eax
0x1800069f9  mov     ecx, r8d
0x1800069fc  setnz   dil
0x180006a00  neg     ecx
0x180006a02  sbb     edx, edx
0x180006a04  neg     edx
0x180006a06  add     edx, 6
0x180006a09  xchg    edx, [rbx]
0x180006a0b  test    r8d, r8d
0x180006a0e  jnz     short loc_180006A27
0x180006a10  test    dl, 4
0x180006a13  jnz     short loc_180006A27
0x180006a15  mov     r9d, r14d
0x180006a18  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180006a1f  mov     rdx, rbx
0x180006a22  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180006a27  mov     al, dil
0x180006a2a  jmp     short loc_180006A47
0x180006a2c  mov     rax, [rsp+38h+arg_20]
0x180006a31  mov     r8d, edi
0x180006a34  xor     r9d, r9d
0x180006a37  mov     dword ptr [rax], 1
0x180006a3d  call    wil_RtlStagingConfig_QueryFeatureState
0x180006a42  test    eax, eax
0x180006a44  setnz   al
0x180006a47  mov     rbx, [rsp+38h+arg_0]
0x180006a4c  mov     rbp, [rsp+38h+arg_8]
0x180006a51  add     rsp, 20h
0x180006a55  pop     r14
0x180006a57  pop     rdi
0x180006a58  pop     rsi
0x180006a59  retn
```
