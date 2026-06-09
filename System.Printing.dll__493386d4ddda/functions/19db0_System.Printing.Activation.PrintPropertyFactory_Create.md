# System.Printing.Activation.PrintPropertyFactory::Create

- ea: `0x19db0`
- end: `0x19dd0`
- name: `System.Printing.Activation.PrintPropertyFactory::Create`
- size: `32`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0xad90`
- `0xaef0`
- `0xb050`
- `0x100d0`
- `0x129c0`
- `0x13a60`
- `0x181a0`

## callees

- `0x147f0`

## pseudocode

```c

```

## disassembly

```asm
0x19db0  ldarg.0
0x19db1  ldfld    class [mscorlib]System.Collections.Hashtable System.Printing.Activation.PrintPropertyFactory::valueLinkedDelegatesTable
0x19db6  ldarg.1
0x19db7  callvirt instance string [mscorlib]System.Type::get_FullName()
0x19dbc  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x19dc1  castclass CreateWithValueLinked
0x19dc6  ldarg.2
0x19dc7  ldarg.3
0x19dc8  ldarg.s  4
0x19dca  callvirt instance class System.Printing.IndexedProperties.PrintProperty CreateWithValueLinked::Invoke(string attributeName, object attributeValue, class [mscorlib]System.MulticastDelegate delegate)
0x19dcf  ret
```
