# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x14000a864`
- end: `0x14000a93d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b00c`

## callees

- `0x140004568`
- `0x140007e64`
- `0x14000a864`
- `0x14000a944`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_UxAccOptimization__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x14000a864  mov     [rsp+arg_10], rbx
0x14000a869  mov     [rsp+arg_0], rcx
0x14000a86e  push    rbp
0x14000a86f  push    rsi
0x14000a870  push    rdi
0x14000a871  sub     rsp, 20h
0x14000a875  mov     rsi, cs:Feature_UxAccOptimization__descriptor
0x14000a87c  mov     rdi, rdx
0x14000a87f  mov     qword ptr [rdx], 0
0x14000a886  mov     eax, [rsi]
0x14000a888  mov     [rdx], eax
0x14000a88a  and     eax, 6
0x14000a88d  cmp     al, 6
0x14000a88f  jz      loc_14000A92D
0x14000a895  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000a89a  lea     r8, [rsp+38h+arg_0]
0x14000a89f  mov     dword ptr [rsp+38h+arg_0], 0
0x14000a8a7  lea     rdx, [rsp+38h+arg_8]
0x14000a8ac  mov     ebp, eax
0x14000a8ae  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x14000a8b3  mov     eax, [rdi]
0x14000a8b5  mov     rbx, [rsp+38h+arg_8]
0x14000a8ba  cmp     dword ptr [rsp+38h+arg_0], 0
0x14000a8bf  mov     edx, eax
0x14000a8c1  mov     [rdi], eax
0x14000a8c3  mov     ecx, eax
0x14000a8c5  jz      short loc_14000A8E0
0x14000a8c7  test    dl, 2
0x14000a8ca  jnz     short loc_14000A8E0
0x14000a8cc  and     ecx, 0FFFFF63Eh
0x14000a8d2  mov     eax, ebx
0x14000a8d4  and     eax, 9C1h
0x14000a8d9  or      ecx, eax
0x14000a8db  or      ecx, 2
0x14000a8de  mov     [rdi], ecx
0x14000a8e0  mov     r8d, edx
0x14000a8e3  and     r8d, 4
0x14000a8e7  jnz     short loc_14000A8FB
0x14000a8e9  btr     ecx, 0Ah
0x14000a8ed  mov     eax, ebx
0x14000a8ef  and     eax, 400h
0x14000a8f4  or      ecx, eax
0x14000a8f6  or      ecx, 4
0x14000a8f9  mov     [rdi], ecx
0x14000a8fb  mov     eax, edx
0x14000a8fd  lock cmpxchg [rsi], ecx
0x14000a901  jnz     short loc_14000A8BA
0x14000a903  test    r8d, r8d
0x14000a906  jnz     short loc_14000A918
0x14000a908  mov     r8d, ebp
0x14000a90b  mov     edx, 3
0x14000a910  mov     rcx, rsi
0x14000a913  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14000a918  mov     eax, [rdi]
0x14000a91a  test    al, 2
0x14000a91c  jnz     short loc_14000A92D
0x14000a91e  and     eax, 0FFFFF63Eh
0x14000a923  and     ebx, 9C1h
0x14000a929  or      eax, ebx
0x14000a92b  mov     [rdi], eax
0x14000a92d  mov     rbx, [rsp+38h+arg_10]
0x14000a932  mov     rax, rdi
0x14000a935  add     rsp, 20h
0x14000a939  pop     rdi
0x14000a93a  pop     rsi
0x14000a93b  pop     rbp
0x14000a93c  retn
```
