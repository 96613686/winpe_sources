# PreventSystemSleepMode

- ea: `0x18010f324`
- end: `0x18010f798`
- name: `PreventSystemSleepMode`
- size: `1140`
- prototype: ``
- caller_count: `7`
- callee_count: `10`
- tags: `loader_planting, service_task`

## callers

- `0x1800b76d0`
- `0x1800e8698`
- `0x1800f8cd0`
- `0x1800fcb34`
- `0x18016f73c`
- `0x18018cddc`
- `0x1802af790`

## callees

- `0x180034954`
- `0x180095e34`
- `0x180098538`
- `0x180099390`
- `0x180099548`
- `0x18009cf78`
- `0x1800e37d4`
- `0x1800eb920`
- `0x18010f324`
- `0x1802d5010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18010f4a1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18010f53b`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18010f4a1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18010f53b`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18010f3cf`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18010f3cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f4b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f54f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f6c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f406`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f4b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f54f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f620`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010f6c1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010f6df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010f6df`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18010f3ee`
- `api-ms-win-core-kernel32-legacy-l1-1-0!LoadLibraryW` at `0x18010f3ee`

## string_xrefs

- `0x18010f3c1`: `Kernel32.dll`
- `0x18010f4d7`: `Failed to call GetProcAddress on PowerCreateRequest`
- `0x18010f497`: `PowerCreateRequest`
- `0x18010f3e7`: `api-ms-win-core-kernel32-legacy-l1-1-1.dll`
- `0x18010f64b`: `Failed to create power request for: {}`
- `0x18010f75b`: `Failed to Initialize PDC task client `

## pseudocode

```c

```
