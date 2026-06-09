# _lambda_b6b9433f1507361566af959273ff0d59_::operator()(HSTRING__ *,HSTRING__ *)

- ea: `0x1800d1e40`
- end: `0x1800d1f46`
- name: `??R_lambda_b6b9433f1507361566af959273ff0d59_@@QEBA@PEAUHSTRING__@@0@Z`
- size: `262`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800d1c90`

## callees

- `0x18009aff4`
- `0x1800c9ec8`
- `0x1800d1e40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1ee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1ee1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d1e5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d1ec9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d1e5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800d1ec9`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800d1ed7`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800d1ed7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d1f38`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800d1f38`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800d1e70`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800d1e70`

## string_xrefs

- `0x1800d1f07`: `hrCreateDirectory`
- `0x1800d1e86`: `OSIntegration::DEH::FileManager::CreateManagedDirectories::<lambda_b6b9433f1507361566af959273ff0d59>::operator ()`
- `0x1800d1f12`: `OSIntegration::DEH::FileManager::CreateManagedDirectories::<lambda_b6b9433f1507361566af959273ff0d59>::operator ()`
- `0x1800d1e7f`: `ConvertStringSecurityDescriptorToSecurityDescriptor( WindowsGetStringRawBuffer(securityDescriptorString, nullptr), SDDL_REVISION_1, reinterpret_cast<PSECURITY_DESCRIPTOR*>(&binarySecurityDescriptor), nullptr)`

## pseudocode

```c

```
