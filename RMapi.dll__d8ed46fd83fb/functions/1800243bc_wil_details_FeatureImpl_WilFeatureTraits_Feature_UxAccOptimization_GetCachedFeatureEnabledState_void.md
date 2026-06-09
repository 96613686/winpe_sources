# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x1800243bc`
- end: `0x1800244a7`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024808`
- `0x180024a84`

## callees

- `0x18000d2a0`
- `0x1800120d0`
- `0x180016180`
- `0x1800243bc`
- `0x1800245f4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
      v5,
      &v12,
      &v13);
    v6 = *(_DWORD *)a2;
    v7 = v12;
    do
    {
      v8 = v13 == 0;
      v9 = v6;
      *(_DWORD *)a2 = v6;
      v10 = v6;
      if ( !v8 && (v6 & 2) == 0 )
      {
        v10 = v7 & 0x9C1 | v6 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v10;
      }
      if ( (v6 & 4) == 0 )
      {
        v10 = v7 & 0x400 | v10 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v10;
      }
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_UxAccOptimization__descriptor,
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
0x1800243bc  push    rbx
0x1800243be  push    rbp
0x1800243bf  push    rsi
0x1800243c0  push    rdi
0x1800243c1  sub     rsp, 48h
0x1800243c5  mov     rax, cs:__security_cookie
0x1800243cc  xor     rax, rsp
0x1800243cf  mov     [rsp+68h+var_38], rax
0x1800243d4  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x1800243db  mov     rdi, rdx
0x1800243de  mov     qword ptr [rdx], 0
0x1800243e5  mov     eax, [rsi]
0x1800243e7  mov     [rdx], eax
0x1800243e9  and     eax, 6
0x1800243ec  cmp     al, 6
0x1800243ee  jz      loc_18002448E
0x1800243f4  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800243f9  lea     r8, [rsp+68h+var_40]
0x1800243fe  mov     [rsp+68h+var_40], 0
0x180024406  lea     rdx, [rsp+68h+var_48]
0x18002440b  mov     ebp, eax
0x18002440d  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x180024412  mov     eax, [rdi]
0x180024414  mov     rbx, [rsp+68h+var_48]
0x180024419  cmp     [rsp+68h+var_40], 0
0x18002441e  mov     edx, eax
0x180024420  mov     [rdi], eax
0x180024422  mov     ecx, eax
0x180024424  jz      short loc_18002443F
0x180024426  test    dl, 2
0x180024429  jnz     short loc_18002443F
0x18002442b  and     ecx, 0FFFFF63Eh
0x180024431  mov     eax, ebx
0x180024433  and     eax, 9C1h
0x180024438  or      ecx, eax
0x18002443a  or      ecx, 2
0x18002443d  mov     [rdi], ecx
0x18002443f  mov     r8d, edx
0x180024442  and     r8d, 4
0x180024446  jnz     short loc_18002445A
0x180024448  btr     ecx, 0Ah
0x18002444c  mov     eax, ebx
0x18002444e  and     eax, 400h
0x180024453  or      ecx, eax
0x180024455  or      ecx, 4
0x180024458  mov     [rdi], ecx
0x18002445a  mov     eax, edx
0x18002445c  lock cmpxchg [rsi], ecx
0x180024460  jnz     short loc_180024419
0x180024462  test    r8d, r8d
0x180024465  jnz     short loc_180024477
0x180024467  mov     r8d, ebp
0x18002446a  mov     edx, 3
0x18002446f  mov     rcx, rsi
0x180024472  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180024477  mov     ecx, [rdi]
0x180024479  test    cl, 2
0x18002447c  jnz     short loc_18002448E
0x18002447e  and     ecx, 0FFFFF63Eh
0x180024484  and     ebx, 9C1h
0x18002448a  or      ecx, ebx
0x18002448c  mov     [rdi], ecx
0x18002448e  mov     rax, rdi
0x180024491  mov     rcx, [rsp+68h+var_38]
0x180024496  xor     rcx, rsp; StackCookie
0x180024499  call    __security_check_cookie
0x18002449e  add     rsp, 48h
0x1800244a2  pop     rdi
0x1800244a3  pop     rsi
0x1800244a4  pop     rbp
0x1800244a5  pop     rbx
0x1800244a6  retn
```
