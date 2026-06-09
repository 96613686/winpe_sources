# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x18000fe00`
- end: `0x18000fed9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011e28`

## callees

- `0x18000ee50`
- `0x18000fe00`
- `0x180010790`
- `0x180011648`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_ValAccTest__descriptor,
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
0x18000fe00  mov     [rsp+arg_10], rbx
0x18000fe05  mov     [rsp+arg_0], rcx
0x18000fe0a  push    rbp
0x18000fe0b  push    rsi
0x18000fe0c  push    rdi
0x18000fe0d  sub     rsp, 20h
0x18000fe11  mov     rsi, cs:Feature_ValAccTest__descriptor
0x18000fe18  mov     rdi, rdx
0x18000fe1b  mov     qword ptr [rdx], 0
0x18000fe22  mov     eax, [rsi]
0x18000fe24  mov     [rdx], eax
0x18000fe26  and     eax, 6
0x18000fe29  cmp     al, 6
0x18000fe2b  jz      loc_18000FEC9
0x18000fe31  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000fe36  lea     r8, [rsp+38h+arg_0]
0x18000fe3b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000fe43  lea     rdx, [rsp+38h+arg_8]
0x18000fe48  mov     ebp, eax
0x18000fe4a  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x18000fe4f  mov     eax, [rdi]
0x18000fe51  mov     rbx, [rsp+38h+arg_8]
0x18000fe56  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000fe5b  mov     edx, eax
0x18000fe5d  mov     [rdi], eax
0x18000fe5f  mov     ecx, eax
0x18000fe61  jz      short loc_18000FE7C
0x18000fe63  test    dl, 2
0x18000fe66  jnz     short loc_18000FE7C
0x18000fe68  and     ecx, 0FFFFF63Eh
0x18000fe6e  mov     eax, ebx
0x18000fe70  and     eax, 9C1h
0x18000fe75  or      ecx, eax
0x18000fe77  or      ecx, 2
0x18000fe7a  mov     [rdi], ecx
0x18000fe7c  mov     r8d, edx
0x18000fe7f  and     r8d, 4
0x18000fe83  jnz     short loc_18000FE97
0x18000fe85  btr     ecx, 0Ah
0x18000fe89  mov     eax, ebx
0x18000fe8b  and     eax, 400h
0x18000fe90  or      ecx, eax
0x18000fe92  or      ecx, 4
0x18000fe95  mov     [rdi], ecx
0x18000fe97  mov     eax, edx
0x18000fe99  lock cmpxchg [rsi], ecx
0x18000fe9d  jnz     short loc_18000FE56
0x18000fe9f  test    r8d, r8d
0x18000fea2  jnz     short loc_18000FEB4
0x18000fea4  mov     r8d, ebp
0x18000fea7  mov     edx, 3
0x18000feac  mov     rcx, rsi
0x18000feaf  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000feb4  mov     eax, [rdi]
0x18000feb6  test    al, 2
0x18000feb8  jnz     short loc_18000FEC9
0x18000feba  and     eax, 0FFFFF63Eh
0x18000febf  and     ebx, 9C1h
0x18000fec5  or      eax, ebx
0x18000fec7  mov     [rdi], eax
0x18000fec9  mov     rbx, [rsp+38h+arg_10]
0x18000fece  mov     rax, rdi
0x18000fed1  add     rsp, 20h
0x18000fed5  pop     rdi
0x18000fed6  pop     rsi
0x18000fed7  pop     rbp
0x18000fed8  retn
```
