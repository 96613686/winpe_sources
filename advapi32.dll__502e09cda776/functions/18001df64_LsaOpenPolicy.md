# LsaOpenPolicy

- ea: `0x18001df64`
- end: `0x18001e11a`
- name: `LsaOpenPolicy`
- size: `438`
- prototype: `NTSTATUS __stdcall(PLSA_UNICODE_STRING SystemName, PLSA_OBJECT_ATTRIBUTES ObjectAttributes, ACCESS_MASK DesiredAccess, PLSA_HANDLE PolicyHandle)`
- caller_count: `9`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x18001ce40`
- `0x18001dc90`
- `0x18001de30`
- `0x18001de40`
- `0x18001f6bc`
- `0x18002c1cc`
- `0x1800438a0`
- `0x180056490`
- `0x18005d648`

## callees

- `0x18001df64`
- `0x18001e1b8`
- `0x180028260`
- `0x18002a014`

## import_xrefs

- `RPCRT4!I_RpcMapWin32Status` at `0x18001e03c`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001e0c7`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001e03c`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001e0c7`
- `RPCRT4!I_RpcExceptionFilter` at `0x18007234e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180072370`
- `RPCRT4!I_RpcExceptionFilter` at `0x18007234e`
- `RPCRT4!I_RpcExceptionFilter` at `0x180072370`
- `RPCRT4!NdrClientCall3` at `0x18001e0a8`
- `RPCRT4!NdrClientCall3` at `0x18001e0a8`

## pseudocode

```c

```
