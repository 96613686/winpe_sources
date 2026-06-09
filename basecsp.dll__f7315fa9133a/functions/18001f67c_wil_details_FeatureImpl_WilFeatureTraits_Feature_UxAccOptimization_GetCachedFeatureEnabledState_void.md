# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x18001f67c`
- end: `0x18001f755`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001f9dc`
- `0x18001faa0`

## callees

- `0x18000d7e0`
- `0x1800170d0`
- `0x18001f67c`
- `0x18001f824`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_UxAccOptimization__descriptor,
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
0x18001f67c  mov     [rsp+arg_10], rbx
0x18001f681  mov     [rsp+arg_0], rcx
0x18001f686  push    rbp
0x18001f687  push    rsi
0x18001f688  push    rdi
0x18001f689  sub     rsp, 20h
0x18001f68d  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18001f694  mov     rdi, rdx
0x18001f697  mov     qword ptr [rdx], 0
0x18001f69e  mov     eax, [rsi]
0x18001f6a0  mov     [rdx], eax
0x18001f6a2  and     eax, 6
0x18001f6a5  cmp     al, 6
0x18001f6a7  jz      loc_18001F745
0x18001f6ad  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001f6b2  lea     r8, [rsp+38h+arg_0]
0x18001f6b7  mov     dword ptr [rsp+38h+arg_0], 0
0x18001f6bf  lea     rdx, [rsp+38h+arg_8]
0x18001f6c4  mov     ebp, eax
0x18001f6c6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18001f6cb  mov     eax, [rdi]
0x18001f6cd  mov     rbx, [rsp+38h+arg_8]
0x18001f6d2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001f6d7  mov     edx, eax
0x18001f6d9  mov     [rdi], eax
0x18001f6db  mov     ecx, eax
0x18001f6dd  jz      short loc_18001F6F8
0x18001f6df  test    dl, 2
0x18001f6e2  jnz     short loc_18001F6F8
0x18001f6e4  and     ecx, 0FFFFF63Eh
0x18001f6ea  mov     eax, ebx
0x18001f6ec  and     eax, 9C1h
0x18001f6f1  or      ecx, eax
0x18001f6f3  or      ecx, 2
0x18001f6f6  mov     [rdi], ecx
0x18001f6f8  mov     r8d, edx
0x18001f6fb  and     r8d, 4
0x18001f6ff  jnz     short loc_18001F713
0x18001f701  btr     ecx, 0Ah
0x18001f705  mov     eax, ebx
0x18001f707  and     eax, 400h
0x18001f70c  or      ecx, eax
0x18001f70e  or      ecx, 4
0x18001f711  mov     [rdi], ecx
0x18001f713  mov     eax, edx
0x18001f715  lock cmpxchg [rsi], ecx
0x18001f719  jnz     short loc_18001F6D2
0x18001f71b  test    r8d, r8d
0x18001f71e  jnz     short loc_18001F730
0x18001f720  mov     r8d, ebp
0x18001f723  mov     edx, 3
0x18001f728  mov     rcx, rsi
0x18001f72b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001f730  mov     eax, [rdi]
0x18001f732  test    al, 2
0x18001f734  jnz     short loc_18001F745
0x18001f736  and     eax, 0FFFFF63Eh
0x18001f73b  and     ebx, 9C1h
0x18001f741  or      eax, ebx
0x18001f743  mov     [rdi], eax
0x18001f745  mov     rbx, [rsp+38h+arg_10]
0x18001f74a  mov     rax, rdi
0x18001f74d  add     rsp, 20h
0x18001f751  pop     rdi
0x18001f752  pop     rsi
0x18001f753  pop     rbp
0x18001f754  retn
```
