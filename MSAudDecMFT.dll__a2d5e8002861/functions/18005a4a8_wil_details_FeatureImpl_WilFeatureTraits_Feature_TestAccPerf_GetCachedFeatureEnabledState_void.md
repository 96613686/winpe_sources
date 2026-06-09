# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x18005a4a8`
- end: `0x18005a58a`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `226`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18005c2d0`
- `0x18005cc44`

## callees

- `0x180048c10`
- `0x18005a4a8`
- `0x18005af5c`
- `0x18005c704`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(
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
      v8 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v12, v8);
    }
    while ( v11 != v8 );
    if ( (v11 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_TestAccPerf__descriptor,
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
0x18005a4a8  mov     [rsp+arg_10], rbx
0x18005a4ad  mov     [rsp+arg_0], rcx
0x18005a4b2  push    rbp
0x18005a4b3  push    rsi
0x18005a4b4  push    rdi
0x18005a4b5  sub     rsp, 20h
0x18005a4b9  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x18005a4c0  mov     rdi, rdx
0x18005a4c3  mov     qword ptr [rdx], 0
0x18005a4ca  mov     eax, [rsi]
0x18005a4cc  mov     [rdx], eax
0x18005a4ce  and     eax, 6
0x18005a4d1  cmp     al, 6
0x18005a4d3  jz      loc_18005A579
0x18005a4d9  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18005a4de  lea     r8, [rsp+38h+arg_0]
0x18005a4e3  mov     dword ptr [rsp+38h+arg_0], 0
0x18005a4eb  lea     rdx, [rsp+38h+arg_8]
0x18005a4f0  mov     ebp, eax
0x18005a4f2  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18005a4f7  mov     eax, [rdi]
0x18005a4f9  mov     rbx, [rsp+38h+arg_8]
0x18005a4fe  cmp     dword ptr [rsp+38h+arg_0], 0
0x18005a503  mov     edx, eax
0x18005a505  mov     [rdi], eax
0x18005a507  mov     ecx, eax
0x18005a509  jz      short loc_18005A524
0x18005a50b  test    dl, 2
0x18005a50e  jnz     short loc_18005A524
0x18005a510  and     ecx, 0FFFFF63Eh
0x18005a516  mov     eax, ebx
0x18005a518  and     eax, 9C1h
0x18005a51d  or      ecx, eax
0x18005a51f  or      ecx, 2
0x18005a522  mov     [rdi], ecx
0x18005a524  mov     r8d, edx
0x18005a527  and     r8d, 4
0x18005a52b  jnz     short loc_18005A53F
0x18005a52d  btr     ecx, 0Ah
0x18005a531  mov     eax, ebx
0x18005a533  and     eax, 400h
0x18005a538  or      ecx, eax
0x18005a53a  or      ecx, 4
0x18005a53d  mov     [rdi], ecx
0x18005a53f  mov     eax, edx
0x18005a541  lock cmpxchg [rsi], ecx
0x18005a545  jnz     short loc_18005A4FE
0x18005a547  test    r8d, r8d
0x18005a54a  jnz     short loc_18005A564
0x18005a54c  mov     r9d, ebp
0x18005a54f  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18005a556  mov     r8d, 3
0x18005a55c  mov     rdx, rsi
0x18005a55f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18005a564  mov     eax, [rdi]
0x18005a566  test    al, 2
0x18005a568  jnz     short loc_18005A579
0x18005a56a  and     eax, 0FFFFF63Eh
0x18005a56f  and     ebx, 9C1h
0x18005a575  or      eax, ebx
0x18005a577  mov     [rdi], eax
0x18005a579  mov     rbx, [rsp+38h+arg_10]
0x18005a57e  mov     rax, rdi
0x18005a581  add     rsp, 20h
0x18005a585  pop     rdi
0x18005a586  pop     rsi
0x18005a587  pop     rbp
0x18005a588  retn
```
