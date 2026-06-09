# DmRevertToSelf(void)

- ea: `0x18006aa00`
- end: `0x18006aa5a`
- name: `?DmRevertToSelf@@YAJXZ`
- size: `90`
- prototype: `int(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180061a64`

## callees

- `0x18005fb48`
- `0x18006aa00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006aa18`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006aa18`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006aa08`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18006aa08`

## string_xrefs

- `0x18006aa3c`: `onecoreuap\admin\dm\dmcmnutils\securityutils\securityutils.cpp`

## pseudocode

```c

```
