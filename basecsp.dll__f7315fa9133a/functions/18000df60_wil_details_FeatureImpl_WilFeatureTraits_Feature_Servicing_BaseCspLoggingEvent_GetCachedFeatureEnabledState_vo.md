# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent>::GetCachedFeatureEnabledState(void)

- ea: `0x18000df60`
- end: `0x18000e039`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `217`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180015bd8`
- `0x18001866c`

## callees

- `0x18000d7e0`
- `0x18000df60`
- `0x18000ed80`
- `0x1800170d0`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_BaseCspLoggingEvent__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_BaseCspLoggingEvent__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v13) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent>::GetCurrentFeatureEnabledState(
      v6,
      &v14,
      &v13);
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_BaseCspLoggingEvent__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( (v10 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        (volatile signed __int32 *)Feature_Servicing_BaseCspLoggingEvent__descriptor,
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
0x18000df60  mov     [rsp+arg_10], rbx
0x18000df65  mov     [rsp+arg_0], rcx
0x18000df6a  push    rbp
0x18000df6b  push    rsi
0x18000df6c  push    rdi
0x18000df6d  sub     rsp, 20h
0x18000df71  mov     rsi, cs:Feature_Servicing_BaseCspLoggingEvent__descriptor
0x18000df78  mov     rdi, rdx
0x18000df7b  mov     qword ptr [rdx], 0
0x18000df82  mov     eax, [rsi]
0x18000df84  mov     [rdx], eax
0x18000df86  and     eax, 6
0x18000df89  cmp     al, 6
0x18000df8b  jz      loc_18000E029
0x18000df91  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000df96  lea     r8, [rsp+38h+arg_0]
0x18000df9b  mov     dword ptr [rsp+38h+arg_0], 0
0x18000dfa3  lea     rdx, [rsp+38h+arg_8]
0x18000dfa8  mov     ebp, eax
0x18000dfaa  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_BaseCspLoggingEvent>::GetCurrentFeatureEnabledState(int *)
0x18000dfaf  mov     eax, [rdi]
0x18000dfb1  mov     rbx, [rsp+38h+arg_8]
0x18000dfb6  cmp     dword ptr [rsp+38h+arg_0], 0
0x18000dfbb  mov     edx, eax
0x18000dfbd  mov     [rdi], eax
0x18000dfbf  mov     ecx, eax
0x18000dfc1  jz      short loc_18000DFDC
0x18000dfc3  test    dl, 2
0x18000dfc6  jnz     short loc_18000DFDC
0x18000dfc8  and     ecx, 0FFFFF63Eh
0x18000dfce  mov     eax, ebx
0x18000dfd0  and     eax, 9C1h
0x18000dfd5  or      ecx, eax
0x18000dfd7  or      ecx, 2
0x18000dfda  mov     [rdi], ecx
0x18000dfdc  mov     r8d, edx
0x18000dfdf  and     r8d, 4
0x18000dfe3  jnz     short loc_18000DFF7
0x18000dfe5  btr     ecx, 0Ah
0x18000dfe9  mov     eax, ebx
0x18000dfeb  and     eax, 400h
0x18000dff0  or      ecx, eax
0x18000dff2  or      ecx, 4
0x18000dff5  mov     [rdi], ecx
0x18000dff7  mov     eax, edx
0x18000dff9  lock cmpxchg [rsi], ecx
0x18000dffd  jnz     short loc_18000DFB6
0x18000dfff  test    r8d, r8d
0x18000e002  jnz     short loc_18000E014
0x18000e004  mov     r8d, ebp
0x18000e007  mov     edx, 3
0x18000e00c  mov     rcx, rsi
0x18000e00f  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000e014  mov     eax, [rdi]
0x18000e016  test    al, 2
0x18000e018  jnz     short loc_18000E029
0x18000e01a  and     eax, 0FFFFF63Eh
0x18000e01f  and     ebx, 9C1h
0x18000e025  or      eax, ebx
0x18000e027  mov     [rdi], eax
0x18000e029  mov     rbx, [rsp+38h+arg_10]
0x18000e02e  mov     rax, rdi
0x18000e031  add     rsp, 20h
0x18000e035  pop     rdi
0x18000e036  pop     rsi
0x18000e037  pop     rbp
0x18000e038  retn
```
