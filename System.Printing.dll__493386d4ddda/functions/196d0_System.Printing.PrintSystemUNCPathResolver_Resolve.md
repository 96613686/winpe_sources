# System.Printing.PrintSystemUNCPathResolver::Resolve

- ea: `0x196d0`
- end: `0x19711`
- name: `System.Printing.PrintSystemUNCPathResolver::Resolve`
- size: `65`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x194e0`
- `0x19520`
- `0x196d0`
- `0x19a00`
- `0x19ab0`

## pseudocode

```c

```

## disassembly

```asm
0x196d0  ldarg.1
0x196d1  brtrue.s loc_196DE
0x196d3  ldstr    aParameterscoll// "parametersCollection"
0x196d8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x196dd  throw
0x196de  ldarg.1
0x196df  callvirt instance class [mscorlib]System.Collections.IDictionaryEnumerator [mscorlib]System.Collections.Hashtable::GetEnumerator()
0x196e4  stloc.1
0x196e5  ldarg.0
0x196e6  ldloc.1
0x196e7  call     instance void System.Printing.PrintSystemUNCPathResolver::ValidateCollectionAndCaptureParameters(class [mscorlib]System.Collections.IDictionaryEnumerator enumerator)
0x196ec  ldarg.0
0x196ed  call     instance void System.Printing.PrintSystemUNCPathResolver::BuildUncPath()
0x196f2  ldc.i4.1
0x196f3  ldarg.0
0x196f4  ldfld    string System.Printing.PrintSystemUNCPathResolver::uncPath
0x196f9  newobj   instance void System.Printing.PrintSystemProtocol::.ctor(valuetype System.Printing.TransportProtocol transportType, string transportpath)
0x196fe  stloc.0
0x196ff  ldloc.0
0x19700  brtrue.s loc_1970F
0x19702  ldarg.0
0x19703  ldfld    class System.Printing.IPrintSystemPathResolver System.Printing.PrintSystemUNCPathResolver::chainLink
0x19708  ldarg.1
0x19709  callvirt instance class System.Printing.PrintSystemProtocol System.Printing.IPrintSystemPathResolver::Resolve(class System.Printing.IndexedProperties.PrintPropertyDictionary collection)
0x1970e  stloc.0
0x1970f  ldloc.0
0x19710  ret
```
