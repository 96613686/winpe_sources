# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::GetCachedFeatureEnabledState(void)

- ea: `0x180005054`
- end: `0x18000513f`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `235`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800085a8`
- `0x18000ac14`

## callees

- `0x1800049e4`
- `0x180005054`
- `0x180005430`
- `0x180009528`
- `0x18000c610`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // ebp
  __int64 v5; // rcx
  signed __int32 v6; // eax
  __int16 v7; // bx
  bool v8; // zf
  signed __int32 v9; // edx
  unsigned int v10; // ecx
  __int64 v12; // [rsp+20h] [rbp-48h] BYREF
  int v13; // [rsp+28h] [rbp-40h] BYREF

  *a2 = 0;
  v3 = *(_DWORD *)Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::GetCurrentFeatureEnabledState(
      v5,
      &v12,
      &v13);
    v6 = *(_DWORD *)a2;
    v7 = v12;
    do
    {
      v8 = v13 == 0;
      v9 = v6;
      *(_DWORD *)a2 = v6;
      v10 = v6;
      if ( !v8 && (v6 & 2) == 0 )
      {
        v10 = v7 & 0x9C1 | v6 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v10;
      }
      if ( (v6 & 4) == 0 )
      {
        v10 = v7 & 0x400 | v10 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v10;
      }
      v6 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask__descriptor,
             v10,
             v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask__descriptor,
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
0x180005054  push    rbx
0x180005056  push    rbp
0x180005057  push    rsi
0x180005058  push    rdi
0x180005059  sub     rsp, 48h
0x18000505d  mov     rax, cs:__security_cookie
0x180005064  xor     rax, rsp
0x180005067  mov     [rsp+68h+var_38], rax
0x18000506c  mov     rsi, cs:Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask__descriptor
0x180005073  mov     rdi, rdx
0x180005076  mov     qword ptr [rdx], 0
0x18000507d  mov     eax, [rsi]
0x18000507f  mov     [rdx], eax
0x180005081  and     eax, 6
0x180005084  cmp     al, 6
0x180005086  jz      loc_180005126
0x18000508c  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180005091  lea     r8, [rsp+68h+var_40]
0x180005096  mov     [rsp+68h+var_40], 0
0x18000509e  lea     rdx, [rsp+68h+var_48]
0x1800050a3  mov     ebp, eax
0x1800050a5  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RecoveryRobustness_SetupRecoveryDataTask>::GetCurrentFeatureEnabledState(int *)
0x1800050aa  mov     eax, [rdi]
0x1800050ac  mov     rbx, [rsp+68h+var_48]
0x1800050b1  cmp     [rsp+68h+var_40], 0
0x1800050b6  mov     edx, eax
0x1800050b8  mov     [rdi], eax
0x1800050ba  mov     ecx, eax
0x1800050bc  jz      short loc_1800050D7
0x1800050be  test    dl, 2
0x1800050c1  jnz     short loc_1800050D7
0x1800050c3  and     ecx, 0FFFFF63Eh
0x1800050c9  mov     eax, ebx
0x1800050cb  and     eax, 9C1h
0x1800050d0  or      ecx, eax
0x1800050d2  or      ecx, 2
0x1800050d5  mov     [rdi], ecx
0x1800050d7  mov     r8d, edx
0x1800050da  and     r8d, 4
0x1800050de  jnz     short loc_1800050F2
0x1800050e0  btr     ecx, 0Ah
0x1800050e4  mov     eax, ebx
0x1800050e6  and     eax, 400h
0x1800050eb  or      ecx, eax
0x1800050ed  or      ecx, 4
0x1800050f0  mov     [rdi], ecx
0x1800050f2  mov     eax, edx
0x1800050f4  lock cmpxchg [rsi], ecx
0x1800050f8  jnz     short loc_1800050B1
0x1800050fa  test    r8d, r8d
0x1800050fd  jnz     short loc_18000510F
0x1800050ff  mov     r8d, ebp
0x180005102  mov     edx, 3
0x180005107  mov     rcx, rsi
0x18000510a  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x18000510f  mov     ecx, [rdi]
0x180005111  test    cl, 2
0x180005114  jnz     short loc_180005126
0x180005116  and     ecx, 0FFFFF63Eh
0x18000511c  and     ebx, 9C1h
0x180005122  or      ecx, ebx
0x180005124  mov     [rdi], ecx
0x180005126  mov     rax, rdi
0x180005129  mov     rcx, [rsp+68h+var_38]
0x18000512e  xor     rcx, rsp; StackCookie
0x180005131  call    __security_check_cookie
0x180005136  add     rsp, 48h
0x18000513a  pop     rdi
0x18000513b  pop     rsi
0x18000513c  pop     rbp
0x18000513d  pop     rbx
0x18000513e  retn
```
