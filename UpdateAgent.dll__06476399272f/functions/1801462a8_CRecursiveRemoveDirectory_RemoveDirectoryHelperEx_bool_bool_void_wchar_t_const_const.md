# CRecursiveRemoveDirectory::RemoveDirectoryHelperEx(bool,bool,void *,wchar_t const * const)

- ea: `0x1801462a8`
- end: `0x180146f53`
- name: `?RemoveDirectoryHelperEx@CRecursiveRemoveDirectory@@AEAAJ_N0PEAXQEB_W@Z`
- size: `3243`
- prototype: `int(CRecursiveRemoveDirectory *__hidden this, bool, bool, void *, const wchar_t *const)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, loader_planting`

## callers

- `0x180146f5c`

## callees

- `0x1800059d0`
- `0x1800059f4`
- `0x180006a18`
- `0x18000a0e8`
- `0x18000b508`
- `0x18000c4c4`
- `0x180012460`
- `0x18001270c`
- `0x1800692fc`
- `0x18008b38c`
- `0x1800bdd54`
- `0x1800cb880`
- `0x18014361c`
- `0x1801458f0`
- `0x180145990`
- `0x180145a14`
- `0x180145ff4`
- `0x1801462a8`
- `0x180147754`
- `0x180148104`
- `0x18014a060`
- `0x18014b0c8`
- `0x18014bd44`

## import_xrefs

- `ntdll!NtClose` at `0x1801463a9`
- `ntdll!NtClose` at `0x1801464c7`
- `ntdll!NtClose` at `0x18014658b`
- `ntdll!NtClose` at `0x1801465fa`
- `ntdll!NtClose` at `0x1801466b8`
- `ntdll!NtClose` at `0x1801469be`
- `ntdll!NtClose` at `0x1801469f1`
- `ntdll!NtClose` at `0x180146aa4`
- `ntdll!NtClose` at `0x180146b59`
- `ntdll!NtClose` at `0x180146b8d`
- `ntdll!NtClose` at `0x180146c3e`
- `ntdll!NtClose` at `0x180146c72`
- `ntdll!NtClose` at `0x180146cd0`
- `ntdll!NtClose` at `0x180146d04`
- `ntdll!NtClose` at `0x180146d9b`
- `ntdll!NtClose` at `0x180146dcf`
- `ntdll!NtClose` at `0x180146e8d`
- `ntdll!NtClose` at `0x180146ec6`
- `ntdll!NtClose` at `0x180146eff`
- `ntdll!NtClose` at `0x1801463a9`
- `ntdll!NtClose` at `0x1801464c7`
- `ntdll!NtClose` at `0x18014658b`
- `ntdll!NtClose` at `0x1801465fa`
- `ntdll!NtClose` at `0x1801466b8`
- `ntdll!NtClose` at `0x1801469be`
- `ntdll!NtClose` at `0x1801469f1`
- `ntdll!NtClose` at `0x180146aa4`
- `ntdll!NtClose` at `0x180146b59`
- `ntdll!NtClose` at `0x180146b8d`
- `ntdll!NtClose` at `0x180146c3e`
- `ntdll!NtClose` at `0x180146c72`
- `ntdll!NtClose` at `0x180146cd0`
- `ntdll!NtClose` at `0x180146d04`
- `ntdll!NtClose` at `0x180146d9b`
- `ntdll!NtClose` at `0x180146dcf`
- `ntdll!NtClose` at `0x180146e8d`
- `ntdll!NtClose` at `0x180146ec6`
- `ntdll!NtClose` at `0x180146eff`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18014678a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18014678a`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18014680d`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18014680d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801467b3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801467b3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180146700`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180146700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801467c3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180146718`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801467c3`

## string_xrefs

- `0x180146336`: `No directory specified`
- `0x180146749`: `Remove directory cancelled`
- `0x180146450`: `Failed to open {} for deletion`
- `0x180146d35`: `Failed to open {} for deletion`
- `0x180146641`: `Failed to backslash-terminate directory path.`
- `0x180146514`: `Failed to add item to directory stack`
- `0x180146ad8`: `Failed to add item to directory stack`
- `0x180146bbd`: `Failed to backslash-terminate subdirectory path.`
- `0x180146a56`: `Unable to remove directory {}.`

## pseudocode

```c

```
