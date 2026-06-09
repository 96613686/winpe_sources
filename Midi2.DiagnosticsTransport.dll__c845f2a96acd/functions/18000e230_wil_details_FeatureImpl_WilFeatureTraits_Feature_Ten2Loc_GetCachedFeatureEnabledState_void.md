# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e230`
- end: `0x18000e309`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010118`

## callees

- `0x18000d6e0`
- `0x18000e230`
- `0x18000e8f0`
- `0x18000ff38`

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
0x18000e230  mov     [rsp+arg_10], rbx
0x18000e235  mov     [rsp+arg_0], rcx
0x18000e23a  push    rbp
0x18000e23b  push    rsi
0x18000e23c  push    rdi
0x18000e23d  sub     rsp, 20h
0x18000e241  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18000e248  mov     rdi, rdx
0x18000e24b  mov     qword ptr [rdx], 0
0x18000e252  mov     eax, [rsi]
0x18000e254  mov     [rdx], eax
0x18000e256  and     eax, 6
0x18000e259  cmp     al, 6
0x18000e25b  jz      loc_18000E2F9
0x18000e261  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e266  lea     r8, [rsp+38h+arg_0]
0x18000e26b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e273  lea     rdx, [rsp+38h+arg_8]
0x18000e278  mov     ebp, eax
0x18000e27a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18000e27f  mov     eax, [rdi]
0x18000e281  mov     rbx, [rsp+38h+arg_8]
0x18000e286  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e28b  mov     edx, eax
0x18000e28d  mov     [rdi], eax
0x18000e28f  mov     ecx, eax
0x18000e291  jz      short loc_18000E2AC
0x18000e293  test    dl, 2
0x18000e296  jnz     short loc_18000E2AC
0x18000e298  and     ecx, 0FFFFF63Eh
0x18000e29e  mov     eax, ebx
0x18000e2a0  and     eax, 9C1h
0x18000e2a5  or      ecx, eax
0x18000e2a7  or      ecx, 2
0x18000e2aa  mov     [rdi], ecx
0x18000e2ac  mov     r8d, edx
0x18000e2af  and     r8d, 4
0x18000e2b3  jnz     short loc_18000E2C7
0x18000e2b5  btr     ecx, 0Ah
0x18000e2b9  mov     eax, ebx
0x18000e2bb  and     eax, 400h
0x18000e2c0  or      ecx, eax
0x18000e2c2  or      ecx, 4
0x18000e2c5  mov     [rdi], ecx
0x18000e2c7  mov     eax, edx
0x18000e2c9  lock cmpxchg [rsi], ecx
0x18000e2cd  jnz     short loc_18000E286
0x18000e2cf  test    r8d, r8d
0x18000e2d2  jnz     short loc_18000E2E4
0x18000e2d4  mov     r8d, ebp
0x18000e2d7  mov     edx, 3
0x18000e2dc  mov     rcx, rsi
0x18000e2df  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e2e4  mov     eax, [rdi]
0x18000e2e6  test    al, 2
0x18000e2e8  jnz     short loc_18000E2F9
0x18000e2ea  and     eax, 0FFFFF63Eh
0x18000e2ef  and     ebx, 9C1h
0x18000e2f5  or      eax, ebx
0x18000e2f7  mov     [rdi], eax
0x18000e2f9  mov     rbx, [rsp+38h+arg_10]
0x18000e2fe  mov     rax, rdi
0x18000e301  add     rsp, 20h
0x18000e305  pop     rdi
0x18000e306  pop     rsi
0x18000e307  pop     rbp
0x18000e308  retn
```
