# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000eca4`
- end: `0x18000ed7d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013eac`

## callees

- `0x1800058e8`
- `0x180009270`
- `0x18000eca4`
- `0x18000f424`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestLoc1Perf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestLoc1Perf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestLoc1Perf__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000eca4  mov     [rsp+arg_10], rbx
0x18000eca9  mov     [rsp+arg_0], rcx
0x18000ecae  push    rbp
0x18000ecaf  push    rsi
0x18000ecb0  push    rdi
0x18000ecb1  sub     rsp, 20h
0x18000ecb5  mov     rsi, cs:Feature_TestLoc1Perf__descriptor
0x18000ecbc  mov     rdi, rdx
0x18000ecbf  mov     qword ptr [rdx], 0
0x18000ecc6  mov     eax, [rsi]
0x18000ecc8  mov     [rdx], eax
0x18000ecca  and     eax, 6
0x18000eccd  cmp     al, 6
0x18000eccf  jz      loc_18000ED6D
0x18000ecd5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000ecda  lea     r8, [rsp+38h+arg_0]
0x18000ecdf  mov     dword ptr [rsp+38h+arg_0], 0
0x18000ece7  lea     rdx, [rsp+38h+arg_8]
0x18000ecec  mov     ebp, eax
0x18000ecee  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestLoc1Perf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestLoc1Perf>::GetCurrentFeatureEnabledState(int *)
0x18000ecf3  mov     eax, [rdi]
0x18000ecf5  mov     rbx, [rsp+38h+arg_8]
0x18000ecfa  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000ecff  mov     edx, eax
0x18000ed01  mov     [rdi], eax
0x18000ed03  mov     ecx, eax
0x18000ed05  jz      short loc_18000ED20
0x18000ed07  test    dl, 2
0x18000ed0a  jnz     short loc_18000ED20
0x18000ed0c  and     ecx, 0FFFFF63Eh
0x18000ed12  mov     eax, ebx
0x18000ed14  and     eax, 9C1h
0x18000ed19  or      ecx, eax
0x18000ed1b  or      ecx, 2
0x18000ed1e  mov     [rdi], ecx
0x18000ed20  mov     r8d, edx
0x18000ed23  and     r8d, 4
0x18000ed27  jnz     short loc_18000ED3B
0x18000ed29  btr     ecx, 0Ah
0x18000ed2d  mov     eax, ebx
0x18000ed2f  and     eax, 400h
0x18000ed34  or      ecx, eax
0x18000ed36  or      ecx, 4
0x18000ed39  mov     [rdi], ecx
0x18000ed3b  mov     eax, edx
0x18000ed3d  lock cmpxchg [rsi], ecx
0x18000ed41  jnz     short loc_18000ECFA
0x18000ed43  test    r8d, r8d
0x18000ed46  jnz     short loc_18000ED58
0x18000ed48  mov     r8d, ebp
0x18000ed4b  mov     edx, 3
0x18000ed50  mov     rcx, rsi
0x18000ed53  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000ed58  mov     eax, [rdi]
0x18000ed5a  test    al, 2
0x18000ed5c  jnz     short loc_18000ED6D
0x18000ed5e  and     eax, 0FFFFF63Eh
0x18000ed63  and     ebx, 9C1h
0x18000ed69  or      eax, ebx
0x18000ed6b  mov     [rdi], eax
0x18000ed6d  mov     rbx, [rsp+38h+arg_10]
0x18000ed72  mov     rax, rdi
0x18000ed75  add     rsp, 20h
0x18000ed79  pop     rdi
0x18000ed7a  pop     rsi
0x18000ed7b  pop     rbp
0x18000ed7c  retn
```
