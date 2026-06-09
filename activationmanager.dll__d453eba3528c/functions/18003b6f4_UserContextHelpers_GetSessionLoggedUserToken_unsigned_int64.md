# UserContextHelpers::GetSessionLoggedUserToken(unsigned __int64 *)

- ea: `0x18003b6f4`
- end: `0x18003b7a4`
- name: `?GetSessionLoggedUserToken@UserContextHelpers@@QEAAJPEA_K@Z`
- size: `176`
- prototype: `int(UserContextHelpers *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18007ce74`

## callees

- `0x18000b5c0`
- `0x18003b6f4`
- `0x180044514`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b74e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b796`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b74e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003b796`
- `ntdll!NtOpenProcessTokenEx` at `0x18003b71a`
- `ntdll!NtOpenProcessTokenEx` at `0x18003b71a`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18003b760`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18003b760`

## pseudocode

```c

```
