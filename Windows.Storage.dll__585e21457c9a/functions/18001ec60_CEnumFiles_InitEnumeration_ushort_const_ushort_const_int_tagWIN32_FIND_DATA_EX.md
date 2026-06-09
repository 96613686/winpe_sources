# CEnumFiles::_InitEnumeration(ushort const *,ushort const *,int,tagWIN32_FIND_DATA_EX *)

- ea: `0x18001ec60`
- end: `0x18001f2e0`
- name: `?_InitEnumeration@CEnumFiles@@AEAAJPEBG0HPEAUtagWIN32_FIND_DATA_EX@@@Z`
- size: `1664`
- prototype: `__int64 __usercall@<rax>(CEnumFiles *__hidden this@<rcx>, LPCWSTR lpFileName@<rdx>, const unsigned __int16 *@<r8>, int@<r9d>, struct tagWIN32_FIND_DATA_EX *)`
- caller_count: `7`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001d170`
- `0x18001d190`
- `0x18001e5c0`
- `0x1800b69d0`
- `0x18024dfb0`
- `0x18035ad00`
- `0x18054947c`

## callees

- `0x18001ec60`
- `0x18001f2f0`
- `0x18019b8c0`
- `0x1801b0e80`
- `0x1802182f0`
- `0x1802232a0`
- `0x180223cb0`
- `0x1802a0a28`
- `0x18034f504`
- `0x18035af34`
- `0x18035c2a0`
- `0x18035ca2c`
- `0x1803a4cb0`
- `0x1803a57e0`
- `0x1803a96e5`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001efb6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eefb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001eefb`
- `ntdll!RtlNtStatusToDosError` at `0x18063e4cf`
- `ntdll!RtlNtStatusToDosError` at `0x18063e4cf`
- `ntdll!RtlQueryThreadPlaceholderCompatibilityMode` at `0x18001ecb1`
- `ntdll!RtlQueryThreadPlaceholderCompatibilityMode` at `0x18001ecb1`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x18001ecc1`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x18001ef1f`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x18001ecc1`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x18001ef1f`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001ef5d`
- `ntdll!RtlInitUnicodeStringEx` at `0x18001ef5d`
- `ntdll!NtQueryDirectoryFile` at `0x18001edcd`
- `ntdll!NtQueryDirectoryFile` at `0x18001edcd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f041`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f20e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f041`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f20e`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001f012`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x18001f012`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ed2b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001ed2b`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001f2cd`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001f2cd`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18001f299`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x18001f299`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18001ecf1`
- `SHCORE!__imp_SHWindowsPolicy` at `0x18001ecf1`

## pseudocode

```c

```
