# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e3f0`
- end: `0x18000e4c9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010250`

## callees

- `0x18000d6e0`
- `0x18000e3f0`
- `0x18000ebd0`
- `0x18000ff38`

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
0x18000e3f0  mov     [rsp+arg_10], rbx
0x18000e3f5  mov     [rsp+arg_0], rcx
0x18000e3fa  push    rbp
0x18000e3fb  push    rsi
0x18000e3fc  push    rdi
0x18000e3fd  sub     rsp, 20h
0x18000e401  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x18000e408  mov     rdi, rdx
0x18000e40b  mov     qword ptr [rdx], 0
0x18000e412  mov     eax, [rsi]
0x18000e414  mov     [rdx], eax
0x18000e416  and     eax, 6
0x18000e419  cmp     al, 6
0x18000e41b  jz      loc_18000E4B9
0x18000e421  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e426  lea     r8, [rsp+38h+arg_0]
0x18000e42b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e433  lea     rdx, [rsp+38h+arg_8]
0x18000e438  mov     ebp, eax
0x18000e43a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x18000e43f  mov     eax, [rdi]
0x18000e441  mov     rbx, [rsp+38h+arg_8]
0x18000e446  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e44b  mov     edx, eax
0x18000e44d  mov     [rdi], eax
0x18000e44f  mov     ecx, eax
0x18000e451  jz      short loc_18000E46C
0x18000e453  test    dl, 2
0x18000e456  jnz     short loc_18000E46C
0x18000e458  and     ecx, 0FFFFF63Eh
0x18000e45e  mov     eax, ebx
0x18000e460  and     eax, 9C1h
0x18000e465  or      ecx, eax
0x18000e467  or      ecx, 2
0x18000e46a  mov     [rdi], ecx
0x18000e46c  mov     r8d, edx
0x18000e46f  and     r8d, 4
0x18000e473  jnz     short loc_18000E487
0x18000e475  btr     ecx, 0Ah
0x18000e479  mov     eax, ebx
0x18000e47b  and     eax, 400h
0x18000e480  or      ecx, eax
0x18000e482  or      ecx, 4
0x18000e485  mov     [rdi], ecx
0x18000e487  mov     eax, edx
0x18000e489  lock cmpxchg [rsi], ecx
0x18000e48d  jnz     short loc_18000E446
0x18000e48f  test    r8d, r8d
0x18000e492  jnz     short loc_18000E4A4
0x18000e494  mov     r8d, ebp
0x18000e497  mov     edx, 3
0x18000e49c  mov     rcx, rsi
0x18000e49f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e4a4  mov     eax, [rdi]
0x18000e4a6  test    al, 2
0x18000e4a8  jnz     short loc_18000E4B9
0x18000e4aa  and     eax, 0FFFFF63Eh
0x18000e4af  and     ebx, 9C1h
0x18000e4b5  or      eax, ebx
0x18000e4b7  mov     [rdi], eax
0x18000e4b9  mov     rbx, [rsp+38h+arg_10]
0x18000e4be  mov     rax, rdi
0x18000e4c1  add     rsp, 20h
0x18000e4c5  pop     rdi
0x18000e4c6  pop     rsi
0x18000e4c7  pop     rbp
0x18000e4c8  retn
```
