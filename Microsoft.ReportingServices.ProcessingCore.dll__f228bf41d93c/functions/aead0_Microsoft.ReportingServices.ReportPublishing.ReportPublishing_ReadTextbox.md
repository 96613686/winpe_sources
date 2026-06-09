# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadTextbox

- ea: `0xaead0`
- end: `0xaf330`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadTextbox`
- size: `2144`
- prototype: ``
- caller_count: `3`
- callee_count: `68`
- tags: `service_task, broker_com_uri`

## callers

- `0x9ec50`
- `0xa8b30`
- `0xb3ab0`

## callees

- `0x9d040`
- `0x9d080`
- `0x9f700`
- `0x9f830`
- `0x9f860`
- `0x9f890`
- `0x9f8c0`
- `0x9fe00`
- `0xac760`
- `0xac7a0`
- `0xaca00`
- `0xaead0`
- `0xaf330`
- `0xafc40`
- `0xb07f0`
- `0xb10f0`
- `0xb1150`
- `0xb9b90`
- `0xbb940`
- `0xbb9a0`
- `0xbcda0`
- `0xbcdc0`
- `0xbcdd0`
- `0xbcde0`
- `0xbcdf0`
- `0xbce20`
- `0xbe1c0`
- `0xbe2b0`
- `0xbf380`
- `0xc1260`
- `0x124ca0`
- `0x124cb0`
- `0x124cd0`
- `0x124d20`
- `0x124d60`
- `0x124da0`
- `0x124de0`
- `0x124ee0`
- `0x124f00`
- `0x124f20`
- `0x124f40`
- `0x124f60`
- `0x124f80`
- `0x124fc0`
- `0x124ff0`
- `0x125030`
- `0x1250b0`
- `0x125270`
- `0x1252a0`
- `0x128ef0`

## string_xrefs

- `0xaeec0`: `StructureTypeOverwrite`

## pseudocode

```c

