# Microsoft.VisualStudio.Setup.ExtensionRecords::get_Uris

- ea: `0x4e50`
- end: `0x4e57`
- name: `Microsoft.VisualStudio.Setup.ExtensionRecords::get_Uris`
- size: `7`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5050`
- `0x5160`
- `0x5310`
- `0x5350`
- `0x5390`
- `0xeed0`

## pseudocode

```c

```

## disassembly

```asm
0x4e50  ldarg.0
0x4e51  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> Microsoft.VisualStudio.Setup.ExtensionRecords::<Uris>k__BackingField
0x4e56  ret
```
