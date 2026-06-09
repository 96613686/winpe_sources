# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x140005554`
- end: `0x14000562d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000b674`

## callees

- `0x1400049e0`
- `0x140005554`
- `0x140005b90`
- `0x14000a88c`

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
0x140005554  mov     [rsp+arg_10], rbx
0x140005559  mov     [rsp+arg_0], rcx
0x14000555e  push    rbp
0x14000555f  push    rsi
0x140005560  push    rdi
0x140005561  sub     rsp, 20h
0x140005565  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x14000556c  mov     rdi, rdx
0x14000556f  mov     qword ptr [rdx], 0
0x140005576  mov     eax, [rsi]
0x140005578  mov     [rdx], eax
0x14000557a  and     eax, 6
0x14000557d  cmp     al, 6
0x14000557f  jz      loc_14000561D
0x140005585  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000558a  lea     r8, [rsp+38h+arg_0]
0x14000558f  mov     dword ptr [rsp+38h+arg_0], 0
0x140005597  lea     rdx, [rsp+38h+arg_8]
0x14000559c  mov     ebp, eax
0x14000559e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x1400055a3  mov     eax, [rdi]
0x1400055a5  mov     rbx, [rsp+38h+arg_8]
0x1400055aa  cmp     dword ptr [rsp+38h+arg_0], 0
0x1400055af  mov     edx, eax
0x1400055b1  mov     [rdi], eax
0x1400055b3  mov     ecx, eax
0x1400055b5  jz      short loc_1400055D0
0x1400055b7  test    dl, 2
0x1400055ba  jnz     short loc_1400055D0
0x1400055bc  and     ecx, 0FFFFF63Eh
0x1400055c2  mov     eax, ebx
0x1400055c4  and     eax, 9C1h
0x1400055c9  or      ecx, eax
0x1400055cb  or      ecx, 2
0x1400055ce  mov     [rdi], ecx
0x1400055d0  mov     r8d, edx
0x1400055d3  and     r8d, 4
0x1400055d7  jnz     short loc_1400055EB
0x1400055d9  btr     ecx, 0Ah
0x1400055dd  mov     eax, ebx
0x1400055df  and     eax, 400h
0x1400055e4  or      ecx, eax
0x1400055e6  or      ecx, 4
0x1400055e9  mov     [rdi], ecx
0x1400055eb  mov     eax, edx
0x1400055ed  lock cmpxchg [rsi], ecx
0x1400055f1  jnz     short loc_1400055AA
0x1400055f3  test    r8d, r8d
0x1400055f6  jnz     short loc_140005608
0x1400055f8  mov     r8d, ebp
0x1400055fb  mov     edx, 3
0x140005600  mov     rcx, rsi
0x140005603  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x140005608  mov     eax, [rdi]
0x14000560a  test    al, 2
0x14000560c  jnz     short loc_14000561D
0x14000560e  and     eax, 0FFFFF63Eh
0x140005613  and     ebx, 9C1h
0x140005619  or      eax, ebx
0x14000561b  mov     [rdi], eax
0x14000561d  mov     rbx, [rsp+38h+arg_10]
0x140005622  mov     rax, rdi
0x140005625  add     rsp, 20h
0x140005629  pop     rdi
0x14000562a  pop     rsi
0x14000562b  pop     rbp
0x14000562c  retn
```
