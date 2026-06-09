# MmpcDiscoveryUrl(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort * *,ushort * *,Windows::Internal::Management::Enrollment::MDMAuthPolicy *)

- ea: `0x140055960`
- end: `0x140055e9a`
- name: `?MmpcDiscoveryUrl@@YAJPEBG0000PEAPEAG1PEAW4MDMAuthPolicy@Enrollment@Management@Internal@Windows@@@Z`
- size: `1338`
- prototype: `int(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **, unsigned __int16 **, enum Windows::Internal::Management::Enrollment::MDMAuthPolicy *)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140053430`
- `0x140054320`

## callees

- `0x1400042f0`
- `0x140004e28`
- `0x140005a5c`
- `0x140005ac4`
- `0x1400095b4`
- `0x14000a0fc`
- `0x14000bb88`
- `0x14000f78c`
- `0x1400176f0`
- `0x14001d65c`
- `0x14001d764`
- `0x14003d008`
- `0x1400532f8`
- `0x140055960`

## import_xrefs

- `dmEnrollEngine!MmpcDiscoverEndpoint` at `0x140055d33`
- `dmEnrollEngine!MmpcDiscoverEndpoint` at `0x140055d33`
- `dmEnrollEngine!GetEnrollmentEntDmId` at `0x140055c89`
- `dmEnrollEngine!GetEnrollmentEntDmId` at `0x140055c89`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140055e56`
- `ntdll!RtlIsStateSeparationEnabled` at `0x140055e56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140055cce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140055df6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140055cce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140055df6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140055cc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140055de8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140055cc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140055de8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140055b0c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140055bdf`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140055b0c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140055bdf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140055cd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140055e01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140055cd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140055e01`

## string_xrefs

- `0x140055e2b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140055e88`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x140055e5c`: `Software\Microsoft\Enrollments\%s\LinkedEnrollment`
- `0x140055e63`: `OSData\Software\Microsoft\Enrollments\%s\LinkedEnrollment`

## pseudocode

```c

```
