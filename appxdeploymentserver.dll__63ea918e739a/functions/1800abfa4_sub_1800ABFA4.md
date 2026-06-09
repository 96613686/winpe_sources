# sub_1800ABFA4

- ea: `0x1800abfa4`
- end: `0x1800ac1ba`
- name: `sub_1800ABFA4`
- size: `534`
- prototype: `__int64 __usercall@<rax>(LPCWSTR lpFileName@<rcx>, PSID Sid1@<rdx>, __int64)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800abbd4`
- `0x1800be818`
- `0x180115440`
- `0x18032c23c`

## callees

- `0x180024b6c`
- `0x1800abfa4`
- `0x1800ac1c0`
- `0x18011edd8`
- `0x18012b038`
- `0x1801ed4ec`

## import_xrefs

- `ntdll!RtlFindAceByType` at `0x1800ac113`
- `ntdll!RtlFindAceByType` at `0x1800ac113`
- `ntdll!RtlEqualSid` at `0x1800ac12e`
- `ntdll!RtlEqualSid` at `0x1800ac12e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac073`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac08e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac1a5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac073`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac08e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ac1a5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ac01a`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ac01a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ac14f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ac197`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ac14f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ac197`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!GetSecurityInfo` at `0x1800ac0fc`
- `ext-ms-win-advapi32-ntmarta-l1-1-0!GetSecurityInfo` at `0x1800ac0fc`

## pseudocode

```c

```
