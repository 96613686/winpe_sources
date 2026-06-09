# Microsoft.VisualStudio.Setup.Manifest`1::ParseJson

- ea: `0x8c00`
- end: `0x8c1e`
- name: `Microsoft.VisualStudio.Setup.Manifest`1::ParseJson`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0xc1a0`
- `0xc1d0`

## string_xrefs

- `0x8c01`: `catalogJson`

## pseudocode

```c

```

## disassembly

```asm
0x8c00  ldarg.0
0x8c01  ldstr    aCatalogjson// "catalogJson"
0x8c06  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string s, string paramName)
0x8c0b  ldarg.1
0x8c0c  ldstr    aSerializer// "serializer"
0x8c11  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x8c16  ldarg.1
0x8c17  ldarg.0
0x8c18  callvirt instance var<u1> class Microsoft.VisualStudio.Setup.Serialization.ModelSerializer`1<mvar<u1>>::Deserialize(!!T0)
0x8c1d  ret
```
