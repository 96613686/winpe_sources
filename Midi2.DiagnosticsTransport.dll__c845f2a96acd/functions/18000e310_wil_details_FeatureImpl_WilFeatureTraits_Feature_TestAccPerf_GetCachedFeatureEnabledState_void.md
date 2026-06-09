# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e310`
- end: `0x18000e3e9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800101b4`

## callees

- `0x18000d6e0`
- `0x18000e310`
- `0x18000ea60`
- `0x18000ff38`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestAccPerf__descriptor,
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
0x18000e310  mov     [rsp+arg_10], rbx
0x18000e315  mov     [rsp+arg_0], rcx
0x18000e31a  push    rbp
0x18000e31b  push    rsi
0x18000e31c  push    rdi
0x18000e31d  sub     rsp, 20h
0x18000e321  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x18000e328  mov     rdi, rdx
0x18000e32b  mov     qword ptr [rdx], 0
0x18000e332  mov     eax, [rsi]
0x18000e334  mov     [rdx], eax
0x18000e336  and     eax, 6
0x18000e339  cmp     al, 6
0x18000e33b  jz      loc_18000E3D9
0x18000e341  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e346  lea     r8, [rsp+38h+arg_0]
0x18000e34b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e353  lea     rdx, [rsp+38h+arg_8]
0x18000e358  mov     ebp, eax
0x18000e35a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18000e35f  mov     eax, [rdi]
0x18000e361  mov     rbx, [rsp+38h+arg_8]
0x18000e366  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e36b  mov     edx, eax
0x18000e36d  mov     [rdi], eax
0x18000e36f  mov     ecx, eax
0x18000e371  jz      short loc_18000E38C
0x18000e373  test    dl, 2
0x18000e376  jnz     short loc_18000E38C
0x18000e378  and     ecx, 0FFFFF63Eh
0x18000e37e  mov     eax, ebx
0x18000e380  and     eax, 9C1h
0x18000e385  or      ecx, eax
0x18000e387  or      ecx, 2
0x18000e38a  mov     [rdi], ecx
0x18000e38c  mov     r8d, edx
0x18000e38f  and     r8d, 4
0x18000e393  jnz     short loc_18000E3A7
0x18000e395  btr     ecx, 0Ah
0x18000e399  mov     eax, ebx
0x18000e39b  and     eax, 400h
0x18000e3a0  or      ecx, eax
0x18000e3a2  or      ecx, 4
0x18000e3a5  mov     [rdi], ecx
0x18000e3a7  mov     eax, edx
0x18000e3a9  lock cmpxchg [rsi], ecx
0x18000e3ad  jnz     short loc_18000E366
0x18000e3af  test    r8d, r8d
0x18000e3b2  jnz     short loc_18000E3C4
0x18000e3b4  mov     r8d, ebp
0x18000e3b7  mov     edx, 3
0x18000e3bc  mov     rcx, rsi
0x18000e3bf  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e3c4  mov     eax, [rdi]
0x18000e3c6  test    al, 2
0x18000e3c8  jnz     short loc_18000E3D9
0x18000e3ca  and     eax, 0FFFFF63Eh
0x18000e3cf  and     ebx, 9C1h
0x18000e3d5  or      eax, ebx
0x18000e3d7  mov     [rdi], eax
0x18000e3d9  mov     rbx, [rsp+38h+arg_10]
0x18000e3de  mov     rax, rdi
0x18000e3e1  add     rsp, 20h
0x18000e3e5  pop     rdi
0x18000e3e6  pop     rsi
0x18000e3e7  pop     rbp
0x18000e3e8  retn
```
