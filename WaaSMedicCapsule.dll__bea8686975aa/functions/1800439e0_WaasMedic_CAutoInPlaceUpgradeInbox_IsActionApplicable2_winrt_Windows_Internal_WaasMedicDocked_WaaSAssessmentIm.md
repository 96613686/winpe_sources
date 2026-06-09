# WaasMedic::CAutoInPlaceUpgradeInbox::IsActionApplicable2(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,bool,tagPluginActionApplicability *)

- ea: `0x1800439e0`
- end: `0x180043b1d`
- name: `?IsActionApplicable2@CAutoInPlaceUpgradeInbox@WaasMedic@@UEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@_NPEAW4tagPluginActionApplicability@@@Z`
- size: `317`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180009a54`
- `0x1800179c4`
- `0x18001cae0`
- `0x18002543c`
- `0x1800432ac`
- `0x18004375c`
- `0x1800439e0`

## string_xrefs

- `0x180043a71`: `Plugin is applicable due to manual remediation.`
- `0x180043b01`: `Plugin not applicable. Reason code: %d`
- `0x1800439fb`: `onecore\enduser\waasmedic\lib\plugins\autoinplaceupgradeinboxplugin.cpp`
- `0x180043a32`: `onecore\enduser\waasmedic\lib\plugins\autoinplaceupgradeinboxplugin.cpp`
- `0x180043ad9`: `Plugin applicable. Reason code: IPU Applicability Override is set to true. Reason code: %d`
- `0x180043aaa`: `Plugin applicable. Reason code: Reset CTAC attribute is set to true. Reason code: %d`

## pseudocode

```c
__int64 __fastcall WaasMedic::CAutoInPlaceUpgradeInbox::IsActionApplicable2(
        WaasMedic::CAutoInPlaceUpgradeInbox *a1,
        int a2,
        __int64 a3,
        _DWORD *a4)
{
  int IsActionApplicable2; // eax
  unsigned int v9; // edi
  __int64 v10; // r8
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  bool v13; // [rsp+68h] [rbp+20h] BYREF

  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x36,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\autoinplaceupgradeinboxplugin.cpp",
      (const char *)0x80004003LL,
      v11);
    return 2147500035LL;
  }
  *a4 = 12;
  IsActionApplicable2 = WaasMedic::CRemediationPluginBase::IsActionApplicable2();
  v9 = IsActionApplicable2;
  if ( IsActionApplicable2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3A,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\autoinplaceupgradeinboxplugin.cpp",
      (const char *)(unsigned int)IsActionApplicable2,
      v11);
    return v9;
  }
  v10 = 5;
  if ( *a4 == 5 )
    goto LABEL_19;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl'::`2'::impl)
    || *a4 != 16 )
  {
    v13 = 0;
    if ( (int)WaasMedic::CAutoInPlaceUpgradeInbox::GetResetIpuCTACAttributeSettingsValue(a1, &v13) >= 0 && v13 )
    {
      *a4 = 0;
      LogLevelW(4u, L"Plugin applicable. Reason code: Reset CTAC attribute is set to true. Reason code: %d", 0);
      return 0;
    }
    v13 = 0;
    if ( (int)WaasMedic::CAutoInPlaceUpgradeInbox::GetIpuApplicabilityOverrideSettingsValue(a1, &v13) >= 0 && v13 )
    {
      *a4 = 0;
      LogLevelW(4u, L"Plugin applicable. Reason code: IPU Applicability Override is set to true. Reason code: %d", 0);
      return 0;
    }
    v10 = (unsigned int)*a4;
    if ( (_DWORD)v10 == 3 || !(_DWORD)v10 )
    {
      if ( a2 )
        return 0;
      *a4 = 12;
      v10 = 12;
    }
LABEL_19:
    LogLevelW(4u, L"Plugin not applicable. Reason code: %d", v10);
    return 0;
  }
  LogLevelW(4u, L"Plugin is applicable due to manual remediation.");
  return 0;
}

