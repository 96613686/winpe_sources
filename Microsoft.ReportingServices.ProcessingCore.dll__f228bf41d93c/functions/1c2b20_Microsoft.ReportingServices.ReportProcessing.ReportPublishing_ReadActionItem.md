# Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadActionItem

- ea: `0x1c2b20`
- end: `0x1c2ce2`
- name: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadActionItem`
- size: `450`
- prototype: ``
- caller_count: `4`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1ba120`
- `0x1baac0`
- `0x1bfdb0`
- `0x1c2a60`

## callees

- `0x1767c0`
- `0x19a5d0`
- `0x19a650`
- `0x19a670`
- `0x19a690`
- `0x19ab10`
- `0x1c2b20`
- `0x1c2cf0`
- `0x1c32a0`
- `0x2643a0`
- `0x2643c0`
- `0x2643e0`

## string_xrefs

- `0x1c2b89`: `Hyperlink`
- `0x1c2ba5`: `BookmarkLink`

## pseudocode

```c

```

## disassembly

```asm
0x1c2b20  newobj   instance void Microsoft.ReportingServices.ReportProcessing.ActionItem::.ctor()
0x1c2b25  stloc.0
0x1c2b26  ldc.i4.0
0x1c2b27  stloc.1
0x1c2b28  ldc.i4.0
0x1c2b29  stloc.2
0x1c2b2a  ldc.i4.0
0x1c2b2b  stloc.3
0x1c2b2c  ldc.i4.0
0x1c2b2d  stloc.s  4
0x1c2b2f  ldc.i4.0
0x1c2b30  stloc.s  5
0x1c2b32  ldc.i4.0
0x1c2b33  stloc.s  6
0x1c2b35  ldc.i4.0
0x1c2b36  stloc.s  7
0x1c2b38  ldc.i4.0
0x1c2b39  stloc.s  8
0x1c2b3b  ldarg.0
0x1c2b3c  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1c2b41  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1c2b46  brtrue   loc_1C2C5B
0x1c2b4b  ldc.i4.0
0x1c2b4c  stloc.s  0xA
0x1c2b4e  ldarg.0
0x1c2b4f  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1c2b54  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1c2b59  pop
0x1c2b5a  ldarg.0
0x1c2b5b  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1c2b60  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1c2b65  stloc.s  0xB
0x1c2b67  ldloc.s  0xB
0x1c2b69  ldc.i4.1
0x1c2b6a  beq.s    loc_1C2B7A
0x1c2b6c  ldloc.s  0xB
0x1c2b6e  ldc.i4.s 0xF
0x1c2b70  beq      loc_1C2C3A
0x1c2b75  br       loc_1C2C54
0x1c2b7a  ldarg.0
0x1c2b7b  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1c2b80  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1c2b85  stloc.s  0xC
0x1c2b87  ldloc.s  0xC
0x1c2b89  ldstr    aHyperlink// "Hyperlink"
0x1c2b8e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c2b93  brtrue.s loc_1C2BC4
0x1c2b95  ldloc.s  0xC
0x1c2b97  ldstr    aDrillthrough// "Drillthrough"
0x1c2b9c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c2ba1  brtrue.s loc_1C2BEB
0x1c2ba3  ldloc.s  0xC
0x1c2ba5  ldstr    aBookmarklink// "BookmarkLink"
0x1c2baa  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c2baf  brtrue.s loc_1C2BF9
0x1c2bb1  ldloc.s  0xC
0x1c2bb3  ldstr    aLabel// "Label"
0x1c2bb8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c2bbd  brtrue.s loc_1C2C19
0x1c2bbf  br       loc_1C2C54
0x1c2bc4  ldarg.0
0x1c2bc5  ldc.i4.1
0x1c2bc6  stfld    bool Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_hasHyperlinks
0x1c2bcb  ldc.i4.1
0x1c2bcc  stloc.1
0x1c2bcd  ldloc.0
0x1c2bce  ldarg.0
0x1c2bcf  ldarg.0
0x1c2bd0  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1c2bd5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1c2bda  ldc.i4.0
0x1c2bdb  ldc.i4.0
0x1c2bdc  ldarg.1
0x1c2bdd  ldloca.s 5
0x1c2bdf  call     instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype ConstantType constantType, valuetype PublishingContextStruct context, [out] bool& computed)
0x1c2be4  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ActionItem::set_HyperLinkURL(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo value)
0x1c2be9  br.s     loc_1C2C54
0x1c2beb  ldc.i4.1
0x1c2bec  stloc.2
0x1c2bed  ldarg.0
0x1c2bee  ldarg.1
0x1c2bef  ldloc.0
0x1c2bf0  ldloca.s 6
0x1c2bf2  call     instance void Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadDrillthrough(valuetype PublishingContextStruct context, class Microsoft.ReportingServices.ReportProcessing.ActionItem actionItem, [out] bool& computed)
0x1c2bf7  br.s     loc_1C2C54
0x1c2bf9  ldc.i4.1
0x1c2bfa  stloc.3
0x1c2bfb  ldloc.0
0x1c2bfc  ldarg.0
0x1c2bfd  ldarg.0
0x1c2bfe  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1c2c03  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1c2c08  ldc.i4.0
0x1c2c09  ldc.i4.0
0x1c2c0a  ldarg.1
0x1c2c0b  ldloca.s 7
0x1c2c0d  call     instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype ConstantType constantType, valuetype PublishingContextStruct context, [out] bool& computed)
0x1c2c12  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ActionItem::set_BookmarkLink(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo value)
0x1c2c17  br.s     loc_1C2C54
0x1c2c19  ldc.i4.1
0x1c2c1a  stloc.s  4
0x1c2c1c  ldloc.0
0x1c2c1d  ldarg.0
0x1c2c1e  ldarg.0
0x1c2c1f  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1c2c24  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1c2c29  ldc.i4.0
0x1c2c2a  ldc.i4.0
0x1c2c2b  ldarg.1
0x1c2c2c  ldloca.s 8
0x1c2c2e  call     instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype ConstantType constantType, valuetype PublishingContextStruct context, [out] bool& computed)
0x1c2c33  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ActionItem::set_Label(class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo value)
0x1c2c38  br.s     loc_1C2C54
0x1c2c3a  ldstr    aAction_0// "Action"
0x1c2c3f  ldarg.0
0x1c2c40  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1c2c45  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1c2c4a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1c2c4f  brfalse.s loc_1C2C54
0x1c2c51  ldc.i4.1
0x1c2c52  stloc.s  0xA
0x1c2c54  ldloc.s  0xA
0x1c2c56  brfalse  loc_1C2B4E
0x1c2c5b  ldc.i4.0
0x1c2c5c  stloc.s  9
0x1c2c5e  ldloc.1
0x1c2c5f  brfalse.s loc_1C2C67
0x1c2c61  ldloc.s  9
0x1c2c63  ldc.i4.1
0x1c2c64  add
0x1c2c65  stloc.s  9
0x1c2c67  ldloc.2
0x1c2c68  brfalse.s loc_1C2C84
0x1c2c6a  ldloc.s  9
0x1c2c6c  ldc.i4.1
0x1c2c6d  add
0x1c2c6e  stloc.s  9
0x1c2c70  ldarga.s 1
0x1c2c72  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.LocationFlags PublishingContextStruct::get_Location()
0x1c2c77  ldc.i4.s 0x40
0x1c2c79  and
0x1c2c7a  ldc.i4.0
0x1c2c7b  ble.s    loc_1C2C84
0x1c2c7d  ldarg.0
0x1c2c7e  ldc.i4.1
0x1c2c7f  stfld    bool Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_pageSectionDrillthroughs
0x1c2c84  ldloc.3
0x1c2c85  brfalse.s loc_1C2C8D
0x1c2c87  ldloc.s  9
0x1c2c89  ldc.i4.1
0x1c2c8a  add
0x1c2c8b  stloc.s  9
0x1c2c8d  ldc.i4.1
0x1c2c8e  ldloc.s  9
0x1c2c90  beq.s    loc_1C2CB9
0x1c2c92  ldarg.0
0x1c2c93  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_errorContext
0x1c2c98  ldc.i4.s 0x54
0x1c2c9a  ldc.i4.0
0x1c2c9b  ldarga.s 1
0x1c2c9d  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType PublishingContextStruct::get_ObjectType()
0x1c2ca2  ldarga.s 1
0x1c2ca4  call     instance string PublishingContextStruct::get_ObjectName()
0x1c2ca9  ldstr    aAction_0// "Action"
0x1c2cae  call     T0x2B000001
0x1c2cb3  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x1c2cb8  pop
0x1c2cb9  ldloc.s  4
0x1c2cbb  brtrue.s loc_1C2CC1
0x1c2cbd  ldarg.s  4
0x1c2cbf  ldc.i4.1
0x1c2cc0  stind.i1
0x1c2cc1  ldarg.2
0x1c2cc2  ldloc.s  5
0x1c2cc4  ldloc.s  6
0x1c2cc6  or
0x1c2cc7  ldloc.s  7
0x1c2cc9  or
0x1c2cca  ldloc.s  8
0x1c2ccc  or
0x1c2ccd  stind.i1
0x1c2cce  ldarg.2
0x1c2ccf  ldind.u1
0x1c2cd0  brfalse.s loc_1C2CE0
0x1c2cd2  ldarg.3
0x1c2cd3  ldarg.3
0x1c2cd4  ldind.i4
0x1c2cd5  ldc.i4.1
0x1c2cd6  add
0x1c2cd7  stind.i4
0x1c2cd8  ldloc.0
0x1c2cd9  ldarg.3
0x1c2cda  ldind.i4
0x1c2cdb  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ActionItem::set_ComputedIndex(int32 value)
0x1c2ce0  ldloc.0
0x1c2ce1  ret
```
