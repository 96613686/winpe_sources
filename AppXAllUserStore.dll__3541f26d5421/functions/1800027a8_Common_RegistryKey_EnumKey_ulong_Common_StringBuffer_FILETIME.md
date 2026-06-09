# Common::RegistryKey::EnumKey(ulong,Common::StringBuffer &,_FILETIME *)

- ea: `0x1800027a8`
- end: `0x1800028f3`
- name: `?EnumKey@RegistryKey@Common@@QEAAJKAEAVStringBuffer@2@PEAU_FILETIME@@@Z`
- size: `331`
- prototype: `int(Common::RegistryKey *__hidden this, unsigned int, struct Common::StringBuffer *, struct _FILETIME *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180003e28`
- `0x18001eaa8`
- `0x18003254c`

## callees

- `0x1800027a8`
- `0x180007a30`
- `0x1800092c0`
- `0x180018248`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000280d`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x18000280d`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180002880`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x180002880`

## string_xrefs

- `0x1800028cd`: `onecore\base\appmodel\common\registrykey.cpp`

## pseudocode

```c

```
