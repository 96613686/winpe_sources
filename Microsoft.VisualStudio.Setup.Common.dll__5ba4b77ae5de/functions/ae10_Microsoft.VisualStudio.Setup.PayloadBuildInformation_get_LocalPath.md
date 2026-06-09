# Microsoft.VisualStudio.Setup.PayloadBuildInformation::get_LocalPath

- ea: `0xae10`
- end: `0xae1c`
- name: `Microsoft.VisualStudio.Setup.PayloadBuildInformation::get_LocalPath`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4dd0`

## string_xrefs

- `0xae11`: `LocalPath`

## pseudocode

```c

```

## disassembly

```asm
0xae10  ldarg.0
0xae11  ldstr    aLocalpath// "LocalPath"
0xae16  call     instance string Microsoft.VisualStudio.Setup.ExtensibleObject::get_Item(string key)
0xae1b  ret
```
