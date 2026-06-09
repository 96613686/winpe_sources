# wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)

- ea: `0x180007f50`
- end: `0x180008051`
- name: `?IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z`
- size: `257`
- prototype: `bool __fastcall(__int64, __int64, unsigned __int8, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180017300`

## callees

- `0x180007f50`
- `0x180008060`
- `0x180008ce8`
- `0x180008da0`

## pseudocode

```c
bool __fastcall wil::details::IsFeatureConfigured(__int64 a1, __int64 a2, unsigned __int8 a3, int a4, _DWORD *a5)
{
  unsigned int v5; // esi
  unsigned int v6; // ebp
  __int64 *v7; // rbx
  unsigned int v10; // edi
  int v11; // eax
  int v12; // edx
  bool v13; // si
  char v14; // al
  int v15; // [rsp+58h] [rbp+20h] BYREF

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
    v10 = dword_18002EDCC;
    if ( !dword_18002EDCC )
      v10 = wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl((RTL_SRWLOCK *)wil::details::g_enabledStateManager);
    v15 = 0;
    *a5 = 1;
    v11 = wil_RtlStagingConfig_QueryFeatureState(a1, v6, v5, &v15);
    v12 = v15;
    v13 = v11 != 0;
    v14 = _InterlockedExchange((volatile __int32 *)v7, (v15 != 0) + 6);
    if ( !v12 && (v14 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        wil::details::g_enabledStateManager,
        v7,
        0,
        v10);
    return v13;
  }
}

```

## disassembly

```asm
0x180007f50  mov     [rsp+arg_8], rbx
0x180007f55  push    rbp
0x180007f56  push    rsi
0x180007f57  push    r14
0x180007f59  sub     rsp, 20h
0x180007f5d  test    r9d, r9d
0x180007f60  movzx   esi, r8b
0x180007f64  lea     rax, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::userStoreProbe
0x180007f6b  mov     ebp, edx
0x180007f6d  lea     rbx, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x180007f74  mov     r14, rcx
0x180007f77  cmovnz  rbx, rax
0x180007f7b  mov     r9d, [rbx]
0x180007f7e  mov     eax, r9d
0x180007f81  and     al, 3
0x180007f83  cmp     al, 2
0x180007f85  jnz     short loc_180007F97
0x180007f87  xor     al, al
0x180007f89  mov     rbx, [rsp+38h+arg_8]
0x180007f8e  add     rsp, 20h
0x180007f92  pop     r14
0x180007f94  pop     rsi
0x180007f95  pop     rbp
0x180007f96  retn
0x180007f97  test    r9b, 2
0x180007f9b  jnz     short loc_180008003
0x180007f9d  mov     [rsp+38h+arg_0], rdi
0x180007fa2  mov     edi, cs:dword_18002EDCC
0x180007fa8  nop
0x180007fa9  test    edi, edi
0x180007fab  jz      short loc_180008023
0x180007fad  mov     rcx, [rsp+38h+arg_20]
0x180007fb2  lea     r9, [rsp+38h+arg_18]
0x180007fb7  mov     r8d, esi
0x180007fba  mov     [rsp+38h+arg_18], 0
0x180007fc2  mov     edx, ebp
0x180007fc4  mov     dword ptr [rcx], 1
0x180007fca  mov     rcx, r14
0x180007fcd  call    wil_RtlStagingConfig_QueryFeatureState
0x180007fd2  mov     edx, [rsp+38h+arg_18]
0x180007fd6  test    eax, eax
0x180007fd8  setnz   sil
0x180007fdc  xor     eax, eax
0x180007fde  test    edx, edx
0x180007fe0  setnz   al
0x180007fe3  add     eax, 6
0x180007fe6  xchg    eax, [rbx]
0x180007fe8  test    edx, edx
0x180007fea  jz      short loc_180008036
0x180007fec  mov     rdi, [rsp+38h+arg_0]
0x180007ff1  movzx   eax, sil
0x180007ff5  mov     rbx, [rsp+38h+arg_8]
0x180007ffa  add     rsp, 20h
0x180007ffe  pop     r14
0x180008000  pop     rsi
0x180008001  pop     rbp
0x180008002  retn
0x180008003  mov     rax, [rsp+38h+arg_20]
0x180008008  mov     r8d, esi
0x18000800b  xor     r9d, r9d
0x18000800e  mov     dword ptr [rax], 1
0x180008014  call    wil_RtlStagingConfig_QueryFeatureState
0x180008019  test    eax, eax
0x18000801b  setnz   al
0x18000801e  jmp     loc_180007F89
0x180008023  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; this
0x18000802a  call    ?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ; wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)
0x18000802f  mov     edi, eax
0x180008031  jmp     loc_180007FAD
0x180008036  test    al, 4
0x180008038  jnz     short loc_180007FEC
0x18000803a  mov     r9d, edi
0x18000803d  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180008044  xor     r8d, r8d
0x180008047  mov     rdx, rbx
0x18000804a  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000804f  jmp     short loc_180007FEC
```
