# LsaCreateTrustedDomainEx

- ea: `0x180041390`
- end: `0x180041521`
- name: `LsaCreateTrustedDomainEx`
- size: `401`
- prototype: `NTSTATUS __stdcall(LSA_HANDLE PolicyHandle, PTRUSTED_DOMAIN_INFORMATION_EX TrustedDomainInformation, PTRUSTED_DOMAIN_AUTH_INFORMATION AuthenticationInformation, ACCESS_MASK DesiredAccess, PLSA_HANDLE TrustedDomainHandle)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config`

## callees

- `0x1800202c0`
- `0x180041328`
- `0x180041390`
- `0x1800420a8`
- `0x180042338`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800414e0`
- `KERNEL32!LocalFree` at `0x1800414f4`
- `KERNEL32!LocalFree` at `0x1800414fd`
- `KERNEL32!LocalFree` at `0x1800414e0`
- `KERNEL32!LocalFree` at `0x1800414f4`
- `KERNEL32!LocalFree` at `0x1800414fd`
- `RPCRT4!I_RpcMapWin32Status` at `0x18004149f`
- `RPCRT4!I_RpcMapWin32Status` at `0x18004149f`
- `RPCRT4!NdrClientCall3` at `0x180041451`
- `RPCRT4!NdrClientCall3` at `0x18004148a`
- `RPCRT4!NdrClientCall3` at `0x180041451`
- `RPCRT4!NdrClientCall3` at `0x18004148a`

## pseudocode

```c

```
