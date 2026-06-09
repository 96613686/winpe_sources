# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b554`
- end: `0x18000b62d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000de18`

## callees

- `0x18000ab78`
- `0x18000b554`
- `0x18000bb34`
- `0x18000d258`

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
0x18000b554  mov     [rsp+arg_10], rbx
0x18000b559  mov     [rsp+arg_0], rcx
0x18000b55e  push    rbp
0x18000b55f  push    rsi
0x18000b560  push    rdi
0x18000b561  sub     rsp, 20h
0x18000b565  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18000b56c  mov     rdi, rdx
0x18000b56f  mov     qword ptr [rdx], 0
0x18000b576  mov     eax, [rsi]
0x18000b578  mov     [rdx], eax
0x18000b57a  and     eax, 6
0x18000b57d  cmp     al, 6
0x18000b57f  jz      loc_18000B61D
0x18000b585  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b58a  lea     r8, [rsp+38h+arg_0]
0x18000b58f  mov     dword ptr [rsp+38h+arg_0], 0
0x18000b597  lea     rdx, [rsp+38h+arg_8]
0x18000b59c  mov     ebp, eax
0x18000b59e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18000b5a3  mov     eax, [rdi]
0x18000b5a5  mov     rbx, [rsp+38h+arg_8]
0x18000b5aa  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000b5af  mov     edx, eax
0x18000b5b1  mov     [rdi], eax
0x18000b5b3  mov     ecx, eax
0x18000b5b5  jz      short loc_18000B5D0
0x18000b5b7  test    dl, 2
0x18000b5ba  jnz     short loc_18000B5D0
0x18000b5bc  and     ecx, 0FFFFF63Eh
0x18000b5c2  mov     eax, ebx
0x18000b5c4  and     eax, 9C1h
0x18000b5c9  or      ecx, eax
0x18000b5cb  or      ecx, 2
0x18000b5ce  mov     [rdi], ecx
0x18000b5d0  mov     r8d, edx
0x18000b5d3  and     r8d, 4
0x18000b5d7  jnz     short loc_18000B5EB
0x18000b5d9  btr     ecx, 0Ah
0x18000b5dd  mov     eax, ebx
0x18000b5df  and     eax, 400h
0x18000b5e4  or      ecx, eax
0x18000b5e6  or      ecx, 4
0x18000b5e9  mov     [rdi], ecx
0x18000b5eb  mov     eax, edx
0x18000b5ed  lock cmpxchg [rsi], ecx
0x18000b5f1  jnz     short loc_18000B5AA
0x18000b5f3  test    r8d, r8d
0x18000b5f6  jnz     short loc_18000B608
0x18000b5f8  mov     r8d, ebp
0x18000b5fb  mov     edx, 3
0x18000b600  mov     rcx, rsi
0x18000b603  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000b608  mov     eax, [rdi]
0x18000b60a  test    al, 2
0x18000b60c  jnz     short loc_18000B61D
0x18000b60e  and     eax, 0FFFFF63Eh
0x18000b613  and     ebx, 9C1h
0x18000b619  or      eax, ebx
0x18000b61b  mov     [rdi], eax
0x18000b61d  mov     rbx, [rsp+38h+arg_10]
0x18000b622  mov     rax, rdi
0x18000b625  add     rsp, 20h
0x18000b629  pop     rdi
0x18000b62a  pop     rsi
0x18000b62b  pop     rbp
0x18000b62c  retn
```
