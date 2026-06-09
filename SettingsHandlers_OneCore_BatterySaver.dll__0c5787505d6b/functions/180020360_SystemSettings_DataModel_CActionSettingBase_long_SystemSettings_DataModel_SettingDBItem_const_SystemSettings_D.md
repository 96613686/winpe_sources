# SystemSettings::DataModel::CActionSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180020360`
- end: `0x18002037d`
- name: `?GetRuntimeClassName@?$CActionSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180020390`
- `0x1800203a0`
- `0x1800203b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180020376`

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
0x180020360  mov     qword ptr [rdx], 0
0x180020367  lea     rcx, aSystemsettings_32; "SystemSettings.DataModel.CActionSetting"
0x18002036e  mov     r8, rdx
0x180020371  mov     edx, 27h ; '''
0x180020376  jmp     cs:__imp_WindowsCreateString
```
