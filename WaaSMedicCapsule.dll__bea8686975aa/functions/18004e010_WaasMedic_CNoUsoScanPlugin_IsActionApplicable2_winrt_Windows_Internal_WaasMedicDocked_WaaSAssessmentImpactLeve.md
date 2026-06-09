# WaasMedic::CNoUsoScanPlugin::IsActionApplicable2(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,bool,tagPluginActionApplicability *)

- ea: `0x18004e010`
- end: `0x18004e13c`
- name: `?IsActionApplicable2@CNoUsoScanPlugin@WaasMedic@@UEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@_NPEAW4tagPluginActionApplicability@@@Z`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800179c4`
- `0x18001cae0`
- `0x18002543c`
- `0x18004e010`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e0a8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004e0a8`

## string_xrefs

- `0x18004e055`: `Plugin is applicable due to manual remediation.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall WaasMedic::CNoUsoScanPlugin::IsActionApplicable2(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  __int64 result; // rax
  int v6; // ebx
  bool v7; // si
  HRESULT v8; // eax
  int v9; // eax
  LPVOID v10; // rcx
  LPVOID ppv; // [rsp+30h] [rbp-18h] BYREF
  int v12; // [rsp+68h] [rbp+20h] BYREF

  if ( !a4 )
    return 2147500035LL;
  result = WaasMedic::CRemediationPluginBase::IsActionApplicable2();
  v6 = result;
  if ( (int)result >= 0 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl'::`2'::impl)
      && *a4 == 16 )
    {
      LogLevelW(4u, L"Plugin is applicable due to manual remediation.");
      return 0;
    }
    else
    {
      if ( !*a4 )
      {
        v7 = 0;
        v12 = 0;
        ppv = 0;
        v8 = CoCreateInstance(&CLSID_NetworkListManager, 0, 1u, &GUID_dcb00000_570f_4a9b_8d69_199fdba5723b, &ppv);
        v6 = v8;
        if ( v8 >= 0 )
        {
          v9 = (*(__int64 (__fastcall **)(LPVOID, int *))(*(_QWORD *)ppv + 104LL))(ppv, &v12);
          v6 = v9;
          if ( v9 >= 0 )
            v7 = (v12 & 0x440) != 0;
          else
            LogLevelW(2u, L"Failed to GetConnectivity status. hr = 0x%08x.", (unsigned int)v9);
        }
        else
        {
          LogLevelW(2u, L"Failed CCI on INetworkListManager. hr = 0x%08x.", (unsigned int)v8);
        }
        v10 = ppv;
        if ( ppv )
        {
          ppv = 0;
          (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v10 + 16LL))(v10);
        }
        if ( v6 >= 0 && !v7 )
          *a4 = 4;
      }
      return (unsigned int)v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18004e010  mov     [rsp+arg_0], rbx
0x18004e015  mov     [rsp+arg_8], rsi
0x18004e01a  push    rdi
0x18004e01b  sub     rsp, 40h
0x18004e01f  mov     rdi, r9
0x18004e022  test    r9, r9
0x18004e025  jnz     short loc_18004E031
0x18004e027  mov     eax, 80004003h
0x18004e02c  jmp     loc_18004E12C
0x18004e031  call    ?IsActionApplicable2@CRemediationPluginBase@WaasMedic@@UEAAJW4WaaSAssessmentImpactLevel@WaasMedicDocked@Internal@Windows@winrt@@_NPEAW4tagPluginActionApplicability@@@Z; WaasMedic::CRemediationPluginBase::IsActionApplicable2(winrt::Windows::Internal::WaasMedicDocked::WaaSAssessmentImpactLevel,bool,tagPluginActionApplicability *)
0x18004e036  mov     ebx, eax
0x18004e038  test    eax, eax
0x18004e03a  js      loc_18004E12C
0x18004e040  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation> `wil::Feature<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::GetImpl(void)'::`2'::impl
0x18004e047  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WaaSMedicSettingsInitiatedRemediation>::__private_IsEnabled(void)
0x18004e04c  test    al, al
0x18004e04e  jz      short loc_18004E06D
0x18004e050  cmp     dword ptr [rdi], 10h
0x18004e053  jnz     short loc_18004E06D
0x18004e055  lea     rdx, aPluginIsApplic; "Plugin is applicable due to manual reme"...
0x18004e05c  mov     ecx, 4; unsigned __int8
0x18004e061  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004e066  xor     eax, eax
0x18004e068  jmp     loc_18004E12C
0x18004e06d  cmp     dword ptr [rdi], 0
0x18004e070  jnz     loc_18004E12A
0x18004e076  xor     sil, sil
0x18004e079  mov     [rsp+48h+arg_18], 0
0x18004e081  mov     [rsp+48h+var_18], 0
0x18004e08a  lea     rax, [rsp+48h+var_18]
0x18004e08f  mov     [rsp+48h+ppv], rax; ppv
0x18004e094  lea     r9, _GUID_dcb00000_570f_4a9b_8d69_199fdba5723b; riid
0x18004e09b  xor     edx, edx; pUnkOuter
0x18004e09d  lea     r8d, [rdx+1]; dwClsContext
0x18004e0a1  lea     rcx, CLSID_NetworkListManager; rclsid
0x18004e0a8  call    cs:__imp_CoCreateInstance
0x18004e0ae  mov     ebx, eax
0x18004e0b0  test    eax, eax
0x18004e0b2  jns     short loc_18004E0CA
0x18004e0b4  lea     rdx, aFailedCciOnIne; "Failed CCI on INetworkListManager. hr ="...
0x18004e0bb  mov     r8d, eax
0x18004e0be  mov     ecx, 2; unsigned __int8
0x18004e0c3  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x18004e0c8  jmp     short loc_18004E0FB
0x18004e0ca  mov     rcx, [rsp+48h+var_18]
0x18004e0cf  mov     rax, [rcx]
0x18004e0d2  lea     rdx, [rsp+48h+arg_18]
0x18004e0d7  mov     rax, [rax+68h]
0x18004e0db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e0e0  mov     ebx, eax
0x18004e0e2  test    eax, eax
0x18004e0e4  jns     short loc_18004E0EF
0x18004e0e6  lea     rdx, aFailedToGetcon; "Failed to GetConnectivity status. hr = "...
0x18004e0ed  jmp     short loc_18004E0BB
0x18004e0ef  test    [rsp+48h+arg_18], 440h
0x18004e0f7  setnz   sil
0x18004e0fb  mov     rcx, [rsp+48h+var_18]
0x18004e100  test    rcx, rcx
0x18004e103  jz      short loc_18004E11B
0x18004e105  mov     [rsp+48h+var_18], 0
0x18004e10e  mov     rax, [rcx]
0x18004e111  mov     rax, [rax+10h]
0x18004e115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e11a  nop
0x18004e11b  test    ebx, ebx
0x18004e11d  js      short loc_18004E12A
0x18004e11f  test    sil, sil
0x18004e122  jnz     short loc_18004E12A
0x18004e124  mov     dword ptr [rdi], 4
0x18004e12a  mov     eax, ebx
0x18004e12c  mov     rbx, [rsp+48h+arg_0]
0x18004e131  mov     rsi, [rsp+48h+arg_8]
0x18004e136  add     rsp, 40h
0x18004e13a  pop     rdi
0x18004e13b  retn
```
