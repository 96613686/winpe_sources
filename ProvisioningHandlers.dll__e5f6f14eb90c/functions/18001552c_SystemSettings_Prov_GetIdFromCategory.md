# SystemSettings::Prov::GetIdFromCategory

- ea: `0x18001552c`
- end: `0x1800156dd`
- name: `SystemSettings::Prov::GetIdFromCategory`
- size: `433`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d764`

## callees

- `0x18001552c`
- `0x18002019c`

## string_xrefs

- `0x1800155e3`: `SystemSettingsProvisioningPackageAffects_ContentCategorySecurity`

## pseudocode

```c
__int64 __fastcall SystemSettings::Prov::GetIdFromCategory(unsigned int a1, __int64 a2)
{
  unsigned int v3; // ecx
  unsigned int v4; // ecx
  unsigned int v5; // ecx
  unsigned int v6; // ecx
  const wchar_t *v7; // rdx
  const char *v8; // r9
  unsigned int v9; // ecx
  unsigned int v10; // ecx
  unsigned int v11; // ecx
  unsigned int v12; // ecx
  unsigned int v13; // ecx
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a1 <= 0xC )
  {
    if ( a1 == 12 )
    {
      v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryConnectivity";
      goto LABEL_56;
    }
    if ( a1 > 6 )
    {
      v9 = a1 - 7;
      if ( !v9 )
      {
        v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryCertificates";
        goto LABEL_56;
      }
      v10 = v9 - 1;
      if ( !v10 )
      {
        v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryUXLockdown";
        goto LABEL_56;
      }
      v11 = v10 - 1;
      if ( !v11 )
      {
        v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategorySecurity";
        goto LABEL_56;
      }
      v12 = v11 - 1;
      if ( !v12 )
      {
        v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryContent";
        goto LABEL_56;
      }
      if ( v12 == 1 )
      {
        v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryLegacy";
        goto LABEL_56;
      }
    }
    else
    {
      if ( a1 == 6 )
      {
        v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryApplications";
        goto LABEL_56;
      }
      if ( !a1 )
      {
        v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryNone";
        goto LABEL_56;
      }
      v3 = a1 - 1;
      if ( !v3 )
      {
        v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryProvisioning";
        goto LABEL_56;
      }
      v4 = v3 - 1;
      if ( !v4 )
      {
        v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryReboot";
        goto LABEL_56;
      }
      v5 = v4 - 1;
      if ( !v5 )
      {
        v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryLanguages";
        goto LABEL_56;
      }
      v6 = v5 - 1;
      if ( !v6 )
      {
        v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryDrivers";
        goto LABEL_56;
      }
      if ( v6 == 1 )
      {
        v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryInitialCustomization";
LABEL_56:
        try
        {
          std::wstring::assign(a2, v7);
        }
        catch ( ... )
        {
          return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                                 retaddr,
                                 (void *)0x8B,
                                 (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
                                 v8);
        }
        return 0;
      }
    }
    return 2147943568LL;
  }
  if ( a1 <= 0x13 )
  {
    if ( a1 == 19 )
    {
      v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryCleanPC";
      goto LABEL_56;
    }
    v13 = a1 - 14;
    if ( !v13 )
    {
      v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryDeviceName";
      goto LABEL_56;
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryUpgradeWindowsEdition";
      goto LABEL_56;
    }
    v15 = v14 - 1;
    if ( !v15 )
    {
      v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryDeviceManagement";
      goto LABEL_56;
    }
    v16 = v15 - 1;
    if ( !v16 )
    {
      v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryPolicies";
      goto LABEL_56;
    }
    if ( v16 == 1 )
    {
      v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryPowerSettings";
      goto LABEL_56;
    }
    return 2147943568LL;
  }
  v17 = a1 - 20;
  if ( v17 )
  {
    v18 = v17 - 1;
    if ( !v18 )
    {
      v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryDeviceAADJoin";
      goto LABEL_56;
    }
    v19 = v18 - 1;
    if ( !v19 )
    {
      v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategorySharedPC";
      goto LABEL_56;
    }
    v20 = v19 - 1;
    if ( !v20 )
    {
      v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryTakeATest";
      goto LABEL_56;
    }
    if ( v20 == 1 )
    {
      v7 = L"SystemSettingsProvisioningPackageAffects_ContentCategoryLocalAccount";
      goto LABEL_56;
    }
    return 2147943568LL;
  }
  std::wstring::assign(a2, L"SystemSettingsProvisioningPackageAffects_ContentCategoryDeviceADJoin");
  return 0;
}

