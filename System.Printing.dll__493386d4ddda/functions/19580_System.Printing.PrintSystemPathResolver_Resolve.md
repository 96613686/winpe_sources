# System.Printing.PrintSystemPathResolver::Resolve

- ea: `0x19580`
- end: `0x195a3`
- name: `System.Printing.PrintSystemPathResolver::Resolve`
- size: `35`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x11410`
- `0x13db0`

## callees

- `0x19520`
- `0x19580`

## pseudocode

```c

```

## disassembly

```asm
0x19580  ldarg.0
0x19581  ldfld    class System.Printing.IPrintSystemPathResolver System.Printing.PrintSystemPathResolver::chainLink
0x19586  ldarg.0
0x19587  ldfld    class System.Printing.IndexedProperties.PrintPropertyDictionary System.Printing.PrintSystemPathResolver::protocolParametersCollection
0x1958c  callvirt instance class System.Printing.PrintSystemProtocol System.Printing.IPrintSystemPathResolver::Resolve(class System.Printing.IndexedProperties.PrintPropertyDictionary collection)
0x19591  stloc.0
0x19592  ldarg.0
0x19593  ldloc.0
0x19594  stfld    class System.Printing.PrintSystemProtocol System.Printing.PrintSystemPathResolver::protocol
0x19599  ldloc.0
0x1959a  ldnull
0x1959b  bne.un.s loc_195A0
0x1959d  ldc.i4.0
0x1959e  br.s     loc_195A1
0x195a0  ldc.i4.1
0x195a1  conv.u1
0x195a2  ret
```
