# SystemSettings::Prov::CProvisioningPackageItemSetting::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180017930`
- end: `0x18001794d`
- name: `?GetRuntimeClassName@CProvisioningPackageItemSetting@Prov@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(SystemSettings::Prov::CProvisioningPackageItemSetting *__hidden this, HSTRING *)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180017960`
- `0x180017970`
- `0x180017980`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017946`

## pseudocode

```c
HRESULT __fastcall SystemSettings::Prov::CProvisioningPackageItemSetting::GetRuntimeClassName(
        SystemSettings::Prov::CProvisioningPackageItemSetting *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"SystemSettings.DataModel.CProvisioningPackageItemSetting", 0x38u, a2);
}

```

## disassembly

```asm
0x180017930  mov     qword ptr [rdx], 0
0x180017937  lea     rcx, aSystemsettings_14; "SystemSettings.DataModel.CProvisioningP"...
0x18001793e  mov     r8, rdx
0x180017941  mov     edx, 38h ; '8'
0x180017946  jmp     cs:__imp_WindowsCreateString
```
