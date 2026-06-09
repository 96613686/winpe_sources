# CRegistryInfo::SafeReadBinaryValue(RegKey *,ushort const *,uchar * *,uint *)

- ea: `0x180064458`
- end: `0x1800645e3`
- name: `?SafeReadBinaryValue@CRegistryInfo@@IEAAJPEAVRegKey@@PEBGPEAPEAEPEAI@Z`
- size: `395`
- prototype: `int(CRegistryInfo *__hidden this, struct RegKey *, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800640a4`
- `0x1800cd1e8`
- `0x1800d3390`

## callees

- `0x180064458`
- `0x1800bd9d4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180064598`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180064598`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800644f7`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800644f7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800644b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180064527`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800644b7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180064527`

## pseudocode

```c

```
