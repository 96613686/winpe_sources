# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x18001bcd8`
- end: `0x18001bdb1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c940`

## callees

- `0x18000ace8`
- `0x18000eed4`
- `0x18001bcd8`
- `0x18001bdb8`

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
  signed __int32 v8; // edx
  unsigned int v9; // ecx
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_UxAccOptimization__descriptor,
        3u,
        v4);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v7 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001bcd8  mov     [rsp+arg_10], rbx
0x18001bcdd  mov     [rsp+arg_0], rcx
0x18001bce2  push    rbp
0x18001bce3  push    rsi
0x18001bce4  push    rdi
0x18001bce5  sub     rsp, 20h
0x18001bce9  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x18001bcf0  mov     rdi, rdx
0x18001bcf3  mov     qword ptr [rdx], 0
0x18001bcfa  mov     eax, [rsi]
0x18001bcfc  mov     [rdx], eax
0x18001bcfe  and     eax, 6
0x18001bd01  cmp     al, 6
0x18001bd03  jz      loc_18001BDA1
0x18001bd09  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001bd0e  lea     r8, [rsp+38h+arg_0]
0x18001bd13  mov     dword ptr [rsp+38h+arg_0], 0
0x18001bd1b  lea     rdx, [rsp+38h+arg_8]
0x18001bd20  mov     ebp, eax
0x18001bd22  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18001bd27  mov     eax, [rdi]
0x18001bd29  mov     rbx, [rsp+38h+arg_8]
0x18001bd2e  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001bd33  mov     edx, eax
0x18001bd35  mov     [rdi], eax
0x18001bd37  mov     ecx, eax
0x18001bd39  jz      short loc_18001BD54
0x18001bd3b  test    dl, 2
0x18001bd3e  jnz     short loc_18001BD54
0x18001bd40  and     ecx, 0FFFFF63Eh
0x18001bd46  mov     eax, ebx
0x18001bd48  and     eax, 9C1h
0x18001bd4d  or      ecx, eax
0x18001bd4f  or      ecx, 2
0x18001bd52  mov     [rdi], ecx
0x18001bd54  mov     r8d, edx
0x18001bd57  and     r8d, 4
0x18001bd5b  jnz     short loc_18001BD6F
0x18001bd5d  btr     ecx, 0Ah
0x18001bd61  mov     eax, ebx
0x18001bd63  and     eax, 400h
0x18001bd68  or      ecx, eax
0x18001bd6a  or      ecx, 4
0x18001bd6d  mov     [rdi], ecx
0x18001bd6f  mov     eax, edx
0x18001bd71  lock cmpxchg [rsi], ecx
0x18001bd75  jnz     short loc_18001BD2E
0x18001bd77  test    r8d, r8d
0x18001bd7a  jnz     short loc_18001BD8C
0x18001bd7c  mov     r8d, ebp
0x18001bd7f  mov     edx, 3
0x18001bd84  mov     rcx, rsi
0x18001bd87  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001bd8c  mov     eax, [rdi]
0x18001bd8e  test    al, 2
0x18001bd90  jnz     short loc_18001BDA1
0x18001bd92  and     eax, 0FFFFF63Eh
0x18001bd97  and     ebx, 9C1h
0x18001bd9d  or      eax, ebx
0x18001bd9f  mov     [rdi], eax
0x18001bda1  mov     rbx, [rsp+38h+arg_10]
0x18001bda6  mov     rax, rdi
0x18001bda9  add     rsp, 20h
0x18001bdad  pop     rdi
0x18001bdae  pop     rsi
0x18001bdaf  pop     rbp
0x18001bdb0  retn
```
