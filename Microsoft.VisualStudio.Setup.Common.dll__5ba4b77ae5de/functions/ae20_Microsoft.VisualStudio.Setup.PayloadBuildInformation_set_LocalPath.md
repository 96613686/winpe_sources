# Microsoft.VisualStudio.Setup.PayloadBuildInformation::set_LocalPath

- ea: `0xae20`
- end: `0xae2d`
- name: `Microsoft.VisualStudio.Setup.PayloadBuildInformation::set_LocalPath`
- size: `13`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x4df0`

## string_xrefs

- `0xae21`: `LocalPath`

## pseudocode

```c

```

## disassembly

```asm
0xae20  ldarg.0
0xae21  ldstr    aLocalpath// "LocalPath"
0xae26  ldarg.1
0xae27  call     instance void Microsoft.VisualStudio.Setup.ExtensibleObject::set_Item(string key, string value)
0xae2c  ret
```
