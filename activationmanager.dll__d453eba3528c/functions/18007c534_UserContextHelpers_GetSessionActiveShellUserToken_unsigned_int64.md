# UserContextHelpers::GetSessionActiveShellUserToken(unsigned __int64 *)

- ea: `0x18007c534`
- end: `0x18007c607`
- name: `?GetSessionActiveShellUserToken@UserContextHelpers@@QEAAJPEA_K@Z`
- size: `211`
- prototype: `__int64 __fastcall(UserContextHelpers *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18007ce74`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x180027ce8`
- `0x180044514`
- `0x18007c534`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x18007c570`
- `ntdll!NtQueryInformationProcess` at `0x18007c570`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x18007c5ac`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrGetSessionActiveShellUserToken` at `0x18007c5ac`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18007c5db`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserContext` at `0x18007c5db`

## pseudocode

```c

```
