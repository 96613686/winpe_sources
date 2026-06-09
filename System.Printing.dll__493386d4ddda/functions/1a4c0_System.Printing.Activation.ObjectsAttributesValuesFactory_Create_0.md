# System.Printing.Activation.ObjectsAttributesValuesFactory::Create_0

- ea: `0x1a4c0`
- end: `0x1a4de`
- name: `System.Printing.Activation.ObjectsAttributesValuesFactory::Create_0`
- size: `30`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0xa890`
- `0x110f0`
- `0x12fd0`
- `0x13a80`
- `0x18420`

## callees

- `0xab20`

## pseudocode

```c

```

## disassembly

```asm
0x1a4c0  ldarg.0
0x1a4c1  ldfld    class [mscorlib]System.Collections.Hashtable System.Printing.Activation.ObjectsAttributesValuesFactory::noValueLinkedDelegatesTable
0x1a4c6  ldarg.1
0x1a4c7  callvirt instance string [mscorlib]System.Type::get_FullName()
0x1a4cc  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x1a4d1  castclass CreateWithNoValueLinked
0x1a4d6  ldarg.2
0x1a4d7  ldarg.3
0x1a4d8  callvirt instance class System.Printing.IndexedProperties.PrintProperty CreateWithNoValueLinked::Invoke(string attributeName, class [mscorlib]System.MulticastDelegate delegate)
0x1a4dd  ret
```
