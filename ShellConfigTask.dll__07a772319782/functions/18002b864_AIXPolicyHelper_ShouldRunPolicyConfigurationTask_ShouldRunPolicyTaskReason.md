# AIXPolicyHelper::ShouldRunPolicyConfigurationTask(ShouldRunPolicyTaskReason *)

- ea: `0x18002b864`
- end: `0x18002bc56`
- name: `?ShouldRunPolicyConfigurationTask@AIXPolicyHelper@@YA_NPEAW4ShouldRunPolicyTaskReason@@@Z`
- size: `1010`
- prototype: `bool __fastcall(AIXPolicyHelper *__hidden this, enum ShouldRunPolicyTaskReason *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002d050`

## callees

- `0x18000163c`
- `0x180002590`
- `0x18000830c`
- `0x18000896c`
- `0x18001a570`
- `0x18001c988`
- `0x18001cce4`
- `0x18001d048`
- `0x18001d0d4`
- `0x18001d484`
- `0x18001d63c`
- `0x18001e518`
- `0x18001ed90`
- `0x180020d3c`
- `0x180020f7c`
- `0x180020fbc`
- `0x18002105c`
- `0x18002131c`
- `0x1800233ec`
- `0x180024e7c`
- `0x18002a7b4`
- `0x18002b864`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b9bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bb51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bc2d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002b9bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bb51`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002bc2d`

## string_xrefs

