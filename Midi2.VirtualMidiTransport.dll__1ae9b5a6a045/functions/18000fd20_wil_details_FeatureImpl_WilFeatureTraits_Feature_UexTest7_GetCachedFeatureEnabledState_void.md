# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x18000fd20`
- end: `0x18000fdf9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011d8c`

## callees

- `0x18000ee50`
- `0x18000fd20`
- `0x180010620`
- `0x180011648`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UexTest7__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UexTest7__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UexTest7__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_UexTest7__descriptor,
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
0x18000fd20  mov     [rsp+arg_10], rbx
0x18000fd25  mov     [rsp+arg_0], rcx
0x18000fd2a  push    rbp
0x18000fd2b  push    rsi
0x18000fd2c  push    rdi
0x18000fd2d  sub     rsp, 20h
0x18000fd31  mov     rsi, cs:Feature_UexTest7__descriptor
0x18000fd38  mov     rdi, rdx
0x18000fd3b  mov     qword ptr [rdx], 0
0x18000fd42  mov     eax, [rsi]
0x18000fd44  mov     [rdx], eax
0x18000fd46  and     eax, 6
0x18000fd49  cmp     al, 6
0x18000fd4b  jz      loc_18000FDE9
0x18000fd51  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000fd56  lea     r8, [rsp+38h+arg_0]
0x18000fd5b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000fd63  lea     rdx, [rsp+38h+arg_8]
0x18000fd68  mov     ebp, eax
0x18000fd6a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x18000fd6f  mov     eax, [rdi]
0x18000fd71  mov     rbx, [rsp+38h+arg_8]
0x18000fd76  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000fd7b  mov     edx, eax
0x18000fd7d  mov     [rdi], eax
0x18000fd7f  mov     ecx, eax
0x18000fd81  jz      short loc_18000FD9C
0x18000fd83  test    dl, 2
0x18000fd86  jnz     short loc_18000FD9C
0x18000fd88  and     ecx, 0FFFFF63Eh
0x18000fd8e  mov     eax, ebx
0x18000fd90  and     eax, 9C1h
0x18000fd95  or      ecx, eax
0x18000fd97  or      ecx, 2
0x18000fd9a  mov     [rdi], ecx
0x18000fd9c  mov     r8d, edx
0x18000fd9f  and     r8d, 4
0x18000fda3  jnz     short loc_18000FDB7
0x18000fda5  btr     ecx, 0Ah
0x18000fda9  mov     eax, ebx
0x18000fdab  and     eax, 400h
0x18000fdb0  or      ecx, eax
0x18000fdb2  or      ecx, 4
0x18000fdb5  mov     [rdi], ecx
0x18000fdb7  mov     eax, edx
0x18000fdb9  lock cmpxchg [rsi], ecx
0x18000fdbd  jnz     short loc_18000FD76
0x18000fdbf  test    r8d, r8d
0x18000fdc2  jnz     short loc_18000FDD4
0x18000fdc4  mov     r8d, ebp
0x18000fdc7  mov     edx, 3
0x18000fdcc  mov     rcx, rsi
0x18000fdcf  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000fdd4  mov     eax, [rdi]
0x18000fdd6  test    al, 2
0x18000fdd8  jnz     short loc_18000FDE9
0x18000fdda  and     eax, 0FFFFF63Eh
0x18000fddf  and     ebx, 9C1h
0x18000fde5  or      eax, ebx
0x18000fde7  mov     [rdi], eax
0x18000fde9  mov     rbx, [rsp+38h+arg_10]
0x18000fdee  mov     rax, rdi
0x18000fdf1  add     rsp, 20h
0x18000fdf5  pop     rdi
0x18000fdf6  pop     rsi
0x18000fdf7  pop     rbp
0x18000fdf8  retn
```
