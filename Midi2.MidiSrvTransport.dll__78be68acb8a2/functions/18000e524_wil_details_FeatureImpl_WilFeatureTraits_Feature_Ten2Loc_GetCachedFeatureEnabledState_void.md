# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e524`
- end: `0x18000e5fd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800113bc`

## callees

- `0x18000da08`
- `0x18000e524`
- `0x18000eb34`
- `0x180010c28`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Ten2Loc__descriptor,
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
0x18000e524  mov     [rsp+arg_10], rbx
0x18000e529  mov     [rsp+arg_0], rcx
0x18000e52e  push    rbp
0x18000e52f  push    rsi
0x18000e530  push    rdi
0x18000e531  sub     rsp, 20h
0x18000e535  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18000e53c  mov     rdi, rdx
0x18000e53f  mov     qword ptr [rdx], 0
0x18000e546  mov     eax, [rsi]
0x18000e548  mov     [rdx], eax
0x18000e54a  and     eax, 6
0x18000e54d  cmp     al, 6
0x18000e54f  jz      loc_18000E5ED
0x18000e555  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e55a  lea     r8, [rsp+38h+arg_0]
0x18000e55f  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e567  lea     rdx, [rsp+38h+arg_8]
0x18000e56c  mov     ebp, eax
0x18000e56e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18000e573  mov     eax, [rdi]
0x18000e575  mov     rbx, [rsp+38h+arg_8]
0x18000e57a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e57f  mov     edx, eax
0x18000e581  mov     [rdi], eax
0x18000e583  mov     ecx, eax
0x18000e585  jz      short loc_18000E5A0
0x18000e587  test    dl, 2
0x18000e58a  jnz     short loc_18000E5A0
0x18000e58c  and     ecx, 0FFFFF63Eh
0x18000e592  mov     eax, ebx
0x18000e594  and     eax, 9C1h
0x18000e599  or      ecx, eax
0x18000e59b  or      ecx, 2
0x18000e59e  mov     [rdi], ecx
0x18000e5a0  mov     r8d, edx
0x18000e5a3  and     r8d, 4
0x18000e5a7  jnz     short loc_18000E5BB
0x18000e5a9  btr     ecx, 0Ah
0x18000e5ad  mov     eax, ebx
0x18000e5af  and     eax, 400h
0x18000e5b4  or      ecx, eax
0x18000e5b6  or      ecx, 4
0x18000e5b9  mov     [rdi], ecx
0x18000e5bb  mov     eax, edx
0x18000e5bd  lock cmpxchg [rsi], ecx
0x18000e5c1  jnz     short loc_18000E57A
0x18000e5c3  test    r8d, r8d
0x18000e5c6  jnz     short loc_18000E5D8
0x18000e5c8  mov     r8d, ebp
0x18000e5cb  mov     edx, 3
0x18000e5d0  mov     rcx, rsi
0x18000e5d3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e5d8  mov     eax, [rdi]
0x18000e5da  test    al, 2
0x18000e5dc  jnz     short loc_18000E5ED
0x18000e5de  and     eax, 0FFFFF63Eh
0x18000e5e3  and     ebx, 9C1h
0x18000e5e9  or      eax, ebx
0x18000e5eb  mov     [rdi], eax
0x18000e5ed  mov     rbx, [rsp+38h+arg_10]
0x18000e5f2  mov     rax, rdi
0x18000e5f5  add     rsp, 20h
0x18000e5f9  pop     rdi
0x18000e5fa  pop     rsi
0x18000e5fb  pop     rbp
0x18000e5fc  retn
```
