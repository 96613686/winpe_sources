# LsaCreateTrustedDomainEx

- ea: `0x1800465c0`
- end: `0x180046776`
- name: `LsaCreateTrustedDomainEx`
- size: `438`
- prototype: `NTSTATUS __stdcall(LSA_HANDLE PolicyHandle, PTRUSTED_DOMAIN_INFORMATION_EX TrustedDomainInformation, PTRUSTED_DOMAIN_AUTH_INFORMATION AuthenticationInformation, ACCESS_MASK DesiredAccess, PLSA_HANDLE TrustedDomainHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x18001e1b8`
- `0x180046554`
- `0x1800465c0`
- `0x1800473e8`
- `0x1800476b4`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180046722`
- `KERNEL32!LocalFree` at `0x18004673c`
- `KERNEL32!LocalFree` at `0x18004674b`
- `KERNEL32!LocalFree` at `0x180046722`
- `KERNEL32!LocalFree` at `0x18004673c`
- `KERNEL32!LocalFree` at `0x18004674b`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800466db`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800466db`
- `RPCRT4!NdrClientCall3` at `0x180046681`
- `RPCRT4!NdrClientCall3` at `0x1800466c0`
- `RPCRT4!NdrClientCall3` at `0x180046681`
- `RPCRT4!NdrClientCall3` at `0x1800466c0`

## pseudocode

```c

```
