# FirewallHandle::Get(void)

- ea: `0x180091a60`
- end: `0x180091b0b`
- name: `?Get@FirewallHandle@@QEAAPEAXXZ`
- size: `171`
- prototype: `void *__fastcall(FirewallHandle *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800931cc`

## callees

- `0x18007cbc8`
- `0x180091a60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180091adf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180091adf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091acc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180091acc`
- `FirewallAPI!FWOpenPolicyStore` at `0x180091aa0`
- `FirewallAPI!FWOpenPolicyStore` at `0x180091aa0`
- `FirewallAPI!FWClosePolicyStore` at `0x180091ad7`
- `FirewallAPI!FWClosePolicyStore` at `0x180091ad7`

## string_xrefs

- `0x180091af9`: `onecore\vm\dv\net\hns\service\common\vfp\src\aclhelper.cpp`

## pseudocode

```c

```
