# Ids_ProcessImage(ulong,ulong,ushort *)

- ea: `0x1800ab824`
- end: `0x1800ab9bb`
- name: `?Ids_ProcessImage@@YAKKKPEAG@Z`
- size: `407`
- prototype: `unsigned int __fastcall(DWORD dwProcessId, unsigned int, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x1800ab238`

## callees

- `0x18000c018`
- `0x180012920`
- `0x180019c84`
- `0x1800ab824`
- `0x1800abd04`
- `0x1800ba724`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!towupper` at `0x1800ab963`
- `msvcrt!towupper` at `0x1800ab963`
- `msvcrt!wcsrchr` at `0x1800ab939`
- `msvcrt!wcsrchr` at `0x1800ab939`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab8ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab8ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab8ad`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ab8ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab990`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ab990`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ab89f`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ab89f`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800ab8f5`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800ab8f5`

## string_xrefs

- `0x1800ab8b3`: `Failed to get open the process [%d] for PID [%d]`
- `0x1800ab905`: `Failed to get the image path [%d] for PID [%d]`

## pseudocode

```c

```
