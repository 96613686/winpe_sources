# SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting::get_Id(HSTRING__ * *)

- ea: `0x180022a00`
- end: `0x180022a16`
- name: `?get_Id@CPointInTimeRestoreMaxDiskUsageSetting@PointInTimeRestore@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180022a0f`

## pseudocode

```c
HRESULT __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting::get_Id(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreMaxDiskUsageSetting *this,
        HSTRING *a2)
{
  return WindowsCreateString(L"SystemSettings_PointInTimeRestore_Dialog_MaxDiskUsage", 0x35u, a2);
}

```

## disassembly

```asm
0x180022a00  mov     r8, rdx
0x180022a03  lea     rcx, aSystemsettings_55; "SystemSettings_PointInTimeRestore_Dialo"...
0x180022a0a  mov     edx, 35h ; '5'
0x180022a0f  jmp     cs:__imp_WindowsCreateString
```
