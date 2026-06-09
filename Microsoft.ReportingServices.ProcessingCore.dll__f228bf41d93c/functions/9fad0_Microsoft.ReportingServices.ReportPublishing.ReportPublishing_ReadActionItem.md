# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadActionItem

- ea: `0x9fad0`
- end: `0x9fcae`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadActionItem`
- size: `478`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callers

- `0x9f9f0`

## callees

- `0x9fad0`
- `0x9fcb0`
- `0xac760`
- `0xbcdc0`
- `0xbcde0`
- `0xbce10`
- `0xbce20`
- `0xeedb0`
- `0xeede0`
- `0xeee30`
- `0xeee50`
- `0xeee70`
- `0xef5b0`
- `0x1767c0`

## string_xrefs

- `0x9fb49`: `Hyperlink`
- `0x9fb65`: `BookmarkLink`

## pseudocode

```c

```

## disassembly

```asm
0x9fad0  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::.ctor()
0x9fad5  stloc.0
0x9fad6  ldc.i4.0
0x9fad7  stloc.1
0x9fad8  ldc.i4.0
0x9fad9  stloc.2
0x9fada  ldc.i4.0
0x9fadb  stloc.3
0x9fadc  ldc.i4.0
0x9fadd  stloc.s  4
0x9fadf  ldc.i4.0
0x9fae0  stloc.s  5
0x9fae2  ldc.i4.0
0x9fae3  stloc.s  6
0x9fae5  ldc.i4.0
0x9fae6  stloc.s  7
0x9fae8  ldc.i4.0
0x9fae9  stloc.s  8
0x9faeb  ldarg.s  5
0x9faed  ldc.i4.0
0x9faee  stind.i1
0x9faef  ldarga.s 1
0x9faf1  ldstr    aActioninfoActi// "ActionInfo.Action."
0x9faf6  call     instance void Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::set_PrefixPropertyName(string value)
0x9fafb  ldarg.0
0x9fafc  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9fb01  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x9fb06  brtrue   loc_9FC1E
0x9fb0b  ldc.i4.0
0x9fb0c  stloc.s  0xA
0x9fb0e  ldarg.0
0x9fb0f  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9fb14  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x9fb19  pop
0x9fb1a  ldarg.0
0x9fb1b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9fb20  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x9fb25  stloc.s  0xB
0x9fb27  ldloc.s  0xB
0x9fb29  ldc.i4.1
0x9fb2a  beq.s    loc_9FB3A
0x9fb2c  ldloc.s  0xB
0x9fb2e  ldc.i4.s 0xF
0x9fb30  beq      loc_9FBFD
0x9fb35  br       loc_9FC17
0x9fb3a  ldarg.0
0x9fb3b  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9fb40  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9fb45  stloc.s  0xC
0x9fb47  ldloc.s  0xC
0x9fb49  ldstr    aHyperlink// "Hyperlink"
0x9fb4e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fb53  brtrue.s loc_9FB84
0x9fb55  ldloc.s  0xC
0x9fb57  ldstr    aDrillthrough// "Drillthrough"
0x9fb5c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fb61  brtrue.s loc_9FBAC
0x9fb63  ldloc.s  0xC
0x9fb65  ldstr    aBookmarklink// "BookmarkLink"
0x9fb6a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fb6f  brtrue.s loc_9FBBA
0x9fb71  ldloc.s  0xC
0x9fb73  ldstr    aLabel// "Label"
0x9fb78  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fb7d  brtrue.s loc_9FBDB
0x9fb7f  br       loc_9FC17
0x9fb84  ldarg.0
0x9fb85  ldc.i4.1
0x9fb86  stfld    bool Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_hasHyperlinks
0x9fb8b  ldc.i4.1
0x9fb8c  stloc.1
0x9fb8d  ldloc.0
0x9fb8e  ldarg.0
0x9fb8f  ldarg.0
0x9fb90  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9fb95  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9fb9a  ldc.i4.0
0x9fb9b  ldc.i4.s 0x12
0x9fb9d  ldarg.1
0x9fb9e  ldloca.s 5
0x9fba0  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, [out] bool& computed)
0x9fba5  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::set_HyperLinkURL(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9fbaa  br.s     loc_9FC17
0x9fbac  ldc.i4.1
0x9fbad  stloc.2
0x9fbae  ldarg.0
0x9fbaf  ldarg.1
0x9fbb0  ldloc.0
0x9fbb1  ldloca.s 6
0x9fbb3  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadDrillthrough(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, class Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem actionItem, [out] bool& computed)
0x9fbb8  br.s     loc_9FC17
0x9fbba  ldc.i4.1
0x9fbbb  stloc.3
0x9fbbc  ldloc.0
0x9fbbd  ldarg.0
0x9fbbe  ldarg.0
0x9fbbf  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9fbc4  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9fbc9  ldc.i4.0
0x9fbca  ldc.i4.s 0x12
0x9fbcc  ldarg.1
0x9fbcd  ldloca.s 7
0x9fbcf  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, [out] bool& computed)
0x9fbd4  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::set_BookmarkLink(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9fbd9  br.s     loc_9FC17
0x9fbdb  ldc.i4.1
0x9fbdc  stloc.s  4
0x9fbde  ldloc.0
0x9fbdf  ldarg.0
0x9fbe0  ldarg.0
0x9fbe1  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9fbe6  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9fbeb  ldc.i4.0
0x9fbec  ldc.i4.s 0x12
0x9fbee  ldarg.1
0x9fbef  ldloca.s 8
0x9fbf1  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadExpression(string propertyName, valuetype ExpressionType expressionType, valuetype Microsoft.ReportingServices.ReportProcessing.DataType constantType, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, [out] bool& computed)
0x9fbf6  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::set_Label(class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo value)
0x9fbfb  br.s     loc_9FC17
0x9fbfd  ldstr    aAction_0// "Action"
0x9fc02  ldarg.0
0x9fc03  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0x9fc08  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x9fc0d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9fc12  brfalse.s loc_9FC17
0x9fc14  ldc.i4.1
0x9fc15  stloc.s  0xA
0x9fc17  ldloc.s  0xA
0x9fc19  brfalse  loc_9FB0E
0x9fc1e  ldc.i4.0
0x9fc1f  stloc.s  9
0x9fc21  ldloc.1
0x9fc22  brfalse.s loc_9FC2A
0x9fc24  ldloc.s  9
0x9fc26  ldc.i4.1
0x9fc27  add
0x9fc28  stloc.s  9
0x9fc2a  ldloc.2
0x9fc2b  brfalse.s loc_9FC4F
0x9fc2d  ldloc.s  9
0x9fc2f  ldc.i4.1
0x9fc30  add
0x9fc31  stloc.s  9
0x9fc33  ldarg.s  5
0x9fc35  ldloc.0
0x9fc36  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::get_DrillthroughParameters()
0x9fc3b  brfalse.s loc_9FC4D
0x9fc3d  ldloc.0
0x9fc3e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue> Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::get_DrillthroughParameters()
0x9fc43  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterValue>::get_Count()
0x9fc48  ldc.i4.0
0x9fc49  cgt
0x9fc4b  br.s     loc_9FC4E
0x9fc4d  ldc.i4.0
0x9fc4e  stind.i1
0x9fc4f  ldloc.3
0x9fc50  brfalse.s loc_9FC58
0x9fc52  ldloc.s  9
0x9fc54  ldc.i4.1
0x9fc55  add
0x9fc56  stloc.s  9
0x9fc58  ldc.i4.1
0x9fc59  ldloc.s  9
0x9fc5b  beq.s    loc_9FC85
0x9fc5d  ldarga.s 1
0x9fc5f  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0x9fc64  ldc.i4.s 0x54
0x9fc66  ldc.i4.0
0x9fc67  ldarga.s 1
0x9fc69  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0x9fc6e  ldarga.s 1
0x9fc70  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0x9fc75  ldstr    aAction_0// "Action"
0x9fc7a  call     T0x2B000001
0x9fc7f  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0x9fc84  pop
0x9fc85  ldloc.s  4
0x9fc87  brtrue.s loc_9FC8D
0x9fc89  ldarg.s  4
0x9fc8b  ldc.i4.1
0x9fc8c  stind.i1
0x9fc8d  ldarg.2
0x9fc8e  ldloc.s  5
0x9fc90  ldloc.s  6
0x9fc92  or
0x9fc93  ldloc.s  7
0x9fc95  or
0x9fc96  ldloc.s  8
0x9fc98  or
0x9fc99  stind.i1
0x9fc9a  ldarg.2
0x9fc9b  ldind.u1
0x9fc9c  brfalse.s loc_9FCAC
0x9fc9e  ldarg.3
0x9fc9f  ldarg.3
0x9fca0  ldind.i4
0x9fca1  ldc.i4.1
0x9fca2  add
0x9fca3  stind.i4
0x9fca4  ldloc.0
0x9fca5  ldarg.3
0x9fca6  ldind.i4
0x9fca7  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ActionItem::set_ComputedIndex(int32 value)
0x9fcac  ldloc.0
0x9fcad  ret
```
