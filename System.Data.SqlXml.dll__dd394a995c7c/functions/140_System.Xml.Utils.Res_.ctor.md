# System.Xml.Utils.Res::.ctor

- ea: `0x140`
- end: `0x162`
- name: `System.Xml.Utils.Res::.ctor`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x170`

## string_xrefs

- `0x147`: `System.Xml.Utils`

## pseudocode

```c

```

## disassembly

```asm
0x140  ldarg.0
0x141  call     instance void [mscorlib]System.Object::.ctor()
0x146  ldarg.0
0x147  ldstr    aSystemXmlUtils// "System.Xml.Utils"
0x14c  ldarg.0
0x14d  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x152  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x157  newobj   instance void [mscorlib]System.Resources.ResourceManager::.ctor(string, class [mscorlib]System.Reflection.Assembly)
0x15c  stfld    class [mscorlib]System.Resources.ResourceManager System.Xml.Utils.Res::resources
0x161  ret
```
