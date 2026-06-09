# SystemSettings::DataModel::CDataSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180017530`
- end: `0x18001754d`
- name: `?GetRuntimeClassName@?$CDataSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180017560`
- `0x180017570`
- `0x180017580`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180017546`

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
0x180017530  mov     qword ptr [rdx], 0
0x180017537  lea     rcx, aSystemsettings_30; "SystemSettings.DataModel.CDataSetting"
0x18001753e  mov     r8, rdx
0x180017541  mov     edx, 25h ; '%'
0x180017546  jmp     cs:__imp_WindowsCreateString
```
