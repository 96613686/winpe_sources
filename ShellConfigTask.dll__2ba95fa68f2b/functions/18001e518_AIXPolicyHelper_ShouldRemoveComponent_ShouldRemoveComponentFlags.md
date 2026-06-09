# AIXPolicyHelper::ShouldRemoveComponent(ShouldRemoveComponentFlags)

- ea: `0x18001e518`
- end: `0x18001e78e`
- name: `?ShouldRemoveComponent@AIXPolicyHelper@@YA_NW4ShouldRemoveComponentFlags@@@Z`
- size: `630`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `3`
- callee_count: `22`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001fd50`
- `0x18002b864`
- `0x18002d050`

## callees

- `0x18001bf24`
- `0x18001c81c`
- `0x18001c988`
- `0x18001cb74`
- `0x18001cc08`
- `0x18001cce4`
- `0x18001d048`
- `0x18001d0d4`
- `0x18001d2a4`
- `0x18001d484`
- `0x18001d63c`
- `0x18001e518`
- `0x18001e794`
- `0x18001ed90`
- `0x180020bbc`
- `0x180020d3c`
- `0x180020fbc`
- `0x18002105c`
- `0x1800210fc`
- `0x18002119c`
- `0x18002131c`
- `0x1800233ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e5c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6e4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e5c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001e6e4`

## string_xrefs

- `0x18001e5af`: `Software\Microsoft\Windows\CurrentVersion\Shell\Update\Packages\MicrosoftWindows.Client.AIX_cw5n1h2txyewy`
- `0x18001e6cb`: `Software\Microsoft\Windows\CurrentVersion\Shell\Update\Packages\MicrosoftWindows.Client.AIX_cw5n1h2txyewy`

## pseudocode

```c
bool __fastcall AIXPolicyHelper::ShouldRemoveComponent(AIXPolicyHelper *a1)
{
  bool IsEnterpriseSKU; // r12
  AIXPolicyHelper *v2; // rcx
  bool IsEduSku; // r13
  AIXPolicyHelper *v4; // rcx
  bool IsDeviceITManaged; // al
  bool v6; // r15
  char v7; // si
  char IsAllowedOnDeviceByPolicy; // bl
  AIXPolicyHelper *v9; // rcx
  AIXPolicyHelper *v10; // rcx
  bool v11; // di
  bool v12; // r14
  AIXPolicyHelper *v13; // rcx
  bool v14; // al
  char v15; // bp
  bool IsDLPProviderPolicyConfigured; // bl
  AIXPolicyHelper *v17; // rcx
  bool v18; // cl
  AIXPolicyHelper *v19; // rcx
  bool IsPolicyConfiguredAndAllowed; // bl
  AIXPolicyHelper *v21; // rcx
  unsigned __int8 IsPolicyConfigured; // al
  AIXPolicyHelper *v23; // rcx
  enum LastOperationKind *v25; // [rsp+40h] [rbp-68h]
  char v26; // [rsp+B0h] [rbp+8h]
  BOOL v27; // [rsp+B8h] [rbp+10h] BYREF
  bool IsWipUser; // [rsp+C0h] [rbp+18h]
  HKEY hKey; // [rsp+C8h] [rbp+20h] BYREF

  v26 = (char)a1;
  IsEnterpriseSKU = AIXPolicyHelper::IsEnterpriseSKU(a1);
  IsEduSku = AIXPolicyHelper::IsEduSku(v2);
  IsDeviceITManaged = AIXPolicyHelper::IsDeviceITManaged(v4);
  v27 = 1;
  v6 = IsDeviceITManaged;
  v7 = winrt::WindowsUdk::System::Profile::HardwareRequirements::MeetsRequirement((const enum winrt::WindowsUdk::System::Profile::HardwareRequirement *)&v27);
  IsAllowedOnDeviceByPolicy = AIXPolicyHelper::IsAllowedOnDeviceByPolicy(0);
  LOBYTE(v27) = IsAllowedOnDeviceByPolicy;
  IsWipUser = AIXPolicyHelper::IsWipUser(v9);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57306871>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57306871>::GetImpl'::`2'::impl) )
  {
    if ( !v7 )
    {
      hKey = 0;
      wil::reg::open_unique_key_nothrow(
        HKEY_LOCAL_MACHINE,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell\\Update\\Packages\\MicrosoftWindows.Client.AIX_cw5n1h2txyewy",
        &hKey,
        0);
      if ( hKey )
      {
        RegCloseKey(hKey);
        v7 = AIXPolicyHelper::IsLCUVersionChanged(v10) != 0;
      }
    }
  }
  v11 = IsEnterpriseSKU || IsEduSku || v6 || !v7 || !IsAllowedOnDeviceByPolicy;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55136573>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55136573>::GetImpl'::`2'::impl) )
    v11 = (!IsAllowedOnDeviceByPolicy || !v7) && (IsEnterpriseSKU || IsEduSku || v6 || !v7);
  v12 = 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_55856303>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_55856303>::GetImpl'::`2'::impl) )
  {
    v14 = AIXPolicyHelper::MeetsAdditionalDriverRequirements(v13);
    v12 = v14;
    if ( v11 || !v14 )
      v11 = 1;
  }
  v15 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ID45522024>::GetImpl'::`2'::impl)
      ^ 1;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57247651>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57247651>::GetImpl'::`2'::impl)
    && (v11 || v15) )
  {
    v11 = 1;
  }
  IsDLPProviderPolicyConfigured = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_58474338>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_58474338>::GetImpl'::`2'::impl) )
    IsDLPProviderPolicyConfigured = AIXPolicyHelper::IsDLPProviderPolicyConfigured(v17);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_57798780>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_57798780>::GetImpl'::`2'::impl)
    && (hKey = 0,
        wil::reg::open_unique_key_nothrow(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Shell\\Update\\Packages\\MicrosoftWindows.Client.AIX_cw5n1h2txyewy",
          &hKey,
          0),
        hKey) )
  {
    RegCloseKey(hKey);
    v18 = 1;
  }
  else
  {
    v18 = 0;
  }
  AIXTelemetry::ShouldRemoveComponent(
    v11,
    IsEnterpriseSKU,
    IsEduSku,
    v6,
    v7,
    1,
    IsWipUser,
    v27,
    !v12,
    v15,
    v18,
    IsDLPProviderPolicyConfigured);
  if ( (v26 & 1) != 0 )
  {
    IsPolicyConfiguredAndAllowed = AIXPolicyHelper::IsPolicyConfiguredAndAllowed(v19);
    IsPolicyConfigured = AIXPolicyHelper::IsPolicyConfigured(v21);
    LOBYTE(v25) = 0;
    LOBYTE(v23) = v7;
    AIXPolicyHelper::StoreConfigState(v23, v6, 1u, IsPolicyConfigured, IsPolicyConfiguredAndAllowed, v12, v15, 0, v25);
  }
  return v11;
}

