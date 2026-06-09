# SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800203c0`
- end: `0x1800203dd`
- name: `?GetRuntimeClassName@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x1800203f0`
- `0x180020400`
- `0x180020410`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800203d6`

## pseudocode

```c
HRESULT __fastcall SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"SystemSettings.DataModel.CDataSetting", 0x25u, a2);
}

```

## disassembly

```asm
0x1800203c0  mov     qword ptr [rdx], 0
0x1800203c7  lea     rcx, aSystemsettings_28; "SystemSettings.DataModel.CDataSetting"
0x1800203ce  mov     r8, rdx
0x1800203d1  mov     edx, 25h ; '%'
0x1800203d6  jmp     cs:__imp_WindowsCreateString
```
