# RegEnumKeyExA

- ea: `0x1800fc9a0`
- end: `0x1800fcc69`
- name: `RegEnumKeyExA`
- size: `713`
- prototype: `LSTATUS __stdcall(HKEY hKey, DWORD dwIndex, LPSTR lpName, LPDWORD lpcchName, LPDWORD lpReserved, LPSTR lpClass, LPDWORD lpcchClass, PFILETIME lpftLastWriteTime)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18012166c`
- `0x18013ea80`

## callees

- `0x18005bb80`
- `0x18005d0a0`
- `0x1800600c0`
- `0x1800fc9a0`
- `0x18012d578`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800fcb4d`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800fcc54`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800fcb4d`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x1800fcc54`
- `ntdll!RtlNtStatusToDosError` at `0x1800fcb78`
- `ntdll!RtlNtStatusToDosError` at `0x1800fcb78`
- `ntdll!RtlFreeHeap` at `0x1800fcb6a`
- `ntdll!RtlFreeHeap` at `0x1800fcc1c`
- `ntdll!RtlFreeHeap` at `0x1800fcb6a`
- `ntdll!RtlFreeHeap` at `0x1800fcc1c`
- `ntdll!RtlAllocateHeap` at `0x1800fca9d`
- `ntdll!RtlAllocateHeap` at `0x1800fca9d`
- `ext-ms-win-advapi32-registry-l1-1-0!RemoteRegEnumKeyWrapper` at `0x180195540`
- `ext-ms-win-advapi32-registry-l1-1-0!RemoteRegEnumKeyWrapper` at `0x180195540`

## pseudocode

```c

```
