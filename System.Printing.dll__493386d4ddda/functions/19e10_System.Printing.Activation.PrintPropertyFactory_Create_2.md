# System.Printing.Activation.PrintPropertyFactory::Create_2

- ea: `0x19e10`
- end: `0x19e2d`
- name: `System.Printing.Activation.PrintPropertyFactory::Create_2`
- size: `29`
- prototype: ``
- caller_count: `7`
- callee_count: `1`
- tags: ``

## callers

- `0xad30`
- `0xae90`
- `0xaff0`
- `0x10070`
- `0x12960`
- `0x13a00`
- `0x18140`

## callees

- `0x14700`

## pseudocode

```c

```

## disassembly

```asm
0x19e10  ldarg.0
0x19e11  ldfld    class [mscorlib]System.Collections.Hashtable System.Printing.Activation.PrintPropertyFactory::noValueDelegatesTable
0x19e16  ldarg.1
0x19e17  callvirt instance string [mscorlib]System.Type::get_FullName()
0x19e1c  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x19e21  castclass CreateWithNoValue
0x19e26  ldarg.2
0x19e27  callvirt instance class System.Printing.IndexedProperties.PrintProperty CreateWithNoValue::Invoke(string attributeName)
0x19e2c  ret
```
