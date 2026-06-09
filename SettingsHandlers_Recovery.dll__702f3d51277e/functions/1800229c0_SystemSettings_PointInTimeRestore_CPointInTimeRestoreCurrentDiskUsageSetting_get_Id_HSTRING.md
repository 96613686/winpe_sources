# SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting::get_Id(HSTRING__ * *)

- ea: `0x1800229c0`
- end: `0x1800229d6`
- name: `?get_Id@CPointInTimeRestoreCurrentDiskUsageSetting@PointInTimeRestore@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800229cf`

## pseudocode

```c
HRESULT __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting::get_Id(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentDiskUsageSetting *this,
        HSTRING *a2)
{
  return WindowsCreateString(L"SystemSettings_PointInTimeRestore_Dialog_CurrentDiskUsage", 0x39u, a2);
}

```

## disassembly

```asm
0x1800229c0  mov     r8, rdx
0x1800229c3  lea     rcx, aSystemsettings_61; "SystemSettings_PointInTimeRestore_Dialo"...
0x1800229ca  mov     edx, 39h ; '9'
0x1800229cf  jmp     cs:__imp_WindowsCreateString
```
