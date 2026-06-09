# FlushHivesAndSystemVolume(void)

- ea: `0x1800f7ba4`
- end: `0x1800f7f5b`
- name: `?FlushHivesAndSystemVolume@@YAJXZ`
- size: `951`
- prototype: `__int64(void)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callers

- `0x1800f7290`
- `0x1800f8af0`
- `0x1800faf90`

## callees

- `0x180013250`
- `0x18002e280`
- `0x180055fc8`
- `0x18005ec58`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800ad504`
- `0x1800eb920`
- `0x1800f6a50`
- `0x1800f7ba4`
- `0x18010e8a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7e4e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7d88`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f7e4e`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800f7c22`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800f7c35`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800f7c48`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800f7c5b`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800f7c22`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800f7c35`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800f7c48`
- `api-ms-win-core-registry-l1-1-0!RegFlushKey` at `0x1800f7c5b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f7d5c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f7d5c`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800f7e3a`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800f7e3a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f7c0f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f7e2b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f7c0f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f7e2b`

## string_xrefs

- `0x1800f7bd0`: `Flush: registry...`
- `0x1800f7cc3`: `Failed to get windows directory path.`
- `0x1800f7c88`: `Flush: registry took: {} ms.`
- `0x1800f7da2`: `Failed opening the system volume`

## pseudocode

```c

```
