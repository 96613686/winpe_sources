# UfhpUtilityExpandConvertToDosPath(ushort *,ulong,int)

- ea: `0x18000b8e8`
- end: `0x18000bcda`
- name: `?UfhpUtilityExpandConvertToDosPath@@YAKPEAGKH@Z`
- size: `1010`
- prototype: `unsigned int __fastcall(unsigned __int16 *, unsigned int, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, loader_planting`

## callers

- `0x18000b4b0`

## callees

- `0x18000b8e8`
- `0x18000c018`
- `0x180013334`
- `0x1800133c0`
- `0x180056648`
- `0x18007a9cf`
- `0x1800f1f10`

## import_xrefs

- `msvcrt!wcsstr` at `0x18000b9d4`
- `msvcrt!wcsstr` at `0x18000bb95`
- `msvcrt!wcsstr` at `0x18000bc77`
- `msvcrt!wcsstr` at `0x18000b9d4`
- `msvcrt!wcsstr` at `0x18000bb95`
- `msvcrt!wcsstr` at `0x18000bc77`
- `ntdll!RtlDoesFileExists_U` at `0x18000bc02`
- `ntdll!RtlDoesFileExists_U` at `0x18000bc02`
- `ntdll!RtlFreeHeap` at `0x18000ba58`
- `ntdll!RtlFreeHeap` at `0x18000ba58`
- `ntdll!RtlAllocateHeap` at `0x18000b97c`
- `ntdll!RtlAllocateHeap` at `0x18000b97c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcc7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcc7`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x18000bb08`
- `api-ms-win-core-file-l1-1-0!GetShortPathNameW` at `0x18000bb08`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000bb7b`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000bb7b`

## string_xrefs

- `0x18000bb5c`: `%SYSTEMROOT%\system32\`

## pseudocode

```c

```
