# LsaAddAccountRights

- ea: `0x180063d68`
- end: `0x180063de3`
- name: `LsaAddAccountRights`
- size: `123`
- prototype: `NTSTATUS __stdcall(LSA_HANDLE PolicyHandle, PSID AccountSid, PLSA_UNICODE_STRING UserRights, ULONG CountOfRights)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180041b64`
- `0x1800507a8`
- `0x180059200`

## callees

- `0x180063d68`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180063db5`
- `RPCRT4!NdrClientCall3` at `0x180063db5`
- `RPCRT4!I_RpcExceptionFilter` at `0x180066fa5`
- `RPCRT4!I_RpcExceptionFilter` at `0x180066fa5`
- `RPCRT4!I_RpcMapWin32Status` at `0x180063dc8`
- `RPCRT4!I_RpcMapWin32Status` at `0x180063dc8`

## pseudocode

```c

```
