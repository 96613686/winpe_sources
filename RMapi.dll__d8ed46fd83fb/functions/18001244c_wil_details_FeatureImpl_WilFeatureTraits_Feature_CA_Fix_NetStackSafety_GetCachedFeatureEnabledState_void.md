# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetCachedFeatureEnabledState(void)

- ea: `0x18001244c`
- end: `0x180012537`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CA_Fix_NetStackSafety@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014f70`
- `0x180016a44`

## callees

- `0x18000d2a0`
- `0x1800120d0`
- `0x18001244c`
- `0x180012bec`
- `0x180016180`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CA_Fix_NetStackSafety__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CA_Fix_NetStackSafety__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetCurrentFeatureEnabledState(
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_CA_Fix_NetStackSafety__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_CA_Fix_NetStackSafety__descriptor,
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
0x18001244c  push    rbx
0x18001244e  push    rbp
0x18001244f  push    rsi
0x180012450  push    rdi
0x180012451  sub     rsp, 48h
0x180012455  mov     rax, cs:__security_cookie
0x18001245c  xor     rax, rsp
0x18001245f  mov     [rsp+68h+var_38], rax
0x180012464  mov     rsi, cs:Feature_CA_Fix_NetStackSafety__descriptor
0x18001246b  mov     rdi, rdx
0x18001246e  mov     qword ptr [rdx], 0
0x180012475  mov     eax, [rsi]
0x180012477  mov     [rdx], eax
0x180012479  and     eax, 6
0x18001247c  cmp     al, 6
0x18001247e  jz      loc_18001251E
0x180012484  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180012489  lea     r8, [rsp+68h+var_40]
0x18001248e  mov     [rsp+68h+var_40], 0
0x180012496  lea     rdx, [rsp+68h+var_48]
0x18001249b  mov     ebp, eax
0x18001249d  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CA_Fix_NetStackSafety@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CA_Fix_NetStackSafety>::GetCurrentFeatureEnabledState(int *)
0x1800124a2  mov     eax, [rdi]
0x1800124a4  mov     rbx, [rsp+68h+var_48]
0x1800124a9  cmp     [rsp+68h+var_40], 0
0x1800124ae  mov     edx, eax
0x1800124b0  mov     [rdi], eax
0x1800124b2  mov     ecx, eax
0x1800124b4  jz      short loc_1800124CF
0x1800124b6  test    dl, 2
0x1800124b9  jnz     short loc_1800124CF
0x1800124bb  and     ecx, 0FFFFF63Eh
0x1800124c1  mov     eax, ebx
0x1800124c3  and     eax, 9C1h
0x1800124c8  or      ecx, eax
0x1800124ca  or      ecx, 2
0x1800124cd  mov     [rdi], ecx
0x1800124cf  mov     r8d, edx
0x1800124d2  and     r8d, 4
0x1800124d6  jnz     short loc_1800124EA
0x1800124d8  btr     ecx, 0Ah
0x1800124dc  mov     eax, ebx
0x1800124de  and     eax, 400h
0x1800124e3  or      ecx, eax
0x1800124e5  or      ecx, 4
0x1800124e8  mov     [rdi], ecx
0x1800124ea  mov     eax, edx
0x1800124ec  lock cmpxchg [rsi], ecx
0x1800124f0  jnz     short loc_1800124A9
0x1800124f2  test    r8d, r8d
0x1800124f5  jnz     short loc_180012507
0x1800124f7  mov     r8d, ebp
0x1800124fa  mov     edx, 3
0x1800124ff  mov     rcx, rsi
0x180012502  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180012507  mov     ecx, [rdi]
0x180012509  test    cl, 2
0x18001250c  jnz     short loc_18001251E
0x18001250e  and     ecx, 0FFFFF63Eh
0x180012514  and     ebx, 9C1h
0x18001251a  or      ecx, ebx
0x18001251c  mov     [rdi], ecx
0x18001251e  mov     rax, rdi
0x180012521  mov     rcx, [rsp+68h+var_38]
0x180012526  xor     rcx, rsp; StackCookie
0x180012529  call    __security_check_cookie
0x18001252e  add     rsp, 48h
0x180012532  pop     rdi
0x180012533  pop     rsi
0x180012534  pop     rbp
0x180012535  pop     rbx
0x180012536  retn
```
