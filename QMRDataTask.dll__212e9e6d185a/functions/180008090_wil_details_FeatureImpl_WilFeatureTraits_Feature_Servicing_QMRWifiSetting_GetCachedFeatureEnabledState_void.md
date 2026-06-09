# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting>::GetCachedFeatureEnabledState(void)

- ea: `0x180008090`
- end: `0x180008169`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRWifiSetting@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800118e0`

## callees

- `0x18000787c`
- `0x180008090`
- `0x180008f18`
- `0x180010684`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_QMRWifiSetting__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_QMRWifiSetting__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting>::GetCurrentFeatureEnabledState(
      v5,
      &v11);
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
      v6 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Servicing_QMRWifiSetting__descriptor, v9, v6);
    }
    while ( v8 != v6 );
    if ( (v8 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Servicing_QMRWifiSetting__descriptor,
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
0x180008090  mov     [rsp+arg_10], rbx
0x180008095  mov     [rsp+arg_0], rcx
0x18000809a  push    rbp
0x18000809b  push    rsi
0x18000809c  push    rdi
0x18000809d  sub     rsp, 20h
0x1800080a1  mov     rsi, cs:Feature_Servicing_QMRWifiSetting__descriptor
0x1800080a8  mov     rdi, rdx
0x1800080ab  mov     qword ptr [rdx], 0
0x1800080b2  mov     eax, [rsi]
0x1800080b4  mov     [rdx], eax
0x1800080b6  and     eax, 6
0x1800080b9  cmp     al, 6
0x1800080bb  jz      loc_180008159
0x1800080c1  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800080c6  lea     r8, [rsp+38h+arg_0]
0x1800080cb  mov     dword ptr [rsp+38h+arg_0], 0
0x1800080d3  lea     rdx, [rsp+38h+arg_8]
0x1800080d8  mov     ebp, eax
0x1800080da  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_QMRWifiSetting@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_QMRWifiSetting>::GetCurrentFeatureEnabledState(int *)
0x1800080df  mov     eax, [rdi]
0x1800080e1  mov     rbx, [rsp+38h+arg_8]
0x1800080e6  cmp     dword ptr [rsp+38h+arg_0], 0
0x1800080eb  mov     edx, eax
0x1800080ed  mov     [rdi], eax
0x1800080ef  mov     ecx, eax
0x1800080f1  jz      short loc_18000810C
0x1800080f3  test    dl, 2
0x1800080f6  jnz     short loc_18000810C
0x1800080f8  and     ecx, 0FFFFF63Eh
0x1800080fe  mov     eax, ebx
0x180008100  and     eax, 9C1h
0x180008105  or      ecx, eax
0x180008107  or      ecx, 2
0x18000810a  mov     [rdi], ecx
0x18000810c  mov     r8d, edx
0x18000810f  and     r8d, 4
0x180008113  jnz     short loc_180008127
0x180008115  btr     ecx, 0Ah
0x180008119  mov     eax, ebx
0x18000811b  and     eax, 400h
0x180008120  or      ecx, eax
0x180008122  or      ecx, 4
0x180008125  mov     [rdi], ecx
0x180008127  mov     eax, edx
0x180008129  lock cmpxchg [rsi], ecx
0x18000812d  jnz     short loc_1800080E6
0x18000812f  test    r8d, r8d
0x180008132  jnz     short loc_180008144
0x180008134  mov     r8d, ebp
0x180008137  mov     edx, 3
0x18000813c  mov     rcx, rsi
0x18000813f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180008144  mov     eax, [rdi]
0x180008146  test    al, 2
0x180008148  jnz     short loc_180008159
0x18000814a  and     eax, 0FFFFF63Eh
0x18000814f  and     ebx, 9C1h
0x180008155  or      eax, ebx
0x180008157  mov     [rdi], eax
0x180008159  mov     rbx, [rsp+38h+arg_10]
0x18000815e  mov     rax, rdi
0x180008161  add     rsp, 20h
0x180008165  pop     rdi
0x180008166  pop     rsi
0x180008167  pop     rbp
0x180008168  retn
```
