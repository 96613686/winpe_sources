# Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadLegend

- ea: `0x1bf970`
- end: `0x1bfaad`
- name: `Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadLegend`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1bde50`

## callees

- `0x1a5930`
- `0x1a5950`
- `0x1a5970`
- `0x1a5990`
- `0x1a59b0`
- `0x1a5a90`
- `0x1bf970`
- `0x1c3690`
- `0x1c36c0`
- `0x1c3ce0`
- `0x1cbc90`
- `0x2643c0`
- `0x2643e0`
- `0x264820`
- `0x264830`
- `0x264880`
- `0x264af0`

## string_xrefs

- `0x1bf9f8`: `InsidePlotArea`

## pseudocode

```c

```

## disassembly

```asm
0x1bf970  newobj   instance void Microsoft.ReportingServices.ReportProcessing.Legend::.ctor()
0x1bf975  stloc.0
0x1bf976  ldarg.0
0x1bf977  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1bf97c  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0x1bf981  brtrue   loc_1BFAAB
0x1bf986  ldc.i4.0
0x1bf987  stloc.1
0x1bf988  ldarg.0
0x1bf989  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1bf98e  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x1bf993  pop
0x1bf994  ldarg.0
0x1bf995  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1bf99a  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x1bf99f  stloc.2
0x1bf9a0  ldloc.2
0x1bf9a1  ldc.i4.1
0x1bf9a2  beq.s    loc_1BF9B1
0x1bf9a4  ldloc.2
0x1bf9a5  ldc.i4.s 0xF
0x1bf9a7  beq      loc_1BFA8C
0x1bf9ac  br       loc_1BFAA5
0x1bf9b1  ldarg.0
0x1bf9b2  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1bf9b7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1bf9bc  stloc.s  4
0x1bf9be  ldloc.s  4
0x1bf9c0  ldstr    aVisible// "Visible"
0x1bf9c5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bf9ca  brtrue.s loc_1BFA09
0x1bf9cc  ldloc.s  4
0x1bf9ce  ldstr    aStyle_1// "Style"
0x1bf9d3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bf9d8  brtrue.s loc_1BFA1F
0x1bf9da  ldloc.s  4
0x1bf9dc  ldstr    aPosition// "Position"
0x1bf9e1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bf9e6  brtrue.s loc_1BFA5D
0x1bf9e8  ldloc.s  4
0x1bf9ea  ldstr    aLayout// "Layout"
0x1bf9ef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bf9f4  brtrue.s loc_1BFA6B
0x1bf9f6  ldloc.s  4
0x1bf9f8  ldstr    aInsideplotarea// "InsidePlotArea"
0x1bf9fd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bfa02  brtrue.s loc_1BFA79
0x1bfa04  br       loc_1BFAA5
0x1bfa09  ldloc.0
0x1bfa0a  ldarg.0
0x1bfa0b  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1bfa10  callvirt instance bool RmlValidatingReader::ReadBoolean()
0x1bfa15  callvirt instance void Microsoft.ReportingServices.ReportProcessing.Legend::set_Visible(bool value)
0x1bfa1a  br       loc_1BFAA5
0x1bfa1f  ldarg.0
0x1bfa20  ldarg.1
0x1bfa21  call     instance class StyleInformation Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadStyle(valuetype PublishingContextStruct context)
0x1bfa26  stloc.3
0x1bfa27  ldloc.3
0x1bfa28  ldc.i4.s 0xB
0x1bfa2a  ldc.i4.0
0x1bfa2b  callvirt instance void StyleInformation::Filter(valuetype StyleOwnerType ownerType, bool hasNoRows)
0x1bfa30  ldloc.0
0x1bfa31  ldloc.3
0x1bfa32  callvirt instance class Microsoft.ReportingServices.ReportProcessing.StringList StyleInformation::get_Names()
0x1bfa37  ldloc.3
0x1bfa38  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfoList StyleInformation::get_Values()
0x1bfa3d  ldarga.s 1
0x1bfa3f  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType PublishingContextStruct::get_ObjectType()
0x1bfa44  ldarga.s 1
0x1bfa46  call     instance string PublishingContextStruct::get_ObjectName()
0x1bfa4b  ldarg.0
0x1bfa4c  ldfld    class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_errorContext
0x1bfa51  call     class Microsoft.ReportingServices.ReportProcessing.Style Microsoft.ReportingServices.ReportProcessing.PublishingValidator::ValidateAndCreateStyle(class Microsoft.ReportingServices.ReportProcessing.StringList names, class Microsoft.ReportingServices.ReportProcessing.ExpressionInfoList values, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0x1bfa56  callvirt instance void Microsoft.ReportingServices.ReportProcessing.Legend::set_StyleClass(class Microsoft.ReportingServices.ReportProcessing.Style value)
0x1bfa5b  br.s     loc_1BFAA5
0x1bfa5d  ldloc.0
0x1bfa5e  ldarg.0
0x1bfa5f  call     instance valuetype Positions Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadLegendPosition()
0x1bfa64  callvirt instance void Microsoft.ReportingServices.ReportProcessing.Legend::set_Position(valuetype Positions value)
0x1bfa69  br.s     loc_1BFAA5
0x1bfa6b  ldloc.0
0x1bfa6c  ldarg.0
0x1bfa6d  call     instance valuetype LegendLayout Microsoft.ReportingServices.ReportProcessing.ReportPublishing::ReadLegendLayout()
0x1bfa72  callvirt instance void Microsoft.ReportingServices.ReportProcessing.Legend::set_Layout(valuetype LegendLayout value)
0x1bfa77  br.s     loc_1BFAA5
0x1bfa79  ldloc.0
0x1bfa7a  ldarg.0
0x1bfa7b  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1bfa80  callvirt instance bool RmlValidatingReader::ReadBoolean()
0x1bfa85  callvirt instance void Microsoft.ReportingServices.ReportProcessing.Legend::set_InsidePlotArea(bool value)
0x1bfa8a  br.s     loc_1BFAA5
0x1bfa8c  ldstr    aLegend// "Legend"
0x1bfa91  ldarg.0
0x1bfa92  ldfld    class RmlValidatingReader Microsoft.ReportingServices.ReportProcessing.ReportPublishing::m_reader
0x1bfa97  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0x1bfa9c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1bfaa1  brfalse.s loc_1BFAA5
0x1bfaa3  ldc.i4.1
0x1bfaa4  stloc.1
0x1bfaa5  ldloc.1
0x1bfaa6  brfalse  loc_1BF988
0x1bfaab  ldloc.0
0x1bfaac  ret
```
