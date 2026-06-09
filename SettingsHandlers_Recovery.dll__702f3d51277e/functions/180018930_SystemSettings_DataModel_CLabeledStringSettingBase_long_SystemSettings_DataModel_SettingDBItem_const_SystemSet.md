# SystemSettings::DataModel::CLabeledStringSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180018930`
- end: `0x18001894d`
- name: `?GetRuntimeClassName@?$CLabeledStringSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180018960`
- `0x180018970`
- `0x180018980`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018946`

## pseudocode

```c
HRESULT __fastcall SystemSettings::DataModel::CLabeledStringSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"SystemSettings.DataModel.CLabeledStringSetting", 0x2Eu, a2);
}

```

## disassembly

```asm
0x180018930  mov     qword ptr [rdx], 0
0x180018937  lea     rcx, aSystemsettings_88; "SystemSettings.DataModel.CLabeledString"...
0x18001893e  mov     r8, rdx
0x180018941  mov     edx, 2Eh ; '.'
0x180018946  jmp     cs:__imp_WindowsCreateString
```
