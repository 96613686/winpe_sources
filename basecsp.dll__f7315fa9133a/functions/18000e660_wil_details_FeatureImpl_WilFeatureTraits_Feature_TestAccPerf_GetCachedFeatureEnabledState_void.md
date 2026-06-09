# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e660`
- end: `0x18000e739`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180016004`
- `0x1800186e4`

## callees

- `0x18000d7e0`
- `0x18000e660`
- `0x18000f220`
- `0x1800170d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestAccPerf__descriptor,
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
0x18000e660  mov     [rsp+arg_10], rbx
0x18000e665  mov     [rsp+arg_0], rcx
0x18000e66a  push    rbp
0x18000e66b  push    rsi
0x18000e66c  push    rdi
0x18000e66d  sub     rsp, 20h
0x18000e671  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x18000e678  mov     rdi, rdx
0x18000e67b  mov     qword ptr [rdx], 0
0x18000e682  mov     eax, [rsi]
0x18000e684  mov     [rdx], eax
0x18000e686  and     eax, 6
0x18000e689  cmp     al, 6
0x18000e68b  jz      loc_18000E729
0x18000e691  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e696  lea     r8, [rsp+38h+arg_0]
0x18000e69b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e6a3  lea     rdx, [rsp+38h+arg_8]
0x18000e6a8  mov     ebp, eax
0x18000e6aa  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18000e6af  mov     eax, [rdi]
0x18000e6b1  mov     rbx, [rsp+38h+arg_8]
0x18000e6b6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e6bb  mov     edx, eax
0x18000e6bd  mov     [rdi], eax
0x18000e6bf  mov     ecx, eax
0x18000e6c1  jz      short loc_18000E6DC
0x18000e6c3  test    dl, 2
0x18000e6c6  jnz     short loc_18000E6DC
0x18000e6c8  and     ecx, 0FFFFF63Eh
0x18000e6ce  mov     eax, ebx
0x18000e6d0  and     eax, 9C1h
0x18000e6d5  or      ecx, eax
0x18000e6d7  or      ecx, 2
0x18000e6da  mov     [rdi], ecx
0x18000e6dc  mov     r8d, edx
0x18000e6df  and     r8d, 4
0x18000e6e3  jnz     short loc_18000E6F7
0x18000e6e5  btr     ecx, 0Ah
0x18000e6e9  mov     eax, ebx
0x18000e6eb  and     eax, 400h
0x18000e6f0  or      ecx, eax
0x18000e6f2  or      ecx, 4
0x18000e6f5  mov     [rdi], ecx
0x18000e6f7  mov     eax, edx
0x18000e6f9  lock cmpxchg [rsi], ecx
0x18000e6fd  jnz     short loc_18000E6B6
0x18000e6ff  test    r8d, r8d
0x18000e702  jnz     short loc_18000E714
0x18000e704  mov     r8d, ebp
0x18000e707  mov     edx, 3
0x18000e70c  mov     rcx, rsi
0x18000e70f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e714  mov     eax, [rdi]
0x18000e716  test    al, 2
0x18000e718  jnz     short loc_18000E729
0x18000e71a  and     eax, 0FFFFF63Eh
0x18000e71f  and     ebx, 9C1h
0x18000e725  or      eax, ebx
0x18000e727  mov     [rdi], eax
0x18000e729  mov     rbx, [rsp+38h+arg_10]
0x18000e72e  mov     rax, rdi
0x18000e731  add     rsp, 20h
0x18000e735  pop     rdi
0x18000e736  pop     rsi
0x18000e737  pop     rbp
0x18000e738  retn
```
