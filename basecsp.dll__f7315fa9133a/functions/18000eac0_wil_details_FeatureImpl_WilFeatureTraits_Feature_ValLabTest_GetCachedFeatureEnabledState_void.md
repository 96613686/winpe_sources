# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000eac0`
- end: `0x18000eb99`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800162ac`

## callees

- `0x18000d7e0`
- `0x18000eac0`
- `0x18000f6ac`
- `0x1800170d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValLabTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValLabTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValLabTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValLabTest__descriptor,
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
0x18000eac0  mov     [rsp+arg_10], rbx
0x18000eac5  mov     [rsp+arg_0], rcx
0x18000eaca  push    rbp
0x18000eacb  push    rsi
0x18000eacc  push    rdi
0x18000eacd  sub     rsp, 20h
0x18000ead1  mov     rsi, cs:Feature_ValLabTest__descriptor
0x18000ead8  mov     rdi, rdx
0x18000eadb  mov     qword ptr [rdx], 0
0x18000eae2  mov     eax, [rsi]
0x18000eae4  mov     [rdx], eax
0x18000eae6  and     eax, 6
0x18000eae9  cmp     al, 6
0x18000eaeb  jz      loc_18000EB89
0x18000eaf1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000eaf6  lea     r8, [rsp+38h+arg_0]
0x18000eafb  mov     dword ptr [rsp+38h+arg_0], 0
0x18000eb03  lea     rdx, [rsp+38h+arg_8]
0x18000eb08  mov     ebp, eax
0x18000eb0a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValLabTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValLabTest>::GetCurrentFeatureEnabledState(int *)
0x18000eb0f  mov     eax, [rdi]
0x18000eb11  mov     rbx, [rsp+38h+arg_8]
0x18000eb16  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000eb1b  mov     edx, eax
0x18000eb1d  mov     [rdi], eax
0x18000eb1f  mov     ecx, eax
0x18000eb21  jz      short loc_18000EB3C
0x18000eb23  test    dl, 2
0x18000eb26  jnz     short loc_18000EB3C
0x18000eb28  and     ecx, 0FFFFF63Eh
0x18000eb2e  mov     eax, ebx
0x18000eb30  and     eax, 9C1h
0x18000eb35  or      ecx, eax
0x18000eb37  or      ecx, 2
0x18000eb3a  mov     [rdi], ecx
0x18000eb3c  mov     r8d, edx
0x18000eb3f  and     r8d, 4
0x18000eb43  jnz     short loc_18000EB57
0x18000eb45  btr     ecx, 0Ah
0x18000eb49  mov     eax, ebx
0x18000eb4b  and     eax, 400h
0x18000eb50  or      ecx, eax
0x18000eb52  or      ecx, 4
0x18000eb55  mov     [rdi], ecx
0x18000eb57  mov     eax, edx
0x18000eb59  lock cmpxchg [rsi], ecx
0x18000eb5d  jnz     short loc_18000EB16
0x18000eb5f  test    r8d, r8d
0x18000eb62  jnz     short loc_18000EB74
0x18000eb64  mov     r8d, ebp
0x18000eb67  mov     edx, 3
0x18000eb6c  mov     rcx, rsi
0x18000eb6f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000eb74  mov     eax, [rdi]
0x18000eb76  test    al, 2
0x18000eb78  jnz     short loc_18000EB89
0x18000eb7a  and     eax, 0FFFFF63Eh
0x18000eb7f  and     ebx, 9C1h
0x18000eb85  or      eax, ebx
0x18000eb87  mov     [rdi], eax
0x18000eb89  mov     rbx, [rsp+38h+arg_10]
0x18000eb8e  mov     rax, rdi
0x18000eb91  add     rsp, 20h
0x18000eb95  pop     rdi
0x18000eb96  pop     rsi
0x18000eb97  pop     rbp
0x18000eb98  retn
```
