# System.Windows.Markup.XmlnsDefinitionAttribute::.ctor

- ea: `0x1b290`
- end: `0x1b2c1`
- name: `System.Windows.Markup.XmlnsDefinitionAttribute::.ctor`
- size: `49`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1b290`

## string_xrefs

- `0x1b299`: `xmlNamespace`

## pseudocode

```c

```

## disassembly

```asm
0x1b290  ldarg.0
0x1b291  call     instance void [mscorlib]System.Attribute::.ctor()
0x1b296  ldarg.1
0x1b297  brtrue.s loc_1B2A4
0x1b299  ldstr    aXmlnamespace// "xmlNamespace"
0x1b29e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1b2a3  throw
0x1b2a4  ldarg.2
0x1b2a5  brtrue.s loc_1B2B2
0x1b2a7  ldstr    aClrnamespace// "clrNamespace"
0x1b2ac  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1b2b1  throw
0x1b2b2  ldarg.0
0x1b2b3  ldarg.1
0x1b2b4  stfld    string System.Windows.Markup.XmlnsDefinitionAttribute::_xmlNamespace
0x1b2b9  ldarg.0
0x1b2ba  ldarg.2
0x1b2bb  stfld    string System.Windows.Markup.XmlnsDefinitionAttribute::_clrNamespace
0x1b2c0  ret
```
