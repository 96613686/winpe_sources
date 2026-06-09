# SystemSettings::Prov::CProvisioningLabeledStringSetting::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800178a0`
- end: `0x1800178bd`
- name: `?GetRuntimeClassName@CProvisioningLabeledStringSetting@Prov@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(SystemSettings::Prov::CProvisioningLabeledStringSetting *__hidden this, HSTRING *)`
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800178d0`
- `0x1800178e0`
- `0x1800178f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800178b6`

## pseudocode

```c
HRESULT __fastcall SystemSettings::Prov::CProvisioningLabeledStringSetting::GetRuntimeClassName(
        SystemSettings::Prov::CProvisioningLabeledStringSetting *this,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"SystemSettings.DataModel.CProvisioningLabeledStringSetting", 0x3Au, a2);
}

```

## disassembly

```asm
0x1800178a0  mov     qword ptr [rdx], 0
0x1800178a7  lea     rcx, aSystemsettings_20; "SystemSettings.DataModel.CProvisioningL"...
0x1800178ae  mov     r8, rdx
0x1800178b1  mov     edx, 3Ah ; ':'
0x1800178b6  jmp     cs:__imp_WindowsCreateString
```
