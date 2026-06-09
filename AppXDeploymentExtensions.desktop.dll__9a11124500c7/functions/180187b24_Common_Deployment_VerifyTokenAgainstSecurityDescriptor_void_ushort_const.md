# Common::Deployment::VerifyTokenAgainstSecurityDescriptor(void *,ushort const *)

- ea: `0x180187b24`
- end: `0x180187c55`
- name: `?VerifyTokenAgainstSecurityDescriptor@Deployment@Common@@YAJPEAXPEBG@Z`
- size: `305`
- prototype: `__int64 __fastcall(HANDLE ClientToken, void *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800a96c0`

## callees

- `0x1800aed10`
- `0x180187b24`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180187b87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180187b87`
- `ntdll!NtAccessCheck` at `0x180187bf2`
- `ntdll!NtAccessCheck` at `0x180187bf2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180187c04`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180187c04`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180187b77`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180187b77`

## pseudocode

```c

```
