# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f36c`
- end: `0x18001f445`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021500`

## callees

- `0x18001e65c`
- `0x18001f36c`
- `0x18001fb4c`
- `0x180020fe4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  signed __int32 v8; // edx
  unsigned int v9; // ecx
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v5, &v11);
    v6 = *(_DWORD *)a2;
    v7 = v11;
    do
    {
      v8 = v6;
      *(_DWORD *)a2 = v6;
      v9 = v6;
      if ( (v6 & 4) == 0 )
      {
        v9 = v7 & 0x400 | v6 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v9;
      }
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestLoc1Perf__descriptor,
        3,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001f36c  mov     [rsp+arg_10], rbx
0x18001f371  mov     [rsp+arg_0], rcx
0x18001f376  push    rbp
0x18001f377  push    rsi
0x18001f378  push    rdi
0x18001f379  sub     rsp, 20h
0x18001f37d  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x18001f384  mov     rdi, rdx
0x18001f387  mov     qword ptr [rdx], 0
0x18001f38e  mov     eax, [rsi]
0x18001f390  mov     [rdx], eax
0x18001f392  and     eax, 6
0x18001f395  cmp     al, 6
0x18001f397  jz      loc_18001F435
0x18001f39d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f3a2  lea     r8, [rsp+38h+arg_0]
0x18001f3a7  mov     dword ptr [rsp+38h+arg_0], 0
0x18001f3af  lea     rdx, [rsp+38h+arg_8]
0x18001f3b4  mov     ebp, eax
0x18001f3b6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x18001f3bb  mov     eax, [rdi]
0x18001f3bd  mov     rbx, [rsp+38h+arg_8]
0x18001f3c2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001f3c7  mov     edx, eax
0x18001f3c9  mov     [rdi], eax
0x18001f3cb  mov     ecx, eax
0x18001f3cd  jz      short loc_18001F3E8
0x18001f3cf  test    dl, 2
0x18001f3d2  jnz     short loc_18001F3E8
0x18001f3d4  and     ecx, 0FFFFF63Eh
0x18001f3da  mov     eax, ebx
0x18001f3dc  and     eax, 9C1h
0x18001f3e1  or      ecx, eax
0x18001f3e3  or      ecx, 2
0x18001f3e6  mov     [rdi], ecx
0x18001f3e8  mov     r8d, edx
0x18001f3eb  and     r8d, 4
0x18001f3ef  jnz     short loc_18001F403
0x18001f3f1  btr     ecx, 0Ah
0x18001f3f5  mov     eax, ebx
0x18001f3f7  and     eax, 400h
0x18001f3fc  or      ecx, eax
0x18001f3fe  or      ecx, 4
0x18001f401  mov     [rdi], ecx
0x18001f403  mov     eax, edx
0x18001f405  lock cmpxchg [rsi], ecx
0x18001f409  jnz     short loc_18001F3C2
0x18001f40b  test    r8d, r8d
0x18001f40e  jnz     short loc_18001F420
0x18001f410  mov     r8d, ebp
0x18001f413  mov     edx, 3
0x18001f418  mov     rcx, rsi
0x18001f41b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f420  mov     eax, [rdi]
0x18001f422  test    al, 2
0x18001f424  jnz     short loc_18001F435
0x18001f426  and     eax, 0FFFFF63Eh
0x18001f42b  and     ebx, 9C1h
0x18001f431  or      eax, ebx
0x18001f433  mov     [rdi], eax
0x18001f435  mov     rbx, [rsp+38h+arg_10]
0x18001f43a  mov     rax, rdi
0x18001f43d  add     rsp, 20h
0x18001f441  pop     rdi
0x18001f442  pop     rsi
0x18001f443  pop     rbp
0x18001f444  retn
```
