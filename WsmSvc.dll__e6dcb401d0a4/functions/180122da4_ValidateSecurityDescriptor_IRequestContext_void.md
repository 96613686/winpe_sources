# ValidateSecurityDescriptor(IRequestContext &,void *)

- ea: `0x180122da4`
- end: `0x180122f58`
- name: `?ValidateSecurityDescriptor@@YA_NAEAVIRequestContext@@PEAX@Z`
- size: `436`
- prototype: `bool(struct IRequestContext *, void *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18013b450`
- `0x18015d140`

## callees

- `0x180103850`
- `0x180112380`
- `0x18011ae5c`
- `0x180122da4`
- `0x1801c2010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180122e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180122f1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180122e26`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180122f1c`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180122f0b`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180122f0b`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180122e5d`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180122e5d`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180122e15`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x180122e15`

## pseudocode

```c

```
