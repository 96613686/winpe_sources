# AppContainerLoad(void)

- ea: `0x1800c5e14`
- end: `0x1800c613a`
- name: `?AppContainerLoad@@YAJXZ`
- size: `806`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800f3f0c`

## callees

- `0x180032b58`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800c5e14`
- `0x1800eb920`
- `0x180125964`
- `0x18012b630`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800c5fba`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800c605a`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800c5fba`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x1800c605a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800c5ee8`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800c5ee8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5f0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5fd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6072`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5f0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c5fd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c6072`

## string_xrefs

- `0x1800c608e`: `Failed to get proc address for DeriveAppContainerSidFromAppContainerName.`
- `0x1800c5fee`: `Failed to get proc address for CreateAppContainerProfile.`
- `0x1800c5f29`: `Failed to load userenv DLL`
- `0x1800c5fb3`: `CreateAppContainerProfile`
- `0x1800c6053`: `DeriveAppContainerSidFromAppContainerName`
- `0x1800c5edf`: `userenv.dll`

## pseudocode

```c

```
