# LsaSetSecurityObject

- ea: `0x180041140`
- end: `0x18004124d`
- name: `LsaSetSecurityObject`
- size: `269`
- prototype: `NTSTATUS __stdcall(LSA_HANDLE ObjectHandle, SECURITY_INFORMATION SecurityInformation, PSECURITY_DESCRIPTOR SecurityDescriptor)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180041140`

## import_xrefs

- `ntdll!RtlMakeSelfRelativeSD` at `0x180041180`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800411c4`
- `ntdll!RtlMakeSelfRelativeSD` at `0x180041180`
- `ntdll!RtlMakeSelfRelativeSD` at `0x1800411c4`
- `KERNELBASE!LocalAlloc` at `0x1800411a0`
- `KERNELBASE!LocalAlloc` at `0x1800411a0`
- `KERNEL32!LocalFree` at `0x180041235`
- `KERNEL32!LocalFree` at `0x180041235`
- `RPCRT4!I_RpcMapWin32Status` at `0x180041217`
- `RPCRT4!I_RpcMapWin32Status` at `0x180041217`
- `RPCRT4!NdrClientCall3` at `0x180041201`
- `RPCRT4!NdrClientCall3` at `0x180041201`

## pseudocode

```c

```