- `0x18002b9a3`: `Software\Microsoft\Windows\CurrentVersion\Shell\Update\Packages\MicrosoftWindows.Client.AIX_cw5n1h2txyewy`
- `0x18002bb35`: `Software\Microsoft\Windows\CurrentVersion\Shell\Update\Packages\MicrosoftWindows.Client.AIX_cw5n1h2txyewy`
- `0x18002b89f`: `SOFTWARE\Microsoft\Windows\CurrentVersion\WindowsAI\LastConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
bool __fastcall AIXPolicyHelper::ShouldRunPolicyConfigurationTask(
        AIXPolicyHelper *this,
        enum ShouldRunPolicyTaskReason *a2)
{
  char v3; // r12
  AIXPolicyHelper *v4; // rcx
  bool v6; // di
  bool IsPolicyConfigured; // si
  __int64 value_dword; // rax
  AIXPolicyHelper *v9; // rcx
  int v10; // eax
  bool IsPolicyConfiguredAndAllowed; // r14
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rax
  int v15; // esi
  char v16; // r14
  AIXPolicyHelper *v17; // rcx
  __int64 v18; // rax
  __int64 v19; // rax
  AIXPolicyHelper *v20; // rcx
  int v21; // esi
  bool IsDeviceITManaged; // r13
  bool v23; // r15
  __int64 v24; // rax
  AIXPolicyHelper *v25; // rcx
  int v26; // esi
  char v27; // r14
  __int64 v28; // rax
  int v29; // eax
  unsigned int v30; // esi
  unsigned int LastOperationKind; // eax
  __int64 v32; // rax
  const struct _tlgProvider_t *v33; // rcx
  _DWORD *v34; // rax
  AIXPolicyHelper *v35; // rcx
  bool v36; // si
  bool v37; // bl
  AIXTelemetry *v38; // rcx
  enum LastOperationKind *v39; // [rsp+40h] [rbp-49h]
  bool v40; // [rsp+48h] [rbp-41h]
  unsigned int v41; // [rsp+48h] [rbp-41h]
  bool v42; // [rsp+50h] [rbp-39h]
  bool v43; // [rsp+51h] [rbp-38h]
  bool v44; // [rsp+52h] [rbp-37h]
  HKEY phkResult; // [rsp+58h] [rbp-31h] BYREF
  HKEY v46; // [rsp+60h] [rbp-29h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-21h] BYREF
  char v48[32]; // [rsp+70h] [rbp-19h] BYREF

  v3 = 0;
  *(_DWORD *)this = 0;
  phkResult = 0;
  wil::reg::open_unique_key_nothrow(
    HKEY_LOCAL_MACHINE,
    L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WindowsAI\\LastConfiguration",
    &phkResult);
  if ( !phkResult )
    return 0;
  v6 = 0;
  IsPolicyConfigured = AIXPolicyHelper::IsPolicyConfigured(v4);
  v43 = IsPolicyConfigured;
  value_dword = wil::reg::try_get_value_dword(&v46, phkResult, c_policyConfigured);
  if ( *(_BYTE *)(value_dword + 4) )
    v10 = *(_DWORD *)value_dword;
  else
    v10 = 0;
  if ( (v10 != 0) != IsPolicyConfigured )
  {
    v6 = 1;
    *(_DWORD *)this |= 1u;
  }
  IsPolicyConfiguredAndAllowed = AIXPolicyHelper::IsPolicyConfiguredAndAllowed(v9);
  v44 = IsPolicyConfiguredAndAllowed;
  if ( IsPolicyConfigured )
  {
    v12 = wil::reg::try_get_value_dword(&v46, phkResult, c_policyConfiguredAndEnabled);
    v13 = *(_BYTE *)(v12 + 4) ? *(_DWORD *)v12 : 0;
    if ( (v13 != 0) != IsPolicyConfiguredAndAllowed )
    {
      v6 = 1;
      *(_DWORD *)this |= 2u;
    }
  }
  v14 = wil::reg::try_get_value_dword(&v46, phkResult, c_hardwareCompatible);
  if ( *(_BYTE *)(v14 + 4) )
    v15 = *(_DWORD *)v14;
  else
    v15 = 0;
  LODWORD(hKey) = 1;
  v16 = winrt::WindowsUdk::System::Profile::HardwareRequirements::MeetsRequirement((const enum winrt::WindowsUdk::System::Profile::HardwareRequirement *)&hKey);
  v42 = v16;
  if ( (v15 != 0) != v16 )
  {
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57306871>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57306871>::GetImpl'::`2'::impl)
      || v16
      || (hKey = 0,
          wil::reg::open_unique_key_nothrow(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell\\Update\\Packages\\MicrosoftWindows.Client.AIX_cw5n1h2txyewy",
            &hKey),
          !hKey)
      || (RegCloseKey(hKey), !AIXPolicyHelper::IsLCUVersionChanged(v17)) )
    {
      v6 = 1;
      *(_DWORD *)this |= 4u;
    }
  }
  v18 = wil::reg::try_get_value_dword(&v46, phkResult, c_allowedInRegion);
  if ( !*(_BYTE *)(v18 + 4) || !*(_DWORD *)v18 )
  {
    v6 = 1;
    *(_DWORD *)this |= 8u;
  }
  v19 = wil::reg::try_get_value_dword(&v46, phkResult, c_itManaged);
  if ( *(_BYTE *)(v19 + 4) )
    v21 = *(_DWORD *)v19;
  else
    v21 = 0;
  IsDeviceITManaged = AIXPolicyHelper::IsDeviceITManaged(v20);
  if ( (v21 != 0) != IsDeviceITManaged )
  {
    v6 = 1;
    *(_DWORD *)this |= 0x10u;
  }
  v23 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55856303>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55856303>::GetImpl'::`2'::impl) )
  {
    v24 = wil::reg::try_get_value_dword(&v46, phkResult, c_meetsAdditionalDriverRequirements);
    v26 = *(_BYTE *)(v24 + 4) ? *(_DWORD *)v24 : 0;
    v23 = AIXPolicyHelper::MeetsAdditionalDriverRequirements(v25);
    if ( (v26 != 0) != v23 )
    {
      v6 = 1;
      *(_DWORD *)this |= 0x20u;
    }
  }
  v27 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID45522024>::GetImpl'::`2'::impl)
      ^ 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57247651>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57247651>::GetImpl'::`2'::impl) )
  {
    v28 = wil::reg::try_get_value_dword(&v46, phkResult, c_recallDisabledState);
    v29 = *(_BYTE *)(v28 + 4) ? *(_DWORD *)v28 : 0;
    if ( (v29 != 0) != v27 )
    {
      v6 = 1;
      *(_DWORD *)this |= 0x40u;
    }
  }
  v30 = 0;
  LODWORD(hKey) = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769617>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56769617>::GetImpl'::`2'::impl) )
  {
    LastOperationKind = AIXPolicyHelper::GetLastOperationKind();
    v30 = LastOperationKind;
    LODWORD(hKey) = LastOperationKind;
    if ( (LastOperationKind & 0xFFFFFFFC) == 0 && LastOperationKind != 2 )
    {
      v6 = 1;
      *(_DWORD *)this |= 0x80u;
    }
    v32 = wil::reg::try_get_value_dword(&v46, phkResult, c_desiredStateMismatch);
    if ( (!*(_BYTE *)(v32 + 4) || !*(_DWORD *)v32) && v30 == 2 )
    {
      v46 = 0;
      wil::reg::open_unique_key_nothrow(
        HKEY_LOCAL_MACHINE,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell\\Update\\Packages\\MicrosoftWindows.Client.AIX_cw5n1h2txyewy",
        &v46);
      if ( v46 )
      {
        RegCloseKey(v46);
      }
      else if ( !(unsigned __int8)AIXPolicyHelper::ShouldRemoveComponent(0) )
      {
        v33 = AIXTelemetryLogging::Provider();
        if ( *(_DWORD *)v33 > 5u )
          tlgWriteTransfer_EventWriteTransfer(v33, &byte_18003A097, 0, 0, 2, v48);
        v6 = 1;
        v3 = 1;
        *(_DWORD *)this |= 0x100u;
      }
    }
  }
  v34 = (_DWORD *)*((_QWORD *)AIXTelemetry::Instance() + 1);
  if ( v34 && *v34 )
  {
    AIXTelemetry::Instance();
    v41 = v30;
    v36 = v43;
    v37 = v42;
    AIXTelemetry::PolicyTaskShouldRun_(v38, v6, v42, IsDeviceITManaged, 1, v43, v44, v23, v27, v41);
  }
  else
  {
    v36 = v43;
    v37 = v42;
  }
  LOBYTE(v39) = v3;
  LOBYTE(v35) = v37;
  AIXPolicyHelper::StoreConfigState(v35, IsDeviceITManaged, 1, v36, v44, v23, v27, (bool)&hKey, v39, v40);
  if ( phkResult )
    RegCloseKey(phkResult);
  return v6;
}

