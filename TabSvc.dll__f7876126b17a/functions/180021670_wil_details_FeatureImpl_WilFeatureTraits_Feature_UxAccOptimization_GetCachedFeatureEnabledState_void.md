# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x180021670`
- end: `0x180021749`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002570c`
- `0x180028b8c`

## callees

- `0x180019930`
- `0x18001a080`
- `0x180021670`
- `0x180022288`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UxAccOptimization__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x180021670  mov     [rsp+arg_10], rbx
0x180021675  mov     [rsp+arg_0], rcx
0x18002167a  push    rbp
0x18002167b  push    rsi
0x18002167c  push    rdi
0x18002167d  sub     rsp, 20h
0x180021681  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x180021688  mov     rdi, rdx
0x18002168b  mov     qword ptr [rdx], 0
0x180021692  mov     eax, [rsi]
0x180021694  mov     [rdx], eax
0x180021696  and     eax, 6
0x180021699  cmp     al, 6
0x18002169b  jz      loc_180021739
0x1800216a1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800216a6  lea     r8, [rsp+38h+arg_0]
0x1800216ab  mov     dword ptr [rsp+38h+arg_0], 0
0x1800216b3  lea     rdx, [rsp+38h+arg_8]
0x1800216b8  mov     ebp, eax
0x1800216ba  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x1800216bf  mov     eax, [rdi]
0x1800216c1  mov     rbx, [rsp+38h+arg_8]
0x1800216c6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800216cb  mov     edx, eax
0x1800216cd  mov     [rdi], eax
0x1800216cf  mov     ecx, eax
0x1800216d1  jz      short loc_1800216EC
0x1800216d3  test    dl, 2
0x1800216d6  jnz     short loc_1800216EC
0x1800216d8  and     ecx, 0FFFFF63Eh
0x1800216de  mov     eax, ebx
0x1800216e0  and     eax, 9C1h
0x1800216e5  or      ecx, eax
0x1800216e7  or      ecx, 2
0x1800216ea  mov     [rdi], ecx
0x1800216ec  mov     r8d, edx
0x1800216ef  and     r8d, 4
0x1800216f3  jnz     short loc_180021707
0x1800216f5  btr     ecx, 0Ah
0x1800216f9  mov     eax, ebx
0x1800216fb  and     eax, 400h
0x180021700  or      ecx, eax
0x180021702  or      ecx, 4
0x180021705  mov     [rdi], ecx
0x180021707  mov     eax, edx
0x180021709  lock cmpxchg [rsi], ecx
0x18002170d  jnz     short loc_1800216C6
0x18002170f  test    r8d, r8d
0x180021712  jnz     short loc_180021724
0x180021714  mov     r8d, ebp
0x180021717  mov     edx, 3
0x18002171c  mov     rcx, rsi
0x18002171f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180021724  mov     eax, [rdi]
0x180021726  test    al, 2
0x180021728  jnz     short loc_180021739
0x18002172a  and     eax, 0FFFFF63Eh
0x18002172f  and     ebx, 9C1h
0x180021735  or      eax, ebx
0x180021737  mov     [rdi], eax
0x180021739  mov     rbx, [rsp+38h+arg_10]
0x18002173e  mov     rax, rdi
0x180021741  add     rsp, 20h
0x180021745  pop     rdi
0x180021746  pop     rsi
0x180021747  pop     rbp
0x180021748  retn
```
