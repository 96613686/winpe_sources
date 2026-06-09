# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56809673>::GetCachedFeatureEnabledState(void)

- ea: `0x180014554`
- end: `0x180014635`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56809673@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ab8c`
- `0x18001ccd4`

## callees

- `0x180005ac4`
- `0x18000a09c`
- `0x180014554`
- `0x180016878`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56809673>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_56809673__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_56809673__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_56809673>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_56809673__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_56809673__descriptor,
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
0x180014554  mov     [rsp+arg_10], rbx
0x180014559  mov     [rsp+arg_0], rcx
0x18001455e  push    rbp
0x18001455f  push    rsi
0x180014560  push    rdi
0x180014561  sub     rsp, 20h
0x180014565  mov     rsi, cs:Feature_56809673__descriptor
0x18001456c  mov     rdi, rdx
0x18001456f  mov     qword ptr [rdx], 0
0x180014576  mov     eax, [rsi]
0x180014578  mov     [rdx], eax
0x18001457a  and     eax, 6
0x18001457d  cmp     al, 6
0x18001457f  jz      loc_180014625
0x180014585  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001458a  lea     r8, [rsp+38h+arg_0]
0x18001458f  mov     dword ptr [rsp+38h+arg_0], 0
0x180014597  lea     rdx, [rsp+38h+arg_8]
0x18001459c  mov     ebp, eax
0x18001459e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56809673@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56809673>::GetCurrentFeatureEnabledState(int *)
0x1800145a3  mov     eax, [rdi]
0x1800145a5  mov     rbx, [rsp+38h+arg_8]
0x1800145aa  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800145af  mov     edx, eax
0x1800145b1  mov     [rdi], eax
0x1800145b3  mov     ecx, eax
0x1800145b5  jz      short loc_1800145D0
0x1800145b7  test    dl, 2
0x1800145ba  jnz     short loc_1800145D0
0x1800145bc  and     ecx, 0FFFFF63Eh
0x1800145c2  mov     eax, ebx
0x1800145c4  and     eax, 9C1h
0x1800145c9  or      ecx, eax
0x1800145cb  or      ecx, 2
0x1800145ce  mov     [rdi], ecx
0x1800145d0  mov     r8d, edx
0x1800145d3  and     r8d, 4
0x1800145d7  jnz     short loc_1800145EB
0x1800145d9  btr     ecx, 0Ah
0x1800145dd  mov     eax, ebx
0x1800145df  and     eax, 400h
0x1800145e4  or      ecx, eax
0x1800145e6  or      ecx, 4
0x1800145e9  mov     [rdi], ecx
0x1800145eb  mov     eax, edx
0x1800145ed  lock cmpxchg [rsi], ecx
0x1800145f1  jnz     short loc_1800145AA
0x1800145f3  test    r8d, r8d
0x1800145f6  jnz     short loc_180014610
0x1800145f8  mov     r9d, ebp
0x1800145fb  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180014602  mov     r8d, 3
0x180014608  mov     rdx, rsi
0x18001460b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180014610  mov     eax, [rdi]
0x180014612  test    al, 2
0x180014614  jnz     short loc_180014625
0x180014616  and     eax, 0FFFFF63Eh
0x18001461b  and     ebx, 9C1h
0x180014621  or      eax, ebx
0x180014623  mov     [rdi], eax
0x180014625  mov     rbx, [rsp+38h+arg_10]
0x18001462a  mov     rax, rdi
0x18001462d  add     rsp, 20h
0x180014631  pop     rdi
0x180014632  pop     rsi
0x180014633  pop     rbp
0x180014634  retn
```
