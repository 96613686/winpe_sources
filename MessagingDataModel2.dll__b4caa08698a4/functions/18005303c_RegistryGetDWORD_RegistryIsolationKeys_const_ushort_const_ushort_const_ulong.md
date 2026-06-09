# RegistryGetDWORD(RegistryIsolationKeys const &,ushort const *,ushort const *,ulong *)

- ea: `0x18005303c`
- end: `0x18005316d`
- name: `?RegistryGetDWORD@@YAJAEBURegistryIsolationKeys@@PEBG1PEAK@Z`
- size: `305`
- prototype: `int(const struct RegistryIsolationKeys *, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180052820`
- `0x1800528d0`

## callees

- `0x180008870`
- `0x18000a754`
- `0x18004e2ec`
- `0x1800527b4`
- `0x18005303c`
- `0x1800c6940`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800530f1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005312b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800530f1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005312b`

## string_xrefs

- `0x1800530ad`: `onecoreuap\internal\net\inc\phone\RegistryIsolationUtil.h`

## pseudocode

```c

```
