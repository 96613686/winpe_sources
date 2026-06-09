# SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::get_Id(HSTRING__ * *)

- ea: `0x180022a20`
- end: `0x180022a36`
- name: `?get_Id@CPointInTimeRestoreSnapshotCadenceSetting@PointInTimeRestore@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180022a2f`

## pseudocode

```c
HRESULT __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting::get_Id(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotCadenceSetting *this,
        HSTRING *a2)
{
  return WindowsCreateString(L"SystemSettings_PointInTimeRestore_Dialog_SnapshotCadence", 0x38u, a2);
}

```

## disassembly

```asm
0x180022a20  mov     r8, rdx
0x180022a23  lea     rcx, aSystemsettings_14; "SystemSettings_PointInTimeRestore_Dialo"...
0x180022a2a  mov     edx, 38h ; '8'
0x180022a2f  jmp     cs:__imp_WindowsCreateString
```
