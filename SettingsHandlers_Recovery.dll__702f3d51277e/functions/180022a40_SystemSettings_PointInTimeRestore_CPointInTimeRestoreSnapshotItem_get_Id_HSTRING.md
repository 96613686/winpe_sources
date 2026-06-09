# SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotItem::get_Id(HSTRING__ * *)

- ea: `0x180022a40`
- end: `0x180022a56`
- name: `?get_Id@CPointInTimeRestoreSnapshotItem@PointInTimeRestore@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotItem *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180022a4f`

## pseudocode

```c
HRESULT __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotItem::get_Id(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreSnapshotItem *this,
        HSTRING *a2)
{
  return WindowsCreateString(L"SystemSettings_PointInTimeRestore_Dialog_PointInTimeRestoreSnapshotItem", 0x47u, a2);
}

```

## disassembly

```asm
0x180022a40  mov     r8, rdx
0x180022a43  lea     rcx, aSystemsettings_106; "SystemSettings_PointInTimeRestore_Dialo"...
0x180022a4a  mov     edx, 47h ; 'G'
0x180022a4f  jmp     cs:__imp_WindowsCreateString
```
