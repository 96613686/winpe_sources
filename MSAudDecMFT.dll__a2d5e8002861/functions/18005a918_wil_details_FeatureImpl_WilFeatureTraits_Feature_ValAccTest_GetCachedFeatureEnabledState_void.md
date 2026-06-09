# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18005a918`
- end: `0x18005a9fa`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c35c`
- `0x18005ccc4`

## callees

- `0x180048c10`
- `0x18005a918`
- `0x18005b1d4`
- `0x18005c704`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
  __int64 v6; // rcx
  int *v7; // r9
  signed __int32 v8; // eax
  __int16 v9; // bx
  bool v10; // zf
  signed __int32 v11; // edx
  unsigned int v12; // ecx
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(
      v6,
      &v15,
      (enum FEATURE_CHANGE_TIME)&v14,
      v7);
    v8 = *(_DWORD *)a2;
    v9 = v15;
    do
    {
      v10 = (_DWORD)v14 == 0;
      v11 = v8;
      *(_DWORD *)a2 = v8;
      v12 = v8;
      if ( !v10 && (v8 & 2) == 0 )
      {
        v12 = v9 & 0x9C1 | v8 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v12;
      }
      if ( (v8 & 4) == 0 )
      {
        v12 = v9 & 0x400 | v12 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v12;
      }
      v8 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v12, v8);
    }
    while ( v11 != v8 );
    if ( (v11 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_ValAccTest__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v9 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18005a918  mov     [rsp+arg_10], rbx
0x18005a91d  mov     [rsp+arg_0], rcx
0x18005a922  push    rbp
0x18005a923  push    rsi
0x18005a924  push    rdi
0x18005a925  sub     rsp, 20h
0x18005a929  mov     rsi, cs:Feature_ValAccTest__descriptor
0x18005a930  mov     rdi, rdx
0x18005a933  mov     qword ptr [rdx], 0
0x18005a93a  mov     eax, [rsi]
0x18005a93c  mov     [rdx], eax
0x18005a93e  and     eax, 6
0x18005a941  cmp     al, 6
0x18005a943  jz      loc_18005A9E9
0x18005a949  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18005a94e  lea     r8, [rsp+38h+arg_0]
0x18005a953  mov     dword ptr [rsp+38h+arg_0], 0
0x18005a95b  lea     rdx, [rsp+38h+arg_8]
0x18005a960  mov     ebp, eax
0x18005a962  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18005a967  mov     eax, [rdi]
0x18005a969  mov     rbx, [rsp+38h+arg_8]
0x18005a96e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18005a973  mov     edx, eax
0x18005a975  mov     [rdi], eax
0x18005a977  mov     ecx, eax
0x18005a979  jz      short loc_18005A994
0x18005a97b  test    dl, 2
0x18005a97e  jnz     short loc_18005A994
0x18005a980  and     ecx, 0FFFFF63Eh
0x18005a986  mov     eax, ebx
0x18005a988  and     eax, 9C1h
0x18005a98d  or      ecx, eax
0x18005a98f  or      ecx, 2
0x18005a992  mov     [rdi], ecx
0x18005a994  mov     r8d, edx
0x18005a997  and     r8d, 4
0x18005a99b  jnz     short loc_18005A9AF
0x18005a99d  btr     ecx, 0Ah
0x18005a9a1  mov     eax, ebx
0x18005a9a3  and     eax, 400h
0x18005a9a8  or      ecx, eax
0x18005a9aa  or      ecx, 4
0x18005a9ad  mov     [rdi], ecx
0x18005a9af  mov     eax, edx
0x18005a9b1  lock cmpxchg [rsi], ecx
0x18005a9b5  jnz     short loc_18005A96E
0x18005a9b7  test    r8d, r8d
0x18005a9ba  jnz     short loc_18005A9D4
0x18005a9bc  mov     r9d, ebp
0x18005a9bf  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18005a9c6  mov     r8d, 3
0x18005a9cc  mov     rdx, rsi
0x18005a9cf  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18005a9d4  mov     eax, [rdi]
0x18005a9d6  test    al, 2
0x18005a9d8  jnz     short loc_18005A9E9
0x18005a9da  and     eax, 0FFFFF63Eh
0x18005a9df  and     ebx, 9C1h
0x18005a9e5  or      eax, ebx
0x18005a9e7  mov     [rdi], eax
0x18005a9e9  mov     rbx, [rsp+38h+arg_10]
0x18005a9ee  mov     rax, rdi
0x18005a9f1  add     rsp, 20h
0x18005a9f5  pop     rdi
0x18005a9f6  pop     rsi
0x18005a9f7  pop     rbp
0x18005a9f8  retn
```
