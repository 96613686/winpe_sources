# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x18000c1dc`
- end: `0x18000c2b5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cb4c`
- `0x18000d064`

## callees

- `0x18000543c`
- `0x180008794`
- `0x18000c1dc`
- `0x18000c39c`

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
0x18000c1dc  mov     [rsp+arg_10], rbx
0x18000c1e1  mov     [rsp+arg_0], rcx
0x18000c1e6  push    rbp
0x18000c1e7  push    rsi
0x18000c1e8  push    rdi
0x18000c1e9  sub     rsp, 20h
0x18000c1ed  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18000c1f4  mov     rdi, rdx
0x18000c1f7  mov     qword ptr [rdx], 0
0x18000c1fe  mov     eax, [rsi]
0x18000c200  mov     [rdx], eax
0x18000c202  and     eax, 6
0x18000c205  cmp     al, 6
0x18000c207  jz      loc_18000C2A5
0x18000c20d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000c212  lea     r8, [rsp+38h+arg_0]
0x18000c217  mov     dword ptr [rsp+38h+arg_0], 0
0x18000c21f  lea     rdx, [rsp+38h+arg_8]
0x18000c224  mov     ebp, eax
0x18000c226  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18000c22b  mov     eax, [rdi]
0x18000c22d  mov     rbx, [rsp+38h+arg_8]
0x18000c232  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000c237  mov     edx, eax
0x18000c239  mov     [rdi], eax
0x18000c23b  mov     ecx, eax
0x18000c23d  jz      short loc_18000C258
0x18000c23f  test    dl, 2
0x18000c242  jnz     short loc_18000C258
0x18000c244  and     ecx, 0FFFFF63Eh
0x18000c24a  mov     eax, ebx
0x18000c24c  and     eax, 9C1h
0x18000c251  or      ecx, eax
0x18000c253  or      ecx, 2
0x18000c256  mov     [rdi], ecx
0x18000c258  mov     r8d, edx
0x18000c25b  and     r8d, 4
0x18000c25f  jnz     short loc_18000C273
0x18000c261  btr     ecx, 0Ah
0x18000c265  mov     eax, ebx
0x18000c267  and     eax, 400h
0x18000c26c  or      ecx, eax
0x18000c26e  or      ecx, 4
0x18000c271  mov     [rdi], ecx
0x18000c273  mov     eax, edx
0x18000c275  lock cmpxchg [rsi], ecx
0x18000c279  jnz     short loc_18000C232
0x18000c27b  test    r8d, r8d
0x18000c27e  jnz     short loc_18000C290
0x18000c280  mov     r8d, ebp
0x18000c283  mov     edx, 3
0x18000c288  mov     rcx, rsi
0x18000c28b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000c290  mov     eax, [rdi]
0x18000c292  test    al, 2
0x18000c294  jnz     short loc_18000C2A5
0x18000c296  and     eax, 0FFFFF63Eh
0x18000c29b  and     ebx, 9C1h
0x18000c2a1  or      eax, ebx
0x18000c2a3  mov     [rdi], eax
0x18000c2a5  mov     rbx, [rsp+38h+arg_10]
0x18000c2aa  mov     rax, rdi
0x18000c2ad  add     rsp, 20h
0x18000c2b1  pop     rdi
0x18000c2b2  pop     rsi
0x18000c2b3  pop     rbp
0x18000c2b4  retn
```
