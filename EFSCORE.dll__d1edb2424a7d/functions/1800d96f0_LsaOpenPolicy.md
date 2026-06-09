# LsaOpenPolicy

- ea: `0x1800d96f0`
- end: `0x1800d989a`
- name: `LsaOpenPolicy`
- size: `426`
- prototype: `NTSTATUS __stdcall(PLSA_UNICODE_STRING SystemName, PLSA_OBJECT_ATTRIBUTES ObjectAttributes, ACCESS_MASK DesiredAccess, PLSA_HANDLE PolicyHandle)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180028870`

## callees

- `0x1800d9614`
- `0x1800d96f0`
- `0x1800d993c`
- `0x1800d99a0`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x1800d97cd`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800d984a`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800d97cd`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800d984a`
- `RPCRT4!NdrClientCall3` at `0x1800d9831`
- `RPCRT4!NdrClientCall3` at `0x1800d9831`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800df9ac`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800df9c8`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800df9ac`
- `RPCRT4!I_RpcExceptionFilter` at `0x1800df9c8`

## pseudocode

```c

```
