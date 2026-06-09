# Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadRectangle

- ea: `0x1b9640`
- end: `0x1b9c30`
- name: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadRectangle`
- size: `1520`
- prototype: ``
- caller_count: `1`
- callee_count: `50`
- tags: `service_task, broker_com_uri`

## callers

- `0x1b7fe0`

## callees

- `0x1942d0`
- `0x198e00`
- `0x198e10`
- `0x198e20`
- `0x198e40`
- `0x198e60`
- `0x198ea0`
- `0x198ee0`
- `0x198f20`
- `0x199060`
- `0x199080`
- `0x1990a0`
- `0x1990c0`
- `0x1990e0`
- `0x199100`
- `0x199120`
- `0x199180`
- `0x199240`
- `0x199260`
- `0x199280`
- `0x199480`
- `0x19aee0`
- `0x19af10`
- `0x19af30`
- `0x19af40`
- `0x19af50`
- `0x19af60`
- `0x1a74a0`
- `0x1b5180`
- `0x1b7fe0`
- `0x1b9640`
- `0x1bbd70`
- `0x1c2e30`
- `0x1c2f70`
- `0x1c32a0`
- `0x1c3510`
- `0x1c37d0`
- `0x1c3f40`
- `0x1cbc90`
- `0x1cd8d0`
- `0x2643c0`
- `0x2643d0`
- `0x2643e0`
- `0x2643f0`
- `0x264820`
- `0x264830`
- `0x264880`
- `0x264af0`
- `0x264b20`
- `0x264b50`

## string_xrefs

- `0x1b9933`: `LinkToChild`

## pseudocode

```c

