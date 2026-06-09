# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::GetCachedFeatureEnabledState(void)

- ea: `0x1400158c8`
- end: `0x1400159bb`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `243`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140015a38`

## callees

- `0x1400023e0`
- `0x140007374`
- `0x140008f28`
- `0x1400158c8`
- `0x1400159c4`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Servicing_AzureVMFirstBootLogonDelay_38297786__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Servicing_AzureVMFirstBootLogonDelay_38297786__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v13 = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_Servicing_AzureVMFirstBootLogonDelay_38297786__descriptor,
             v10,
             v6);
    }
    while ( v9 != v6 );
    if ( (v9 & 4) == 0 )
      wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        wil::details::g_enabledStateManager,
        Feature_Servicing_AzureVMFirstBootLogonDelay_38297786__descriptor,
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
0x1400158c8  push    rbx
0x1400158ca  push    rbp
0x1400158cb  push    rsi
0x1400158cc  push    rdi
0x1400158cd  sub     rsp, 48h
0x1400158d1  mov     rax, cs:__security_cookie
0x1400158d8  xor     rax, rsp
0x1400158db  mov     [rsp+68h+var_38], rax
0x1400158e0  mov     rsi, cs:Feature_Servicing_AzureVMFirstBootLogonDelay_38297786__descriptor
0x1400158e7  mov     rdi, rdx
0x1400158ea  mov     qword ptr [rdx], 0
0x1400158f1  mov     eax, [rsi]
0x1400158f3  mov     [rdx], eax
0x1400158f5  and     eax, 6
0x1400158f8  cmp     al, 6
0x1400158fa  jz      loc_1400159A2
0x140015900  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x140015905  lea     r8, [rsp+68h+var_40]
0x14001590a  mov     [rsp+68h+var_40], 0
0x140015912  lea     rdx, [rsp+68h+var_48]
0x140015917  mov     ebp, eax
0x140015919  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_AzureVMFirstBootLogonDelay_38297786>::GetCurrentFeatureEnabledState(int *)
0x14001591e  mov     eax, [rdi]
0x140015920  mov     rbx, [rsp+68h+var_48]
0x140015925  cmp     [rsp+68h+var_40], 0
0x14001592a  mov     edx, eax
0x14001592c  mov     [rdi], eax
0x14001592e  mov     ecx, eax
0x140015930  jz      short loc_14001594B
0x140015932  test    dl, 2
0x140015935  jnz     short loc_14001594B
0x140015937  and     ecx, 0FFFFF63Eh
0x14001593d  mov     eax, ebx
0x14001593f  and     eax, 9C1h
0x140015944  or      ecx, eax
0x140015946  or      ecx, 2
0x140015949  mov     [rdi], ecx
0x14001594b  mov     r8d, edx
0x14001594e  and     r8d, 4
0x140015952  jnz     short loc_140015966
0x140015954  btr     ecx, 0Ah
0x140015958  mov     eax, ebx
0x14001595a  and     eax, 400h
0x14001595f  or      ecx, eax
0x140015961  or      ecx, 4
0x140015964  mov     [rdi], ecx
0x140015966  mov     eax, edx
0x140015968  lock cmpxchg [rsi], ecx
0x14001596c  jnz     short loc_140015925
0x14001596e  test    r8d, r8d
0x140015971  jnz     short loc_14001598B
0x140015973  mov     r9d, ebp
0x140015976  lea     rcx, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14001597d  mov     r8d, 3
0x140015983  mov     rdx, rsi
0x140015986  call    ?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x14001598b  mov     ecx, [rdi]
0x14001598d  test    cl, 2
0x140015990  jnz     short loc_1400159A2
0x140015992  and     ecx, 0FFFFF63Eh
0x140015998  and     ebx, 9C1h
0x14001599e  or      ecx, ebx
0x1400159a0  mov     [rdi], ecx
0x1400159a2  mov     rax, rdi
0x1400159a5  mov     rcx, [rsp+68h+var_38]
0x1400159aa  xor     rcx, rsp; StackCookie
0x1400159ad  call    __security_check_cookie
0x1400159b2  add     rsp, 48h
0x1400159b6  pop     rdi
0x1400159b7  pop     rsi
0x1400159b8  pop     rbp
0x1400159b9  pop     rbx
0x1400159ba  retn
```
