# SystemSettings::Prov::CProvisioningDeleteSetting::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180017780`
- end: `0x18001779d`
- name: `?GetRuntimeClassName@CProvisioningDeleteSetting@Prov@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(SystemSettings::Prov::CProvisioningDeleteSetting *__hidden this, HSTRING *)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800177b0`
- `0x1800177c0`
- `0x1800177d0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017796`

## string_xrefs

- `0x180017787`: `SystemSettings.DataModel.CProvisioningDeleteSetting `

## pseudocode

```c
HRESULT __fastcall SystemSettings::Prov::CProvisioningDeleteSetting::GetRuntimeClassName(
        SystemSettings::Prov::CProvisioningDeleteSetting *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"SystemSettings.DataModel.CProvisioningDeleteSetting ", 0x34u, a2);
}

```

## disassembly

```asm
0x180017780  mov     qword ptr [rdx], 0
0x180017787  lea     rcx, aSystemsettings_19; "SystemSettings.DataModel.CProvisioningD"...
0x18001778e  mov     r8, rdx
0x180017791  mov     edx, 34h ; '4'
0x180017796  jmp     cs:__imp_WindowsCreateString
```
