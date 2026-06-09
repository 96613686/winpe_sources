# Common::Deployment::MountedFolder::Remove(ushort const *,ushort const *)

- ea: `0x1800dc344`
- end: `0x1800dc53e`
- name: `?Remove@MountedFolder@Deployment@Common@@SAJPEBG0@Z`
- size: `506`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, char *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800ac104`
- `0x18012bd44`
- `0x1801e848c`

## callees

- `0x18000eb74`
- `0x1800a021c`
- `0x1800a219c`
- `0x1800dc344`
- `0x1800dc544`
- `0x1800f0700`
- `0x1801ef2ac`
- `0x1801ef7c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc3e6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc3e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc408`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc4c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc4d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc408`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc4c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dc4d0`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800dc4e2`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x1800dc4e2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800dc3cb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800dc3cb`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800dc499`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1800dc499`

## string_xrefs

- `0x1800dc378`: `onecore\admin\appmodel\common\mountedfolder.cpp`
- `0x1800dc445`: `onecore\admin\appmodel\common\mountedfolder.cpp`
- `0x1800dc4a8`: `onecore\admin\appmodel\common\mountedfolder.cpp`
- `0x1800dc4f1`: `onecore\admin\appmodel\common\mountedfolder.cpp`

## pseudocode

```c

```
