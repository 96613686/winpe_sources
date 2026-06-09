# PackageStoreBackupFile(wchar_t const *,wchar_t const *)

- ea: `0x1800b0964`
- end: `0x1800b0b05`
- name: `?PackageStoreBackupFile@@YAJPEB_W0@Z`
- size: `417`
- prototype: `__int64 __fastcall(LPCWSTR lpExistingFileName, const wchar_t *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x1800b2990`

## callees

- `0x180010f54`
- `0x180011094`
- `0x180042448`
- `0x180095e34`
- `0x180099390`
- `0x180099548`
- `0x1800b0964`
- `0x1800eb920`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0a64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0a64`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800b0a03`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MoveFileW` at `0x1800b0a03`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b09b4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800b09b4`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b09d6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b0a21`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b09d6`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b0a21`

## string_xrefs

- `0x1800b0a85`: `Failed to delete backup file: {}`

## pseudocode

```c

```
