# WaasMedic::EdgeUpdateRepairPlugin::IsActionApplicable2(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,bool,tagPluginActionApplicability *)

- ea: `0x18000d5e0`
- end: `0x18000d748`
- name: `?IsActionApplicable2@EdgeUpdateRepairPlugin@WaasMedic@@UEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@_NPEAW4tagPluginActionApplicability@@@Z`
- size: `360`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, loader_planting, installer_update`

## callees

- `0x180009a54`
- `0x18000d5e0`
- `0x18000d750`
- `0x1800179c4`
- `0x18001cae0`
- `0x18002543c`
- `0x180025b44`
- `0x1800272b4`

## string_xrefs

- `0x18000d5f7`: `onecore\enduser\waasmedic\lib\plugins\edgeupdaterepairplugin.cpp`
- `0x18000d62c`: `onecore\enduser\waasmedic\lib\plugins\edgeupdaterepairplugin.cpp`
- `0x18000d657`: `Plugin is applicable due to manual remediation.`
- `0x18000d699`: `EdgeUpdateRepairPlugin: Device not eligible for repair`
- `0x18000d6e5`: `EdgeUpdateRepairPlugin: Not enough disk space to perform Repair. Found space: %d MB`
- `0x18000d724`: `EdgeUpdateRepairPlugin: Device not connected to network or metered connection found. Cannot perform Repair`

## pseudocode

```c
__int64 __fastcall WaasMedic::EdgeUpdateRepairPlugin::IsActionApplicable2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        _DWORD *a4)
{
  int IsActionApplicable2; // edi
  __int64 v7; // rdx
  WaasMedic::EdgeUpdateRepairPlugin *v8; // rcx
  int v9; // [rsp+20h] [rbp-18h] BYREF
  int v10[5]; // [rsp+24h] [rbp-14h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  bool v12; // [rsp+58h] [rbp+20h] BYREF

  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1C,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\edgeupdaterepairplugin.cpp",
      (const char *)0x80004003LL,
      v9);
    return 2147500035LL;
  }
  IsActionApplicable2 = WaasMedic::CRemediationPluginBase::IsActionApplicable2();
  if ( IsActionApplicable2 < 0 )
  {
    v7 = 31;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\edgeupdaterepairplugin.cpp",
      (const char *)(unsigned int)IsActionApplicable2,
      v9);
    return (unsigned int)IsActionApplicable2;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl'::`2'::impl)
    && *a4 == 16 )
  {
    LogLevelW(4u, L"Plugin is applicable due to manual remediation.");
  }
  else if ( !*a4 )
  {
    v12 = 0;
    IsActionApplicable2 = WaasMedic::EdgeUpdateRepairPlugin::IsDeviceEligibleForRepair(v8, &v12);
    if ( IsActionApplicable2 < 0 )
    {
      v7 = 49;
      goto LABEL_5;
    }
    if ( v12 )
    {
      v10[0] = 0;
      IsActionApplicable2 = WaasMedic::MiscUtil::FreeSpaceInMB(v10);
      if ( IsActionApplicable2 < 0 )
      {
        v7 = 58;
        goto LABEL_5;
      }
      if ( v10[0] >= 1000 )
      {
        LOBYTE(v9) = 0;
        IsActionApplicable2 = WaasMedic::NetworkUtil::HasUnrestrictedConnection((bool *)&v9);
        if ( IsActionApplicable2 < 0 )
        {
          v7 = 68;
          goto LABEL_5;
        }
        if ( !(_BYTE)v9 )
        {
          LogLevelW(
            4u,
            L"EdgeUpdateRepairPlugin: Device not connected to network or metered connection found. Cannot perform Repair");
          *a4 = 4;
        }
      }
      else
      {
        LogLevelW(4u, L"EdgeUpdateRepairPlugin: Not enough disk space to perform Repair. Found space: %d MB");
        *a4 = 9;
      }
    }
    else
    {
      LogLevelW(4u, L"EdgeUpdateRepairPlugin: Device not eligible for repair");
      *a4 = 12;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000d5e0  mov     [rsp+arg_0], rbx
0x18000d5e5  push    rdi
0x18000d5e6  sub     rsp, 30h
0x18000d5ea  mov     rbx, r9
0x18000d5ed  test    r9, r9
0x18000d5f0  jnz     short loc_18000D617
0x18000d5f2  mov     rcx, [rsp+38h]; this
0x18000d5f7  lea     r8, aOnecoreEnduser_44; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18000d5fe  mov     ebx, 80004003h
0x18000d603  mov     edx, 1Ch; void *
0x18000d608  mov     r9d, ebx; char *
0x18000d60b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d610  mov     eax, ebx
0x18000d612  jmp     loc_18000D73D
0x18000d617  call    ?IsActionApplicable2@CRemediationPluginBase@WaasMedic@@UEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@_NPEAW4tagPluginActionApplicability@@@Z; WaasMedic::CRemediationPluginBase::IsActionApplicable2(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,bool,tagPluginActionApplicability *)
0x18000d61c  mov     edi, eax
0x18000d61e  test    eax, eax
0x18000d620  jns     short loc_18000D642
0x18000d622  mov     edx, 1Fh; void *
0x18000d627  mov     rcx, [rsp+38h]; this
0x18000d62c  lea     r8, aOnecoreEnduser_44; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18000d633  mov     r9d, edi; char *
0x18000d636  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d63b  mov     eax, edi
0x18000d63d  jmp     loc_18000D73D
0x18000d642  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation> `wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl(void)'::`2'::impl
0x18000d649  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(void)
0x18000d64e  test    al, al
0x18000d650  jz      short loc_18000D66D
0x18000d652  cmp     dword ptr [rbx], 10h
0x18000d655  jnz     short loc_18000D66D
0x18000d657  lea     rdx, aPluginIsApplic; "Plugin is applicable due to manual reme"...
0x18000d65e  mov     ecx, 4; unsigned __int8
0x18000d663  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18000d668  jmp     loc_18000D73B
0x18000d66d  cmp     dword ptr [rbx], 0
0x18000d670  jnz     loc_18000D73B
0x18000d676  lea     rdx, [rsp+38h+arg_18]; bool *
0x18000d67b  mov     [rsp+38h+arg_18], 0
0x18000d680  call    ?IsDeviceEligibleForRepair@EdgeUpdateRepairPlugin@WaasMedic@@AEAAJAEA_N@Z; WaasMedic::EdgeUpdateRepairPlugin::IsDeviceEligibleForRepair(bool &)
0x18000d685  mov     edi, eax
0x18000d687  test    eax, eax
0x18000d689  jns     short loc_18000D692
0x18000d68b  mov     edx, 31h ; '1'
0x18000d690  jmp     short loc_18000D627
0x18000d692  cmp     [rsp+38h+arg_18], 0
0x18000d697  jnz     short loc_18000D6B5
0x18000d699  lea     rdx, aEdgeupdaterepa_0; "EdgeUpdateRepairPlugin: Device not elig"...
0x18000d6a0  mov     ecx, 4; unsigned __int8
0x18000d6a5  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18000d6aa  mov     dword ptr [rbx], 0Ch
0x18000d6b0  jmp     loc_18000D73B
0x18000d6b5  lea     rcx, [rsp+38h+var_14]; int *
0x18000d6ba  mov     [rsp+38h+var_14], 0
0x18000d6c2  call    ?FreeSpaceInMB@MiscUtil@WaasMedic@@SAJAEAH@Z; WaasMedic::MiscUtil::FreeSpaceInMB(int &)
0x18000d6c7  mov     edi, eax
0x18000d6c9  test    eax, eax
0x18000d6cb  jns     short loc_18000D6D7
0x18000d6cd  mov     edx, 3Ah ; ':'
0x18000d6d2  jmp     loc_18000D627
0x18000d6d7  mov     r8d, [rsp+38h+var_14]
0x18000d6dc  cmp     r8d, 3E8h
0x18000d6e3  jge     short loc_18000D6FE
0x18000d6e5  lea     rdx, aEdgeupdaterepa; "EdgeUpdateRepairPlugin: Not enough disk"...
0x18000d6ec  mov     ecx, 4; unsigned __int8
0x18000d6f1  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18000d6f6  mov     dword ptr [rbx], 9
0x18000d6fc  jmp     short loc_18000D73B
0x18000d6fe  lea     rcx, [rsp+38h+var_18]; bool *
0x18000d703  mov     byte ptr [rsp+38h+var_18], 0
0x18000d708  call    ?HasUnrestrictedConnection@NetworkUtil@WaasMedic@@SAJAEA_N@Z; WaasMedic::NetworkUtil::HasUnrestrictedConnection(bool &)
0x18000d70d  mov     edi, eax
0x18000d70f  test    eax, eax
0x18000d711  jns     short loc_18000D71D
0x18000d713  mov     edx, 44h ; 'D'
0x18000d718  jmp     loc_18000D627
0x18000d71d  cmp     byte ptr [rsp+38h+var_18], 0
0x18000d722  jnz     short loc_18000D73B
0x18000d724  lea     rdx, aEdgeupdaterepa_1; "EdgeUpdateRepairPlugin: Device not conn"...
0x18000d72b  mov     ecx, 4; unsigned __int8
0x18000d730  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18000d735  mov     dword ptr [rbx], 4
0x18000d73b  xor     eax, eax
0x18000d73d  mov     rbx, [rsp+38h+arg_0]
0x18000d742  add     rsp, 30h
0x18000d746  pop     rdi
0x18000d747  retn
```
