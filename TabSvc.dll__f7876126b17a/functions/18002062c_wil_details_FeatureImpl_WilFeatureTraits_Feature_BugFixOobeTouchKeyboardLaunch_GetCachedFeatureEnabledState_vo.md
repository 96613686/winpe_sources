# wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::GetCachedFeatureEnabledState(void)

- ea: `0x18002062c`
- end: `0x180020705`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019d04`
- `0x18001a760`

## callees

- `0x180019930`
- `0x18001a080`
- `0x18002062c`
- `0x180021acc`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_BugFixOobeTouchKeyboardLaunch__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_BugFixOobeTouchKeyboardLaunch__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_BugFixOobeTouchKeyboardLaunch__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_BugFixOobeTouchKeyboardLaunch__descriptor,
        1,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18002062c  mov     [rsp+arg_10], rbx
0x180020631  mov     [rsp+arg_0], rcx
0x180020636  push    rbp
0x180020637  push    rsi
0x180020638  push    rdi
0x180020639  sub     rsp, 20h
0x18002063d  mov     rsi, cs:Feature_BugFixOobeTouchKeyboardLaunch__descriptor
0x180020644  mov     rdi, rdx
0x180020647  mov     qword ptr [rdx], 0
0x18002064e  mov     eax, [rsi]
0x180020650  mov     [rdx], eax
0x180020652  and     eax, 6
0x180020655  cmp     al, 6
0x180020657  jz      loc_1800206F5
0x18002065d  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180020662  lea     r8, [rsp+38h+arg_0]
0x180020667  mov     dword ptr [rsp+38h+arg_0], 0
0x18002066f  lea     rdx, [rsp+38h+arg_8]
0x180020674  mov     ebp, eax
0x180020676  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixOobeTouchKeyboardLaunch>::GetCurrentFeatureEnabledState(int *)
0x18002067b  mov     eax, [rdi]
0x18002067d  mov     rbx, [rsp+38h+arg_8]
0x180020682  cmp     dword ptr [rsp+38h+arg_0], 0
0x180020687  mov     edx, eax
0x180020689  mov     [rdi], eax
0x18002068b  mov     ecx, eax
0x18002068d  jz      short loc_1800206A8
0x18002068f  test    dl, 2
0x180020692  jnz     short loc_1800206A8
0x180020694  and     ecx, 0FFFFF63Eh
0x18002069a  mov     eax, ebx
0x18002069c  and     eax, 9C1h
0x1800206a1  or      ecx, eax
0x1800206a3  or      ecx, 2
0x1800206a6  mov     [rdi], ecx
0x1800206a8  mov     r8d, edx
0x1800206ab  and     r8d, 4
0x1800206af  jnz     short loc_1800206C3
0x1800206b1  btr     ecx, 0Ah
0x1800206b5  mov     eax, ebx
0x1800206b7  and     eax, 400h
0x1800206bc  or      ecx, eax
0x1800206be  or      ecx, 4
0x1800206c1  mov     [rdi], ecx
0x1800206c3  mov     eax, edx
0x1800206c5  lock cmpxchg [rsi], ecx
0x1800206c9  jnz     short loc_180020682
0x1800206cb  test    r8d, r8d
0x1800206ce  jnz     short loc_1800206E0
0x1800206d0  mov     r8d, ebp
0x1800206d3  mov     edx, 1
0x1800206d8  mov     rcx, rsi
0x1800206db  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800206e0  mov     eax, [rdi]
0x1800206e2  test    al, 2
0x1800206e4  jnz     short loc_1800206F5
0x1800206e6  and     eax, 0FFFFF63Eh
0x1800206eb  and     ebx, 9C1h
0x1800206f1  or      eax, ebx
0x1800206f3  mov     [rdi], eax
0x1800206f5  mov     rbx, [rsp+38h+arg_10]
0x1800206fa  mov     rax, rdi
0x1800206fd  add     rsp, 20h
0x180020701  pop     rdi
0x180020702  pop     rsi
0x180020703  pop     rbp
0x180020704  retn
```
