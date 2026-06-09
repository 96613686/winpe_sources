# Common::RegistryKey::GetStringValue(ushort const *,unsigned __int64,Common::StringBuffer &,ulong *)

- ea: `0x180005ec8`
- end: `0x180006070`
- name: `?GetStringValue@RegistryKey@Common@@QEAAJPEBG_KAEAVStringBuffer@2@PEAK@Z`
- size: `424`
- prototype: `int(Common::RegistryKey *__hidden this, const unsigned __int16 *, unsigned __int64, struct Common::StringBuffer *, unsigned int *)`
- caller_count: `17`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180004bf4`
- `0x18000d180`
- `0x180014a38`
- `0x180015be8`
- `0x180016924`
- `0x18001f28c`
- `0x180020794`
- `0x180028528`
- `0x180028e94`
- `0x18002919c`
- `0x180029940`
- `0x180029c74`
- `0x180031c80`
- `0x18003254c`
- `0x1800348b8`
- `0x1800399a0`
- `0x180046ef8`

## callees

- `0x180005ec8`
- `0x180007a30`
- `0x1800092c0`
- `0x180018248`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005f29`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180005f29`

## string_xrefs

- `0x180006008`: `onecore\base\appmodel\common\registrykey.cpp`

## pseudocode

```c

```
