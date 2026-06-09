# MS.Internal.Printing.Configuration.PrintCapBuilder::BuildFeature

- ea: `0x15bd0`
- end: `0x15d29`
- name: `MS.Internal.Printing.Configuration.PrintCapBuilder::BuildFeature`
- size: `345`
- prototype: ``
- caller_count: `2`
- callee_count: `18`
- tags: `registry_config`

## callers

- `0x15b70`
- `0x15bd0`

## callees

- `0x157a0`
- `0x157b0`
- `0x157c0`
- `0x157d0`
- `0x157e0`
- `0x157f0`
- `0x15820`
- `0x15840`
- `0x15bd0`
- `0x15e10`
- `0x15e60`
- `0x16680`
- `0x16800`
- `0x169d0`
- `0x169e0`
- `0x169f0`
- `0x16a00`
- `0x3f210`

## pseudocode

```c

```

## disassembly

```asm
0x15bd0  ldarg.0
0x15bd1  ldfld    class MS.Internal.Printing.Configuration.XmlPrintCapReader MS.Internal.Printing.Configuration.PrintCapBuilder::_reader
0x15bd6  callvirt instance string MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementNameAttrValue()
0x15bdb  ldarg.2
0x15bdc  ldnull
0x15bdd  cgt.un
0x15bdf  call     int32 MS.Internal.Printing.Configuration.PrintCapBuilder::LookupFeatureIndex(string featureName, bool isSubFeature)
0x15be4  stloc.0
0x15be5  ldloc.0
0x15be6  ldc.i4.0
0x15be7  bge.s    loc_15BEA
0x15be9  ret
0x15bea  ldarg.0
0x15beb  ldfld    class MS.Internal.Printing.Configuration.XmlPrintCapReader MS.Internal.Printing.Configuration.PrintCapBuilder::_reader
0x15bf0  callvirt instance string MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementNameAttrValue()
0x15bf5  ldarg.2
0x15bf6  ldnull
0x15bf7  cgt.un
0x15bf9  ldloca.s 1
0x15bfb  call     void MS.Internal.Printing.Configuration.PrintCapBuilder::LookupFeatureCallbacks(string featureName, bool isSubFeature, [out] class NewFeatureHandler& newFeatureCallback)
0x15c00  ldloc.1
0x15c01  ldarg.1
0x15c02  callvirt instance class MS.Internal.Printing.Configuration.PrintCapabilityFeature NewFeatureHandler::Invoke(class MS.Internal.Printing.Configuration.InternalPrintCapabilities printCap)
0x15c07  stloc.2
0x15c08  ldarg.0
0x15c09  ldfld    class MS.Internal.Printing.Configuration.XmlPrintCapReader MS.Internal.Printing.Configuration.PrintCapBuilder::_reader
0x15c0e  callvirt instance int32 MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementDepth()
0x15c13  ldc.i4.1
0x15c14  add
0x15c15  stloc.3
0x15c16  ldloc.2
0x15c17  callvirt instance bool MS.Internal.Printing.Configuration.PrintCapabilityFeature::get_HasSubFeature()
0x15c1c  brfalse.s loc_15C2A
0x15c1e  ldc.i4   0x118
0x15c23  stloc.s  4
0x15c25  br       loc_15CF9
0x15c2a  ldc.i4   0x110
0x15c2f  stloc.s  4
0x15c31  br       loc_15CF9
0x15c36  ldarg.0
0x15c37  ldfld    class MS.Internal.Printing.Configuration.XmlPrintCapReader MS.Internal.Printing.Configuration.PrintCapBuilder::_reader
0x15c3c  callvirt instance valuetype MS.Internal.Printing.Configuration.PrintSchemaNodeTypes MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementNodeType()
0x15c41  ldc.i4   0x100
0x15c46  bne.un.s loc_15C66
0x15c48  ldc.i4.0
0x15c49  stloc.s  5
0x15c4b  ldloc.2
0x15c4c  ldloc.2
0x15c4d  ldarg.0
0x15c4e  ldfld    class MS.Internal.Printing.Configuration.XmlPrintCapReader MS.Internal.Printing.Configuration.PrintCapBuilder::_reader
0x15c53  callvirt instance bool MS.Internal.Printing.Configuration.PrintCapabilityFeature::FeaturePropCallback(class MS.Internal.Printing.Configuration.PrintCapabilityFeature feature, class MS.Internal.Printing.Configuration.XmlPrintCapReader reader)
0x15c58  stloc.s  5
0x15c5a  ldloc.s  5
0x15c5c  brtrue   loc_15CF9
0x15c61  br       loc_15CF9
0x15c66  ldarg.0
0x15c67  ldfld    class MS.Internal.Printing.Configuration.XmlPrintCapReader MS.Internal.Printing.Configuration.PrintCapBuilder::_reader
0x15c6c  callvirt instance valuetype MS.Internal.Printing.Configuration.PrintSchemaNodeTypes MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementNodeType()
0x15c71  ldc.i4.s 0x10
0x15c73  bne.un.s loc_15CE3
0x15c75  ldloc.2
0x15c76  ldloc.2
0x15c77  callvirt instance class MS.Internal.Printing.Configuration.PrintCapabilityOption MS.Internal.Printing.Configuration.PrintCapabilityFeature::NewOptionCallback(class MS.Internal.Printing.Configuration.PrintCapabilityFeature baseFeature)
0x15c7c  stloc.s  6
0x15c7e  ldarg.0
0x15c7f  ldfld    class MS.Internal.Printing.Configuration.XmlPrintCapReader MS.Internal.Printing.Configuration.PrintCapBuilder::_reader
0x15c84  ldloc.s  6
0x15c86  callvirt instance void MS.Internal.Printing.Configuration.XmlPrintCapReader::OptionAttributeGenericHandler(class MS.Internal.Printing.Configuration.PrintCapabilityOption option)
0x15c8b  ldloc.2
0x15c8c  ldloc.s  6
0x15c8e  ldarg.0
0x15c8f  ldfld    class MS.Internal.Printing.Configuration.XmlPrintCapReader MS.Internal.Printing.Configuration.PrintCapBuilder::_reader
0x15c94  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilityFeature::OptionAttrCallback(class MS.Internal.Printing.Configuration.PrintCapabilityOption option, class MS.Internal.Printing.Configuration.XmlPrintCapReader reader)
0x15c99  ldarg.0
0x15c9a  ldfld    class MS.Internal.Printing.Configuration.XmlPrintCapReader MS.Internal.Printing.Configuration.PrintCapBuilder::_reader
0x15c9f  callvirt instance bool MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementIsEmpty()
0x15ca4  brtrue.s loc_15CD7
0x15ca6  ldloc.3
0x15ca7  ldc.i4.1
0x15ca8  add
0x15ca9  stloc.s  7
0x15cab  br.s     loc_15CC3
0x15cad  ldc.i4.0
0x15cae  stloc.s  8
0x15cb0  ldloc.2
0x15cb1  ldloc.s  6
0x15cb3  ldarg.0
0x15cb4  ldfld    class MS.Internal.Printing.Configuration.XmlPrintCapReader MS.Internal.Printing.Configuration.PrintCapBuilder::_reader
0x15cb9  callvirt instance bool MS.Internal.Printing.Configuration.PrintCapabilityFeature::OptionPropCallback(class MS.Internal.Printing.Configuration.PrintCapabilityOption option, class MS.Internal.Printing.Configuration.XmlPrintCapReader reader)
0x15cbe  stloc.s  8
0x15cc0  ldloc.s  8
0x15cc2  pop
0x15cc3  ldarg.0
0x15cc4  ldfld    class MS.Internal.Printing.Configuration.XmlPrintCapReader MS.Internal.Printing.Configuration.PrintCapBuilder::_reader
0x15cc9  ldloc.s  7
0x15ccb  ldc.i4   0x300
0x15cd0  callvirt instance bool MS.Internal.Printing.Configuration.XmlPrintCapReader::MoveToNextSchemaElement(int32 depth, valuetype MS.Internal.Printing.Configuration.PrintSchemaNodeTypes typeFilterFlags)
0x15cd5  brtrue.s loc_15CAD
0x15cd7  ldloc.2
0x15cd8  ldloc.s  6
0x15cda  callvirt instance bool MS.Internal.Printing.Configuration.PrintCapabilityFeature::AddOptionCallback(class MS.Internal.Printing.Configuration.PrintCapabilityOption option)
0x15cdf  brtrue.s loc_15CF9
0x15ce1  br.s     loc_15CF9
0x15ce3  ldarg.0
0x15ce4  ldfld    class MS.Internal.Printing.Configuration.XmlPrintCapReader MS.Internal.Printing.Configuration.PrintCapBuilder::_reader
0x15ce9  callvirt instance valuetype MS.Internal.Printing.Configuration.PrintSchemaNodeTypes MS.Internal.Printing.Configuration.XmlPrintCapReader::get_CurrentElementNodeType()
0x15cee  ldc.i4.8
0x15cef  bne.un.s loc_15CF9
0x15cf1  ldarg.0
0x15cf2  ldarg.1
0x15cf3  ldloc.2
0x15cf4  call     instance void MS.Internal.Printing.Configuration.PrintCapBuilder::BuildFeature(class MS.Internal.Printing.Configuration.InternalPrintCapabilities printCap, class MS.Internal.Printing.Configuration.PrintCapabilityFeature parentFeature)
0x15cf9  ldarg.0
0x15cfa  ldfld    class MS.Internal.Printing.Configuration.XmlPrintCapReader MS.Internal.Printing.Configuration.PrintCapBuilder::_reader
0x15cff  ldloc.3
0x15d00  ldloc.s  4
0x15d02  callvirt instance bool MS.Internal.Printing.Configuration.XmlPrintCapReader::MoveToNextSchemaElement(int32 depth, valuetype MS.Internal.Printing.Configuration.PrintSchemaNodeTypes typeFilterFlags)
0x15d07  brtrue   loc_15C36
0x15d0c  ldloc.2
0x15d0d  callvirt instance bool MS.Internal.Printing.Configuration.PrintCapabilityFeature::get_IsValid()
0x15d12  brfalse.s loc_15D28
0x15d14  ldarg.2
0x15d15  brfalse.s loc_15D1F
0x15d17  ldarg.2
0x15d18  ldloc.2
0x15d19  callvirt instance void MS.Internal.Printing.Configuration.PrintCapabilityFeature::AddSubFeatureCallback(class MS.Internal.Printing.Configuration.PrintCapabilityFeature subFeature)
0x15d1e  ret
0x15d1f  ldarg.1
0x15d20  ldfld    object[] MS.Internal.Printing.Configuration.InternalPrintCapabilities::_pcRootFeatures
0x15d25  ldloc.0
0x15d26  ldloc.2
0x15d27  stelem.ref
0x15d28  ret
```