```

## disassembly

```asm
0x18001552c  sub     rsp, 28h
0x180015530  mov     rax, rdx
0x180015533  cmp     ecx, 0Ch
0x180015536  ja      loc_180015607
0x18001553c  jz      loc_1800155FE
0x180015542  cmp     ecx, 6
0x180015545  ja      short loc_1800155B4
0x180015547  jz      short loc_1800155AB
0x180015549  test    ecx, ecx
0x18001554b  jz      short loc_180015597
0x18001554d  sub     ecx, 1
0x180015550  jz      short loc_18001558E
0x180015552  sub     ecx, 1
0x180015555  jz      short loc_180015585
0x180015557  sub     ecx, 1
0x18001555a  jz      short loc_18001557C
0x18001555c  sub     ecx, 1
0x18001555f  jz      short loc_180015573
0x180015561  cmp     ecx, 1
0x180015564  jnz     loc_180015688
0x18001556a  lea     rdx, aSystemsettings_9; "SystemSettingsProvisioningPackageAffect"...
0x180015571  jmp     short loc_18001559E
0x180015573  lea     rdx, aSystemsettings_26; "SystemSettingsProvisioningPackageAffect"...
0x18001557a  jmp     short loc_18001559E
0x18001557c  lea     rdx, aSystemsettings_47; "SystemSettingsProvisioningPackageAffect"...
0x180015583  jmp     short loc_18001559E
0x180015585  lea     rdx, aSystemsettings_0; "SystemSettingsProvisioningPackageAffect"...
0x18001558c  jmp     short loc_18001559E
0x18001558e  lea     rdx, aSystemsettings_22; "SystemSettingsProvisioningPackageAffect"...
0x180015595  jmp     short loc_18001559E
0x180015597  lea     rdx, aSystemsettings_23; "SystemSettingsProvisioningPackageAffect"...
0x18001559e  mov     rcx, rax
0x1800155a1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800155a6  jmp     loc_1800156CF
0x1800155ab  lea     rdx, aSystemsettings_43; "SystemSettingsProvisioningPackageAffect"...
0x1800155b2  jmp     short loc_18001559E
0x1800155b4  sub     ecx, 7
0x1800155b7  jz      short loc_1800155F5
0x1800155b9  sub     ecx, 1
0x1800155bc  jz      short loc_1800155EC
0x1800155be  sub     ecx, 1
0x1800155c1  jz      short loc_1800155E3
0x1800155c3  sub     ecx, 1
0x1800155c6  jz      short loc_1800155DA
0x1800155c8  cmp     ecx, 1
0x1800155cb  jnz     loc_180015688
0x1800155d1  lea     rdx, aSystemsettings_4; "SystemSettingsProvisioningPackageAffect"...
0x1800155d8  jmp     short loc_18001559E
0x1800155da  lea     rdx, aSystemsettings_36; "SystemSettingsProvisioningPackageAffect"...
0x1800155e1  jmp     short loc_18001559E
0x1800155e3  lea     rdx, aSystemsettings_27; "SystemSettingsProvisioningPackageAffect"...
0x1800155ea  jmp     short loc_18001559E
0x1800155ec  lea     rdx, aSystemsettings_13; "SystemSettingsProvisioningPackageAffect"...
0x1800155f3  jmp     short loc_18001559E
0x1800155f5  lea     rdx, aSystemsettings_18; "SystemSettingsProvisioningPackageAffect"...
0x1800155fc  jmp     short loc_18001559E
0x1800155fe  lea     rdx, aSystemsettings_25; "SystemSettingsProvisioningPackageAffect"...
0x180015605  jmp     short loc_18001559E
0x180015607  cmp     ecx, 13h
0x18001560a  ja      short loc_18001566F
0x18001560c  jz      short loc_180015663
0x18001560e  sub     ecx, 0Eh
0x180015611  jz      short loc_180015657
0x180015613  sub     ecx, 1
0x180015616  jz      short loc_18001564B
0x180015618  sub     ecx, 1
0x18001561b  jz      short loc_18001563F
0x18001561d  sub     ecx, 1
0x180015620  jz      short loc_180015633
0x180015622  cmp     ecx, 1
0x180015625  jnz     short loc_180015688
0x180015627  lea     rdx, aSystemsettings_7; "SystemSettingsProvisioningPackageAffect"...
0x18001562e  jmp     loc_18001559E
0x180015633  lea     rdx, aSystemsettings_39; "SystemSettingsProvisioningPackageAffect"...
0x18001563a  jmp     loc_18001559E
0x18001563f  lea     rdx, aSystemsettings_11; "SystemSettingsProvisioningPackageAffect"...
0x180015646  jmp     loc_18001559E
0x18001564b  lea     rdx, aSystemsettings_3; "SystemSettingsProvisioningPackageAffect"...
0x180015652  jmp     loc_18001559E
0x180015657  lea     rdx, aSystemsettings_45; "SystemSettingsProvisioningPackageAffect"...
0x18001565e  jmp     loc_18001559E
0x180015663  lea     rdx, aSystemsettings_16; "SystemSettingsProvisioningPackageAffect"...
0x18001566a  jmp     loc_18001559E
0x18001566f  sub     ecx, 14h
0x180015672  jz      short loc_1800156BF
0x180015674  sub     ecx, 1
0x180015677  jz      short loc_1800156B3
0x180015679  sub     ecx, 1
0x18001567c  jz      short loc_1800156A7
0x18001567e  sub     ecx, 1
0x180015681  jz      short loc_18001569B
0x180015683  cmp     ecx, 1
0x180015686  jz      short loc_18001568F
0x180015688  mov     eax, 80070490h
0x18001568d  jmp     short loc_1800156D7
0x18001568f  lea     rdx, aSystemsettings_6; "SystemSettingsProvisioningPackageAffect"...
0x180015696  jmp     loc_18001559E
0x18001569b  lea     rdx, aSystemsettings_44; "SystemSettingsProvisioningPackageAffect"...
0x1800156a2  jmp     loc_18001559E
0x1800156a7  lea     rdx, aSystemsettings_21; "SystemSettingsProvisioningPackageAffect"...
0x1800156ae  jmp     loc_18001559E
0x1800156b3  lea     rdx, aSystemsettings_32; "SystemSettingsProvisioningPackageAffect"...
0x1800156ba  jmp     loc_18001559E
0x1800156bf  lea     rdx, aSystemsettings_38; "SystemSettingsProvisioningPackageAffect"...
0x1800156c6  mov     rcx, rax
0x1800156c9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800156ce  nop
0x1800156cf  xor     eax, eax
0x1800156d1  jmp     short loc_1800156D7
0x1800156d3  mov     eax, [rsp+28h+arg_0]
0x1800156d7  add     rsp, 28h
0x1800156db  retn
```
