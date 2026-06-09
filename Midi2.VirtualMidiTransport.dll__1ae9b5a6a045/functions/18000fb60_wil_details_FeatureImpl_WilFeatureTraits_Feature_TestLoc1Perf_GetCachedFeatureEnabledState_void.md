# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000fb60`
- end: `0x18000fc39`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011c54`

## callees

- `0x18000ee50`
- `0x18000fb60`
- `0x180010340`
- `0x180011648`

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
0x18000fb60  mov     [rsp+arg_10], rbx
0x18000fb65  mov     [rsp+arg_0], rcx
0x18000fb6a  push    rbp
0x18000fb6b  push    rsi
0x18000fb6c  push    rdi
0x18000fb6d  sub     rsp, 20h
0x18000fb71  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x18000fb78  mov     rdi, rdx
0x18000fb7b  mov     qword ptr [rdx], 0
0x18000fb82  mov     eax, [rsi]
0x18000fb84  mov     [rdx], eax
0x18000fb86  and     eax, 6
0x18000fb89  cmp     al, 6
0x18000fb8b  jz      loc_18000FC29
0x18000fb91  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000fb96  lea     r8, [rsp+38h+arg_0]
0x18000fb9b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000fba3  lea     rdx, [rsp+38h+arg_8]
0x18000fba8  mov     ebp, eax
0x18000fbaa  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x18000fbaf  mov     eax, [rdi]
0x18000fbb1  mov     rbx, [rsp+38h+arg_8]
0x18000fbb6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000fbbb  mov     edx, eax
0x18000fbbd  mov     [rdi], eax
0x18000fbbf  mov     ecx, eax
0x18000fbc1  jz      short loc_18000FBDC
0x18000fbc3  test    dl, 2
0x18000fbc6  jnz     short loc_18000FBDC
0x18000fbc8  and     ecx, 0FFFFF63Eh
0x18000fbce  mov     eax, ebx
0x18000fbd0  and     eax, 9C1h
0x18000fbd5  or      ecx, eax
0x18000fbd7  or      ecx, 2
0x18000fbda  mov     [rdi], ecx
0x18000fbdc  mov     r8d, edx
0x18000fbdf  and     r8d, 4
0x18000fbe3  jnz     short loc_18000FBF7
0x18000fbe5  btr     ecx, 0Ah
0x18000fbe9  mov     eax, ebx
0x18000fbeb  and     eax, 400h
0x18000fbf0  or      ecx, eax
0x18000fbf2  or      ecx, 4
0x18000fbf5  mov     [rdi], ecx
0x18000fbf7  mov     eax, edx
0x18000fbf9  lock cmpxchg [rsi], ecx
0x18000fbfd  jnz     short loc_18000FBB6
0x18000fbff  test    r8d, r8d
0x18000fc02  jnz     short loc_18000FC14
0x18000fc04  mov     r8d, ebp
0x18000fc07  mov     edx, 3
0x18000fc0c  mov     rcx, rsi
0x18000fc0f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000fc14  mov     eax, [rdi]
0x18000fc16  test    al, 2
0x18000fc18  jnz     short loc_18000FC29
0x18000fc1a  and     eax, 0FFFFF63Eh
0x18000fc1f  and     ebx, 9C1h
0x18000fc25  or      eax, ebx
0x18000fc27  mov     [rdi], eax
0x18000fc29  mov     rbx, [rsp+38h+arg_10]
0x18000fc2e  mov     rax, rdi
0x18000fc31  add     rsp, 20h
0x18000fc35  pop     rdi
0x18000fc36  pop     rsi
0x18000fc37  pop     rbp
0x18000fc38  retn
```
