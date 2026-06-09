# Microsoft.VisualStudio.Setup.ExtensionRecords::PrintMembers

- ea: `0x5160`
- end: `0x51b2`
- name: `Microsoft.VisualStudio.Setup.ExtensionRecords::PrintMembers`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x5120`

## callees

- `0x4e50`
- `0x4e70`
- `0x5100`

## string_xrefs

- `0x5166`: `Uris = `
- `0x5198`: `, UnknownExtensions = `

## pseudocode

```c

```

## disassembly

```asm
0x5160  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::EnsureSufficientExecutionStack()
0x5165  ldarg.1
0x5166  ldstr    aUris// "Uris = "
0x516b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5170  pop
0x5171  ldarg.1
0x5172  ldarg.0
0x5173  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> Microsoft.VisualStudio.Setup.ExtensionRecords::get_Uris()
0x5178  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x517d  pop
0x517e  ldarg.1
0x517f  ldstr    aMarketplaceite// ", MarketPlaceItemNames = "
0x5184  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x5189  pop
0x518a  ldarg.1
0x518b  ldarg.0
0x518c  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> Microsoft.VisualStudio.Setup.ExtensionRecords::get_MarketPlaceItemNames()
0x5191  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x5196  pop
0x5197  ldarg.1
0x5198  ldstr    aUnknownextensi// ", UnknownExtensions = "
0x519d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x51a2  pop
0x51a3  ldarg.1
0x51a4  ldarg.0
0x51a5  call     instance class [mscorlib]System.Collections.Generic.IReadOnlyDictionary`2<string, valuetype Microsoft.VisualStudio.Setup.ExtensionOrigin> Microsoft.VisualStudio.Setup.ExtensionRecords::get_UnknownExtensions()
0x51aa  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(object)
0x51af  pop
0x51b0  ldc.i4.1
0x51b1  ret
```
