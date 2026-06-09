# Microsoft.VisualStudio.Setup.ExtensionRecords::Merge

- ea: `0x5050`
- end: `0x50b2`
- name: `Microsoft.VisualStudio.Setup.ExtensionRecords::Merge`
- size: `98`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x4e20`
- `0x4e50`
- `0x4e70`
- `0x5050`
- `0x5100`
- `0x5110`

## pseudocode

```c

```

## disassembly

```asm
0x5050  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::.ctor()
0x5055  stloc.0
0x5056  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::.ctor()
0x505b  stloc.1
0x505c  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin>::.ctor()
0x5061  stloc.2
0x5062  ldarg.0
0x5063  stloc.3
0x5064  ldc.i4.0
0x5065  stloc.s  4
0x5067  br.s     loc_509C
0x5069  ldloc.3
0x506a  ldloc.s  4
0x506c  ldelem.ref
0x506d  stloc.s  5
0x506f  ldloc.0
0x5070  ldloc.s  5
0x5072  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> Microsoft.VisualStudio.Setup.ExtensionRecords::get_Uris()
0x5077  call     T0x2B00001A
0x507c  ldloc.1
0x507d  ldloc.s  5
0x507f  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> Microsoft.VisualStudio.Setup.ExtensionRecords::get_MarketPlaceItemNames()
0x5084  call     T0x2B00001A
0x5089  ldloc.2
0x508a  ldloc.s  5
0x508c  callvirt instance class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> Microsoft.VisualStudio.Setup.ExtensionRecords::get_UnknownExtensions()
0x5091  call     T0x2B00001A
0x5096  ldloc.s  4
0x5098  ldc.i4.1
0x5099  add
0x509a  stloc.s  4
0x509c  ldloc.s  4
0x509e  ldloc.3
0x509f  ldlen
0x50a0  conv.i4
0x50a1  blt.s    loc_5069
0x50a3  ldloc.0
0x50a4  ldloc.1
0x50a5  newobj   instance void Microsoft.VisualStudio.Setup.ExtensionRecords::.ctor(class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> Uris, class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> MarketPlaceItemNames)
0x50aa  dup
0x50ab  ldloc.2
0x50ac  callvirt instance modreq(System.Runtime.CompilerServices.IsExternalInit) void Microsoft.VisualStudio.Setup.ExtensionRecords::set_UnknownExtensions(class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> value)
0x50b1  ret
```
