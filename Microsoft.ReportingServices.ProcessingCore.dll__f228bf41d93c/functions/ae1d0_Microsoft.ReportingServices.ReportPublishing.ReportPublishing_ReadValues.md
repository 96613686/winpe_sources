# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadValues

- ea: `0xae1d0`
- end: `0xae2d1`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadValues`
- size: `257`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xae0f0`

## callees

- `0xae1d0`
- `0xae530`
- `0x117740`
- `0x117880`
- `0x11fca0`

## string_xrefs

- `0xae22a`: `http://www.w3.org/2001/XMLSchema-instance`

## pseudocode

```c

```

## disassembly

```asm
0xae1d0  ldnull
0xae1d1  stloc.0
0xae1d2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo>::.ctor()
0xae1d7  stloc.1
0xae1d8  ldnull
0xae1d9  stloc.2
0xae1da  ldc.i4.0
0xae1db  stloc.3
0xae1dc  ldc.i4.0
0xae1dd  stloc.s  4
0xae1df  ldarg.0
0xae1e0  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xae1e5  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xae1ea  pop
0xae1eb  ldarg.0
0xae1ec  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xae1f1  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xae1f6  stloc.s  5
0xae1f8  ldloc.s  5
0xae1fa  ldc.i4.1
0xae1fb  beq.s    loc_AE208
0xae1fd  ldloc.s  5
0xae1ff  ldc.i4.s 0xF
0xae201  beq.s    loc_AE26E
0xae203  br       loc_AE288
0xae208  ldarg.0
0xae209  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xae20e  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xae213  ldstr    aValue// "Value"
0xae218  call     bool [mscorlib]System.String::op_Equality(string, string)
0xae21d  brfalse.s loc_AE288
0xae21f  ldarg.0
0xae220  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xae225  ldstr    aNil// "nil"
0xae22a  ldstr    aHttpWwwW3Org20// "http://www.w3.org/2001/XMLSchema-instan"...
0xae22f  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string, string)
0xae234  stloc.s  6
0xae236  ldloc.s  6
0xae238  brfalse.s loc_AE24C
0xae23a  ldloc.s  6
0xae23c  call     bool [System.Xml]System.Xml.XmlConvert::ToBoolean(string)
0xae241  brfalse.s loc_AE24C
0xae243  ldnull
0xae244  call     class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::CreateConstExpression(string value)
0xae249  stloc.2
0xae24a  br.s     loc_AE265
0xae24c  ldarg.0
0xae24d  ldarg.0
0xae24e  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xae253  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xae258  ldarg.1
0xae259  ldarg.2
0xae25a  ldarg.3
0xae25b  ldloca.s 3
0xae25d  ldarg.s  4
0xae25f  call     instance class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadParameterExpression(string propertyName, valuetype Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct context, class Microsoft.ReportingServices.ReportIntermediateFormat.ParameterDef parameter, class [mscorlib]System.Collections.Hashtable parameterNames, bool& dynamic, bool& isComplex)
0xae264  stloc.2
0xae265  ldloc.1
0xae266  ldloc.2
0xae267  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo>::Add(var<u1>)
0xae26c  br.s     loc_AE288
0xae26e  ldstr    aValues// "Values"
0xae273  ldarg.0
0xae274  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xae279  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xae27e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xae283  brfalse.s loc_AE288
0xae285  ldc.i4.1
0xae286  stloc.s  4
0xae288  ldloc.s  4
0xae28a  brfalse  loc_AE1DF
0xae28f  ldloc.3
0xae290  brfalse.s loc_AE29B
0xae292  ldarg.2
0xae293  ldloc.1
0xae294  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ParameterDef::set_DefaultExpressions(class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo> value)
0xae299  br.s     loc_AE2CF
0xae29b  ldloc.1
0xae29c  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo>::get_Count()
0xae2a1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(int32)
0xae2a6  stloc.0
0xae2a7  ldc.i4.0
0xae2a8  stloc.s  7
0xae2aa  br.s     loc_AE2C5
0xae2ac  ldloc.0
0xae2ad  ldloc.1
0xae2ae  ldloc.s  7
0xae2b0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo>::get_Item(!!T0)
0xae2b5  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo::get_StringValue()
0xae2ba  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0xae2bf  ldloc.s  7
0xae2c1  ldc.i4.1
0xae2c2  add
0xae2c3  stloc.s  7
0xae2c5  ldloc.s  7
0xae2c7  ldloc.1
0xae2c8  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.ExpressionInfo>::get_Count()
0xae2cd  blt.s    loc_AE2AC
0xae2cf  ldloc.0
0xae2d0  ret
```
