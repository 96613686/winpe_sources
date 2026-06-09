# LsaOpenPolicy

- ea: `0x180063a08`
- end: `0x180063bee`
- name: `LsaOpenPolicy`
- size: `486`
- prototype: `NTSTATUS __stdcall(PLSA_UNICODE_STRING SystemName, PLSA_OBJECT_ATTRIBUTES ObjectAttributes, ACCESS_MASK DesiredAccess, PLSA_HANDLE PolicyHandle)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180041b64`
- `0x180044df4`
- `0x1800507a8`
- `0x1800526c0`
- `0x180059200`
- `0x18005a684`

## callees

- `0x180063a08`
- `0x180063c90`
- `0x180063cf4`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180063af3`
- `RPCRT4!NdrClientCall3` at `0x180063b84`
- `RPCRT4!NdrClientCall3` at `0x180063af3`
- `RPCRT4!NdrClientCall3` at `0x180063b84`
- `RPCRT4!I_RpcExceptionFilter` at `0x180066fe9`
- `RPCRT4!I_RpcExceptionFilter` at `0x180067005`
- `RPCRT4!I_RpcExceptionFilter` at `0x180066fe9`
- `RPCRT4!I_RpcExceptionFilter` at `0x180067005`
- `RPCRT4!I_RpcMapWin32Status` at `0x180063b1e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180063b9c`
- `RPCRT4!I_RpcMapWin32Status` at `0x180063b1e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180063b9c`

## pseudocode

```c

```
