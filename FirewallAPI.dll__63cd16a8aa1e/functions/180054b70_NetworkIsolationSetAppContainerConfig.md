# NetworkIsolationSetAppContainerConfig

- ea: `0x180054b70`
- end: `0x180054c87`
- name: `NetworkIsolationSetAppContainerConfig`
- size: `279`
- prototype: `DWORD __stdcall(DWORD dwNumPublicAppCs, PSID_AND_ATTRIBUTES appContainerSids)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180005954`
- `0x18000e960`
- `0x180024c3c`
- `0x1800277b0`
- `0x180054b70`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180054bfb`
- `RPCRT4!NdrClientCall3` at `0x180054bfb`
- `RPCRT4!RpcBindingFree` at `0x180054c57`
- `RPCRT4!RpcBindingFree` at `0x180054c57`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054b9c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180054b9c`

## pseudocode

```c

```
