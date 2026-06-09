# LsaOpenPolicy

- ea: `0x180020088`
- end: `0x18002022b`
- name: `LsaOpenPolicy`
- size: `419`
- prototype: `NTSTATUS __stdcall(PLSA_UNICODE_STRING SystemName, PLSA_OBJECT_ATTRIBUTES ObjectAttributes, ACCESS_MASK DesiredAccess, PLSA_HANDLE PolicyHandle)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001e0bc`
- `0x18001fdf0`
- `0x18001ff70`
- `0x18001ff80`
- `0x18002062c`
- `0x180027848`
- `0x18003ead0`
- `0x18004fde0`
- `0x180051d90`

## callees

- `0x180020088`
- `0x1800202c0`
- `0x180024c1c`
- `0x180026c80`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x180020160`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800201df`
- `RPCRT4!I_RpcMapWin32Status` at `0x180020160`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800201df`
- `RPCRT4!I_RpcExceptionFilter` at `0x18006535f`
- `RPCRT4!I_RpcExceptionFilter` at `0x18006537b`
- `RPCRT4!I_RpcExceptionFilter` at `0x18006535f`
- `RPCRT4!I_RpcExceptionFilter` at `0x18006537b`
- `RPCRT4!NdrClientCall3` at `0x1800201c6`
- `RPCRT4!NdrClientCall3` at `0x1800201c6`

## pseudocode

```c

```
