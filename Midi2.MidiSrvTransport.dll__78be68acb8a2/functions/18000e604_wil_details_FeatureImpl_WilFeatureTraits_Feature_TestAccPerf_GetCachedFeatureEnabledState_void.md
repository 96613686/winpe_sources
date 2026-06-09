# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x18000e604`
- end: `0x18000e6dd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011458`

## callees

- `0x18000da08`
- `0x18000e604`
- `0x18000eca4`
- `0x180010c28`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_TestAccPerf__descriptor,
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
0x18000e604  mov     [rsp+arg_10], rbx
0x18000e609  mov     [rsp+arg_0], rcx
0x18000e60e  push    rbp
0x18000e60f  push    rsi
0x18000e610  push    rdi
0x18000e611  sub     rsp, 20h
0x18000e615  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x18000e61c  mov     rdi, rdx
0x18000e61f  mov     qword ptr [rdx], 0
0x18000e626  mov     eax, [rsi]
0x18000e628  mov     [rdx], eax
0x18000e62a  and     eax, 6
0x18000e62d  cmp     al, 6
0x18000e62f  jz      loc_18000E6CD
0x18000e635  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000e63a  lea     r8, [rsp+38h+arg_0]
0x18000e63f  mov     dword ptr [rsp+38h+arg_0], 0
0x18000e647  lea     rdx, [rsp+38h+arg_8]
0x18000e64c  mov     ebp, eax
0x18000e64e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x18000e653  mov     eax, [rdi]
0x18000e655  mov     rbx, [rsp+38h+arg_8]
0x18000e65a  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000e65f  mov     edx, eax
0x18000e661  mov     [rdi], eax
0x18000e663  mov     ecx, eax
0x18000e665  jz      short loc_18000E680
0x18000e667  test    dl, 2
0x18000e66a  jnz     short loc_18000E680
0x18000e66c  and     ecx, 0FFFFF63Eh
0x18000e672  mov     eax, ebx
0x18000e674  and     eax, 9C1h
0x18000e679  or      ecx, eax
0x18000e67b  or      ecx, 2
0x18000e67e  mov     [rdi], ecx
0x18000e680  mov     r8d, edx
0x18000e683  and     r8d, 4
0x18000e687  jnz     short loc_18000E69B
0x18000e689  btr     ecx, 0Ah
0x18000e68d  mov     eax, ebx
0x18000e68f  and     eax, 400h
0x18000e694  or      ecx, eax
0x18000e696  or      ecx, 4
0x18000e699  mov     [rdi], ecx
0x18000e69b  mov     eax, edx
0x18000e69d  lock cmpxchg [rsi], ecx
0x18000e6a1  jnz     short loc_18000E65A
0x18000e6a3  test    r8d, r8d
0x18000e6a6  jnz     short loc_18000E6B8
0x18000e6a8  mov     r8d, ebp
0x18000e6ab  mov     edx, 3
0x18000e6b0  mov     rcx, rsi
0x18000e6b3  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e6b8  mov     eax, [rdi]
0x18000e6ba  test    al, 2
0x18000e6bc  jnz     short loc_18000E6CD
0x18000e6be  and     eax, 0FFFFF63Eh
0x18000e6c3  and     ebx, 9C1h
0x18000e6c9  or      eax, ebx
0x18000e6cb  mov     [rdi], eax
0x18000e6cd  mov     rbx, [rsp+38h+arg_10]
0x18000e6d2  mov     rax, rdi
0x18000e6d5  add     rsp, 20h
0x18000e6d9  pop     rdi
0x18000e6da  pop     rsi
0x18000e6db  pop     rbp
0x18000e6dc  retn
```