```

## disassembly

```asm
0x1800439e0  push    rbx
0x1800439e2  push    rbp
0x1800439e3  push    rsi
0x1800439e4  push    rdi
0x1800439e5  sub     rsp, 28h
0x1800439e9  mov     rbx, r9
0x1800439ec  mov     ebp, edx
0x1800439ee  mov     rsi, rcx
0x1800439f1  test    r9, r9
0x1800439f4  jnz     short loc_180043A1B
0x1800439f6  mov     rcx, [rsp+48h]; this
0x1800439fb  lea     r8, aOnecoreEnduser_27; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180043a02  mov     ebx, 80004003h
0x180043a07  mov     edx, 36h ; '6'; void *
0x180043a0c  mov     r9d, ebx; char *
0x180043a0f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043a14  mov     eax, ebx
0x180043a16  jmp     loc_180043B14
0x180043a1b  mov     dword ptr [r9], 0Ch
0x180043a22  call    ?IsActionApplicable2@CRemediationPluginBase@WaasMedic@@UEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@_NPEAW4tagPluginActionApplicability@@@Z; WaasMedic::CRemediationPluginBase::IsActionApplicable2(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,bool,tagPluginActionApplicability *)
0x180043a27  mov     edi, eax
0x180043a29  test    eax, eax
0x180043a2b  jns     short loc_180043A4D
0x180043a2d  mov     rcx, [rsp+48h]; this
0x180043a32  lea     r8, aOnecoreEnduser_27; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x180043a39  mov     r9d, eax; char *
0x180043a3c  mov     edx, 3Ah ; ':'; void *
0x180043a41  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043a46  mov     eax, edi
0x180043a48  jmp     loc_180043B14
0x180043a4d  mov     r8d, 5
0x180043a53  cmp     [rbx], r8d
0x180043a56  jz      loc_180043B01
0x180043a5c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation> `wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl(void)'::`2'::impl
0x180043a63  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(void)
0x180043a68  test    al, al
0x180043a6a  jz      short loc_180043A87
0x180043a6c  cmp     dword ptr [rbx], 10h
0x180043a6f  jnz     short loc_180043A87
0x180043a71  lea     rdx, aPluginIsApplic; "Plugin is applicable due to manual reme"...
0x180043a78  mov     ecx, 4; unsigned __int8
0x180043a7d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180043a82  jmp     loc_180043B12
0x180043a87  lea     rdx, [rsp+48h+arg_18]; bool *
0x180043a8c  mov     [rsp+48h+arg_18], 0
0x180043a91  mov     rcx, rsi; this
0x180043a94  call    ?GetResetIpuCTACAttributeSettingsValue@CAutoInPlaceUpgradeInbox@WaasMedic@@AEAAJPEA_N@Z; WaasMedic::CAutoInPlaceUpgradeInbox::GetResetIpuCTACAttributeSettingsValue(bool *)
0x180043a99  test    eax, eax
0x180043a9b  js      short loc_180043AB6
0x180043a9d  cmp     [rsp+48h+arg_18], 0
0x180043aa2  jz      short loc_180043AB6
0x180043aa4  mov     dword ptr [rbx], 0
0x180043aaa  lea     rdx, aPluginApplicab; "Plugin applicable. Reason code: Reset C"...
0x180043ab1  xor     r8d, r8d
0x180043ab4  jmp     short loc_180043B08
0x180043ab6  lea     rdx, [rsp+48h+arg_18]; bool *
0x180043abb  mov     [rsp+48h+arg_18], 0
0x180043ac0  mov     rcx, rsi; this
0x180043ac3  call    ?GetIpuApplicabilityOverrideSettingsValue@CAutoInPlaceUpgradeInbox@WaasMedic@@AEAAJPEA_N@Z; WaasMedic::CAutoInPlaceUpgradeInbox::GetIpuApplicabilityOverrideSettingsValue(bool *)
0x180043ac8  test    eax, eax
0x180043aca  js      short loc_180043AE5
0x180043acc  cmp     [rsp+48h+arg_18], 0
0x180043ad1  jz      short loc_180043AE5
0x180043ad3  mov     dword ptr [rbx], 0
0x180043ad9  lea     rdx, aPluginApplicab_0; "Plugin applicable. Reason code: IPU App"...
0x180043ae0  xor     r8d, r8d
0x180043ae3  jmp     short loc_180043B08
0x180043ae5  mov     r8d, [rbx]
0x180043ae8  cmp     r8d, 3
0x180043aec  jz      short loc_180043AF3
0x180043aee  test    r8d, r8d
0x180043af1  jnz     short loc_180043B01
0x180043af3  test    ebp, ebp
0x180043af5  jnz     short loc_180043B12
0x180043af7  mov     dword ptr [rbx], 0Ch
0x180043afd  lea     r8d, [rbp+0Ch]
0x180043b01  lea     rdx, aPluginNotAppli; "Plugin not applicable. Reason code: %d"
0x180043b08  mov     ecx, 4; unsigned __int8
0x180043b0d  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x180043b12  xor     eax, eax
0x180043b14  add     rsp, 28h
0x180043b18  pop     rdi
0x180043b19  pop     rsi
0x180043b1a  pop     rbp
0x180043b1b  pop     rbx
0x180043b1c  retn
```
