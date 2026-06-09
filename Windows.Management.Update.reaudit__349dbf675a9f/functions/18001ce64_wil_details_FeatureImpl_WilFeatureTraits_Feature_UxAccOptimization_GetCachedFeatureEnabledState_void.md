# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(void)

- ea: `0x18001ce64`
- end: `0x18001cf43`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001dc00`

## callees

- `0x18000b284`
- `0x18000f6bc`
- `0x18001ce64`
- `0x18001d050`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  int v4; // eax
  int v5; // esi
  __int64 v6; // rcx
  signed __int32 i; // r8d
  bool v8; // zf
  unsigned int v9; // edx
  __int16 v10; // ax
  signed __int32 v11; // eax
  int v13; // [rsp+38h] [rbp+10h] BYREF
  __int64 v14; // [rsp+40h] [rbp+18h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UxAccOptimization__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    v13 = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
    for ( i = *(_DWORD *)a2; ; i = v11 )
    {
      v8 = v13 == 0;
      v9 = i;
      v10 = v14;
      *(_DWORD *)a2 = i;
      if ( !v8 && (i & 2) == 0 )
      {
        v9 = v10 & 0x9C1 | i & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v9;
      }
      if ( (i & 4) == 0 )
      {
        v9 = v10 & 0x400 | v9 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v9;
      }
      v11 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UxAccOptimization__descriptor, v9, i);
      if ( i == v11 )
        break;
    }
    if ( (i & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_UxAccOptimization__descriptor,
        3,
        v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v14 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001ce64  mov     [rsp+arg_0], rbx
0x18001ce69  mov     [rsp+arg_18], rsi
0x18001ce6e  push    rdi
0x18001ce6f  sub     rsp, 20h
0x18001ce73  and     qword ptr [rdx], 0
0x18001ce77  mov     rbx, rdx
0x18001ce7a  mov     rdi, cs:Feature_UxAccOptimization__descriptor
0x18001ce81  mov     eax, [rdi]
0x18001ce83  mov     [rdx], eax
0x18001ce85  and     eax, 6
0x18001ce88  cmp     al, 6
0x18001ce8a  jz      loc_18001CF2F
0x18001ce90  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001ce95  and     [rsp+28h+arg_8], 0
0x18001ce9a  lea     r8, [rsp+28h+arg_8]
0x18001ce9f  lea     rdx, [rsp+28h+arg_10]
0x18001cea4  mov     esi, eax
0x18001cea6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UxAccOptimization@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UxAccOptimization>::GetCurrentFeatureEnabledState(int *)
0x18001ceab  mov     r8d, [rbx]
0x18001ceae  cmp     [rsp+28h+arg_8], 0
0x18001ceb3  mov     edx, r8d
0x18001ceb6  mov     rax, [rsp+28h+arg_10]
0x18001cebb  mov     [rbx], r8d
0x18001cebe  jz      short loc_18001CEDB
0x18001cec0  test    r8b, 2
0x18001cec4  jnz     short loc_18001CEDB
0x18001cec6  and     edx, 0FFFFF63Eh
0x18001cecc  mov     ecx, eax
0x18001cece  and     ecx, 9C1h
0x18001ced4  or      edx, ecx
0x18001ced6  or      edx, 2
0x18001ced9  mov     [rbx], edx
0x18001cedb  test    r8b, 4
0x18001cedf  jnz     short loc_18001CEF1
0x18001cee1  btr     edx, 0Ah
0x18001cee5  and     eax, 400h
0x18001ceea  or      edx, eax
0x18001ceec  or      edx, 4
0x18001ceef  mov     [rbx], edx
0x18001cef1  mov     eax, r8d
0x18001cef4  lock cmpxchg [rdi], edx
0x18001cef8  jz      short loc_18001CEFF
0x18001cefa  mov     r8d, eax
0x18001cefd  jmp     short loc_18001CEAE
0x18001ceff  test    r8b, 4
0x18001cf03  jnz     short loc_18001CF15
0x18001cf05  mov     r8d, esi
0x18001cf08  mov     edx, 3
0x18001cf0d  mov     rcx, rdi
0x18001cf10  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001cf15  mov     ecx, [rbx]
0x18001cf17  test    cl, 2
0x18001cf1a  jnz     short loc_18001CF2F
0x18001cf1c  mov     eax, dword ptr [rsp+28h+arg_10]
0x18001cf20  and     ecx, 0FFFFF63Eh
0x18001cf26  and     eax, 9C1h
0x18001cf2b  or      ecx, eax
0x18001cf2d  mov     [rbx], ecx
0x18001cf2f  mov     rsi, [rsp+28h+arg_18]
0x18001cf34  mov     rax, rbx
0x18001cf37  mov     rbx, [rsp+28h+arg_0]
0x18001cf3c  add     rsp, 20h
0x18001cf40  pop     rdi
0x18001cf41  retn
```