```

## disassembly

```asm
0x1b9640  ldarg.0
0x1b9641  call     instance int32 Microsoft.ReportingServices.ReportProcessing.ReportPublishing::GenerateID()
0x1b9646  ldarg.0
0x1b9647  call     instance int32 Microsoft.ReportingServices.ReportProcessing.ReportPublishing::GenerateID()
0x1b964c  ldarg.1
0x1b964d  newobj   instance void Microsoft.ReportingServices.ReportProcessing.Rectangle::.ctor(int32 id, int32 idForReportItems, class Microsoft.ReportingServices.ReportProcessing.ReportItem parent)
0x1b9652  stloc.0
0x1b9653  ldloc.0
0x1b9654  ldarg.0
0x1b9655  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b965a  ldstr    aName_1// "Name"
0x1b965f  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0x1b9664  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportItem::set_Name(string value)
0x1b9669  ldarga.s 2
0x1b966b  ldloc.0
0x1b966c  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportProcessing.ReportItem::get_ObjectType()
0x1b9671  call     instance void PublishingContextStruct::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0x1b9676  ldarga.s 2
0x1b9678  ldloc.0
0x1b9679  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ReportItem::get_Name()
0x1b967e  call     instance void PublishingContextStruct::set_ObjectName(string value)
0x1b9683  ldarg.0
0x1b9684  ldfld    class Microsoft.ReportingServices.ReportProcessing.CLSUniqueNameValidator Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reportItemNames
0x1b9689  ldarga.s 2
0x1b968b  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType PublishingContextStruct::get_ObjectType()
0x1b9690  ldarga.s 2
0x1b9692  call     instance string PublishingContextStruct::get_ObjectName()
0x1b9697  ldarg.0
0x1b9698  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_errorContext
0x1b969d  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.CLSUniqueNameValidator::Validate(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string name, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0x1b96a2  pop
0x1b96a3  ldarg.0
0x1b96a4  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reportItemCollectionList
0x1b96a9  ldloc.0
0x1b96aa  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportItemCollection Microsoft.ReportingServices.ReportProcessing.Rectangle::get_ReportItems()
0x1b96af  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x1b96b4  pop
0x1b96b5  ldarg.0
0x1b96b6  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_runningValueHolderList
0x1b96bb  ldloc.0
0x1b96bc  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ReportItemCollection Microsoft.ReportingServices.ReportProcessing.Rectangle::get_ReportItems()
0x1b96c1  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x1b96c6  pop
0x1b96c7  ldc.i4.0
0x1b96c8  stloc.1
0x1b96c9  ldc.i4.0
0x1b96ca  stloc.2
0x1b96cb  ldc.i4.0
0x1b96cc  stloc.3
0x1b96cd  ldc.i4.0
0x1b96ce  stloc.s  4
0x1b96d0  ldc.i4.0
0x1b96d1  stloc.s  5
0x1b96d3  ldc.i4.0
0x1b96d4  stloc.s  6
0x1b96d6  ldc.i4.0
0x1b96d7  stloc.s  7
0x1b96d9  ldc.i4.0
0x1b96da  stloc.s  8
0x1b96dc  ldnull
0x1b96dd  stloc.s  9
0x1b96df  ldnull
0x1b96e0  stloc.s  0xA
0x1b96e2  ldnull
0x1b96e3  stloc.s  0xB
0x1b96e5  ldarg.0
0x1b96e6  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b96eb  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1b96f0  brtrue   loc_1B9BC5
0x1b96f5  ldarg.0
0x1b96f6  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b96fb  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1b9700  pop
0x1b9701  ldarg.0
0x1b9702  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b9707  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1b970c  stloc.s  0xC
0x1b970e  ldloc.s  0xC
0x1b9710  ldc.i4.1
0x1b9711  beq.s    loc_1B9721
0x1b9713  ldloc.s  0xC
0x1b9715  ldc.i4.s 0xF
0x1b9717  beq      loc_1B9BA4
0x1b971c  br       loc_1B9BBE
0x1b9721  ldarg.0
0x1b9722  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1b9727  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1b972c  stloc.s  0xE
0x1b972e  ldloc.s  0xE
0x1b9730  brfalse  loc_1B9BBE
0x1b9735  ldloc.s  0xE
0x1b9737  call     instance int32 [mscorlib]System.String::get_Length()
0x1b973c  stloc.s  0xF
0x1b973e  ldloc.s  0xF
0x1b9740  ldc.i4.3
0x1b9741  sub
0x1b9742  switch   loc_1B9881, loc_1B9897, loc_1B9788, loc_1B97B2, loc_1B991B, loc_1B995D, loc_1B9BBE, loc_1B97DC, loc_1B97FD, loc_1B9BBE, loc_1B9BBE, loc_1B999F, loc_1B99B5, loc_1B981E, loc_1B99CB
0x1b9783  br       loc_1B9BBE
0x1b9788  ldloc.s  0xE
0x1b978a  ldc.i4.0
0x1b978b  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1b9790  stloc.s  0x10
0x1b9792  ldloc.s  0x10
0x1b9794  ldc.i4.s 0x4C
0x1b9796  beq      loc_1B986B
0x1b979b  ldloc.s  0x10
0x1b979d  ldc.i4.s 0x53
0x1b979f  beq      loc_1B983F
0x1b97a4  ldloc.s  0x10
0x1b97a6  ldc.i4.s 0x57
0x1b97a8  beq      loc_1B9855
0x1b97ad  br       loc_1B9BBE
0x1b97b2  ldloc.s  0xE
0x1b97b4  ldc.i4.0
0x1b97b5  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1b97ba  stloc.s  0x10
0x1b97bc  ldloc.s  0x10
0x1b97be  ldc.i4.s 0x43
0x1b97c0  beq      loc_1B98D9
0x1b97c5  ldloc.s  0x10
0x1b97c7  ldc.i4.s 0x48
0x1b97c9  beq      loc_1B98AD
0x1b97ce  ldloc.s  0x10
0x1b97d0  ldc.i4.s 0x5A
0x1b97d2  beq      loc_1B98C3
0x1b97d7  br       loc_1B9BBE
0x1b97dc  ldloc.s  0xE
0x1b97de  ldc.i4.0
0x1b97df  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1b97e4  stloc.s  0x10
0x1b97e6  ldloc.s  0x10
0x1b97e8  ldc.i4.s 0x52
0x1b97ea  beq      loc_1B9905
0x1b97ef  ldloc.s  0x10
0x1b97f1  ldc.i4.s 0x56
0x1b97f3  beq      loc_1B98EF
0x1b97f8  br       loc_1B9BBE
0x1b97fd  ldloc.s  0xE
0x1b97ff  ldc.i4.0
0x1b9800  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1b9805  stloc.s  0x10
0x1b9807  ldloc.s  0x10
0x1b9809  ldc.i4.s 0x4C
0x1b980b  beq      loc_1B9931
0x1b9810  ldloc.s  0x10
0x1b9812  ldc.i4.s 0x52
0x1b9814  beq      loc_1B9947
0x1b9819  br       loc_1B9BBE
0x1b981e  ldloc.s  0xE
0x1b9820  ldc.i4.0
0x1b9821  call     instance char [mscorlib]System.String::get_Chars(int32)
0x1b9826  stloc.s  0x10
0x1b9828  ldloc.s  0x10
0x1b982a  ldc.i4.s 0x43
0x1b982c  beq      loc_1B9973
0x1b9831  ldloc.s  0x10
0x1b9833  ldc.i4.s 0x50
0x1b9835  beq      loc_1B9989
0x1b983a  br       loc_1B9BBE
0x1b983f  ldloc.s  0xE
0x1b9841  ldstr    aStyle_1// "Style"
0x1b9846  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b984b  brtrue   loc_1B99E1
0x1b9850  br       loc_1B9BBE
0x1b9855  ldloc.s  0xE
0x1b9857  ldstr    aWidth// "Width"
0x1b985c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b9861  brtrue   loc_1B9A5A
0x1b9866  br       loc_1B9BBE
0x1b986b  ldloc.s  0xE
0x1b986d  ldstr    aLabel// "Label"
0x1b9872  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b9877  brtrue   loc_1B9AB6
0x1b987c  br       loc_1B9BBE
0x1b9881  ldloc.s  0xE
0x1b9883  ldstr    aTop// "Top"
0x1b9888  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b988d  brtrue   loc_1B9A27
0x1b9892  br       loc_1B9BBE
0x1b9897  ldloc.s  0xE
0x1b9899  ldstr    aLeft// "Left"
0x1b989e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b98a3  brtrue   loc_1B9A38
0x1b98a8  br       loc_1B9BBE
0x1b98ad  ldloc.s  0xE
0x1b98af  ldstr    aHeight// "Height"
0x1b98b4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b98b9  brtrue   loc_1B9A49
0x1b98be  br       loc_1B9BBE
0x1b98c3  ldloc.s  0xE
0x1b98c5  ldstr    aZindex// "ZIndex"
0x1b98ca  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b98cf  brtrue   loc_1B9A6B
0x1b98d4  br       loc_1B9BBE
0x1b98d9  ldloc.s  0xE
0x1b98db  ldstr    aCustom// "Custom"
0x1b98e0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b98e5  brtrue   loc_1B9B22
0x1b98ea  br       loc_1B9BBE
0x1b98ef  ldloc.s  0xE
0x1b98f1  ldstr    aVisibility// "Visibility"
0x1b98f6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b98fb  brtrue   loc_1B9A81
0x1b9900  br       loc_1B9BBE
0x1b9905  ldloc.s  0xE
0x1b9907  ldstr    aRepeatwith// "RepeatWith"
0x1b990c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b9911  brtrue   loc_1B9B05
0x1b9916  br       loc_1B9BBE
0x1b991b  ldloc.s  0xE
0x1b991d  ldstr    aTooltip// "ToolTip"
0x1b9922  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b9927  brtrue   loc_1B9A95
0x1b992c  br       loc_1B9BBE
0x1b9931  ldloc.s  0xE
0x1b9933  ldstr    aLinktochild// "LinkToChild"
0x1b9938  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b993d  brtrue   loc_1B9ADB
0x1b9942  br       loc_1B9BBE
0x1b9947  ldloc.s  0xE
0x1b9949  ldstr    aReportitems// "ReportItems"
0x1b994e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b9953  brtrue   loc_1B9B49
0x1b9958  br       loc_1B9BBE
0x1b995d  ldloc.s  0xE
0x1b995f  ldstr    aBookmark// "Bookmark"
0x1b9964  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b9969  brtrue   loc_1B9AED
0x1b996e  br       loc_1B9BBE
0x1b9973  ldloc.s  0xE
0x1b9975  ldstr    aCustomproperti// "CustomProperties"
0x1b997a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b997f  brtrue   loc_1B9B38
0x1b9984  br       loc_1B9BBE
0x1b9989  ldloc.s  0xE
0x1b998b  ldstr    aPagebreakatsta// "PageBreakAtStart"
0x1b9990  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b9995  brtrue   loc_1B9B5D
0x1b999a  br       loc_1B9BBE
0x1b999f  ldloc.s  0xE
0x1b99a1  ldstr    aPagebreakatend// "PageBreakAtEnd"
0x1b99a6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b99ab  brtrue   loc_1B9B70
0x1b99b0  br       loc_1B9BBE
0x1b99b5  ldloc.s  0xE
0x1b99b7  ldstr    aDataelementnam// "DataElementName"
0x1b99bc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b99c1  brtrue   loc_1B9B83
0x1b99c6  br       loc_1B9BBE
0x1b99cb  ldloc.s  0xE
0x1b99cd  ldstr    aDataelementout// "DataElementOutput"
0x1b99d2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1b99d7  brtrue   loc_1B9B96
0x1b99dc  br       loc_1B9BBE
0x1b99e1  ldarg.0
0x1b99e2  ldarg.2
0x1b99e3  ldloca.s 1
0x1b99e5  call     instance class StyleInformation Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadStyle(valuetype PublishingContextStruct context, [out] bool& computed)
0x1b99ea  stloc.s  0xD
0x1b99ec  ldloc.s  0xD
0x1b99ee  ldc.i4.2
0x1b99ef  ldc.i4.0
0x1b99f0  callvirt instance void StyleInformation::Filter(valuetype StyleOwnerType ownerType, bool hasNoRows)
0x1b99f5  ldloc.0
0x1b99f6  ldloc.s  0xD
0x1b99f8  callvirt instance class Microsoft.ReportingServices.ReportProcessing.StringList StyleInformation::get_Names()
0x1b99fd  ldloc.s  0xD
0x1b99ff  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfoList StyleInformation::get_Values()
0x1b9a04  ldarga.s 2
0x1b9a06  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType PublishingContextStruct::get_ObjectType()
0x1b9a0b  ldarga.s 2
0x1b9a0d  call     instance string PublishingContextStruct::get_ObjectName()
0x1b9a12  ldarg.0
0x1b9a13  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_errorContext
0x1b9a18  call     class Microsoft.ReportingServices.ReportProcessing.Style Microsoft.ReportingServices.ReportProcessing.PublishingValidator::ValidateAndCreateStyle(class Microsoft.ReportingServices.ReportProcessing.StringList names, class Microsoft.ReportingServices.ReportProcessing.ExpressionInfoList values, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0x1b9a1d  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportItem::set_StyleClass(class Microsoft.ReportingServices.ReportProcessing.Style value)
0x1b9a22  br       loc_1B9BBE
0x1b9a27  ldloc.0
0x1b9a28  ldarg.0
0x1b9a29  call     instance string Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadSize()
0x1b9a2e  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportItem::set_Top(string value)
0x1b9a33  br       loc_1B9BBE
0x1b9a38  ldloc.0
0x1b9a39  ldarg.0
0x1b9a3a  call     instance string Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadSize()
0x1b9a3f  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportItem::set_Left(string value)
0x1b9a44  br       loc_1B9BBE
0x1b9a49  ldloc.0
0x1b9a4a  ldarg.0
0x1b9a4b  call     instance string Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadSize()
0x1b9a50  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportItem::set_Height(string value)
0x1b9a55  br       loc_1B9BBE
0x1b9a5a  ldloc.0
0x1b9a5b  ldarg.0
0x1b9a5c  call     instance string Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadSize()
0x1b9a61  callvirt instance void Microsoft.ReportingServices.ReportProcessing.ReportItem::set_Width(string value)
0x1b9a66  br       loc_1B9BBE
0x1b9a6b  ldloc.0
0x1b9a6c  ldarg.0
0x1b9a6d  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
  ... truncated ...
```
