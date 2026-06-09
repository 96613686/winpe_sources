# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x1800213d0`
- end: `0x1800214a9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180025574`
- `0x180028ad8`

## callees

- `0x180019930`
- `0x18001a080`
- `0x1800213d0`
- `0x180021ef4`

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
0x1800213d0  mov     [rsp+arg_10], rbx
0x1800213d5  mov     [rsp+arg_0], rcx
0x1800213da  push    rbp
0x1800213db  push    rsi
0x1800213dc  push    rdi
0x1800213dd  sub     rsp, 20h
0x1800213e1  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x1800213e8  mov     rdi, rdx
0x1800213eb  mov     qword ptr [rdx], 0
0x1800213f2  mov     eax, [rsi]
0x1800213f4  mov     [rdx], eax
0x1800213f6  and     eax, 6
0x1800213f9  cmp     al, 6
0x1800213fb  jz      loc_180021499
0x180021401  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180021406  lea     r8, [rsp+38h+arg_0]
0x18002140b  mov     dword ptr [rsp+38h+arg_0], 0
0x180021413  lea     rdx, [rsp+38h+arg_8]
0x180021418  mov     ebp, eax
0x18002141a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18002141f  mov     eax, [rdi]
0x180021421  mov     rbx, [rsp+38h+arg_8]
0x180021426  cmp     dword ptr [rsp+38h+arg_0], 0
0x18002142b  mov     edx, eax
0x18002142d  mov     [rdi], eax
0x18002142f  mov     ecx, eax
0x180021431  jz      short loc_18002144C
0x180021433  test    dl, 2
0x180021436  jnz     short loc_18002144C
0x180021438  and     ecx, 0FFFFF63Eh
0x18002143e  mov     eax, ebx
0x180021440  and     eax, 9C1h
0x180021445  or      ecx, eax
0x180021447  or      ecx, 2
0x18002144a  mov     [rdi], ecx
0x18002144c  mov     r8d, edx
0x18002144f  and     r8d, 4
0x180021453  jnz     short loc_180021467
0x180021455  btr     ecx, 0Ah
0x180021459  mov     eax, ebx
0x18002145b  and     eax, 400h
0x180021460  or      ecx, eax
0x180021462  or      ecx, 4
0x180021465  mov     [rdi], ecx
0x180021467  mov     eax, edx
0x180021469  lock cmpxchg [rsi], ecx
0x18002146d  jnz     short loc_180021426
0x18002146f  test    r8d, r8d
0x180021472  jnz     short loc_180021484
0x180021474  mov     r8d, ebp
0x180021477  mov     edx, 3
0x18002147c  mov     rcx, rsi
0x18002147f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180021484  mov     eax, [rdi]
0x180021486  test    al, 2
0x180021488  jnz     short loc_180021499
0x18002148a  and     eax, 0FFFFF63Eh
0x18002148f  and     ebx, 9C1h
0x180021495  or      eax, ebx
0x180021497  mov     [rdi], eax
0x180021499  mov     rbx, [rsp+38h+arg_10]
0x18002149e  mov     rax, rdi
0x1800214a1  add     rsp, 20h
0x1800214a5  pop     rdi
0x1800214a6  pop     rsi
0x1800214a7  pop     rbp
0x1800214a8  retn
```
