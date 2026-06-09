# Microsoft.Reporting.CommonStrings::get_MapTileServerConfigurationDesc

- ea: `0xe60`
- end: `0xe6b`
- name: `Microsoft.Reporting.CommonStrings::get_MapTileServerConfigurationDesc`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3a3e0`

## string_xrefs

- `0xe60`: `MapTileServerConfigurationDesc`

## pseudocode

```c

```

## disassembly

```asm
0xe60  ldstr    aMaptileserverc// "MapTileServerConfigurationDesc"
0xe65  call     string Keys::GetString(string key)
0xe6a  ret
```
