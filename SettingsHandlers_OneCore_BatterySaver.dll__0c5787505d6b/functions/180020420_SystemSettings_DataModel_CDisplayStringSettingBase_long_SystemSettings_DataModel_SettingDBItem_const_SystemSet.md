# SystemSettings::DataModel::CDisplayStringSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetRuntimeClassName(HSTRING__ * *)

- ea: `0x180020420`
- end: `0x18002043d`
- name: `?GetRuntimeClassName@?$CDisplayStringSettingBase@P6AJPEBUSettingDBItem@DataModel@SystemSettings@@PEAPEAUISettingItem@23@@Z@DataModel@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `29`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180020450`
- `0x180020460`
- `0x180020470`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180020436`

## pseudocode

```c
HRESULT __fastcall SystemSettings::DataModel::CDisplayStringSettingBase<long (*)(SystemSettings::DataModel::SettingDBItem const *,SystemSettings::DataModel::ISettingItem * *)>::GetRuntimeClassName(
        __int64 a1,
        HSTRING *a2)
{
  *a2 = 0;
  return WindowsCreateString(L"SystemSettings.DataModel.CDisplayStringSetting", 0x2Eu, a2);
}

```

## disassembly

```asm
0x180020420  mov     qword ptr [rdx], 0
0x180020427  lea     rcx, aSystemsettings_0; "SystemSettings.DataModel.CDisplayString"...
0x18002042e  mov     r8, rdx
0x180020431  mov     edx, 2Eh ; '.'
0x180020436  jmp     cs:__imp_WindowsCreateString
```