```

## disassembly

```asm
0x18001e518  mov     [rsp+arg_0], ecx
0x18001e51c  push    rbx
0x18001e51d  push    rbp
0x18001e51e  push    rsi
0x18001e51f  push    rdi
0x18001e520  push    r12
0x18001e522  push    r13
0x18001e524  push    r14
0x18001e526  push    r15
0x18001e528  sub     rsp, 68h
0x18001e52c  call    ?IsEnterpriseSKU@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsEnterpriseSKU(void)
0x18001e531  mov     r12b, al
0x18001e534  call    ?IsEduSku@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsEduSku(void)
0x18001e539  mov     r13b, al
0x18001e53c  call    ?IsDeviceITManaged@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsDeviceITManaged(void)
0x18001e541  mov     ebp, 1
0x18001e546  lea     rcx, [rsp+0A8h+arg_8]; enum winrt::WindowsUdk::System::Profile::HardwareRequirement *
0x18001e54e  mov     [rsp+0A8h+arg_8], ebp
0x18001e555  mov     r15b, al
0x18001e558  call    ?MeetsRequirement@HardwareRequirements@Profile@System@WindowsUdk@winrt@@SA@AEBW4HardwareRequirement@2345@@Z; winrt::WindowsUdk::System::Profile::HardwareRequirements::MeetsRequirement(winrt::WindowsUdk::System::Profile::HardwareRequirement const &)
0x18001e55d  xor     ecx, ecx
0x18001e55f  movzx   esi, al
0x18001e562  call    ?IsAllowedOnDeviceByPolicy@AIXPolicyHelper@@YA_NW4AllowedOnDeviceByPolicyFlags@@@Z; AIXPolicyHelper::IsAllowedOnDeviceByPolicy(AllowedOnDeviceByPolicyFlags)
0x18001e567  mov     bl, al
0x18001e569  mov     byte ptr [rsp+0A8h+arg_8], al
0x18001e570  call    ?IsWipUser@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsWipUser(void)
0x18001e575  mov     [rsp+0A8h+arg_10], al
0x18001e57c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57306871@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57306871@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57306871> `wil::Feature<__WilFeatureTraits_Feature_57306871>::GetImpl(void)'::`2'::impl
0x18001e583  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57306871@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57306871>::__private_IsEnabled(void)
0x18001e588  test    al, al
0x18001e58a  jz      short loc_18001E5D8
0x18001e58c  test    sil, sil
0x18001e58f  jnz     short loc_18001E5D8
0x18001e591  xor     r9d, r9d
0x18001e594  mov     [rsp+0A8h+hKey], 0
0x18001e5a0  lea     r8, [rsp+0A8h+hKey]; phkResult
0x18001e5a8  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e5af  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001e5b6  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18001e5bb  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001e5c3  test    rcx, rcx
0x18001e5c6  jz      short loc_18001E5D8
0x18001e5c8  call    cs:__imp_RegCloseKey
0x18001e5ce  call    ?IsLCUVersionChanged@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsLCUVersionChanged(void)
0x18001e5d3  test    al, al
0x18001e5d5  cmovnz  esi, ebp
0x18001e5d8  test    r12b, r12b
0x18001e5db  jnz     short loc_18001E5F5
0x18001e5dd  test    r13b, r13b
0x18001e5e0  jnz     short loc_18001E5F5
0x18001e5e2  test    r15b, r15b
0x18001e5e5  jnz     short loc_18001E5F5
0x18001e5e7  test    sil, sil
0x18001e5ea  jz      short loc_18001E5F5
0x18001e5ec  test    bl, bl
0x18001e5ee  jz      short loc_18001E5F5
0x18001e5f0  xor     dil, dil
0x18001e5f3  jmp     short loc_18001E5F8
0x18001e5f5  mov     dil, bpl
0x18001e5f8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55136573@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55136573@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55136573> `wil::Feature<__WilFeatureTraits_Feature_55136573>::GetImpl(void)'::`2'::impl
0x18001e5ff  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55136573@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55136573>::__private_IsEnabled(void)
0x18001e604  test    al, al
0x18001e606  jz      short loc_18001E62D
0x18001e608  test    bl, bl
0x18001e60a  jz      short loc_18001E611
0x18001e60c  test    sil, sil
0x18001e60f  jnz     short loc_18001E625
0x18001e611  test    r12b, r12b
0x18001e614  jnz     short loc_18001E62A
0x18001e616  test    r13b, r13b
0x18001e619  jnz     short loc_18001E62A
0x18001e61b  test    r15b, r15b
0x18001e61e  jnz     short loc_18001E62A
0x18001e620  test    sil, sil
0x18001e623  jz      short loc_18001E62A
0x18001e625  xor     dil, dil
0x18001e628  jmp     short loc_18001E62D
0x18001e62a  mov     dil, bpl
0x18001e62d  mov     r14b, bpl
0x18001e630  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_55856303@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_55856303@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55856303> `wil::Feature<__WilFeatureTraits_Feature_55856303>::GetImpl(void)'::`2'::impl
0x18001e637  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_55856303@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_55856303>::__private_IsEnabled(void)
0x18001e63c  test    al, al
0x18001e63e  jz      short loc_18001E654
0x18001e640  call    ?MeetsAdditionalDriverRequirements@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::MeetsAdditionalDriverRequirements(void)
0x18001e645  mov     r14b, al
0x18001e648  test    dil, dil
0x18001e64b  jnz     short loc_18001E651
0x18001e64d  test    al, al
0x18001e64f  jnz     short loc_18001E654
0x18001e651  mov     dil, bpl
0x18001e654  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ID45522024@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ID45522024@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024> `wil::Feature<__WilFeatureTraits_Feature_ID45522024>::GetImpl(void)'::`2'::impl
0x18001e65b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ID45522024@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID45522024>::__private_IsEnabled(void)
0x18001e660  mov     bpl, al
0x18001e663  xor     bpl, 1
0x18001e667  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57247651@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57247651@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57247651> `wil::Feature<__WilFeatureTraits_Feature_57247651>::GetImpl(void)'::`2'::impl
0x18001e66e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57247651@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57247651>::__private_IsEnabled(void)
0x18001e673  test    al, al
0x18001e675  jz      short loc_18001E684
0x18001e677  test    dil, dil
0x18001e67a  jnz     short loc_18001E681
0x18001e67c  test    bpl, bpl
0x18001e67f  jz      short loc_18001E684
0x18001e681  mov     dil, 1
0x18001e684  xor     bl, bl
0x18001e686  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_58474338@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_58474338@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58474338> `wil::Feature<__WilFeatureTraits_Feature_58474338>::GetImpl(void)'::`2'::impl
0x18001e68d  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_58474338@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58474338>::__private_IsEnabled(void)
0x18001e692  test    al, al
0x18001e694  jz      short loc_18001E69D
0x18001e696  call    ?IsDLPProviderPolicyConfigured@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsDLPProviderPolicyConfigured(void)
0x18001e69b  mov     bl, al
0x18001e69d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_57798780@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_57798780@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57798780> `wil::Feature<__WilFeatureTraits_Feature_57798780>::GetImpl(void)'::`2'::impl
0x18001e6a4  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_57798780@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_57798780>::__private_IsEnabled(void)
0x18001e6a9  test    al, al
0x18001e6ab  jz      short loc_18001E6EE
0x18001e6ad  xor     r9d, r9d
0x18001e6b0  mov     [rsp+0A8h+hKey], 0
0x18001e6bc  lea     r8, [rsp+0A8h+hKey]; phkResult
0x18001e6c4  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001e6cb  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18001e6d2  call    ?open_unique_key_nothrow@reg@wil@@YAJPEAUHKEY__@@PEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@2@W4key_access@12@@Z; wil::reg::open_unique_key_nothrow(HKEY__ *,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> &,wil::reg::key_access)
0x18001e6d7  mov     rcx, [rsp+0A8h+hKey]; hKey
0x18001e6df  test    rcx, rcx
0x18001e6e2  jz      short loc_18001E6EE
0x18001e6e4  call    cs:__imp_RegCloseKey
0x18001e6ea  mov     cl, 1
0x18001e6ec  jmp     short loc_18001E6F0
0x18001e6ee  xor     cl, cl
0x18001e6f0  mov     [rsp+0A8h+var_50], bl; bool
0x18001e6f4  mov     al, r14b
0x18001e6f7  mov     [rsp+0A8h+var_58], cl; bool
0x18001e6fb  xor     al, 1
0x18001e6fd  mov     [rsp+0A8h+var_60], bpl; bool
0x18001e702  mov     r9b, r15b; bool
0x18001e705  mov     byte ptr [rsp+0A8h+var_68], al; bool
0x18001e709  mov     r8b, r13b; bool
0x18001e70c  mov     al, byte ptr [rsp+0A8h+arg_8]
0x18001e713  mov     dl, r12b; bool
0x18001e716  mov     [rsp+0A8h+var_70], al; bool
0x18001e71a  mov     cl, dil; bool
0x18001e71d  mov     al, [rsp+0A8h+arg_10]
0x18001e724  mov     [rsp+0A8h+var_78], al; bool
0x18001e728  mov     [rsp+0A8h+var_80], 1; bool
0x18001e72d  mov     [rsp+0A8h+var_88], sil; bool
0x18001e732  call    ?ShouldRemoveComponent@AIXTelemetry@@SAX_N00000000000@Z; AIXTelemetry::ShouldRemoveComponent(bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool,bool)
0x18001e737  test    byte ptr [rsp+0A8h+arg_0], 1
0x18001e73f  jz      short loc_18001E77A
0x18001e741  call    ?IsPolicyConfiguredAndAllowed@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsPolicyConfiguredAndAllowed(void)
0x18001e746  mov     bl, al
0x18001e748  call    ?IsPolicyConfigured@AIXPolicyHelper@@YA_NXZ; AIXPolicyHelper::IsPolicyConfigured(void)
0x18001e74d  mov     byte ptr [rsp+0A8h+var_68], 0; enum LastOperationKind *
0x18001e752  mov     r9b, al; bool
0x18001e755  mov     qword ptr [rsp+0A8h+var_70], 0; bool
0x18001e75e  mov     r8b, 1; bool
0x18001e761  mov     [rsp+0A8h+var_78], bpl; bool
0x18001e766  mov     dl, r15b; bool
0x18001e769  mov     [rsp+0A8h+var_80], r14b; bool
0x18001e76e  mov     cl, sil; this
0x18001e771  mov     [rsp+0A8h+var_88], bl; bool
0x18001e775  call    ?StoreConfigState@AIXPolicyHelper@@YAX_N000000PEAW4LastOperationKind@@0@Z; AIXPolicyHelper::StoreConfigState(bool,bool,bool,bool,bool,bool,bool,LastOperationKind *,bool)
0x18001e77a  mov     al, dil
0x18001e77d  add     rsp, 68h
0x18001e781  pop     r15
0x18001e783  pop     r14
0x18001e785  pop     r13
0x18001e787  pop     r12
0x18001e789  pop     rdi
0x18001e78a  pop     rsi
0x18001e78b  pop     rbp
0x18001e78c  pop     rbx
0x18001e78d  retn
```