```

## disassembly

```asm
0x18002b864  push    rbp
0x18002b866  push    rbx
0x18002b867  push    rsi
0x18002b868  push    rdi
0x18002b869  push    r12
0x18002b86b  push    r13
0x18002b86d  push    r14
0x18002b86f  push    r15
0x18002b871  lea     rbp, [rsp-1Fh]
0x18002b876  sub     rsp, 0A8h
0x18002b87d  mov     rax, cs:__security_cookie
0x18002b884  xor     rax, rsp
0x18002b887  mov     [rbp+57h+var_50], rax
0x18002b88b  mov     rbx, rcx
0x18002b88e  xor     r12d, r12d
0x18002b891  mov     [rcx], r12d
0x18002b894  mov     [rbp+57h+phkResult], r12
0x18002b898  xor     r9d, r9d
0x18002b89b  lea     r8, [rbp+57h+phkResult]; phkResult
0x18002b89f  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x18002b8a6  mov     r15, 0FFFFFFFF80000002h
0x18002b8ad  mov     rcx, r15; hKey
0x18002b8b0  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18002b8b5  cmp     [rbp+57h+phkResult], r12
0x18002b8b9  jnz     short loc_18002B8C2
0x18002b8bb  xor     al, al
0x18002b8bd  jmp     loc_18002BC36
0x18002b8c2  mov     dil, r12b
0x18002b8c5  call    ?IsPolicyConfigured@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsPolicyConfigured(void)
0x18002b8ca  mov     sil, al
0x18002b8cd  mov     byte ptr [rbp+57h+var_90+1], al
0x18002b8d0  mov     r8, cs:?c_policyConfigured@@3QEBGEB; ushort const * const c_policyConfigured
0x18002b8d7  mov     rdx, [rbp+57h+phkResult]
0x18002b8db  lea     rcx, [rbp+57h+var_80]
0x18002b8df  call    ?try_get_value_dword@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEBG@Z; wil::reg::try_get_value_dword(HKEY__ *,ushort const *)
0x18002b8e4  cmp     [rax+4], r12b
0x18002b8e8  jz      short loc_18002B8EE
0x18002b8ea  mov     eax, [rax]
0x18002b8ec  jmp     short loc_18002B8F1
0x18002b8ee  mov     eax, r12d
0x18002b8f1  test    eax, eax
0x18002b8f3  setnz   al
0x18002b8f6  cmp     al, sil
0x18002b8f9  jz      short loc_18002B901
0x18002b8fb  mov     dil, 1
0x18002b8fe  or      dword ptr [rbx], 1
0x18002b901  call    ?IsPolicyConfiguredAndAllowed@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsPolicyConfiguredAndAllowed(void)
0x18002b906  mov     r14b, al
0x18002b909  mov     byte ptr [rbp+57h+var_90+2], al
0x18002b90c  test    sil, sil
0x18002b90f  jz      short loc_18002B942
0x18002b911  mov     r8, cs:?c_policyConfiguredAndEnabled@@3QEBGEB; ushort const * const c_policyConfiguredAndEnabled
0x18002b918  mov     rdx, [rbp+57h+phkResult]
0x18002b91c  lea     rcx, [rbp+57h+var_80]
0x18002b920  call    ?try_get_value_dword@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEBG@Z; wil::reg::try_get_value_dword(HKEY__ *,ushort const *)
0x18002b925  cmp     [rax+4], r12b
0x18002b929  jz      short loc_18002B92F
0x18002b92b  mov     eax, [rax]
0x18002b92d  jmp     short loc_18002B932
0x18002b92f  mov     eax, r12d
0x18002b932  test    eax, eax
0x18002b934  setnz   al
0x18002b937  cmp     al, r14b
0x18002b93a  jz      short loc_18002B942
0x18002b93c  mov     dil, 1
0x18002b93f  or      dword ptr [rbx], 2
0x18002b942  mov     r8, cs:?c_hardwareCompatible@@3QEBGEB; ushort const * const c_hardwareCompatible
0x18002b949  mov     rdx, [rbp+57h+phkResult]
0x18002b94d  lea     rcx, [rbp+57h+var_80]
0x18002b951  call    ?try_get_value_dword@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEBG@Z; wil::reg::try_get_value_dword(HKEY__ *,ushort const *)
0x18002b956  cmp     [rax+4], r12b
0x18002b95a  jz      short loc_18002B960
0x18002b95c  mov     esi, [rax]
0x18002b95e  jmp     short loc_18002B963
0x18002b960  mov     esi, r12d
0x18002b963  mov     dword ptr [rbp+57h+hKey], 1
0x18002b96a  lea     rcx, [rbp+57h+hKey]; enum winrt::WindowsUdk::System::Profile::HardwareRequirement *
0x18002b96e  call    ?MeetsRequirement@HardwareRequirements@Profile@System@WindowsUdk@winrt@@SA@AEBW4HardwareRequirement@2345@@Z; winrt::WindowsUdk::System::Profile::HardwareRequirements::MeetsRequirement(winrt::WindowsUdk::System::Profile::HardwareRequirement const &)
0x18002b973  mov     r14b, al
0x18002b976  mov     byte ptr [rbp+57h+var_90], al
0x18002b979  test    esi, esi
0x18002b97b  setnz   al
0x18002b97e  cmp     al, r14b
0x18002b981  jz      short loc_18002B9D0
0x18002b983  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57306871@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57306871@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57306871> `wil::Feature<__WilFeatureTraits_Feature_57306871>::GetImpl(void)'::`2'::impl
0x18002b98a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57306871@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57306871>::__private_IsEnabled(void)
0x18002b98f  test    al, al
0x18002b991  jz      short loc_18002B9CA
0x18002b993  test    r14b, r14b
0x18002b996  jnz     short loc_18002B9CA
0x18002b998  mov     [rbp+57h+hKey], r12
0x18002b99c  xor     r9d, r9d
0x18002b99f  lea     r8, [rbp+57h+hKey]; phkResult
0x18002b9a3  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002b9aa  mov     rcx, r15; hKey
0x18002b9ad  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18002b9b2  mov     rcx, [rbp+57h+hKey]; hKey
0x18002b9b6  test    rcx, rcx
0x18002b9b9  jz      short loc_18002B9CA
0x18002b9bb  call    cs:__imp_RegCloseKey
0x18002b9c1  call    ?IsLCUVersionChanged@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsLCUVersionChanged(void)
0x18002b9c6  test    al, al
0x18002b9c8  jnz     short loc_18002B9D0
0x18002b9ca  mov     dil, 1
0x18002b9cd  or      dword ptr [rbx], 4
0x18002b9d0  mov     r8, cs:?c_allowedInRegion@@3QEBGEB; ushort const * const c_allowedInRegion
0x18002b9d7  mov     rdx, [rbp+57h+phkResult]
0x18002b9db  lea     rcx, [rbp+57h+var_80]
0x18002b9df  call    ?try_get_value_dword@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEBG@Z; wil::reg::try_get_value_dword(HKEY__ *,ushort const *)
0x18002b9e4  cmp     [rax+4], r12b
0x18002b9e8  jz      short loc_18002B9EF
0x18002b9ea  cmp     [rax], r12d
0x18002b9ed  jnz     short loc_18002B9F5
0x18002b9ef  mov     dil, 1
0x18002b9f2  or      dword ptr [rbx], 8
0x18002b9f5  mov     r8, cs:?c_itManaged@@3QEBGEB; ushort const * const c_itManaged
0x18002b9fc  mov     rdx, [rbp+57h+phkResult]
0x18002ba00  lea     rcx, [rbp+57h+var_80]
0x18002ba04  call    ?try_get_value_dword@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEBG@Z; wil::reg::try_get_value_dword(HKEY__ *,ushort const *)
0x18002ba09  cmp     [rax+4], r12b
0x18002ba0d  jz      short loc_18002BA13
0x18002ba0f  mov     esi, [rax]
0x18002ba11  jmp     short loc_18002BA16
0x18002ba13  mov     esi, r12d
0x18002ba16  call    ?IsDeviceITManaged@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsDeviceITManaged(void)
0x18002ba1b  mov     r13b, al
0x18002ba1e  test    esi, esi
0x18002ba20  setnz   al
0x18002ba23  cmp     al, r13b
0x18002ba26  jz      short loc_18002BA2E
0x18002ba28  mov     dil, 1
0x18002ba2b  or      dword ptr [rbx], 10h
0x18002ba2e  mov     r15b, r12b
0x18002ba31  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55856303@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55856303@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55856303> `wil::Feature<__WilFeatureTraits_Feature_55856303>::GetImpl(void)'::`2'::impl
0x18002ba38  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55856303@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55856303>::__private_IsEnabled(void)
0x18002ba3d  test    al, al
0x18002ba3f  jz      short loc_18002BA7A
0x18002ba41  mov     r8, cs:?c_meetsAdditionalDriverRequirements@@3QEBGEB; ushort const * const c_meetsAdditionalDriverRequirements
0x18002ba48  mov     rdx, [rbp+57h+phkResult]
0x18002ba4c  lea     rcx, [rbp+57h+var_80]
0x18002ba50  call    ?try_get_value_dword@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEBG@Z; wil::reg::try_get_value_dword(HKEY__ *,ushort const *)
0x18002ba55  cmp     [rax+4], r12b
0x18002ba59  jz      short loc_18002BA5F
0x18002ba5b  mov     esi, [rax]
0x18002ba5d  jmp     short loc_18002BA62
0x18002ba5f  mov     esi, r12d
0x18002ba62  call    ?MeetsAdditionalDriverRequirements@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::MeetsAdditionalDriverRequirements(void)
0x18002ba67  mov     r15b, al
0x18002ba6a  test    esi, esi
0x18002ba6c  setnz   al
0x18002ba6f  cmp     al, r15b
0x18002ba72  jz      short loc_18002BA7A
0x18002ba74  mov     dil, 1
0x18002ba77  or      dword ptr [rbx], 20h
0x18002ba7a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID45522024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID45522024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024> `wil::Feature<__WilFeatureTraits_Feature_ID45522024>::GetImpl(void)'::`2'::impl
0x18002ba81  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID45522024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024>::__private_IsEnabled(void)
0x18002ba86  mov     r14b, al
0x18002ba89  xor     r14b, 1
0x18002ba8d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57247651@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57247651@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57247651> `wil::Feature<__WilFeatureTraits_Feature_57247651>::GetImpl(void)'::`2'::impl
0x18002ba94  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57247651@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57247651>::__private_IsEnabled(void)
0x18002ba99  test    al, al
0x18002ba9b  jz      short loc_18002BACE
0x18002ba9d  mov     r8, cs:?c_recallDisabledState@@3QEBGEB; ushort const * const c_recallDisabledState
0x18002baa4  mov     rdx, [rbp+57h+phkResult]
0x18002baa8  lea     rcx, [rbp+57h+var_80]
0x18002baac  call    ?try_get_value_dword@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEBG@Z; wil::reg::try_get_value_dword(HKEY__ *,ushort const *)
0x18002bab1  cmp     [rax+4], r12b
0x18002bab5  jz      short loc_18002BABB
0x18002bab7  mov     eax, [rax]
0x18002bab9  jmp     short loc_18002BABE
0x18002babb  mov     eax, r12d
0x18002babe  test    eax, eax
0x18002bac0  setnz   al
0x18002bac3  cmp     al, r14b
0x18002bac6  jz      short loc_18002BACE
0x18002bac8  mov     dil, 1
0x18002bacb  or      dword ptr [rbx], 40h
0x18002bace  mov     esi, r12d
0x18002bad1  mov     dword ptr [rbp+57h+hKey], r12d
0x18002bad5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56769617@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56769617@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769617> `wil::Feature<__WilFeatureTraits_Feature_56769617>::GetImpl(void)'::`2'::impl
0x18002badc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56769617@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56769617>::__private_IsEnabled(void)
0x18002bae1  test    al, al
0x18002bae3  jz      loc_18002BB9E
0x18002bae9  call    ?GetLastOperationKind@AIXPolicyHelper@@YA?AW4LastOperationKind@@XZ; AIXPolicyHelper::GetLastOperationKind(void)
0x18002baee  mov     esi, eax
0x18002baf0  mov     dword ptr [rbp+57h+hKey], eax
0x18002baf3  test    eax, 0FFFFFFFCh
0x18002baf8  jnz     short loc_18002BB06
0x18002bafa  cmp     eax, 2
0x18002bafd  jz      short loc_18002BB06
0x18002baff  mov     dil, 1
0x18002bb02  bts     dword ptr [rbx], 7
0x18002bb06  mov     r8, cs:?c_desiredStateMismatch@@3QEBGEB; ushort const * const c_desiredStateMismatch
0x18002bb0d  mov     rdx, [rbp+57h+phkResult]
0x18002bb11  lea     rcx, [rbp+57h+var_80]
0x18002bb15  call    ?try_get_value_dword@reg@wil@@YA?AV?$optional@I@std@@PEAUHKEY__@@PEBG@Z; wil::reg::try_get_value_dword(HKEY__ *,ushort const *)
0x18002bb1a  xor     ecx, ecx
0x18002bb1c  cmp     [rax+4], cl
0x18002bb1f  jz      short loc_18002BB25
0x18002bb21  cmp     [rax], ecx
0x18002bb23  jnz     short loc_18002BB9E
0x18002bb25  cmp     esi, 2
0x18002bb28  jnz     short loc_18002BB9E
0x18002bb2a  mov     [rbp+57h+var_80], rcx
0x18002bb2e  xor     r9d, r9d
0x18002bb31  lea     r8, [rbp+57h+var_80]; phkResult
0x18002bb35  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18002bb3c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002bb43  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18002bb48  mov     rcx, [rbp+57h+var_80]; hKey
0x18002bb4c  test    rcx, rcx
0x18002bb4f  jz      short loc_18002BB59
0x18002bb51  call    cs:__imp_RegCloseKey
0x18002bb57  jmp     short loc_18002BB9E
0x18002bb59  call    ?ShouldRemoveComponent@AIXPolicyHelper@@YA_NW4ShouldRemoveComponentFlags@@@Z; AIXPolicyHelper::ShouldRemoveComponent(ShouldRemoveComponentFlags)
0x18002bb5e  test    al, al
0x18002bb60  jnz     short loc_18002BB9E
0x18002bb62  call    ?Provider@AIXTelemetryLogging@@SAPEBU_tlgProvider_t@@XZ; AIXTelemetryLogging::Provider(void)
0x18002bb67  mov     rcx, rax
0x18002bb6a  mov     eax, [rax]
0x18002bb6c  cmp     eax, 5
0x18002bb6f  jbe     short loc_18002BB94
0x18002bb71  lea     rax, [rbp+57h+var_70]
0x18002bb75  mov     qword ptr [rsp+0E0h+var_B8], rax
0x18002bb7a  mov     dword ptr [rsp+0E0h+var_C0], 2
0x18002bb82  xor     r9d, r9d
0x18002bb85  xor     r8d, r8d
0x18002bb88  lea     rdx, byte_18003A097
0x18002bb8f  call    _tlgWriteTransfer_EventWriteTransfer
0x18002bb94  mov     dil, 1
0x18002bb97  mov     r12b, dil
0x18002bb9a  bts     dword ptr [rbx], 8
0x18002bb9e  call    ?Instance@AIXTelemetry@@KAPEAV1@XZ; AIXTelemetry::Instance(void)
0x18002bba3  mov     rax, [rax+8]
0x18002bba7  test    rax, rax
0x18002bbaa  jz      short loc_18002BBED
0x18002bbac  mov     eax, [rax]
0x18002bbae  test    eax, eax
0x18002bbb0  jz      short loc_18002BBED
0x18002bbb2  call    ?Instance@AIXTelemetry@@KAPEAV1@XZ; AIXTelemetry::Instance(void)
0x18002bbb7  mov     [rsp+0E0h+var_98], esi; unsigned int
0x18002bbbb  mov     byte ptr [rsp+0E0h+var_A0], r14b; bool
0x18002bbc0  mov     [rsp+0E0h+var_A8], r15b; bool
0x18002bbc5  mov     al, byte ptr [rbp+57h+var_90+2]
0x18002bbc8  mov     [rsp+0E0h+var_B0], al; bool
0x18002bbcc  mov     sil, byte ptr [rbp+57h+var_90+1]
0x18002bbd0  mov     [rsp+0E0h+var_B8], sil; bool
0x18002bbd5  mov     [rsp+0E0h+var_C0], 1; bool
0x18002bbda  mov     r9b, r13b; bool
0x18002bbdd  mov     bl, byte ptr [rbp+57h+var_90]
0x18002bbe0  mov     r8b, bl; bool
0x18002bbe3  mov     dl, dil; bool
0x18002bbe6  call    ?PolicyTaskShouldRun_@AIXTelemetry@@QEAAX_N0000000K@Z; AIXTelemetry::PolicyTaskShouldRun_(bool,bool,bool,bool,bool,bool,bool,bool,ulong)
0x18002bbeb  jmp     short loc_18002BBF4
0x18002bbed  mov     sil, byte ptr [rbp+57h+var_90+1]
0x18002bbf1  mov     bl, byte ptr [rbp+57h+var_90]
0x18002bbf4  mov     byte ptr [rsp+0E0h+var_A0], r12b; enum LastOperationKind *
0x18002bbf9  lea     rax, [rbp+57h+hKey]
0x18002bbfd  mov     qword ptr [rsp+0E0h+var_A8], rax; bool
0x18002bc02  mov     [rsp+0E0h+var_B0], r14b; bool
0x18002bc07  mov     [rsp+0E0h+var_B8], r15b; bool
0x18002bc0c  mov     al, byte ptr [rbp+57h+var_90+2]
0x18002bc0f  mov     [rsp+0E0h+var_C0], al; bool
0x18002bc13  mov     r9b, sil; bool
0x18002bc16  mov     r8b, 1; bool
0x18002bc19  mov     dl, r13b; bool
0x18002bc1c  mov     cl, bl; this
0x18002bc1e  call    ?StoreConfigState@AIXPolicyHelper@@YAX_N000000PEAW4LastOperationKind@@0@Z; AIXPolicyHelper::StoreConfigState(bool,bool,bool,bool,bool,bool,bool,LastOperationKind *,bool)
0x18002bc23  nop
0x18002bc24  mov     rcx, [rbp+57h+phkResult]; hKey
0x18002bc28  test    rcx, rcx
0x18002bc2b  jz      short loc_18002BC33
0x18002bc2d  call    cs:__imp_RegCloseKey
0x18002bc33  mov     al, dil
0x18002bc36  mov     rcx, [rbp+57h+var_50]
0x18002bc3a  xor     rcx, rsp; StackCookie
0x18002bc3d  call    __security_check_cookie
0x18002bc42  add     rsp, 0A8h
0x18002bc49  pop     r15
0x18002bc4b  pop     r14
0x18002bc4d  pop     r13
0x18002bc4f  pop     r12
0x18002bc51  pop     rdi
0x18002bc52  pop     rsi
0x18002bc53  pop     rbx
0x18002bc54  pop     rbp
0x18002bc55  retn
```
