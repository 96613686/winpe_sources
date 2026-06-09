# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadRectangle

- ea: `0xafdc0`
- end: `0xb041c`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadRectangle`
- size: `1628`
- prototype: ``
- caller_count: `3`
- callee_count: `50`
- tags: `service_task, broker_com_uri`

## callers

- `0x9ec50`
- `0xa8b30`
- `0xb3ab0`

## callees

- `0x9d040`
- `0x9ec50`
- `0x9ef60`
- `0x9f700`
- `0x9f860`
- `0x9fe00`
- `0xac760`
- `0xac7a0`
- `0xafdc0`
- `0xb07f0`
- `0xb10f0`
- `0xb1150`
- `0xbb940`
- `0xbb9a0`
- `0xbcdc0`
- `0xbcdd0`
- `0xbcde0`
- `0xbcdf0`
- `0xbce20`
- `0xbe1c0`
- `0xbe2b0`
- `0xbf360`
- `0xc1260`
- `0x11ee20`
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
- `0x126b60`
- `0x131640`
- `0x131670`
- `0x1316c0`
- `0x1316e0`
- `0x131910`
- `0x131920`

## string_xrefs

- `0xb00c3`: `LinkToChild`

## pseudocode

```c

```

## disassembly

```asm
0xafdc0  ldarg.0
0xafdc1  call     instance int32 Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GenerateID()
0xafdc6  ldarg.0
0xafdc7  call     instance int32 Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GenerateID()
0xafdcc  ldarg.1
0xafdcd  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.Rectangle::.ctor(int32 id, int32 idForReportItems, class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem parent)
0xafdd2  stloc.0
0xafdd3  ldloc.0
0xafdd4  ldarg.0
0xafdd5  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xafdda  ldstr    aName_1// "Name"
0xafddf  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xafde4  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::set_Name(string value)
0xafde9  ldarga.s 2
0xafdeb  ldloc.0
0xafdec  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_ObjectType()
0xafdf1  call     instance void Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0xafdf6  ldarga.s 2
0xafdf8  ldloc.0
0xafdf9  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Name()
0xafdfe  call     instance void Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::set_ObjectName(string value)
0xafe03  ldc.i4.1
0xafe04  stloc.1
0xafe05  ldarg.0
0xafe06  ldfld    class Microsoft.ReportingServices.ReportPublishing.CLSUniqueNameValidator Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reportItemNames
0xafe0b  ldarga.s 2
0xafe0d  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xafe12  ldarga.s 2
0xafe14  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xafe19  ldarga.s 2
0xafe1b  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xafe20  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.CLSUniqueNameValidator::Validate(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string name, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xafe25  brtrue.s loc_AFE29
0xafe27  ldc.i4.0
0xafe28  stloc.1
0xafe29  ldarg.0
0xafe2a  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItemCollection> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reportItemCollectionList
0xafe2f  ldloc.0
0xafe30  callvirt instance class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItemCollection Microsoft.ReportingServices.ReportIntermediateFormat.Rectangle::get_ReportItems()
0xafe35  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItemCollection>::Add(var<u1>)
0xafe3a  ldc.i4.0
0xafe3b  stloc.2
0xafe3c  ldc.i4.0
0xafe3d  stloc.3
0xafe3e  ldc.i4.0
0xafe3f  stloc.s  4
0xafe41  ldc.i4.0
0xafe42  stloc.s  5
0xafe44  ldc.i4.0
0xafe45  stloc.s  6
0xafe47  ldc.i4.0
0xafe48  stloc.s  7
0xafe4a  ldc.i4.0
0xafe4b  stloc.s  8
0xafe4d  ldc.i4.0
0xafe4e  stloc.s  9
0xafe50  ldnull
0xafe51  stloc.s  0xA
0xafe53  ldnull
0xafe54  stloc.s  0xB
0xafe56  ldarg.0
0xafe57  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xafe5c  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xafe61  brtrue   loc_B03CA
0xafe66  ldarg.0
0xafe67  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xafe6c  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xafe71  pop
0xafe72  ldarg.0
0xafe73  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xafe78  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xafe7d  stloc.s  0xC
0xafe7f  ldloc.s  0xC
0xafe81  ldc.i4.1
0xafe82  beq.s    loc_AFE92
0xafe84  ldloc.s  0xC
0xafe86  ldc.i4.s 0xF
0xafe88  beq      loc_B03A9
0xafe8d  br       loc_B03C3
0xafe92  ldarg.0
0xafe93  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xafe98  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xafe9d  stloc.s  0xF
0xafe9f  ldloc.s  0xF
0xafea1  brfalse  loc_B03C3
0xafea6  ldloc.s  0xF
0xafea8  call     instance int32 [mscorlib]System.String::get_Length()
0xafead  stloc.s  0x10
0xafeaf  ldloc.s  0x10
0xafeb1  ldc.i4.3
0xafeb2  sub
0xafeb3  switch   loc_AFFFB, loc_B0011, loc_AFF09, loc_AFF2A, loc_B007F, loc_AFFAE, loc_B0119, loc_AFF4B, loc_AFF8D, loc_B012F, loc_B03C3, loc_B03C3, loc_B0145, loc_AFF6C, loc_B015B, loc_B03C3, loc_B03C3, loc_B03C3, loc_B0171
0xaff04  br       loc_B03C3
0xaff09  ldloc.s  0xF
0xaff0b  ldc.i4.0
0xaff0c  call     instance char [mscorlib]System.String::get_Chars(int32)
0xaff11  stloc.s  0x11
0xaff13  ldloc.s  0x11
0xaff15  ldc.i4.s 0x53
0xaff17  beq      loc_AFFCF
0xaff1c  ldloc.s  0x11
0xaff1e  ldc.i4.s 0x57
0xaff20  beq      loc_AFFE5
0xaff25  br       loc_B03C3
0xaff2a  ldloc.s  0xF
0xaff2c  ldc.i4.0
0xaff2d  call     instance char [mscorlib]System.String::get_Chars(int32)
0xaff32  stloc.s  0x11
0xaff34  ldloc.s  0x11
0xaff36  ldc.i4.s 0x48
0xaff38  beq      loc_B0027
0xaff3d  ldloc.s  0x11
0xaff3f  ldc.i4.s 0x5A
0xaff41  beq      loc_B003D
0xaff46  br       loc_B03C3
0xaff4b  ldloc.s  0xF
0xaff4d  ldc.i4.0
0xaff4e  call     instance char [mscorlib]System.String::get_Chars(int32)
0xaff53  stloc.s  0x11
0xaff55  ldloc.s  0x11
0xaff57  ldc.i4.s 0x52
0xaff59  beq      loc_B0069
0xaff5e  ldloc.s  0x11
0xaff60  ldc.i4.s 0x56
0xaff62  beq      loc_B0053
0xaff67  br       loc_B03C3
0xaff6c  ldloc.s  0xF
0xaff6e  ldc.i4.0
0xaff6f  call     instance char [mscorlib]System.String::get_Chars(int32)
0xaff74  stloc.s  0x11
0xaff76  ldloc.s  0x11
0xaff78  ldc.i4.s 0x43
0xaff7a  beq      loc_B00AB
0xaff7f  ldloc.s  0x11
0xaff81  ldc.i4.s 0x44
0xaff83  beq      loc_B0095
0xaff88  br       loc_B03C3
0xaff8d  ldloc.s  0xF
0xaff8f  ldc.i4.0
0xaff90  call     instance char [mscorlib]System.String::get_Chars(int32)
0xaff95  stloc.s  0x11
0xaff97  ldloc.s  0x11
0xaff99  ldc.i4.s 0x4C
0xaff9b  beq      loc_B00C1
0xaffa0  ldloc.s  0x11
0xaffa2  ldc.i4.s 0x52
0xaffa4  beq      loc_B00D7
0xaffa9  br       loc_B03C3
0xaffae  ldloc.s  0xF
0xaffb0  ldc.i4.0
0xaffb1  call     instance char [mscorlib]System.String::get_Chars(int32)
0xaffb6  stloc.s  0x11
0xaffb8  ldloc.s  0x11
0xaffba  ldc.i4.s 0x42
0xaffbc  beq      loc_B00ED
0xaffc1  ldloc.s  0x11
0xaffc3  ldc.i4.s 0x50
0xaffc5  beq      loc_B0103
0xaffca  br       loc_B03C3
0xaffcf  ldloc.s  0xF
0xaffd1  ldstr    aStyle_1// "Style"
0xaffd6  call     bool [mscorlib]System.String::op_Equality(string, string)
0xaffdb  brtrue   loc_B0187
0xaffe0  br       loc_B03C3
0xaffe5  ldloc.s  0xF
0xaffe7  ldstr    aWidth// "Width"
0xaffec  call     bool [mscorlib]System.String::op_Equality(string, string)
0xafff1  brtrue   loc_B01FA
0xafff6  br       loc_B03C3
0xafffb  ldloc.s  0xF
0xafffd  ldstr    aTop// "Top"
0xb0002  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb0007  brtrue   loc_B01C7
0xb000c  br       loc_B03C3
0xb0011  ldloc.s  0xF
0xb0013  ldstr    aLeft// "Left"
0xb0018  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb001d  brtrue   loc_B01D8
0xb0022  br       loc_B03C3
0xb0027  ldloc.s  0xF
0xb0029  ldstr    aHeight// "Height"
0xb002e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb0033  brtrue   loc_B01E9
0xb0038  br       loc_B03C3
0xb003d  ldloc.s  0xF
0xb003f  ldstr    aZindex// "ZIndex"
0xb0044  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb0049  brtrue   loc_B020B
0xb004e  br       loc_B03C3
0xb0053  ldloc.s  0xF
0xb0055  ldstr    aVisibility// "Visibility"
0xb005a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb005f  brtrue   loc_B023A
0xb0064  br       loc_B03C3
0xb0069  ldloc.s  0xF
0xb006b  ldstr    aRepeatwith// "RepeatWith"
0xb0070  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb0075  brtrue   loc_B02B9
0xb007a  br       loc_B03C3
0xb007f  ldloc.s  0xF
0xb0081  ldstr    aTooltip// "ToolTip"
0xb0086  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb008b  brtrue   loc_B024E
0xb0090  br       loc_B03C3
0xb0095  ldloc.s  0xF
0xb0097  ldstr    aDocumentmaplab_0// "DocumentMapLabel"
0xb009c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb00a1  brtrue   loc_B0270
0xb00a6  br       loc_B03C3
0xb00ab  ldloc.s  0xF
0xb00ad  ldstr    aCustomproperti// "CustomProperties"
0xb00b2  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb00b7  brtrue   loc_B02D6
0xb00bc  br       loc_B03C3
0xb00c1  ldloc.s  0xF
0xb00c3  ldstr    aLinktochild// "LinkToChild"
0xb00c8  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb00cd  brtrue   loc_B0293
0xb00d2  br       loc_B03C3
0xb00d7  ldloc.s  0xF
0xb00d9  ldstr    aReportitems// "ReportItems"
0xb00de  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb00e3  brtrue   loc_B02EA
0xb00e8  br       loc_B03C3
0xb00ed  ldloc.s  0xF
0xb00ef  ldstr    aBookmark// "Bookmark"
0xb00f4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb00f9  brtrue   loc_B02A5
0xb00fe  br       loc_B03C3
0xb0103  ldloc.s  0xF
0xb0105  ldstr    aPagename// "PageName"
0xb010a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb010f  brtrue   loc_B030E
0xb0114  br       loc_B03C3
0xb0119  ldloc.s  0xF
0xb011b  ldstr    aPagebreak// "PageBreak"
0xb0120  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb0125  brtrue   loc_B0301
0xb012a  br       loc_B03C3
0xb012f  ldloc.s  0xF
0xb0131  ldstr    aKeeptogether// "KeepTogether"
0xb0136  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb013b  brtrue   loc_B0330
0xb0140  br       loc_B03C3
0xb0145  ldloc.s  0xF
0xb0147  ldstr    aDataelementnam// "DataElementName"
0xb014c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb0151  brtrue   loc_B035C
0xb0156  br       loc_B03C3
0xb015b  ldloc.s  0xF
0xb015d  ldstr    aDataelementout// "DataElementOutput"
0xb0162  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb0167  brtrue   loc_B036F
0xb016c  br       loc_B03C3
0xb0171  ldloc.s  0xF
0xb0173  ldstr    aOmitborderonpa// "OmitBorderOnPageBreak"
0xb0178  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb017d  brtrue   loc_B037D
0xb0182  br       loc_B03C3
0xb0187  ldarg.0
0xb0188  ldarg.2
0xb0189  ldloca.s 2
0xb018b  call     instance class Microsoft.ReportingServices.ReportPublishing.StyleInformation Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadStyle(valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, [out] bool& computed)
0xb0190  stloc.s  0xD
0xb0192  ldloc.s  0xD
0xb0194  ldc.i4.2
0xb0195  ldc.i4.0
0xb0196  callvirt instance void Microsoft.ReportingServices.ReportPublishing.StyleInformation::Filter(valuetype Microsoft.ReportingServices.ReportPublishing.StyleOwnerType ownerType, bool hasNoRows)
0xb019b  ldloc.0
0xb019c  ldloc.s  0xD
0xb019e  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> Microsoft.ReportingServices.ReportPublishing.StyleInformation::get_Attributes()
0xb01a3  ldarga.s 2
0xb01a5  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb01aa  ldarga.s 2
0xb01ac  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb01b1  ldarga.s 2
0xb01b3  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xb01b8  call     class Microsoft.ReportingServices.ReportIntermediateFormat.Style Microsoft.ReportingServices.ReportPublishing.PublishingValidator::ValidateAndCreateStyle(class [mscorlib]System.Collections.Generic.List`1<class StyleInformationAttribute> attributes, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xb01bd  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::set_StyleClass(class Microsoft.ReportingServices.ReportIntermediateFormat.Style value)
0xb01c2  br       loc_B03C3
0xb01c7  ldloc.0
0xb01c8  ldarg.0
0xb01c9  call     instance string Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadSize()
0xb01ce  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::set_Top(string value)
0xb01d3  br       loc_B03C3
0xb01d8  ldloc.0
0xb01d9  ldarg.0
0xb01da  call     instance string Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadSize()
0xb01df  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::set_Left(string value)
0xb01e4  br       loc_B03C3
0xb01e9  ldloc.0
0xb01ea  ldarg.0
0xb01eb  call     instance string Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadSize()
0xb01f0  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::set_Height(string value)
0xb01f5  br       loc_B03C3
0xb01fa  ldloc.0
0xb01fb  ldarg.0
0xb01fc  call     instance string Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadSize()
0xb0201  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::set_Width(string value)
0xb0206  br       loc_B03C3
  ... truncated ...
```
