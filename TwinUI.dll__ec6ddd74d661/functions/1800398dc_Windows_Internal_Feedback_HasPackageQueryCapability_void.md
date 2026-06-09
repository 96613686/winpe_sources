# Windows::Internal::Feedback::HasPackageQueryCapability(void)

- ea: `0x1800398dc`
- end: `0x180039bcc`
- name: `?HasPackageQueryCapability@Feedback@Internal@Windows@@YAJXZ`
- size: `752`
- prototype: `__int64 __fastcall(Windows::Internal::Feedback *__hidden this)`
- caller_count: `4`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180039140`
- `0x180039c84`
- `0x180234b40`
- `0x180234cc0`

## callees

- `0x180009dd0`
- `0x18002df5c`
- `0x18002fc18`
- `0x1800378dc`
- `0x1800398dc`
- `0x18003a3e0`
- `0x1800ef834`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180039985`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180039985`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039b41`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180039b41`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039b62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039b99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039baa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039bbb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039b62`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039b99`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039baa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039bbb`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800399b8`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x1800399b8`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180039912`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x180039912`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180039a03`
- `api-ms-win-security-capability-l1-1-0!CapabilityCheck` at `0x180039a03`

## string_xrefs

- `0x180039b0d`: `shell\twinui\feedback\lib\feedbackbroker.cpp`

## pseudocode

```c

```
