# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e580`
- end: `0x18000e659`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180015f7c`
- `0x1800186a8`

## callees

- `0x18000d7e0`
- `0x18000e580`
- `0x18000f134`
- `0x1800170d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Ten2Loc__descriptor,
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
0x18000e580  mov     [rsp+arg_10], rbx
0x18000e585  mov     [rsp+arg_0], rcx
0x18000e58a  push    rbp
0x18000e58b  push    rsi
0x18000e58c  push    rdi
0x18000e58d  sub     rsp, 20h
0x18000e591  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18000e598  mov     rdi, rdx
0x18000e59b  mov     qword ptr [rdx], 0
0x18000e5a2  mov     eax, [rsi]
0x18000e5a4  mov     [rdx], eax
0x18000e5a6  and     eax, 6
0x18000e5a9  cmp     al, 6
0x18000e5ab  jz      loc_18000E649
0x18000e5b1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e5b6  lea     r8, [rsp+38h+arg_0]
0x18000e5bb  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e5c3  lea     rdx, [rsp+38h+arg_8]
0x18000e5c8  mov     ebp, eax
0x18000e5ca  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18000e5cf  mov     eax, [rdi]
0x18000e5d1  mov     rbx, [rsp+38h+arg_8]
0x18000e5d6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e5db  mov     edx, eax
0x18000e5dd  mov     [rdi], eax
0x18000e5df  mov     ecx, eax
0x18000e5e1  jz      short loc_18000E5FC
0x18000e5e3  test    dl, 2
0x18000e5e6  jnz     short loc_18000E5FC
0x18000e5e8  and     ecx, 0FFFFF63Eh
0x18000e5ee  mov     eax, ebx
0x18000e5f0  and     eax, 9C1h
0x18000e5f5  or      ecx, eax
0x18000e5f7  or      ecx, 2
0x18000e5fa  mov     [rdi], ecx
0x18000e5fc  mov     r8d, edx
0x18000e5ff  and     r8d, 4
0x18000e603  jnz     short loc_18000E617
0x18000e605  btr     ecx, 0Ah
0x18000e609  mov     eax, ebx
0x18000e60b  and     eax, 400h
0x18000e610  or      ecx, eax
0x18000e612  or      ecx, 4
0x18000e615  mov     [rdi], ecx
0x18000e617  mov     eax, edx
0x18000e619  lock cmpxchg [rsi], ecx
0x18000e61d  jnz     short loc_18000E5D6
0x18000e61f  test    r8d, r8d
0x18000e622  jnz     short loc_18000E634
0x18000e624  mov     r8d, ebp
0x18000e627  mov     edx, 3
0x18000e62c  mov     rcx, rsi
0x18000e62f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e634  mov     eax, [rdi]
0x18000e636  test    al, 2
0x18000e638  jnz     short loc_18000E649
0x18000e63a  and     eax, 0FFFFF63Eh
0x18000e63f  and     ebx, 9C1h
0x18000e645  or      eax, ebx
0x18000e647  mov     [rdi], eax
0x18000e649  mov     rbx, [rsp+38h+arg_10]
0x18000e64e  mov     rax, rdi
0x18000e651  add     rsp, 20h
0x18000e655  pop     rdi
0x18000e656  pop     rsi
0x18000e657  pop     rbp
0x18000e658  retn
```
