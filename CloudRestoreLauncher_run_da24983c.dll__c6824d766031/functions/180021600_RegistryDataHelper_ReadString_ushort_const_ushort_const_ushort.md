# RegistryDataHelper::ReadString(ushort const *,ushort const *,ushort * *)

- ea: `0x180021600`
- end: `0x18002177c`
- name: `?ReadString@RegistryDataHelper@@QEBAJPEBG0PEAPEAG@Z`
- size: `380`
- prototype: `int(RegistryDataHelper *__hidden this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180020f48`
- `0x18003dbe8`

## callees

- `0x18000c6e0`
- `0x18000d688`
- `0x180011ea4`
- `0x180015140`
- `0x18001666c`
- `0x18001cf84`
- `0x180021600`
- `0x180021a0c`

## import_xrefs

- `ADVAPI32!RegGetValueW` at `0x18002167f`
- `ADVAPI32!RegGetValueW` at `0x1800216cf`
- `ADVAPI32!RegGetValueW` at `0x18002167f`
- `ADVAPI32!RegGetValueW` at `0x1800216cf`

## string_xrefs

- `0x18002170b`: `shellcommon\internal\shell\inc\RegistryDataHelper.h`
- `0x18002175c`: `shellcommon\internal\shell\inc\RegistryDataHelper.h`

## pseudocode

```c

```
