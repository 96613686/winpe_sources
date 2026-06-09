# Microsoft.Reporting.CommonStrings::get_MapTileServerConfigurationMaxConnectionsDesc

- ea: `0xe70`
- end: `0xe7b`
- name: `Microsoft.Reporting.CommonStrings::get_MapTileServerConfigurationMaxConnectionsDesc`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3a3e0`

## string_xrefs

- `0xe70`: `MapTileServerConfigurationMaxConnectionsDesc`

## pseudocode

```c

```

## disassembly

```asm
0xe70  ldstr    aMaptileserverc_0// "MapTileServerConfigurationMaxConnection"...
0xe75  call     string Keys::GetString(string key)
0xe7a  ret
```
