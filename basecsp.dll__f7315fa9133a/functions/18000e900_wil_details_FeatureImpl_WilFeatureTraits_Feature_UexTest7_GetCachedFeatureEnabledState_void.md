# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e900`
- end: `0x18000e9d9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001619c`
- `0x180018798`

## callees

- `0x18000d7e0`
- `0x18000e900`
- `0x18000f4e4`
- `0x1800170d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  int v5; // ebp
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
  v3 = *(_DWORD *)Feature_UexTest7__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UexTest7__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UexTest7__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_UexTest7__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000e900  mov     [rsp+arg_10], rbx
0x18000e905  mov     [rsp+arg_0], rcx
0x18000e90a  push    rbp
0x18000e90b  push    rsi
0x18000e90c  push    rdi
0x18000e90d  sub     rsp, 20h
0x18000e911  mov     rsi, cs:Feature_UexTest7__descriptor
0x18000e918  mov     rdi, rdx
0x18000e91b  mov     qword ptr [rdx], 0
0x18000e922  mov     eax, [rsi]
0x18000e924  mov     [rdx], eax
0x18000e926  and     eax, 6
0x18000e929  cmp     al, 6
0x18000e92b  jz      loc_18000E9C9
0x18000e931  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e936  lea     r8, [rsp+38h+arg_0]
0x18000e93b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e943  lea     rdx, [rsp+38h+arg_8]
0x18000e948  mov     ebp, eax
0x18000e94a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x18000e94f  mov     eax, [rdi]
0x18000e951  mov     rbx, [rsp+38h+arg_8]
0x18000e956  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e95b  mov     edx, eax
0x18000e95d  mov     [rdi], eax
0x18000e95f  mov     ecx, eax
0x18000e961  jz      short loc_18000E97C
0x18000e963  test    dl, 2
0x18000e966  jnz     short loc_18000E97C
0x18000e968  and     ecx, 0FFFFF63Eh
0x18000e96e  mov     eax, ebx
0x18000e970  and     eax, 9C1h
0x18000e975  or      ecx, eax
0x18000e977  or      ecx, 2
0x18000e97a  mov     [rdi], ecx
0x18000e97c  mov     r8d, edx
0x18000e97f  and     r8d, 4
0x18000e983  jnz     short loc_18000E997
0x18000e985  btr     ecx, 0Ah
0x18000e989  mov     eax, ebx
0x18000e98b  and     eax, 400h
0x18000e990  or      ecx, eax
0x18000e992  or      ecx, 4
0x18000e995  mov     [rdi], ecx
0x18000e997  mov     eax, edx
0x18000e999  lock cmpxchg [rsi], ecx
0x18000e99d  jnz     short loc_18000E956
0x18000e99f  test    r8d, r8d
0x18000e9a2  jnz     short loc_18000E9B4
0x18000e9a4  mov     r8d, ebp
0x18000e9a7  mov     edx, 3
0x18000e9ac  mov     rcx, rsi
0x18000e9af  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e9b4  mov     eax, [rdi]
0x18000e9b6  test    al, 2
0x18000e9b8  jnz     short loc_18000E9C9
0x18000e9ba  and     eax, 0FFFFF63Eh
0x18000e9bf  and     ebx, 9C1h
0x18000e9c5  or      eax, ebx
0x18000e9c7  mov     [rdi], eax
0x18000e9c9  mov     rbx, [rsp+38h+arg_10]
0x18000e9ce  mov     rax, rdi
0x18000e9d1  add     rsp, 20h
0x18000e9d5  pop     rdi
0x18000e9d6  pop     rsi
0x18000e9d7  pop     rbp
0x18000e9d8  retn
```
