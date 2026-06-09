# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::GetCachedFeatureEnabledState(void)

- ea: `0x18001ad9c`
- end: `0x18001ae75`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2511@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c17c`
- `0x18001c7f8`

## callees

- `0x18001403c`
- `0x180016068`
- `0x18001ad9c`
- `0x18001b81c`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_MediaQI2511__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MediaQI2511__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::GetCurrentFeatureEnabledState(v6, &v14, &v13);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MediaQI2511__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_MediaQI2511__descriptor,
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
0x18001ad9c  mov     [rsp+arg_10], rbx
0x18001ada1  mov     [rsp+arg_0], rcx
0x18001ada6  push    rbp
0x18001ada7  push    rsi
0x18001ada8  push    rdi
0x18001ada9  sub     rsp, 20h
0x18001adad  mov     rsi, cs:Feature_MediaQI2511__descriptor
0x18001adb4  mov     rdi, rdx
0x18001adb7  mov     qword ptr [rdx], 0
0x18001adbe  mov     eax, [rsi]
0x18001adc0  mov     [rdx], eax
0x18001adc2  and     eax, 6
0x18001adc5  cmp     al, 6
0x18001adc7  jz      loc_18001AE65
0x18001adcd  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18001add2  lea     r8, [rsp+38h+arg_0]
0x18001add7  mov     dword ptr [rsp+38h+arg_0], 0
0x18001addf  lea     rdx, [rsp+38h+arg_8]
0x18001ade4  mov     ebp, eax
0x18001ade6  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MediaQI2511@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MediaQI2511>::GetCurrentFeatureEnabledState(int *)
0x18001adeb  mov     eax, [rdi]
0x18001aded  mov     rbx, [rsp+38h+arg_8]
0x18001adf2  cmp     dword ptr [rsp+38h+arg_0], 0
0x18001adf7  mov     edx, eax
0x18001adf9  mov     [rdi], eax
0x18001adfb  mov     ecx, eax
0x18001adfd  jz      short loc_18001AE18
0x18001adff  test    dl, 2
0x18001ae02  jnz     short loc_18001AE18
0x18001ae04  and     ecx, 0FFFFF63Eh
0x18001ae0a  mov     eax, ebx
0x18001ae0c  and     eax, 9C1h
0x18001ae11  or      ecx, eax
0x18001ae13  or      ecx, 2
0x18001ae16  mov     [rdi], ecx
0x18001ae18  mov     r8d, edx
0x18001ae1b  and     r8d, 4
0x18001ae1f  jnz     short loc_18001AE33
0x18001ae21  btr     ecx, 0Ah
0x18001ae25  mov     eax, ebx
0x18001ae27  and     eax, 400h
0x18001ae2c  or      ecx, eax
0x18001ae2e  or      ecx, 4
0x18001ae31  mov     [rdi], ecx
0x18001ae33  mov     eax, edx
0x18001ae35  lock cmpxchg [rsi], ecx
0x18001ae39  jnz     short loc_18001ADF2
0x18001ae3b  test    r8d, r8d
0x18001ae3e  jnz     short loc_18001AE50
0x18001ae40  mov     r8d, ebp
0x18001ae43  mov     edx, 3
0x18001ae48  mov     rcx, rsi
0x18001ae4b  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18001ae50  mov     eax, [rdi]
0x18001ae52  test    al, 2
0x18001ae54  jnz     short loc_18001AE65
0x18001ae56  and     eax, 0FFFFF63Eh
0x18001ae5b  and     ebx, 9C1h
0x18001ae61  or      eax, ebx
0x18001ae63  mov     [rdi], eax
0x18001ae65  mov     rbx, [rsp+38h+arg_10]
0x18001ae6a  mov     rax, rdi
0x18001ae6d  add     rsp, 20h
0x18001ae71  pop     rdi
0x18001ae72  pop     rsi
0x18001ae73  pop     rbp
0x18001ae74  retn
```
