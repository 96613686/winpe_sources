# wil::details::FeatureImpl<__WilFeatureTraits_Feature_DemandStartNetsetupInAI>::GetCachedFeatureEnabledState(void)

- ea: `0x18000a1ac`
- end: `0x18000a297`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DemandStartNetsetupInAI@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000ca70`
- `0x18000da24`

## callees

- `0x1800027c0`
- `0x1800099bc`
- `0x18000a1ac`
- `0x18000a394`
- `0x18000d0e4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_DemandStartNetsetupInAI>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_DemandStartNetsetupInAI__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_DemandStartNetsetupInAI__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_DemandStartNetsetupInAI>::GetCurrentFeatureEnabledState(
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_DemandStartNetsetupInAI__descriptor, v10, v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_DemandStartNetsetupInAI__descriptor, 3, v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000a1ac  push    rbx
0x18000a1ae  push    rbp
0x18000a1af  push    rsi
0x18000a1b0  push    rdi
0x18000a1b1  sub     rsp, 48h
0x18000a1b5  mov     rax, cs:__security_cookie
0x18000a1bc  xor     rax, rsp
0x18000a1bf  mov     [rsp+68h+var_38], rax
0x18000a1c4  mov     rsi, cs:Feature_DemandStartNetsetupInAI__descriptor
0x18000a1cb  mov     rdi, rdx
0x18000a1ce  mov     qword ptr [rdx], 0
0x18000a1d5  mov     eax, [rsi]
0x18000a1d7  mov     [rdx], eax
0x18000a1d9  and     eax, 6
0x18000a1dc  cmp     al, 6
0x18000a1de  jz      loc_18000A27E
0x18000a1e4  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000a1e9  lea     r8, [rsp+68h+var_40]
0x18000a1ee  mov     [rsp+68h+var_40], 0
0x18000a1f6  lea     rdx, [rsp+68h+var_48]
0x18000a1fb  mov     ebp, eax
0x18000a1fd  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_DemandStartNetsetupInAI@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_DemandStartNetsetupInAI>::GetCurrentFeatureEnabledState(int *)
0x18000a202  mov     eax, [rdi]
0x18000a204  mov     rbx, [rsp+68h+var_48]
0x18000a209  cmp     [rsp+68h+var_40], 0
0x18000a20e  mov     edx, eax
0x18000a210  mov     [rdi], eax
0x18000a212  mov     ecx, eax
0x18000a214  jz      short loc_18000A22F
0x18000a216  test    dl, 2
0x18000a219  jnz     short loc_18000A22F
0x18000a21b  and     ecx, 0FFFFF63Eh
0x18000a221  mov     eax, ebx
0x18000a223  and     eax, 9C1h
0x18000a228  or      ecx, eax
0x18000a22a  or      ecx, 2
0x18000a22d  mov     [rdi], ecx
0x18000a22f  mov     r8d, edx
0x18000a232  and     r8d, 4
0x18000a236  jnz     short loc_18000A24A
0x18000a238  btr     ecx, 0Ah
0x18000a23c  mov     eax, ebx
0x18000a23e  and     eax, 400h
0x18000a243  or      ecx, eax
0x18000a245  or      ecx, 4
0x18000a248  mov     [rdi], ecx
0x18000a24a  mov     eax, edx
0x18000a24c  lock cmpxchg [rsi], ecx
0x18000a250  jnz     short loc_18000A209
0x18000a252  test    r8d, r8d
0x18000a255  jnz     short loc_18000A267
0x18000a257  mov     r8d, ebp
0x18000a25a  mov     edx, 3
0x18000a25f  mov     rcx, rsi
0x18000a262  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000a267  mov     ecx, [rdi]
0x18000a269  test    cl, 2
0x18000a26c  jnz     short loc_18000A27E
0x18000a26e  and     ecx, 0FFFFF63Eh
0x18000a274  and     ebx, 9C1h
0x18000a27a  or      ecx, ebx
0x18000a27c  mov     [rdi], ecx
0x18000a27e  mov     rax, rdi
0x18000a281  mov     rcx, [rsp+68h+var_38]
0x18000a286  xor     rcx, rsp; StackCookie
0x18000a289  call    __security_check_cookie
0x18000a28e  add     rsp, 48h
0x18000a292  pop     rdi
0x18000a293  pop     rsi
0x18000a294  pop     rbp
0x18000a295  pop     rbx
0x18000a296  retn
```
