# WaasMedic::CRemediationPluginBase::IsActionApplicable2(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,bool,tagPluginActionApplicability *)

- ea: `0x18001cae0`
- end: `0x18001cc8b`
- name: `?IsActionApplicable2@CRemediationPluginBase@WaasMedic@@UEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@_NPEAW4tagPluginActionApplicability@@@Z`
- size: `427`
- prototype: ``
- caller_count: `10`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, installer_update`

## callers

- `0x18000d5e0`
- `0x1800387e0`
- `0x18003b790`
- `0x18003f430`
- `0x1800439e0`
- `0x180046b70`
- `0x18004e010`
- `0x180050120`
- `0x180051c80`
- `0x180053ce0`

## callees

- `0x180009a54`
- `0x1800179c4`
- `0x18001ba20`
- `0x18001bbb4`
- `0x18001bcdc`
- `0x18001bfc4`
- `0x18001c10c`
- `0x18001c638`
- `0x18001cae0`
- `0x18001ced8`
- `0x18002543c`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18001cb03`
- `OLEAUT32!__imp_VariantInit` at `0x18001cb0f`
- `OLEAUT32!__imp_VariantInit` at `0x18001cb03`
- `OLEAUT32!__imp_VariantInit` at `0x18001cb0f`
- `OLEAUT32!__imp_VariantClear` at `0x18001cc64`
- `OLEAUT32!__imp_VariantClear` at `0x18001cc70`
- `OLEAUT32!__imp_VariantClear` at `0x18001cc64`
- `OLEAUT32!__imp_VariantClear` at `0x18001cc70`

## string_xrefs

- `0x18001cbe7`: `onecore\enduser\waasmedic\lib\plugins\remediationpluginbase.cpp`
- `0x18001cb6a`: `Error encountered when evaluating if device update service is managed! hr = 0x%08x`
- `0x18001cc2a`: `Error encountered when retrieving plugin impact level! hr = 0x%08x`
- `0x18001cc49`: `Error encountered when evaluating plugin action limit! hr = 0x%08x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WaasMedic::CRemediationPluginBase::IsActionApplicable2(
        WaasMedic::CRemediationPluginBase *a1,
        unsigned int a2,
        bool a3,
        enum tagPluginActionApplicability *a4)
{
  int v8; // ebx
  int v9; // eax
  int updated; // eax
  int IsManualRemediationApplicable; // eax
  int v12; // eax
  unsigned int v13; // edi
  int v14; // eax
  int v15; // eax
  int v16; // eax
  VARIANTARG v18; // [rsp+20h] [rbp-48h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  bool v21; // [rsp+88h] [rbp+20h] BYREF

  VariantInit(&pvarg);
  VariantInit(&v18);
  v21 = 0;
  if ( !a4 )
  {
    v8 = -2147467261;
    goto LABEL_25;
  }
  *(_DWORD *)a4 = 0;
  v9 = WaasMedic::CRemediationPluginBase::EvaluateServerSkuBlock(a1, a4);
  v8 = v9;
  if ( v9 < 0 )
  {
    LogLevelW(2u, L"Error encountered when evaluating server SKU block! hr = 0x%08x", (unsigned int)v9);
    goto LABEL_25;
  }
  if ( *(_DWORD *)a4 )
    goto LABEL_25;
  updated = WaasMedic::CRemediationPluginBase::EvaluateUpdateServiceManagedBlock(a1, a4);
  v8 = updated;
  if ( updated < 0 )
  {
    LogLevelW(
      2u,
      L"Error encountered when evaluating if device update service is managed! hr = 0x%08x",
      (unsigned int)updated);
    goto LABEL_25;
  }
  if ( *(_DWORD *)a4 )
    goto LABEL_25;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl'::`2'::impl) )
  {
    IsManualRemediationApplicable = WaasMedic::CRemediationPluginBase::IsManualRemediationApplicable(a1, &v21);
    v8 = IsManualRemediationApplicable;
    if ( IsManualRemediationApplicable < 0 )
    {
      LogLevelW(
        2u,
        L"Error encountered when checking if manual remediation is allowed! hr = 0x%08x",
        (unsigned int)IsManualRemediationApplicable);
      goto LABEL_25;
    }
    if ( v21 )
    {
      *(_DWORD *)a4 = 16;
      goto LABEL_25;
    }
  }
  if ( !a3 )
  {
    v14 = WaasMedic::CRemediationPluginBase::EvaluateTimeBlocks((__int64)a1, a2, a4);
    v8 = v14;
    if ( v14 >= 0 )
    {
      if ( !*(_DWORD *)a4 )
      {
        v15 = WaasMedic::CRemediationPluginBase::EvaluatePluginImpactLevelBlock(a1, a2, a4);
        v8 = v15;
        if ( v15 >= 0 )
        {
          if ( !*(_DWORD *)a4 )
          {
            v16 = WaasMedic::CRemediationPluginBase::EvaluateActionLimitBlock(a1, a4);
            v8 = v16;
            if ( v16 < 0 )
              LogLevelW(2u, L"Error encountered when evaluating plugin action limit! hr = 0x%08x", (unsigned int)v16);
          }
        }
        else
        {
          LogLevelW(2u, L"Error encountered when retrieving plugin impact level! hr = 0x%08x", (unsigned int)v15);
        }
      }
    }
    else
    {
      LogLevelW(2u, L"Error encountered when evaluating time blocks! hr = 0x%08x", (unsigned int)v14);
    }
    goto LABEL_25;
  }
  v12 = WaasMedic::CRemediationPluginBase::EvaluateInteractiveBlock(a1, a3, a4);
  v13 = v12;
  if ( v12 >= 0 )
  {
LABEL_25:
    v13 = v8;
    goto LABEL_26;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x74,
    (unsigned int)"onecore\\enduser\\waasmedic\\lib\\plugins\\remediationpluginbase.cpp",
    (const char *)(unsigned int)v12,
    *(int *)&v18.vt);
