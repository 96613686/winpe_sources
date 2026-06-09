# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x1800154d8`
- end: `0x1800155b1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800174d8`
- `0x180017d98`

## callees

- `0x18000543c`
- `0x180008794`
- `0x1800154d8`
- `0x180015dcc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestLoc1Perf__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800154d8  mov     [rsp+arg_10], rbx
0x1800154dd  mov     [rsp+arg_0], rcx
0x1800154e2  push    rbp
0x1800154e3  push    rsi
0x1800154e4  push    rdi
0x1800154e5  sub     rsp, 20h
0x1800154e9  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x1800154f0  mov     rdi, rdx
0x1800154f3  mov     qword ptr [rdx], 0
0x1800154fa  mov     eax, [rsi]
0x1800154fc  mov     [rdx], eax
0x1800154fe  and     eax, 6
0x180015501  cmp     al, 6
0x180015503  jz      loc_1800155A1
0x180015509  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001550e  lea     r8, [rsp+38h+arg_0]
0x180015513  mov     dword ptr [rsp+38h+arg_0], 0
0x18001551b  lea     rdx, [rsp+38h+arg_8]
0x180015520  mov     ebp, eax
0x180015522  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x180015527  mov     eax, [rdi]
0x180015529  mov     rbx, [rsp+38h+arg_8]
0x18001552e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180015533  mov     edx, eax
0x180015535  mov     [rdi], eax
0x180015537  mov     ecx, eax
0x180015539  jz      short loc_180015554
0x18001553b  test    dl, 2
0x18001553e  jnz     short loc_180015554
0x180015540  and     ecx, 0FFFFF63Eh
0x180015546  mov     eax, ebx
0x180015548  and     eax, 9C1h
0x18001554d  or      ecx, eax
0x18001554f  or      ecx, 2
0x180015552  mov     [rdi], ecx
0x180015554  mov     r8d, edx
0x180015557  and     r8d, 4
0x18001555b  jnz     short loc_18001556F
0x18001555d  btr     ecx, 0Ah
0x180015561  mov     eax, ebx
0x180015563  and     eax, 400h
0x180015568  or      ecx, eax
0x18001556a  or      ecx, 4
0x18001556d  mov     [rdi], ecx
0x18001556f  mov     eax, edx
0x180015571  lock cmpxchg [rsi], ecx
0x180015575  jnz     short loc_18001552E
0x180015577  test    r8d, r8d
0x18001557a  jnz     short loc_18001558C
0x18001557c  mov     r8d, ebp
0x18001557f  mov     edx, 3
0x180015584  mov     rcx, rsi
0x180015587  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001558c  mov     eax, [rdi]
0x18001558e  test    al, 2
0x180015590  jnz     short loc_1800155A1
0x180015592  and     eax, 0FFFFF63Eh
0x180015597  and     ebx, 9C1h
0x18001559d  or      eax, ebx
0x18001559f  mov     [rdi], eax
0x1800155a1  mov     rbx, [rsp+38h+arg_10]
0x1800155a6  mov     rax, rdi
0x1800155a9  add     rsp, 20h
0x1800155ad  pop     rdi
0x1800155ae  pop     rsi
0x1800155af  pop     rbp
0x1800155b0  retn
```
