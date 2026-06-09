# SystemSettings::Prov::CProvisioningPackageNoPackageErrorSetting::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180017990`
- end: `0x1800179ad`
- name: `?GetRuntimeClassName@CProvisioningPackageNoPackageErrorSetting@Prov@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(SystemSettings::Prov::CProvisioningPackageNoPackageErrorSetting *__hidden this, HSTRING *)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800179c0`
- `0x1800179d0`
- `0x1800179e0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800179a6`

## pseudocode

```c
HRESULT __fastcall SystemSettings::Prov::CProvisioningPackageNoPackageErrorSetting::GetRuntimeClassName(
        SystemSettings::Prov::CProvisioningPackageNoPackageErrorSetting *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"SystemSettings.DataModel.CProvisioningPackageNoPackageErrorSetting", 0x42u, a2);
}

```

## disassembly

```asm
0x180017990  mov     qword ptr [rdx], 0
0x180017997  lea     rcx, aSystemsettings_10; "SystemSettings.DataModel.CProvisioningP"...
0x18001799e  mov     r8, rdx
0x1800179a1  mov     edx, 42h ; 'B'
0x1800179a6  jmp     cs:__imp_WindowsCreateString
```
