# System.Windows.Markup.XmlnsPrefixAttribute::.ctor

- ea: `0x1b320`
- end: `0x1b351`
- name: `System.Windows.Markup.XmlnsPrefixAttribute::.ctor`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1b320`

## string_xrefs

- `0x1b329`: `xmlNamespace`

## pseudocode

```c

```

## disassembly

```asm
0x1b320  ldarg.0
0x1b321  call     instance void [mscorlib]System.Attribute::.ctor()
0x1b326  ldarg.1
0x1b327  brtrue.s loc_1B334
0x1b329  ldstr    aXmlnamespace// "xmlNamespace"
0x1b32e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1b333  throw
0x1b334  ldarg.2
0x1b335  brtrue.s loc_1B342
0x1b337  ldstr    aPrefix// "prefix"
0x1b33c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1b341  throw
0x1b342  ldarg.0
0x1b343  ldarg.1
0x1b344  stfld    string System.Windows.Markup.XmlnsPrefixAttribute::_xmlNamespace
0x1b349  ldarg.0
0x1b34a  ldarg.2
0x1b34b  stfld    string System.Windows.Markup.XmlnsPrefixAttribute::_prefix
0x1b350  ret
```
