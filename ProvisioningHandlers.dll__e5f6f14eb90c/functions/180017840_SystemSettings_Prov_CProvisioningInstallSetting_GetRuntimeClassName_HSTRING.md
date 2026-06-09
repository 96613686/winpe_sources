# SystemSettings::Prov::CProvisioningInstallSetting::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180017840`
- end: `0x18001785d`
- name: `?GetRuntimeClassName@CProvisioningInstallSetting@Prov@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(SystemSettings::Prov::CProvisioningInstallSetting *__hidden this, HSTRING *)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, installer_update`

## callers

- `0x180017870`
- `0x180017880`
- `0x180017890`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017856`

## string_xrefs

- `0x180017847`: `SystemSettings.DataModel.CProvisioningInstallSetting`

## pseudocode

```c
HRESULT __fastcall SystemSettings::Prov::CProvisioningInstallSetting::GetRuntimeClassName(
        SystemSettings::Prov::CProvisioningInstallSetting *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"SystemSettings.DataModel.CProvisioningInstallSetting", 0x34u, a2);
}

```

## disassembly

```asm
0x180017840  mov     qword ptr [rdx], 0
0x180017847  lea     rcx, aSystemsettings_5; "SystemSettings.DataModel.CProvisioningI"...
0x18001784e  mov     r8, rdx
0x180017851  mov     edx, 34h ; '4'
0x180017856  jmp     cs:__imp_WindowsCreateString
```
