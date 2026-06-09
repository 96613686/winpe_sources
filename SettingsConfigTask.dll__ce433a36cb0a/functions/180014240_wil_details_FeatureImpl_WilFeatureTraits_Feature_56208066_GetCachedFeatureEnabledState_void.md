# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56208066>::GetCachedFeatureEnabledState(void)

- ea: `0x180014240`
- end: `0x180014323`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56208066@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `227`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a9e8`
- `0x18001cc20`

## callees

- `0x180005ac4`
- `0x18000a09c`
- `0x180014240`
- `0x180016618`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56208066>::GetCachedFeatureEnabledState(
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
  __int64 v12; // r8
  wil::details *v14; // [rsp+40h] [rbp+8h] BYREF
  __int64 v15; // [rsp+48h] [rbp+10h] BYREF

  v14 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_56208066__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_56208066__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v14) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_56208066>::GetCurrentFeatureEnabledState(v6, &v15, &v14);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_56208066__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !(_DWORD)v12 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        &wil::details::g_enabledStateManager,
        Feature_56208066__descriptor,
        v12,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180014240  mov     [rsp+arg_10], rbx
0x180014245  mov     [rsp+arg_0], rcx
0x18001424a  push    rbp
0x18001424b  push    rsi
0x18001424c  push    rdi
0x18001424d  sub     rsp, 20h
0x180014251  mov     rsi, cs:Feature_56208066__descriptor
0x180014258  mov     rdi, rdx
0x18001425b  mov     qword ptr [rdx], 0
0x180014262  mov     eax, [rsi]
0x180014264  mov     [rdx], eax
0x180014266  and     eax, 6
0x180014269  cmp     al, 6
0x18001426b  jz      loc_180014313
0x180014271  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014276  lea     r8, [rsp+38h+arg_0]
0x18001427b  mov     dword ptr [rsp+38h+arg_0], 0
0x180014283  lea     rdx, [rsp+38h+arg_8]
0x180014288  mov     ebp, eax
0x18001428a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56208066@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56208066>::GetCurrentFeatureEnabledState(int *)
0x18001428f  test    ebp, ebp
0x180014291  jnz     short loc_180014297
0x180014293  mov     dword ptr [rsp+38h+arg_0], ebp
0x180014297  mov     eax, [rdi]
0x180014299  mov     rbx, [rsp+38h+arg_8]
0x18001429e  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800142a3  mov     edx, eax
0x1800142a5  mov     [rdi], eax
0x1800142a7  mov     ecx, eax
0x1800142a9  jz      short loc_1800142C4
0x1800142ab  test    dl, 2
0x1800142ae  jnz     short loc_1800142C4
0x1800142b0  and     ecx, 0FFFFF63Eh
0x1800142b6  mov     eax, ebx
0x1800142b8  and     eax, 9C1h
0x1800142bd  or      ecx, eax
0x1800142bf  or      ecx, 2
0x1800142c2  mov     [rdi], ecx
0x1800142c4  mov     r8d, edx
0x1800142c7  and     r8d, 4
0x1800142cb  jnz     short loc_1800142DF
0x1800142cd  btr     ecx, 0Ah
0x1800142d1  mov     eax, ebx
0x1800142d3  and     eax, 400h
0x1800142d8  or      ecx, eax
0x1800142da  or      ecx, 4
0x1800142dd  mov     [rdi], ecx
0x1800142df  mov     eax, edx
0x1800142e1  lock cmpxchg [rsi], ecx
0x1800142e5  jnz     short loc_18001429E
0x1800142e7  test    r8d, r8d
0x1800142ea  jnz     short loc_1800142FE
0x1800142ec  mov     r9d, ebp
0x1800142ef  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800142f6  mov     rdx, rsi
0x1800142f9  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800142fe  mov     eax, [rdi]
0x180014300  test    al, 2
0x180014302  jnz     short loc_180014313
0x180014304  and     eax, 0FFFFF63Eh
0x180014309  and     ebx, 9C1h
0x18001430f  or      eax, ebx
0x180014311  mov     [rdi], eax
0x180014313  mov     rbx, [rsp+38h+arg_10]
0x180014318  mov     rax, rdi
0x18001431b  add     rsp, 20h
0x18001431f  pop     rdi
0x180014320  pop     rsi
0x180014321  pop     rbp
0x180014322  retn
```
