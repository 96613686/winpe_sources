# SuplNode::GetStringRegValue(HKEY__ *,ushort const *,ushort const *,tagVARIANT *)

- ea: `0x1801185f8`
- end: `0x180118759`
- name: `?GetStringRegValue@SuplNode@@AEAAJPEAUHKEY__@@PEBG1PEAUtagVARIANT@@@Z`
- size: `353`
- prototype: `int(SuplNode *__hidden this, HKEY, const unsigned __int16 *, const unsigned __int16 *, struct tagVARIANT *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800a0ac0`
- `0x18011885c`

## callees

- `0x1800a98c0`
- `0x1801185f8`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18011870c`
- `OLEAUT32!__imp_SysAllocString` at `0x18011870c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180118729`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180118729`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180118656`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180118656`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801186a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801186f5`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801186a1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1801186f5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801186c4`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1801186c4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180118732`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180118732`

## pseudocode

```c

```
