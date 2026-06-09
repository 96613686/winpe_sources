# CallerIdentity::CheckCallerCapability(ushort const *,bool *)

- ea: `0x18003a3e0`
- end: `0x18003a6b1`
- name: `?CheckCallerCapability@CallerIdentity@@YAJPEBGPEA_N@Z`
- size: `721`
- prototype: `__int64 __fastcall(CallerIdentity *__hidden this, const unsigned __int16 *, bool *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800398dc`
- `0x180234f80`

## callees

- `0x180009dd0`
- `0x18002df5c`
- `0x18002fc18`
- `0x1800378dc`
- `0x18003a3e0`
- `0x1800ef834`
- `0x1801812f8`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003a4af`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18003a4af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003a619`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18003a619`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a644`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a67d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a68e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a69f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a644`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a67d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a68e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003a69f`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003a4e2`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x18003a4e2`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18003a42c`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x18003a42c`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18003a529`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x18003a529`

## pseudocode

```c

```
