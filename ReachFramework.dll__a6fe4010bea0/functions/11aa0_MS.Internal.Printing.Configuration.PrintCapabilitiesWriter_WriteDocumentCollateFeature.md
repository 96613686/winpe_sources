# MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteDocumentCollateFeature

- ea: `0x11aa0`
- end: `0x11afa`
- name: `MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteDocumentCollateFeature`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0xd8a0`

## callees

- `0x126e0`
- `0x12720`
- `0x12820`

## string_xrefs

- `0x11aa1`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x11aab`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x11ac0`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x11ada`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c

```

## disassembly

```asm
0x11aa0  ldarg.0
0x11aa1  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x11aa6  ldstr    aDocumentcollat// "DocumentCollate"
0x11aab  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x11ab0  ldstr    aPickone// "PickOne"
0x11ab5  ldc.i4   0xFCF4
0x11aba  call     instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteStartFeature(string featureNamespace, string featureName, string selectionTypeNamespace, string selectionTypeName, unsigned int32 displayNameId)
0x11abf  ldarg.0
0x11ac0  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x11ac5  ldstr    aCollated// "Collated"
0x11aca  ldc.i4   0xFCD9
0x11acf  ldstr    aNone// "None"
0x11ad4  call     instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteOption(string optionNamespace, string optionName, unsigned int32 displayNameId, string pskConstraint)
0x11ad9  ldarg.0
0x11ada  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x11adf  ldstr    aUncollated// "Uncollated"
0x11ae4  ldc.i4   0xFCD8
0x11ae9  ldstr    aNone// "None"
0x11aee  call     instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteOption(string optionNamespace, string optionName, unsigned int32 displayNameId, string pskConstraint)
0x11af3  ldarg.0
0x11af4  call     instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteEndFeature()
0x11af9  ret
```
