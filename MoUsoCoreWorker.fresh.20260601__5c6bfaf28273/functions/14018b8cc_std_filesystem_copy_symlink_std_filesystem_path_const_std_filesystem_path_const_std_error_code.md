# std::filesystem::copy_symlink(std::filesystem::path const &,std::filesystem::path const &,std::error_code &)

- ea: `0x14018b8cc`
- end: `0x14018baae`
- name: `?copy_symlink@filesystem@std@@YAXAEBVpath@12@0AEAVerror_code@2@@Z`
- size: `482`
- prototype: `void(std::filesystem *__hidden this, const struct std::filesystem::path *, const struct std::filesystem::path *, struct std::error_code *)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path`

## callers

- `0x14018bbf8`

## callees

- `0x14005867c`
- `0x140058884`
- `0x14018b830`
- `0x14018b8cc`
- `0x140378e10`
- `0x140379070`
- `0x1403790cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14018b9ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14018b9ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14018b92e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14018b95e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14018b9c3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14018b92e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14018b95e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14018b9c3`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x14018b9a8`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x14018b9a8`

## pseudocode

```c

```
