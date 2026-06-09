# NetworkIsolationGetAppContainerConfig

- ea: `0x180054540`
- end: `0x1800546d7`
- name: `NetworkIsolationGetAppContainerConfig`
- size: `407`
- prototype: `DWORD __stdcall(DWORD *pdwNumPublicAppCs, PSID_AND_ATTRIBUTES *appContainerSids)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005954`
- `0x18000e960`
- `0x180024c3c`
- `0x1800277b0`
- `0x180054540`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18005464a`
- `RPCRT4!NdrClientCall3` at `0x18005464a`
- `RPCRT4!RpcBindingFree` at `0x1800546a6`
- `RPCRT4!RpcBindingFree` at `0x1800546a6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005456e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18005456e`

## pseudocode

```c

```
