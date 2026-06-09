# SystemSettings::Prov::CProvisioningPackageInfoDynamicDatabase::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180017900`
- end: `0x18001791d`
- name: `?GetRuntimeClassName@CProvisioningPackageInfoDynamicDatabase@Prov@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(SystemSettings::Prov::CProvisioningPackageInfoDynamicDatabase *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017916`

## pseudocode

```c
HRESULT __fastcall SystemSettings::Prov::CProvisioningPackageInfoDynamicDatabase::GetRuntimeClassName(
        SystemSettings::Prov::CProvisioningPackageInfoDynamicDatabase *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"SystemSettings.DataModel.CProvisioningPackageInfoDynamicDatabase", 0x40u, a2);
}

```

## disassembly

```asm
0x180017900  mov     qword ptr [rdx], 0
0x180017907  lea     rcx, aSystemsettings_46; "SystemSettings.DataModel.CProvisioningP"...
0x18001790e  mov     r8, rdx
0x180017911  mov     edx, 40h ; '@'
0x180017916  jmp     cs:__imp_WindowsCreateString
```
