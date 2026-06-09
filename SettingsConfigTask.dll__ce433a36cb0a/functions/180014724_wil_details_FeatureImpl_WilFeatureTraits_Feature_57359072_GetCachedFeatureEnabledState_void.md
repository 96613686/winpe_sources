# wil::details::FeatureImpl<__WilFeatureTraits_Feature_57359072>::GetCachedFeatureEnabledState(void)

- ea: `0x180014724`
- end: `0x180014805`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57359072@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `225`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001acb0`
- `0x18001cd90`

## callees

- `0x180005ac4`
- `0x18000a09c`
- `0x180014724`
- `0x180016a10`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_57359072>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
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
  v3 = *(_DWORD *)Feature_57359072__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_57359072__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_57359072>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_57359072__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_57359072__descriptor,
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
0x180014724  mov     [rsp+arg_10], rbx
0x180014729  mov     [rsp+arg_0], rcx
0x18001472e  push    rbp
0x18001472f  push    rsi
0x180014730  push    rdi
0x180014731  sub     rsp, 20h
0x180014735  mov     rsi, cs:Feature_57359072__descriptor
0x18001473c  mov     rdi, rdx
0x18001473f  mov     qword ptr [rdx], 0
0x180014746  mov     eax, [rsi]
0x180014748  mov     [rdx], eax
0x18001474a  and     eax, 6
0x18001474d  cmp     al, 6
0x18001474f  jz      loc_1800147F5
0x180014755  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001475a  lea     r8, [rsp+38h+arg_0]
0x18001475f  mov     dword ptr [rsp+38h+arg_0], 0
0x180014767  lea     rdx, [rsp+38h+arg_8]
0x18001476c  mov     ebp, eax
0x18001476e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_57359072@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57359072>::GetCurrentFeatureEnabledState(int *)
0x180014773  mov     eax, [rdi]
0x180014775  mov     rbx, [rsp+38h+arg_8]
0x18001477a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001477f  mov     edx, eax
0x180014781  mov     [rdi], eax
0x180014783  mov     ecx, eax
0x180014785  jz      short loc_1800147A0
0x180014787  test    dl, 2
0x18001478a  jnz     short loc_1800147A0
0x18001478c  and     ecx, 0FFFFF63Eh
0x180014792  mov     eax, ebx
0x180014794  and     eax, 9C1h
0x180014799  or      ecx, eax
0x18001479b  or      ecx, 2
0x18001479e  mov     [rdi], ecx
0x1800147a0  mov     r8d, edx
0x1800147a3  and     r8d, 4
0x1800147a7  jnz     short loc_1800147BB
0x1800147a9  btr     ecx, 0Ah
0x1800147ad  mov     eax, ebx
0x1800147af  and     eax, 400h
0x1800147b4  or      ecx, eax
0x1800147b6  or      ecx, 4
0x1800147b9  mov     [rdi], ecx
0x1800147bb  mov     eax, edx
0x1800147bd  lock cmpxchg [rsi], ecx
0x1800147c1  jnz     short loc_18001477A
0x1800147c3  test    r8d, r8d
0x1800147c6  jnz     short loc_1800147E0
0x1800147c8  mov     r9d, ebp
0x1800147cb  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800147d2  mov     r8d, 3
0x1800147d8  mov     rdx, rsi
0x1800147db  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800147e0  mov     eax, [rdi]
0x1800147e2  test    al, 2
0x1800147e4  jnz     short loc_1800147F5
0x1800147e6  and     eax, 0FFFFF63Eh
0x1800147eb  and     ebx, 9C1h
0x1800147f1  or      eax, ebx
0x1800147f3  mov     [rdi], eax
0x1800147f5  mov     rbx, [rsp+38h+arg_10]
0x1800147fa  mov     rax, rdi
0x1800147fd  add     rsp, 20h
0x180014801  pop     rdi
0x180014802  pop     rsi
0x180014803  pop     rbp
0x180014804  retn
```
