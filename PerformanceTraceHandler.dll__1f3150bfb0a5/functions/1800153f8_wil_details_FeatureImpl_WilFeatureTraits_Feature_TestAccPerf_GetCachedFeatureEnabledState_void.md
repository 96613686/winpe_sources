# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x1800153f8`
- end: `0x1800154d1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180017450`
- `0x180017d5c`

## callees

- `0x18000543c`
- `0x180008794`
- `0x1800153f8`
- `0x180015c7c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(Feature_TestAccPerf__descriptor, 3, v5);
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x1800153f8  mov     [rsp+arg_10], rbx
0x1800153fd  mov     [rsp+arg_0], rcx
0x180015402  push    rbp
0x180015403  push    rsi
0x180015404  push    rdi
0x180015405  sub     rsp, 20h
0x180015409  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x180015410  mov     rdi, rdx
0x180015413  mov     qword ptr [rdx], 0
0x18001541a  mov     eax, [rsi]
0x18001541c  mov     [rdx], eax
0x18001541e  and     eax, 6
0x180015421  cmp     al, 6
0x180015423  jz      loc_1800154C1
0x180015429  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001542e  lea     r8, [rsp+38h+arg_0]
0x180015433  mov     dword ptr [rsp+38h+arg_0], 0
0x18001543b  lea     rdx, [rsp+38h+arg_8]
0x180015440  mov     ebp, eax
0x180015442  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x180015447  mov     eax, [rdi]
0x180015449  mov     rbx, [rsp+38h+arg_8]
0x18001544e  cmp     dword ptr [rsp+38h+arg_0], 0
0x180015453  mov     edx, eax
0x180015455  mov     [rdi], eax
0x180015457  mov     ecx, eax
0x180015459  jz      short loc_180015474
0x18001545b  test    dl, 2
0x18001545e  jnz     short loc_180015474
0x180015460  and     ecx, 0FFFFF63Eh
0x180015466  mov     eax, ebx
0x180015468  and     eax, 9C1h
0x18001546d  or      ecx, eax
0x18001546f  or      ecx, 2
0x180015472  mov     [rdi], ecx
0x180015474  mov     r8d, edx
0x180015477  and     r8d, 4
0x18001547b  jnz     short loc_18001548F
0x18001547d  btr     ecx, 0Ah
0x180015481  mov     eax, ebx
0x180015483  and     eax, 400h
0x180015488  or      ecx, eax
0x18001548a  or      ecx, 4
0x18001548d  mov     [rdi], ecx
0x18001548f  mov     eax, edx
0x180015491  lock cmpxchg [rsi], ecx
0x180015495  jnz     short loc_18001544E
0x180015497  test    r8d, r8d
0x18001549a  jnz     short loc_1800154AC
0x18001549c  mov     r8d, ebp
0x18001549f  mov     edx, 3
0x1800154a4  mov     rcx, rsi
0x1800154a7  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x1800154ac  mov     eax, [rdi]
0x1800154ae  test    al, 2
0x1800154b0  jnz     short loc_1800154C1
0x1800154b2  and     eax, 0FFFFF63Eh
0x1800154b7  and     ebx, 9C1h
0x1800154bd  or      eax, ebx
0x1800154bf  mov     [rdi], eax
0x1800154c1  mov     rbx, [rsp+38h+arg_10]
0x1800154c6  mov     rax, rdi
0x1800154c9  add     rsp, 20h
0x1800154cd  pop     rdi
0x1800154ce  pop     rsi
0x1800154cf  pop     rbp
0x1800154d0  retn
```
