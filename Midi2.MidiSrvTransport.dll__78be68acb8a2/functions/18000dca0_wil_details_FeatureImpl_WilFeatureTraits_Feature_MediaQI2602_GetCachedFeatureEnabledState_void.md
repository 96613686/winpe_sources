# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCachedFeatureEnabledState(void)

- ea: `0x18000dca0`
- end: `0x18000dd79`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011280`

## callees

- `0x18000da08`
- `0x18000dca0`
- `0x18000ea24`
- `0x180010c28`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_MediaQI2602__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MediaQI2602__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCurrentFeatureEnabledState(v5, &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MediaQI2602__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_MediaQI2602__descriptor,
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
0x18000dca0  mov     [rsp+arg_10], rbx
0x18000dca5  mov     [rsp+arg_0], rcx
0x18000dcaa  push    rbp
0x18000dcab  push    rsi
0x18000dcac  push    rdi
0x18000dcad  sub     rsp, 20h
0x18000dcb1  mov     rsi, cs:Feature_MediaQI2602__descriptor
0x18000dcb8  mov     rdi, rdx
0x18000dcbb  mov     qword ptr [rdx], 0
0x18000dcc2  mov     eax, [rsi]
0x18000dcc4  mov     [rdx], eax
0x18000dcc6  and     eax, 6
0x18000dcc9  cmp     al, 6
0x18000dccb  jz      loc_18000DD69
0x18000dcd1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000dcd6  lea     r8, [rsp+38h+arg_0]
0x18000dcdb  mov     dword ptr [rsp+38h+arg_0], 0
0x18000dce3  lea     rdx, [rsp+38h+arg_8]
0x18000dce8  mov     ebp, eax
0x18000dcea  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2602@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2602>::GetCurrentFeatureEnabledState(int *)
0x18000dcef  mov     eax, [rdi]
0x18000dcf1  mov     rbx, [rsp+38h+arg_8]
0x18000dcf6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000dcfb  mov     edx, eax
0x18000dcfd  mov     [rdi], eax
0x18000dcff  mov     ecx, eax
0x18000dd01  jz      short loc_18000DD1C
0x18000dd03  test    dl, 2
0x18000dd06  jnz     short loc_18000DD1C
0x18000dd08  and     ecx, 0FFFFF63Eh
0x18000dd0e  mov     eax, ebx
0x18000dd10  and     eax, 9C1h
0x18000dd15  or      ecx, eax
0x18000dd17  or      ecx, 2
0x18000dd1a  mov     [rdi], ecx
0x18000dd1c  mov     r8d, edx
0x18000dd1f  and     r8d, 4
0x18000dd23  jnz     short loc_18000DD37
0x18000dd25  btr     ecx, 0Ah
0x18000dd29  mov     eax, ebx
0x18000dd2b  and     eax, 400h
0x18000dd30  or      ecx, eax
0x18000dd32  or      ecx, 4
0x18000dd35  mov     [rdi], ecx
0x18000dd37  mov     eax, edx
0x18000dd39  lock cmpxchg [rsi], ecx
0x18000dd3d  jnz     short loc_18000DCF6
0x18000dd3f  test    r8d, r8d
0x18000dd42  jnz     short loc_18000DD54
0x18000dd44  mov     r8d, ebp
0x18000dd47  mov     edx, 3
0x18000dd4c  mov     rcx, rsi
0x18000dd4f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000dd54  mov     eax, [rdi]
0x18000dd56  test    al, 2
0x18000dd58  jnz     short loc_18000DD69
0x18000dd5a  and     eax, 0FFFFF63Eh
0x18000dd5f  and     ebx, 9C1h
0x18000dd65  or      eax, ebx
0x18000dd67  mov     [rdi], eax
0x18000dd69  mov     rbx, [rsp+38h+arg_10]
0x18000dd6e  mov     rax, rdi
0x18000dd71  add     rsp, 20h
0x18000dd75  pop     rdi
0x18000dd76  pop     rsi
0x18000dd77  pop     rbp
0x18000dd78  retn
```
