# System.Printing.Activation.PrintPropertyFactory::Create_1

- ea: `0x19df0`
- end: `0x19e0e`
- name: `System.Printing.Activation.PrintPropertyFactory::Create_1`
- size: `30`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: ``

## callers

- `0x8710`
- `0xad50`
- `0xaeb0`
- `0xb010`
- `0x10090`
- `0x12980`
- `0x13a20`
- `0x18160`

## callees

- `0x14750`

## pseudocode

```c

```

## disassembly

```asm
0x19df0  ldarg.0
0x19df1  ldfld    class [mscorlib]System.Collections.Hashtable System.Printing.Activation.PrintPropertyFactory::valueDelegatesTable
0x19df6  ldarg.1
0x19df7  callvirt instance string [mscorlib]System.Type::get_FullName()
0x19dfc  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x19e01  castclass CreateWithValue
0x19e06  ldarg.2
0x19e07  ldarg.3
0x19e08  callvirt instance class System.Printing.IndexedProperties.PrintProperty CreateWithValue::Invoke(string attributeName, object attributeValue)
0x19e0d  ret
```
