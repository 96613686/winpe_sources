# SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::get_Id(HSTRING__ * *)

- ea: `0x1800229e0`
- end: `0x1800229f6`
- name: `?get_Id@CPointInTimeRestoreCurrentSnapshotCollection@PointInTimeRestore@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800229ef`

## pseudocode

```c
HRESULT __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection::get_Id(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreCurrentSnapshotCollection *this,
        HSTRING *a2)
{
  return WindowsCreateString(L"SystemSettings_PointInTimeRestore_Dialog_CurrentSnapshotCollection", 0x42u, a2);
}

```

## disassembly

```asm
0x1800229e0  mov     r8, rdx
0x1800229e3  lea     rcx, aSystemsettings_99; "SystemSettings_PointInTimeRestore_Dialo"...
0x1800229ea  mov     edx, 42h ; 'B'
0x1800229ef  jmp     cs:__imp_WindowsCreateString
```
