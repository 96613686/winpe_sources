# SystemSettings::Prov::CProvisioningDisplayStringSetting::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800177e0`
- end: `0x1800177fd`
- name: `?GetRuntimeClassName@CProvisioningDisplayStringSetting@Prov@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(SystemSettings::Prov::CProvisioningDisplayStringSetting *__hidden this, HSTRING *)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180017810`
- `0x180017820`
- `0x180017830`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800177f6`

## pseudocode

```c
HRESULT __fastcall SystemSettings::Prov::CProvisioningDisplayStringSetting::GetRuntimeClassName(
        SystemSettings::Prov::CProvisioningDisplayStringSetting *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"SystemSettings.DataModel.CProvisioningDisplayStringSetting", 0x3Au, a2);
}

```

## disassembly

```asm
0x1800177e0  mov     qword ptr [rdx], 0
0x1800177e7  lea     rcx, aSystemsettings_31; "SystemSettings.DataModel.CProvisioningD"...
0x1800177ee  mov     r8, rdx
0x1800177f1  mov     edx, 3Ah ; ':'
0x1800177f6  jmp     cs:__imp_WindowsCreateString
```
