# SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x1800174d0`
- end: `0x1800174ed`
- name: `?GetRuntimeClassName@?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180017500`
- `0x180017510`
- `0x180017520`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800174e6`

## pseudocode

```c
HRESULT __fastcall SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"SystemSettings.DataModel.CActionSetting", 0x27u, a2);
}

```

## disassembly

```asm
0x1800174d0  mov     qword ptr [rdx], 0
0x1800174d7  lea     rcx, aSystemsettings_37; "SystemSettings.DataModel.CActionSetting"
0x1800174de  mov     r8, rdx
0x1800174e1  mov     edx, 27h ; '''
0x1800174e6  jmp     cs:__imp_WindowsCreateString
```