```

## disassembly

```asm
0xaead0  ldarg.0
0xaead1  call     instance int32 Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GenerateID()
0xaead6  ldarg.1
0xaead7  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.TextBox::.ctor(int32 id, class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem parent)
0xaeadc  stloc.0
0xaeadd  ldloc.0
0xaeade  ldarg.0
0xaeadf  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xaeae4  ldstr    aName_1// "Name"
0xaeae9  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xaeaee  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::set_Name(string value)
0xaeaf3  ldloc.0
0xaeaf4  ldarg.0
0xaeaf5  call     instance int32 Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GenerateTextboxSequenceID()
0xaeafa  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.TextBox::set_SequenceID(int32 value)
0xaeaff  ldarga.s 2
0xaeb01  ldloc.0
0xaeb02  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_ObjectType()
0xaeb07  call     instance void Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0xaeb0c  ldarga.s 2
0xaeb0e  ldloc.0
0xaeb0f  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Name()
0xaeb14  call     instance void Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::set_ObjectName(string value)
0xaeb19  ldc.i4.1
0xaeb1a  stloc.1
0xaeb1b  ldarg.0
0xaeb1c  ldfld    class Microsoft.ReportingServices.ReportPublishing.CLSUniqueNameValidator Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reportItemNames
0xaeb21  ldarga.s 2
0xaeb23  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xaeb28  ldarga.s 2
0xaeb2a  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xaeb2f  ldarga.s 2
0xaeb31  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xaeb36  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.CLSUniqueNameValidator::Validate(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string name, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xaeb3b  brtrue.s loc_AEB3F
0xaeb3d  ldc.i4.0
0xaeb3e  stloc.1
0xaeb3f  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0xaeb44  ldarg.0
0xaeb45  ldfld    class Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reportCT
0xaeb4a  callvirt instance bool Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::get_ValueReferenced()
0xaeb4f  ldc.i4.0
0xaeb50  ceq
0xaeb52  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0xaeb57  ldc.i4.0
0xaeb58  stloc.2
0xaeb59  ldc.i4.0
0xaeb5a  stloc.3
0xaeb5b  ldc.i4.0
0xaeb5c  stloc.s  4
0xaeb5e  ldc.i4.0
0xaeb5f  stloc.s  5
0xaeb61  ldc.i4.0
0xaeb62  stloc.s  6
0xaeb64  ldc.i4.0
0xaeb65  stloc.s  7
0xaeb67  ldc.i4.0
0xaeb68  stloc.s  8
0xaeb6a  ldc.i4.0
0xaeb6b  stloc.s  9
0xaeb6d  ldc.i4.0
0xaeb6e  stloc.s  0xA
0xaeb70  ldc.i4.0
0xaeb71  stloc.s  0xB
0xaeb73  ldarg.0
0xaeb74  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xaeb79  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xaeb7e  pop
0xaeb7f  ldarg.0
0xaeb80  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xaeb85  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xaeb8a  stloc.s  0xC
0xaeb8c  ldloc.s  0xC
0xaeb8e  ldc.i4.1
0xaeb8f  beq.s    loc_AEB9F
0xaeb91  ldloc.s  0xC
0xaeb93  ldc.i4.s 0xF
0xaeb95  beq      loc_AF2B1
0xaeb9a  br       loc_AF2CB
0xaeb9f  ldarg.0
0xaeba0  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xaeba5  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xaebaa  stloc.s  0x12
0xaebac  ldloc.s  0x12
0xaebae  brfalse  loc_AF2CB
0xaebb3  ldloc.s  0x12
0xaebb5  call     instance int32 [mscorlib]System.String::get_Length()
0xaebba  stloc.s  0x13
0xaebbc  ldloc.s  0x13
0xaebbe  ldc.i4.3
0xaebbf  sub
0xaebc0  switch   loc_AED8A, loc_AEDA0, loc_AEC1A, loc_AEC79, loc_AEC9A, loc_AECE5, loc_AEE92, loc_AEC3B, loc_AEED4, loc_AEF16, loc_AF2CB, loc_AEEA8, loc_AEEEA, loc_AECBB, loc_AEF00, loc_AF2CB, loc_AEE7C, loc_AF2CB, loc_AF2CB, loc_AEEBE
0xaec15  br       loc_AF2CB
0xaec1a  ldloc.s  0x12
0xaec1c  ldc.i4.0
0xaec1d  call     instance char [mscorlib]System.String::get_Chars(int32)
0xaec22  stloc.s  0x14
0xaec24  ldloc.s  0x14
0xaec26  ldc.i4.s 0x53
0xaec28  beq      loc_AED06
0xaec2d  ldloc.s  0x14
0xaec2f  ldc.i4.s 0x57
0xaec31  beq      loc_AED1C
0xaec36  br       loc_AF2CB
0xaec3b  ldloc.s  0x12
0xaec3d  ldc.i4.0
0xaec3e  call     instance char [mscorlib]System.String::get_Chars(int32)
0xaec43  stloc.s  0x14
0xaec45  ldloc.s  0x14
0xaec47  ldc.i4.s 0x50
0xaec49  bgt.un.s loc_AEC62
0xaec4b  ldloc.s  0x14
0xaec4d  ldc.i4.s 0x41
0xaec4f  beq      loc_AED32
0xaec54  ldloc.s  0x14
0xaec56  ldc.i4.s 0x50
0xaec58  beq      loc_AED74
0xaec5d  br       loc_AF2CB
0xaec62  ldloc.s  0x14
0xaec64  ldc.i4.s 0x52
0xaec66  beq      loc_AED5E
0xaec6b  ldloc.s  0x14
0xaec6d  ldc.i4.s 0x56
0xaec6f  beq      loc_AED48
0xaec74  br       loc_AF2CB
0xaec79  ldloc.s  0x12
0xaec7b  ldc.i4.0
0xaec7c  call     instance char [mscorlib]System.String::get_Chars(int32)
0xaec81  stloc.s  0x14
0xaec83  ldloc.s  0x14
0xaec85  ldc.i4.s 0x48
0xaec87  beq      loc_AEDB6
0xaec8c  ldloc.s  0x14
0xaec8e  ldc.i4.s 0x5A
0xaec90  beq      loc_AEDCC
0xaec95  br       loc_AF2CB
0xaec9a  ldloc.s  0x12
0xaec9c  ldc.i4.0
0xaec9d  call     instance char [mscorlib]System.String::get_Chars(int32)
0xaeca2  stloc.s  0x14
0xaeca4  ldloc.s  0x14
0xaeca6  ldc.i4.s 0x43
0xaeca8  beq      loc_AEDF8
0xaecad  ldloc.s  0x14
0xaecaf  ldc.i4.s 0x54
0xaecb1  beq      loc_AEDE2
0xaecb6  br       loc_AF2CB
0xaecbb  ldloc.s  0x12
0xaecbd  ldc.i4.1
0xaecbe  call     instance char [mscorlib]System.String::get_Chars(int32)
0xaecc3  stloc.s  0x14
0xaecc5  ldloc.s  0x14
0xaecc7  ldc.i4.s 0x61
0xaecc9  beq      loc_AEE3A
0xaecce  ldloc.s  0x14
0xaecd0  ldc.i4.s 0x6F
0xaecd2  beq      loc_AEE0E
0xaecd7  ldloc.s  0x14
0xaecd9  ldc.i4.s 0x75
0xaecdb  beq      loc_AEE24
0xaece0  br       loc_AF2CB
0xaece5  ldloc.s  0x12
0xaece7  ldc.i4.0
0xaece8  call     instance char [mscorlib]System.String::get_Chars(int32)
0xaeced  stloc.s  0x14
0xaecef  ldloc.s  0x14
0xaecf1  ldc.i4.s 0x42
0xaecf3  beq      loc_AEE50
0xaecf8  ldloc.s  0x14
0xaecfa  ldc.i4.s 0x55
0xaecfc  beq      loc_AEE66
0xaed01  br       loc_AF2CB
0xaed06  ldloc.s  0x12
0xaed08  ldstr    aStyle_1// "Style"
0xaed0d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaed12  brtrue   loc_AEF2C
0xaed17  br       loc_AF2CB
0xaed1c  ldloc.s  0x12
0xaed1e  ldstr    aWidth// "Width"
0xaed23  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaed28  brtrue   loc_AF004
0xaed2d  br       loc_AF2CB
0xaed32  ldloc.s  0x12
0xaed34  ldstr    aActioninfo// "ActionInfo"
0xaed39  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaed3e  brtrue   loc_AEFBB
0xaed43  br       loc_AF2CB
0xaed48  ldloc.s  0x12
0xaed4a  ldstr    aVisibility// "Visibility"
0xaed4f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaed54  brtrue   loc_AF044
0xaed59  br       loc_AF2CB
0xaed5e  ldloc.s  0x12
0xaed60  ldstr    aRepeatwith// "RepeatWith"
0xaed65  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaed6a  brtrue   loc_AF0AD
0xaed6f  br       loc_AF2CB
0xaed74  ldloc.s  0x12
0xaed76  ldstr    aParagraphs// "Paragraphs"
0xaed7b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaed80  brtrue   loc_AF0DE
0xaed85  br       loc_AF2CB
0xaed8a  ldloc.s  0x12
0xaed8c  ldstr    aTop// "Top"
0xaed91  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaed96  brtrue   loc_AEFD1
0xaed9b  br       loc_AF2CB
0xaeda0  ldloc.s  0x12
0xaeda2  ldstr    aLeft// "Left"
0xaeda7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaedac  brtrue   loc_AEFE2
0xaedb1  br       loc_AF2CB
0xaedb6  ldloc.s  0x12
0xaedb8  ldstr    aHeight// "Height"
0xaedbd  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaedc2  brtrue   loc_AEFF3
0xaedc7  br       loc_AF2CB
0xaedcc  ldloc.s  0x12
0xaedce  ldstr    aZindex// "ZIndex"
0xaedd3  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaedd8  brtrue   loc_AF015
0xaeddd  br       loc_AF2CB
0xaede2  ldloc.s  0x12
0xaede4  ldstr    aTooltip// "ToolTip"
0xaede9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaedee  brtrue   loc_AF058
0xaedf3  br       loc_AF2CB
0xaedf8  ldloc.s  0x12
0xaedfa  ldstr    aCangrow// "CanGrow"
0xaedff  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaee04  brtrue   loc_AF141
0xaee09  br       loc_AF2CB
0xaee0e  ldloc.s  0x12
0xaee10  ldstr    aDocumentmaplab_0// "DocumentMapLabel"
0xaee15  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaee1a  brtrue   loc_AF07A
0xaee1f  br       loc_AF2CB
0xaee24  ldloc.s  0x12
0xaee26  ldstr    aCustomproperti// "CustomProperties"
0xaee2b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaee30  brtrue   loc_AF0CA
0xaee35  br       loc_AF2CB
0xaee3a  ldloc.s  0x12
0xaee3c  ldstr    aDataelementsty// "DataElementStyle"
0xaee41  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaee46  brtrue   loc_AF264
0xaee4b  br       loc_AF2CB
0xaee50  ldloc.s  0x12
0xaee52  ldstr    aBookmark// "Bookmark"
0xaee57  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaee5c  brtrue   loc_AF099
0xaee61  br       loc_AF2CB
0xaee66  ldloc.s  0x12
0xaee68  ldstr    aUsersort// "UserSort"
0xaee6d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaee72  brtrue   loc_AF22E
0xaee77  br       loc_AF2CB
0xaee7c  ldloc.s  0x12
0xaee7e  ldstr    aCanscrollverti// "CanScrollVertically"
0xaee83  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaee88  brtrue   loc_AF112
0xaee8d  br       loc_AF2CB
0xaee92  ldloc.s  0x12
0xaee94  ldstr    aCanshrink// "CanShrink"
0xaee99  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaee9e  brtrue   loc_AF170
0xaeea3  br       loc_AF2CB
0xaeea8  ldloc.s  0x12
0xaeeaa  ldstr    aHideduplicates// "HideDuplicates"
0xaeeaf  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaeeb4  brtrue   loc_AF19F
0xaeeb9  br       loc_AF2CB
0xaeebe  ldloc.s  0x12
0xaeec0  ldstr    aStructuretypeo// "StructureTypeOverwrite"
0xaeec5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaeeca  brtrue   loc_AF1DF
0xaeecf  br       loc_AF2CB
0xaeed4  ldloc.s  0x12
0xaeed6  ldstr    aToggleimage// "ToggleImage"
0xaeedb  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaeee0  brtrue   loc_AF21A
0xaeee5  br       loc_AF2CB
0xaeeea  ldloc.s  0x12
0xaeeec  ldstr    aDataelementnam// "DataElementName"
0xaeef1  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaeef6  brtrue   loc_AF243
0xaeefb  br       loc_AF2CB
0xaef00  ldloc.s  0x12
0xaef02  ldstr    aDataelementout// "DataElementOutput"
0xaef07  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaef0c  brtrue   loc_AF256
0xaef11  br       loc_AF2CB
0xaef16  ldloc.s  0x12
0xaef18  ldstr    aKeeptogether// "KeepTogether"
0xaef1d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaef22  brtrue   loc_AF285
0xaef27  br       loc_AF2CB
0xaef2c  ldarg.0
0xaef2d  ldfld    class Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reportCT
0xaef32  callvirt instance bool Microsoft.ReportingServices.RdlExpressions.ExprHostCompiler::get_ValueReferenced()
  ... truncated ...
```
