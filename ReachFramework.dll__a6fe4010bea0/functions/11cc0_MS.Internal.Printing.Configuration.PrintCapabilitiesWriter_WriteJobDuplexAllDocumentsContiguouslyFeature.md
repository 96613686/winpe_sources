# MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteJobDuplexAllDocumentsContiguouslyFeature

- ea: `0x11cc0`
- end: `0x11d37`
- name: `MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteJobDuplexAllDocumentsContiguouslyFeature`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0xd8a0`

## callees

- `0x11cc0`
- `0x126e0`
- `0x12720`
- `0x12820`

## string_xrefs

- `0x11cc4`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x11cce`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x11ce3`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x11cfd`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x11d17`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`
- `0x11ce8`: `OneSided`
- `0x11d02`: `TwoSidedLongEdge`
- `0x11d1c`: `TwoSidedShortEdge`

## pseudocode

```c

```

## disassembly

```asm
0x11cc0  ldarg.1
0x11cc1  brfalse.s loc_11D36
0x11cc3  ldarg.0
0x11cc4  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x11cc9  ldstr    aJobduplexalldo// "JobDuplexAllDocumentsContiguously"
0x11cce  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x11cd3  ldstr    aPickone// "PickOne"
0x11cd8  ldc.i4   0xFCE9
0x11cdd  call     instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteStartFeature(string featureNamespace, string featureName, string selectionTypeNamespace, string selectionTypeName, unsigned int32 displayNameId)
0x11ce2  ldarg.0
0x11ce3  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x11ce8  ldstr    aOnesided// "OneSided"
0x11ced  ldc.i4   0xFCFF
0x11cf2  ldstr    aNone// "None"
0x11cf7  call     instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteOption(string optionNamespace, string optionName, unsigned int32 displayNameId, string pskConstraint)
0x11cfc  ldarg.0
0x11cfd  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x11d02  ldstr    aTwosidedlonged// "TwoSidedLongEdge"
0x11d07  ldc.i4   0xFD01
0x11d0c  ldstr    aNone// "None"
0x11d11  call     instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteOption(string optionNamespace, string optionName, unsigned int32 displayNameId, string pskConstraint)
0x11d16  ldarg.0
0x11d17  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x11d1c  ldstr    aTwosidedshorte// "TwoSidedShortEdge"
0x11d21  ldc.i4   0xFD00
0x11d26  ldstr    aNone// "None"
0x11d2b  call     instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteOption(string optionNamespace, string optionName, unsigned int32 displayNameId, string pskConstraint)
0x11d30  ldarg.0
0x11d31  call     instance void MS.Internal.Printing.Configuration.PrintCapabilitiesWriter::WriteEndFeature()
0x11d36  ret
```
