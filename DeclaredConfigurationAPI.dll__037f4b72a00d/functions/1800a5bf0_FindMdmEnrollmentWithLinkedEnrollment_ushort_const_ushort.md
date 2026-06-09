# FindMdmEnrollmentWithLinkedEnrollment(ushort const *,ushort *)

- ea: `0x1800a5bf0`
- end: `0x1800a5f87`
- name: `?FindMdmEnrollmentWithLinkedEnrollment@@YAJPEBGPEAG@Z`
- size: `919`
- prototype: `int(const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007d298`
- `0x1800a72dc`

## callees

- `0x18000b9e0`
- `0x18000c8f4`
- `0x1800117dc`
- `0x180011f9c`
- `0x180014568`
- `0x180018c18`
- `0x18001ce80`
- `0x18001d03c`
- `0x1800370d4`
- `0x1800600bc`
- `0x1800a5bf0`
- `0x180100418`
- `0x180139010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a5efa`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800a5efa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a5ebe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a5f2b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a5ebe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800a5f2b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5e3a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800a5e3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5e29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5eb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5f1d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5e29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5eb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800a5f1d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a5df1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a5e7b`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a5df1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a5e7b`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a5c48`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800a5c48`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x1800a5c62`
- `dmEnrollEngine!__imp_GetDatabaseManagerInstance` at `0x1800a5c62`

## string_xrefs

- `0x1800a5de6`: `LinkedEnrollmentId`
- `0x1800a5e70`: `LinkedEnrollmentId`
- `0x1800a5cd3`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`
- `0x1800a5d9b`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`
- `0x1800a5e9f`: `onecoreuap\admin\enterprisemgmt\declaredconfiguration\objectmodel\lib\dcutils.cpp`
- `0x1800a5c55`: `OSData\Software\Microsoft\Enrollments\%s\LinkedEnrollment`
- `0x1800a5c4e`: `Software\Microsoft\Enrollments\%s\LinkedEnrollment`

## pseudocode

```c

```
