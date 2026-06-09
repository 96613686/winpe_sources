# CCachedINIFile::GetString(ushort const *,ushort const *,ushort const *,CACHEDPRIVATEPROFILEFLAGS,ushort * *)

- ea: `0x18018bb60`
- end: `0x18018c100`
- name: `?GetString@CCachedINIFile@@QEAAJPEBG00W4CACHEDPRIVATEPROFILEFLAGS@@PEAPEAG@Z`
- size: `1440`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18018ba60`
- `0x18018d694`

## callees

- `0x18009c6c0`
- `0x18009c960`
- `0x1800d9b80`
- `0x18018bb60`
- `0x18018c290`
- `0x18018c45c`
- `0x18018c540`
- `0x18018d694`
- `0x1803a4cb0`
- `0x1803a57e0`

## import_xrefs

- `ntdll!RtlUnicodeStringToAnsiString` at `0x18018bc33`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18018bd58`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18018bc33`
- `ntdll!RtlUnicodeStringToAnsiString` at `0x18018bd58`
- `ntdll!RtlFreeAnsiString` at `0x18018bcbc`
- `ntdll!RtlFreeAnsiString` at `0x18018be54`
- `ntdll!RtlFreeAnsiString` at `0x18018bcbc`
- `ntdll!RtlFreeAnsiString` at `0x18018be54`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18018bf78`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18018bf78`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18018bfd8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x18018bfd8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018be90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018bfa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018be90`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18018bfa0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018bfe1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018bff7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018c013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018c05b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018bfe1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018bff7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018c013`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18018c05b`

## pseudocode

```c

```
