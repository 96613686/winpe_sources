# WindowsUpdate::InstallAgentWERReporting::_SaveReportMetadata(ushort *,unsigned __int64,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800ff860`
- end: `0x1800ffa92`
- name: `?_SaveReportMetadata@InstallAgentWERReporting@WindowsUpdate@@YAJPEAG_KPEBG222@Z`
- size: `562`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, unsigned __int16 *@<rdx>, unsigned __int64@<r8>, const unsigned __int16 *@<r9>, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, service_task, installer_update, broker_com_uri`

## callers

- `0x1800ff460`

## callees

- `0x180009ea0`
- `0x18000ad30`
- `0x180011090`
- `0x1800111c8`
- `0x1800ff860`
- `0x1800ffd54`
- `0x1800ffe28`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1800ff8e4`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x1800ff8e4`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x1800ff8de`
- `api-ms-win-crt-private-l1-1-0!_o_srand` at `0x1800ff8de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffa5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ffa5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffa50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ffa50`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ff9e4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ff9e4`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800ff8ca`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentVariableW` at `0x1800ff8ca`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800ff9ac`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800ff9ac`

## pseudocode

```c

```
