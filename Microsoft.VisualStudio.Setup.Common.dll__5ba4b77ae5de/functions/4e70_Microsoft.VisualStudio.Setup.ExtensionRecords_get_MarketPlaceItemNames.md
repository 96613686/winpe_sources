# Microsoft.VisualStudio.Setup.ExtensionRecords::get_MarketPlaceItemNames

- ea: `0x4e70`
- end: `0x4e77`
- name: `Microsoft.VisualStudio.Setup.ExtensionRecords::get_MarketPlaceItemNames`
- size: `7`
- prototype: ``
- caller_count: `7`
- callee_count: `0`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5050`
- `0x50c0`
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
0x4e70  ldarg.0
0x4e71  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> Microsoft.VisualStudio.Setup.ExtensionRecords::<MarketPlaceItemNames>k__BackingField
0x4e76  ret
```