LABEL_26:
  VariantClear(&v18);
  VariantClear(&pvarg);
  return v13;
}

```

## disassembly

```asm
0x18001cae0  mov     [rsp+arg_0], rbx
0x18001cae5  mov     [rsp+arg_8], rbp
0x18001caea  push    rsi
0x18001caeb  push    rdi
0x18001caec  push    r14
0x18001caee  sub     rsp, 50h
0x18001caf2  mov     rdi, r9
0x18001caf5  mov     bpl, r8b
0x18001caf8  mov     r14d, edx
0x18001cafb  mov     rsi, rcx
0x18001cafe  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001cb03  call    cs:__imp_VariantInit
0x18001cb09  nop
0x18001cb0a  lea     rcx, [rsp+68h+var_48]; pvarg
0x18001cb0f  call    cs:__imp_VariantInit
0x18001cb15  nop
0x18001cb16  mov     [rsp+68h+arg_18], 0
0x18001cb1e  test    rdi, rdi
0x18001cb21  jnz     short loc_18001CB2D
0x18001cb23  mov     ebx, 80004003h
0x18001cb28  jmp     loc_18001CC5D
0x18001cb2d  mov     dword ptr [rdi], 0
0x18001cb33  mov     rdx, rdi; enum tagPluginActionApplicability *
0x18001cb36  mov     rcx, rsi; this
0x18001cb39  call    ?EvaluateServerSkuBlock@CRemediationPluginBase@WaasMedic@@AEAAJPEAW4tagPluginActionApplicability@@@Z; WaasMedic::CRemediationPluginBase::EvaluateServerSkuBlock(tagPluginActionApplicability *)
0x18001cb3e  mov     ebx, eax
0x18001cb40  test    eax, eax
0x18001cb42  jns     short loc_18001CB50
0x18001cb44  lea     rdx, aErrorEncounter_9; "Error encountered when evaluating serve"...
0x18001cb4b  jmp     loc_18001CC50
0x18001cb50  cmp     dword ptr [rdi], 0
0x18001cb53  jnz     loc_18001CC5D
0x18001cb59  mov     rdx, rdi; enum tagPluginActionApplicability *
0x18001cb5c  mov     rcx, rsi; this
0x18001cb5f  call    ?EvaluateUpdateServiceManagedBlock@CRemediationPluginBase@WaasMedic@@AEAAJPEAW4tagPluginActionApplicability@@@Z; WaasMedic::CRemediationPluginBase::EvaluateUpdateServiceManagedBlock(tagPluginActionApplicability *)
0x18001cb64  mov     ebx, eax
0x18001cb66  test    eax, eax
0x18001cb68  jns     short loc_18001CB76
0x18001cb6a  lea     rdx, aErrorEncounter_7; "Error encountered when evaluating if de"...
0x18001cb71  jmp     loc_18001CC50
0x18001cb76  cmp     dword ptr [rdi], 0
0x18001cb79  jnz     loc_18001CC5D
0x18001cb7f  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation> `wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl(void)'::`2'::impl
0x18001cb86  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(void)
0x18001cb8b  test    al, al
0x18001cb8d  jz      short loc_18001CBC6
0x18001cb8f  lea     rdx, [rsp+68h+arg_18]; bool *
0x18001cb97  mov     rcx, rsi; this
0x18001cb9a  call    ?IsManualRemediationApplicable@CRemediationPluginBase@WaasMedic@@IEAAJAEA_N@Z; WaasMedic::CRemediationPluginBase::IsManualRemediationApplicable(bool &)
0x18001cb9f  mov     ebx, eax
0x18001cba1  test    eax, eax
0x18001cba3  jns     short loc_18001CBB1
0x18001cba5  lea     rdx, aErrorEncounter_3; "Error encountered when checking if manu"...
0x18001cbac  jmp     loc_18001CC50
0x18001cbb1  cmp     [rsp+68h+arg_18], 0
0x18001cbb9  jz      short loc_18001CBC6
0x18001cbbb  mov     dword ptr [rdi], 10h
0x18001cbc1  jmp     loc_18001CC5D
0x18001cbc6  mov     r8, rdi; enum tagPluginActionApplicability *
0x18001cbc9  mov     rcx, rsi; this
0x18001cbcc  test    bpl, bpl
0x18001cbcf  jz      short loc_18001CBFA
0x18001cbd1  mov     dl, bpl; bool
0x18001cbd4  call    ?EvaluateInteractiveBlock@CRemediationPluginBase@WaasMedic@@AEAAJ_NPEAW4tagPluginActionApplicability@@@Z; WaasMedic::CRemediationPluginBase::EvaluateInteractiveBlock(bool,tagPluginActionApplicability *)
0x18001cbd9  mov     edi, eax
0x18001cbdb  test    eax, eax
0x18001cbdd  jns     short loc_18001CC5D
0x18001cbdf  mov     rcx, [rsp+68h]; this
0x18001cbe4  mov     r9d, eax; char *
0x18001cbe7  lea     r8, aOnecoreEnduser_9; "onecore\\enduser\\waasmedic\\lib\\plugi"...
0x18001cbee  mov     edx, 74h ; 't'; void *
0x18001cbf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cbf8  jmp     short loc_18001CC5F
0x18001cbfa  mov     edx, r14d
0x18001cbfd  call    ?EvaluateTimeBlocks@CRemediationPluginBase@WaasMedic@@AEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@PEAW4tagPluginActionApplicability@@@Z; WaasMedic::CRemediationPluginBase::EvaluateTimeBlocks(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,tagPluginActionApplicability *)
0x18001cc02  mov     ebx, eax
0x18001cc04  test    eax, eax
0x18001cc06  jns     short loc_18001CC11
0x18001cc08  lea     rdx, aErrorEncounter_14; "Error encountered when evaluating time "...
0x18001cc0f  jmp     short loc_18001CC50
0x18001cc11  cmp     dword ptr [rdi], 0
0x18001cc14  jnz     short loc_18001CC5D
0x18001cc16  mov     r8, rdi
0x18001cc19  mov     edx, r14d
0x18001cc1c  mov     rcx, rsi
0x18001cc1f  call    ?EvaluatePluginImpactLevelBlock@CRemediationPluginBase@WaasMedic@@IEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@PEAW4tagPluginActionApplicability@@@Z; WaasMedic::CRemediationPluginBase::EvaluatePluginImpactLevelBlock(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,tagPluginActionApplicability *)
0x18001cc24  mov     ebx, eax
0x18001cc26  test    eax, eax
0x18001cc28  jns     short loc_18001CC33
0x18001cc2a  lea     rdx, aErrorEncounter; "Error encountered when retrieving plugi"...
0x18001cc31  jmp     short loc_18001CC50
0x18001cc33  cmp     dword ptr [rdi], 0
0x18001cc36  jnz     short loc_18001CC5D
0x18001cc38  mov     rdx, rdi; enum tagPluginActionApplicability *
0x18001cc3b  mov     rcx, rsi; this
0x18001cc3e  call    ?EvaluateActionLimitBlock@CRemediationPluginBase@WaasMedic@@IEAAJPEAW4tagPluginActionApplicability@@@Z; WaasMedic::CRemediationPluginBase::EvaluateActionLimitBlock(tagPluginActionApplicability *)
0x18001cc43  mov     ebx, eax
0x18001cc45  test    eax, eax
0x18001cc47  jns     short loc_18001CC5D
0x18001cc49  lea     rdx, aErrorEncounter_11; "Error encountered when evaluating plugi"...
0x18001cc50  mov     r8d, eax
0x18001cc53  mov     ecx, 2; unsigned __int8
0x18001cc58  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18001cc5d  mov     edi, ebx
0x18001cc5f  lea     rcx, [rsp+68h+var_48]; pvarg
0x18001cc64  call    cs:__imp_VariantClear
0x18001cc6a  nop
0x18001cc6b  lea     rcx, [rsp+68h+pvarg]; pvarg
0x18001cc70  call    cs:__imp_VariantClear
0x18001cc76  mov     eax, edi
0x18001cc78  mov     rbx, [rsp+68h+arg_0]
0x18001cc7d  mov     rbp, [rsp+68h+arg_8]
0x18001cc82  add     rsp, 50h
0x18001cc86  pop     r14
0x18001cc88  pop     rdi
0x18001cc89  pop     rsi
0x18001cc8a  retn
```
