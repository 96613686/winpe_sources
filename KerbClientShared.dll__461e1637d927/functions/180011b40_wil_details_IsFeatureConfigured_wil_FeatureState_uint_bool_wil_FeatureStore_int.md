# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180011b40`
- end: `0x180011c1e`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `222`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180013d90`

## callees

- `0x180010ca8`
- `0x180011b40`
- `0x180013780`
- `0x1800148a8`

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
  unsigned int v11; // r14d
  int v12; // eax
  __int64 v13; // r8
  bool v14; // di
  char v15; // dl
  unsigned int v16; // [rsp+58h] [rbp+20h] BYREF

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
    if ( !(_DWORD)v13 && (v15 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        wil::details::g_enabledStateManager,
        v7,
        v13,
        v11);
    return v14;
  }
}

```

## disassembly

```asm
0x180011b40  mov     [rsp+arg_0], rbx
0x180011b45  mov     [rsp+arg_8], rbp
0x180011b4a  push    rsi
0x180011b4b  push    rdi
0x180011b4c  push    r14
0x180011b4e  sub     rsp, 20h
0x180011b52  test    r9d, r9d
0x180011b55  movzx   edi, r8b
0x180011b59  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180011b60  mov     esi, edx
0x180011b62  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180011b69  mov     rbp, rcx
0x180011b6c  cmovnz  rbx, rax
0x180011b70  mov     r9d, [rbx]
0x180011b73  mov     eax, r9d
0x180011b76  and     al, 3
0x180011b78  cmp     al, 2
0x180011b7a  jnz     short loc_180011B83
0x180011b7c  xor     al, al
0x180011b7e  jmp     loc_180011C0B
0x180011b83  test    r9b, 2
0x180011b87  jnz     short loc_180011BF0
0x180011b89  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180011b8e  mov     rcx, [rsp+38h+arg_20]
0x180011b93  lea     r9, [rsp+38h+arg_18]
0x180011b98  mov     r8d, edi
0x180011b9b  mov     [rsp+38h+arg_18], 0
0x180011ba3  mov     edx, esi
0x180011ba5  mov     r14d, eax
0x180011ba8  mov     dword ptr [rcx], 1
0x180011bae  mov     rcx, rbp
0x180011bb1  call    wil_RtlStagingConfig_QueryFeatureState
0x180011bb6  mov     r8d, [rsp+38h+arg_18]
0x180011bbb  test    eax, eax
0x180011bbd  mov     ecx, r8d
0x180011bc0  setnz   dil
0x180011bc4  neg     ecx
0x180011bc6  sbb     edx, edx
0x180011bc8  neg     edx
0x180011bca  add     edx, 6
0x180011bcd  xchg    edx, [rbx]
0x180011bcf  test    r8d, r8d
0x180011bd2  jnz     short loc_180011BEB
0x180011bd4  test    dl, 4
0x180011bd7  jnz     short loc_180011BEB
0x180011bd9  mov     r9d, r14d
0x180011bdc  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180011be3  mov     rdx, rbx
0x180011be6  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180011beb  mov     al, dil
0x180011bee  jmp     short loc_180011C0B
0x180011bf0  mov     rax, [rsp+38h+arg_20]
0x180011bf5  mov     r8d, edi
0x180011bf8  xor     r9d, r9d
0x180011bfb  mov     dword ptr [rax], 1
0x180011c01  call    wil_RtlStagingConfig_QueryFeatureState
0x180011c06  test    eax, eax
0x180011c08  setnz   al
0x180011c0b  mov     rbx, [rsp+38h+arg_0]
0x180011c10  mov     rbp, [rsp+38h+arg_8]
0x180011c15  add     rsp, 20h
0x180011c19  pop     r14
0x180011c1b  pop     rdi
0x180011c1c  pop     rsi
0x180011c1d  retn
```
