# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e6e4`
- end: `0x18000e7bd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800114f4`

## callees

- `0x18000da08`
- `0x18000e6e4`
- `0x18000ee14`
- `0x180010c28`

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
0x18000e6e4  mov     [rsp+arg_10], rbx
0x18000e6e9  mov     [rsp+arg_0], rcx
0x18000e6ee  push    rbp
0x18000e6ef  push    rsi
0x18000e6f0  push    rdi
0x18000e6f1  sub     rsp, 20h
0x18000e6f5  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x18000e6fc  mov     rdi, rdx
0x18000e6ff  mov     qword ptr [rdx], 0
0x18000e706  mov     eax, [rsi]
0x18000e708  mov     [rdx], eax
0x18000e70a  and     eax, 6
0x18000e70d  cmp     al, 6
0x18000e70f  jz      loc_18000E7AD
0x18000e715  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e71a  lea     r8, [rsp+38h+arg_0]
0x18000e71f  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e727  lea     rdx, [rsp+38h+arg_8]
0x18000e72c  mov     ebp, eax
0x18000e72e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x18000e733  mov     eax, [rdi]
0x18000e735  mov     rbx, [rsp+38h+arg_8]
0x18000e73a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e73f  mov     edx, eax
0x18000e741  mov     [rdi], eax
0x18000e743  mov     ecx, eax
0x18000e745  jz      short loc_18000E760
0x18000e747  test    dl, 2
0x18000e74a  jnz     short loc_18000E760
0x18000e74c  and     ecx, 0FFFFF63Eh
0x18000e752  mov     eax, ebx
0x18000e754  and     eax, 9C1h
0x18000e759  or      ecx, eax
0x18000e75b  or      ecx, 2
0x18000e75e  mov     [rdi], ecx
0x18000e760  mov     r8d, edx
0x18000e763  and     r8d, 4
0x18000e767  jnz     short loc_18000E77B
0x18000e769  btr     ecx, 0Ah
0x18000e76d  mov     eax, ebx
0x18000e76f  and     eax, 400h
0x18000e774  or      ecx, eax
0x18000e776  or      ecx, 4
0x18000e779  mov     [rdi], ecx
0x18000e77b  mov     eax, edx
0x18000e77d  lock cmpxchg [rsi], ecx
0x18000e781  jnz     short loc_18000E73A
0x18000e783  test    r8d, r8d
0x18000e786  jnz     short loc_18000E798
0x18000e788  mov     r8d, ebp
0x18000e78b  mov     edx, 3
0x18000e790  mov     rcx, rsi
0x18000e793  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e798  mov     eax, [rdi]
0x18000e79a  test    al, 2
0x18000e79c  jnz     short loc_18000E7AD
0x18000e79e  and     eax, 0FFFFF63Eh
0x18000e7a3  and     ebx, 9C1h
0x18000e7a9  or      eax, ebx
0x18000e7ab  mov     [rdi], eax
0x18000e7ad  mov     rbx, [rsp+38h+arg_10]
0x18000e7b2  mov     rax, rdi
0x18000e7b5  add     rsp, 20h
0x18000e7b9  pop     rdi
0x18000e7ba  pop     rsi
0x18000e7bb  pop     rbp
0x18000e7bc  retn
```
