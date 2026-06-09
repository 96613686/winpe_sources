# MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WritePageColorManagementFeature

- ea: `0x11dd0`
- end: `0x11e4e`
- name: `MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WritePageColorManagementFeature`
- size: `126`
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

- `0x11dd1`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x11ddb`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x11df0`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x11e06`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x11e1c`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x11e32`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c

```

## disassembly

```asm
0x11dd0  ldarg.0
0x11dd1  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x11dd6  ldstr    aPagecolormanag// "PageColorManagement"
0x11ddb  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x11de0  ldstr    aPickone// "PickOne"
0x11de5  ldc.i4   0xFCED
0x11dea  call     instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteStartFeature(string featureNamespace, string featureName, string selectionTypeNamespace, string selectionTypeName, unsigned int32 displayNameId)
0x11def  ldarg.0
0x11df0  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x11df5  ldstr    aNone// "None"
0x11dfa  ldc.i4.m1
0x11dfb  ldstr    aNone// "None"
0x11e00  call     instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteOption(string optionNamespace, string optionName, unsigned int32 displayNameId, string pskConstraint)
0x11e05  ldarg.0
0x11e06  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x11e0b  ldstr    aSystem// "System"
0x11e10  ldc.i4.m1
0x11e11  ldstr    aNone// "None"
0x11e16  call     instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteOption(string optionNamespace, string optionName, unsigned int32 displayNameId, string pskConstraint)
0x11e1b  ldarg.0
0x11e1c  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x11e21  ldstr    aDriver// "Driver"
0x11e26  ldc.i4.m1
0x11e27  ldstr    aNone// "None"
0x11e2c  call     instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteOption(string optionNamespace, string optionName, unsigned int32 displayNameId, string pskConstraint)
0x11e31  ldarg.0
0x11e32  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x11e37  ldstr    aDevice// "Device"
0x11e3c  ldc.i4.m1
0x11e3d  ldstr    aNone// "None"
0x11e42  call     instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteOption(string optionNamespace, string optionName, unsigned int32 displayNameId, string pskConstraint)
0x11e47  ldarg.0
0x11e48  call     instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteEndFeature()
0x11e4d  ret
```
