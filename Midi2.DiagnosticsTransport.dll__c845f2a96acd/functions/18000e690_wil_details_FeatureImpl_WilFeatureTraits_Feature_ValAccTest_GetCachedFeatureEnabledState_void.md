# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e690`
- end: `0x18000e769`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010424`

## callees

- `0x18000d6e0`
- `0x18000e690`
- `0x18000f020`
- `0x18000ff38`

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
0x18000e690  mov     [rsp+arg_10], rbx
0x18000e695  mov     [rsp+arg_0], rcx
0x18000e69a  push    rbp
0x18000e69b  push    rsi
0x18000e69c  push    rdi
0x18000e69d  sub     rsp, 20h
0x18000e6a1  mov     rsi, cs:Feature_ValAccTest__descriptor
0x18000e6a8  mov     rdi, rdx
0x18000e6ab  mov     qword ptr [rdx], 0
0x18000e6b2  mov     eax, [rsi]
0x18000e6b4  mov     [rdx], eax
0x18000e6b6  and     eax, 6
0x18000e6b9  cmp     al, 6
0x18000e6bb  jz      loc_18000E759
0x18000e6c1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e6c6  lea     r8, [rsp+38h+arg_0]
0x18000e6cb  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e6d3  lea     rdx, [rsp+38h+arg_8]
0x18000e6d8  mov     ebp, eax
0x18000e6da  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18000e6df  mov     eax, [rdi]
0x18000e6e1  mov     rbx, [rsp+38h+arg_8]
0x18000e6e6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e6eb  mov     edx, eax
0x18000e6ed  mov     [rdi], eax
0x18000e6ef  mov     ecx, eax
0x18000e6f1  jz      short loc_18000E70C
0x18000e6f3  test    dl, 2
0x18000e6f6  jnz     short loc_18000E70C
0x18000e6f8  and     ecx, 0FFFFF63Eh
0x18000e6fe  mov     eax, ebx
0x18000e700  and     eax, 9C1h
0x18000e705  or      ecx, eax
0x18000e707  or      ecx, 2
0x18000e70a  mov     [rdi], ecx
0x18000e70c  mov     r8d, edx
0x18000e70f  and     r8d, 4
0x18000e713  jnz     short loc_18000E727
0x18000e715  btr     ecx, 0Ah
0x18000e719  mov     eax, ebx
0x18000e71b  and     eax, 400h
0x18000e720  or      ecx, eax
0x18000e722  or      ecx, 4
0x18000e725  mov     [rdi], ecx
0x18000e727  mov     eax, edx
0x18000e729  lock cmpxchg [rsi], ecx
0x18000e72d  jnz     short loc_18000E6E6
0x18000e72f  test    r8d, r8d
0x18000e732  jnz     short loc_18000E744
0x18000e734  mov     r8d, ebp
0x18000e737  mov     edx, 3
0x18000e73c  mov     rcx, rsi
0x18000e73f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e744  mov     eax, [rdi]
0x18000e746  test    al, 2
0x18000e748  jnz     short loc_18000E759
0x18000e74a  and     eax, 0FFFFF63Eh
0x18000e74f  and     ebx, 9C1h
0x18000e755  or      eax, ebx
0x18000e757  mov     [rdi], eax
0x18000e759  mov     rbx, [rsp+38h+arg_10]
0x18000e75e  mov     rax, rdi
0x18000e761  add     rsp, 20h
0x18000e765  pop     rdi
0x18000e766  pop     rsi
0x18000e767  pop     rbp
0x18000e768  retn
```
