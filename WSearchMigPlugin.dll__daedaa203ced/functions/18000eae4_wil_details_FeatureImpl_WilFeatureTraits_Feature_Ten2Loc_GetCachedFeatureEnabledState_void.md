# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18000eae4`
- end: `0x18000ebbd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013d74`

## callees

- `0x1800058e8`
- `0x180009270`
- `0x18000eae4`
- `0x18000f144`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_Ten2Loc__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18000eae4  mov     [rsp+arg_10], rbx
0x18000eae9  mov     [rsp+arg_0], rcx
0x18000eaee  push    rbp
0x18000eaef  push    rsi
0x18000eaf0  push    rdi
0x18000eaf1  sub     rsp, 20h
0x18000eaf5  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18000eafc  mov     rdi, rdx
0x18000eaff  mov     qword ptr [rdx], 0
0x18000eb06  mov     eax, [rsi]
0x18000eb08  mov     [rdx], eax
0x18000eb0a  and     eax, 6
0x18000eb0d  cmp     al, 6
0x18000eb0f  jz      loc_18000EBAD
0x18000eb15  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000eb1a  lea     r8, [rsp+38h+arg_0]
0x18000eb1f  mov     dword ptr [rsp+38h+arg_0], 0
0x18000eb27  lea     rdx, [rsp+38h+arg_8]
0x18000eb2c  mov     ebp, eax
0x18000eb2e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18000eb33  mov     eax, [rdi]
0x18000eb35  mov     rbx, [rsp+38h+arg_8]
0x18000eb3a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000eb3f  mov     edx, eax
0x18000eb41  mov     [rdi], eax
0x18000eb43  mov     ecx, eax
0x18000eb45  jz      short loc_18000EB60
0x18000eb47  test    dl, 2
0x18000eb4a  jnz     short loc_18000EB60
0x18000eb4c  and     ecx, 0FFFFF63Eh
0x18000eb52  mov     eax, ebx
0x18000eb54  and     eax, 9C1h
0x18000eb59  or      ecx, eax
0x18000eb5b  or      ecx, 2
0x18000eb5e  mov     [rdi], ecx
0x18000eb60  mov     r8d, edx
0x18000eb63  and     r8d, 4
0x18000eb67  jnz     short loc_18000EB7B
0x18000eb69  btr     ecx, 0Ah
0x18000eb6d  mov     eax, ebx
0x18000eb6f  and     eax, 400h
0x18000eb74  or      ecx, eax
0x18000eb76  or      ecx, 4
0x18000eb79  mov     [rdi], ecx
0x18000eb7b  mov     eax, edx
0x18000eb7d  lock cmpxchg [rsi], ecx
0x18000eb81  jnz     short loc_18000EB3A
0x18000eb83  test    r8d, r8d
0x18000eb86  jnz     short loc_18000EB98
0x18000eb88  mov     r8d, ebp
0x18000eb8b  mov     edx, 3
0x18000eb90  mov     rcx, rsi
0x18000eb93  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000eb98  mov     eax, [rdi]
0x18000eb9a  test    al, 2
0x18000eb9c  jnz     short loc_18000EBAD
0x18000eb9e  and     eax, 0FFFFF63Eh
0x18000eba3  and     ebx, 9C1h
0x18000eba9  or      eax, ebx
0x18000ebab  mov     [rdi], eax
0x18000ebad  mov     rbx, [rsp+38h+arg_10]
0x18000ebb2  mov     rax, rdi
0x18000ebb5  add     rsp, 20h
0x18000ebb9  pop     rdi
0x18000ebba  pop     rsi
0x18000ebbb  pop     rbp
0x18000ebbc  retn
```
