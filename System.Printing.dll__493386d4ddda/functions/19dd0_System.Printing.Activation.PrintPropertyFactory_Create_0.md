# System.Printing.Activation.PrintPropertyFactory::Create_0

- ea: `0x19dd0`
- end: `0x19dee`
- name: `System.Printing.Activation.PrintPropertyFactory::Create_0`
- size: `30`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0xad70`
- `0xaed0`
- `0xb030`
- `0x100b0`
- `0x129a0`
- `0x13a40`
- `0x18180`

## callees

- `0x147a0`

## pseudocode

```c

```

## disassembly

```asm
0x19dd0  ldarg.0
0x19dd1  ldfld    class [mscorlib]System.Collections.Hashtable System.Printing.Activation.PrintPropertyFactory::noValueLinkedDelegatesTable
0x19dd6  ldarg.1
0x19dd7  callvirt instance string [mscorlib]System.Type::get_FullName()
0x19ddc  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x19de1  castclass CreateWithNoValueLinked
0x19de6  ldarg.2
0x19de7  ldarg.3
0x19de8  callvirt instance class System.Printing.IndexedProperties.PrintProperty CreateWithNoValueLinked::Invoke(string attributeName, class [mscorlib]System.MulticastDelegate delegate)
0x19ded  ret
```
