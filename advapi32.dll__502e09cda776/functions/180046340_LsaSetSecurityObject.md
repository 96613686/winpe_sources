# LsaSetSecurityObject

- ea: `0x180046340`
- end: `0x180046475`
- name: `LsaSetSecurityObject`
- size: `309`
- prototype: `NTSTATUS __stdcall(LSA_HANDLE ObjectHandle, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180046340`

## import_xrefs

- `ntdll!RtlMakeSelfRelativeSD` at `0x180046380`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800463d3`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180046380`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800463d3`
- `KERNELBASE!LocalAlloc` at `0x1800463a6`
- `KERNELBASE!LocalAlloc` at `0x1800463a6`
- `KERNEL32!LocalFree` at `0x180046456`
- `KERNEL32!LocalFree` at `0x180046456`
- `RPCRT4!I_RpcMapWin32Status` at `0x180046432`
- `RPCRT4!I_RpcMapWin32Status` at `0x180046432`
- `RPCRT4!NdrClientCall3` at `0x180046416`
- `RPCRT4!NdrClientCall3` at `0x180046416`

## pseudocode

```c

```
