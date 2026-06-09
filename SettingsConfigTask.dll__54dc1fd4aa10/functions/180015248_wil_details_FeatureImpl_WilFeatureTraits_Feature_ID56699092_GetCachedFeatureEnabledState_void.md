# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56699092>::GetCachedFeatureEnabledState(void)

- ea: `0x180015248`
- end: `0x18001532b`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56699092@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `227`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b21c`

## callees

- `0x180005ac4`
- `0x18000a09c`
- `0x180015248`
- `0x1800171e4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56699092>::GetCachedFeatureEnabledState(
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
  int v12; // r8d
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_ID56699092__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID56699092__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56699092>::GetCurrentFeatureEnabledState(v6, &v15, &v14);
    if ( !v5 )
      LODWORD(v14) = 0;
    v7 = *(_DWORD *)a2;
    v8 = v15;
    do
    {
      v9 = (_DWORD)v14 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      v12 = v7 & 4;
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID56699092__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        (RTL_SRWLOCK *)&wil::details::g_enabledStateManager,
        (volatile signed __int32 *)Feature_ID56699092__descriptor,
        0,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180015248  mov     [rsp+arg_10], rbx
0x18001524d  mov     [rsp+arg_0], rcx
0x180015252  push    rbp
0x180015253  push    rsi
0x180015254  push    rdi
0x180015255  sub     rsp, 20h
0x180015259  mov     rsi, cs:Feature_ID56699092__descriptor
0x180015260  mov     rdi, rdx
0x180015263  mov     qword ptr [rdx], 0
0x18001526a  mov     eax, [rsi]
0x18001526c  mov     [rdx], eax
0x18001526e  and     eax, 6
0x180015271  cmp     al, 6
0x180015273  jz      loc_18001531B
0x180015279  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001527e  lea     r8, [rsp+38h+arg_0]
0x180015283  mov     dword ptr [rsp+38h+arg_0], 0
0x18001528b  lea     rdx, [rsp+38h+arg_8]
0x180015290  mov     ebp, eax
0x180015292  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID56699092@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID56699092>::GetCurrentFeatureEnabledState(int *)
0x180015297  test    ebp, ebp
0x180015299  jnz     short loc_18001529F
0x18001529b  mov     dword ptr [rsp+38h+arg_0], ebp
0x18001529f  mov     eax, [rdi]
0x1800152a1  mov     rbx, [rsp+38h+arg_8]
0x1800152a6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800152ab  mov     edx, eax
0x1800152ad  mov     [rdi], eax
0x1800152af  mov     ecx, eax
0x1800152b1  jz      short loc_1800152CC
0x1800152b3  test    dl, 2
0x1800152b6  jnz     short loc_1800152CC
0x1800152b8  and     ecx, 0FFFFF63Eh
0x1800152be  mov     eax, ebx
0x1800152c0  and     eax, 9C1h
0x1800152c5  or      ecx, eax
0x1800152c7  or      ecx, 2
0x1800152ca  mov     [rdi], ecx
0x1800152cc  mov     r8d, edx
0x1800152cf  and     r8d, 4
0x1800152d3  jnz     short loc_1800152E7
0x1800152d5  btr     ecx, 0Ah
0x1800152d9  mov     eax, ebx
0x1800152db  and     eax, 400h
0x1800152e0  or      ecx, eax
0x1800152e2  or      ecx, 4
0x1800152e5  mov     [rdi], ecx
0x1800152e7  mov     eax, edx
0x1800152e9  lock cmpxchg [rsi], ecx
0x1800152ed  jnz     short loc_1800152A6
0x1800152ef  test    r8d, r8d
0x1800152f2  jnz     short loc_180015306
0x1800152f4  mov     r9d, ebp
0x1800152f7  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800152fe  mov     rdx, rsi
0x180015301  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180015306  mov     eax, [rdi]
0x180015308  test    al, 2
0x18001530a  jnz     short loc_18001531B
0x18001530c  and     eax, 0FFFFF63Eh
0x180015311  and     ebx, 9C1h
0x180015317  or      eax, ebx
0x180015319  mov     [rdi], eax
0x18001531b  mov     rbx, [rsp+38h+arg_10]
0x180015320  mov     rax, rdi
0x180015323  add     rsp, 20h
0x180015327  pop     rdi
0x180015328  pop     rsi
0x180015329  pop     rbp
0x18001532a  retn
```
