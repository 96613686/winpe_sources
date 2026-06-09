# SystemSettings::PointInTimeRestore::CPointInTimeRestoreToggleSetting::get_Id(HSTRING__ * *)

- ea: `0x180022a80`
- end: `0x180022a96`
- name: `?get_Id@CPointInTimeRestoreToggleSetting@PointInTimeRestore@SystemSettings@@UEAAJPEAPEAUHSTRING__@@@Z`
- size: `22`
- prototype: `__int64 __fastcall(SystemSettings::PointInTimeRestore::CPointInTimeRestoreToggleSetting *__hidden this, HSTRING *)`
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180022a8f`

## pseudocode

```c
HRESULT __fastcall SystemSettings::PointInTimeRestore::CPointInTimeRestoreToggleSetting::get_Id(
        SystemSettings::PointInTimeRestore::CPointInTimeRestoreToggleSetting *this,
        HSTRING *a2)
{
  return WindowsCreateString(L"SystemSettings_PointInTimeRestore_Dialog_Toggle", 0x2Fu, a2);
}

```

## disassembly

```asm
0x180022a80  mov     r8, rdx
0x180022a83  lea     rcx, aSystemsettings_130; "SystemSettings_PointInTimeRestore_Dialo"...
0x180022a8a  mov     edx, 2Fh ; '/'
0x180022a8f  jmp     cs:__imp_WindowsCreateString
```
