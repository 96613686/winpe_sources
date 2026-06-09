# SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::get_Id(HSTRING__ * *)

- ea: `0x180022a60`
- end: `0x180022a76`
- name: `?get_Id@CPointInTimeRestoreSnapshotRetentionSetting@PointInTimeRestore@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180022a6f`

## pseudocode

```c
HRESULT __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting::get_Id(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotRetentionSetting *this,
        HSTRING *a2)
{
  return WindowsCreateString(L"SystemSettings_PointInTimeRestore_Dialog_SnapshotRetention", 0x3Au, a2);
}

```

## disassembly

```asm
0x180022a60  mov     r8, rdx
0x180022a63  lea     rcx, aSystemsettings_57; "SystemSettings_PointInTimeRestore_Dialo"...
0x180022a6a  mov     edx, 3Ah ; ':'
0x180022a6f  jmp     cs:__imp_WindowsCreateString
```
