# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000b8d4`
- end: `0x18000b9ad`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e088`

## callees

- `0x18000ab78`
- `0x18000b8d4`
- `0x18000c0f4`
- `0x18000d258`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValAccTest__descriptor,
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
0x18000b8d4  mov     [rsp+arg_10], rbx
0x18000b8d9  mov     [rsp+arg_0], rcx
0x18000b8de  push    rbp
0x18000b8df  push    rsi
0x18000b8e0  push    rdi
0x18000b8e1  sub     rsp, 20h
0x18000b8e5  mov     rsi, cs:Feature_ValAccTest__descriptor
0x18000b8ec  mov     rdi, rdx
0x18000b8ef  mov     qword ptr [rdx], 0
0x18000b8f6  mov     eax, [rsi]
0x18000b8f8  mov     [rdx], eax
0x18000b8fa  and     eax, 6
0x18000b8fd  cmp     al, 6
0x18000b8ff  jz      loc_18000B99D
0x18000b905  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000b90a  lea     r8, [rsp+38h+arg_0]
0x18000b90f  mov     dword ptr [rsp+38h+arg_0], 0
0x18000b917  lea     rdx, [rsp+38h+arg_8]
0x18000b91c  mov     ebp, eax
0x18000b91e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18000b923  mov     eax, [rdi]
0x18000b925  mov     rbx, [rsp+38h+arg_8]
0x18000b92a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000b92f  mov     edx, eax
0x18000b931  mov     [rdi], eax
0x18000b933  mov     ecx, eax
0x18000b935  jz      short loc_18000B950
0x18000b937  test    dl, 2
0x18000b93a  jnz     short loc_18000B950
0x18000b93c  and     ecx, 0FFFFF63Eh
0x18000b942  mov     eax, ebx
0x18000b944  and     eax, 9C1h
0x18000b949  or      ecx, eax
0x18000b94b  or      ecx, 2
0x18000b94e  mov     [rdi], ecx
0x18000b950  mov     r8d, edx
0x18000b953  and     r8d, 4
0x18000b957  jnz     short loc_18000B96B
0x18000b959  btr     ecx, 0Ah
0x18000b95d  mov     eax, ebx
0x18000b95f  and     eax, 400h
0x18000b964  or      ecx, eax
0x18000b966  or      ecx, 4
0x18000b969  mov     [rdi], ecx
0x18000b96b  mov     eax, edx
0x18000b96d  lock cmpxchg [rsi], ecx
0x18000b971  jnz     short loc_18000B92A
0x18000b973  test    r8d, r8d
0x18000b976  jnz     short loc_18000B988
0x18000b978  mov     r8d, ebp
0x18000b97b  mov     edx, 3
0x18000b980  mov     rcx, rsi
0x18000b983  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000b988  mov     eax, [rdi]
0x18000b98a  test    al, 2
0x18000b98c  jnz     short loc_18000B99D
0x18000b98e  and     eax, 0FFFFF63Eh
0x18000b993  and     ebx, 9C1h
0x18000b999  or      eax, ebx
0x18000b99b  mov     [rdi], eax
0x18000b99d  mov     rbx, [rsp+38h+arg_10]
0x18000b9a2  mov     rax, rdi
0x18000b9a5  add     rsp, 20h
0x18000b9a9  pop     rdi
0x18000b9aa  pop     rsi
0x18000b9ab  pop     rbp
0x18000b9ac  retn
```
