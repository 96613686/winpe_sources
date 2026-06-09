# Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteReferenceElement

- ea: `0xb530`
- end: `0xb62f`
- name: `Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteReferenceElement`
- size: `255`
- prototype: ``
- caller_count: `13`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xf8b0`
- `0x11880`
- `0x126b0`
- `0x15850`
- `0x1b590`
- `0x1bc80`
- `0x1c170`
- `0x1eff0`
- `0x21e80`
- `0x22440`
- `0x33ea0`
- `0x3b400`
- `0x3b440`

## callees

- `0x9740`
- `0x97d0`
- `0xb4b0`
- `0xb530`
- `0x139d0`
- `0x13a60`
- `0x187f0`
- `0x21920`
- `0x22ab0`
- `0x25590`

## pseudocode

```c

```

## disassembly

```asm
0xb530  ldarg.2
0xb531  isinst   Microsoft.ReportingServices.Modeling.ModelItem
0xb536  stloc.0
0xb537  ldarg.2
0xb538  isinst   Microsoft.ReportingServices.Modeling.Expression
0xb53d  stloc.1
0xb53e  ldarg.2
0xb53f  isinst   Microsoft.ReportingServices.Modeling.Grouping
0xb544  stloc.2
0xb545  ldarg.2
0xb546  isinst   Microsoft.ReportingServices.Modeling.Parameter
0xb54b  stloc.3
0xb54c  ldarg.2
0xb54d  brtrue.s loc_B550
0xb54f  ret
0xb550  ldloc.0
0xb551  brfalse.s loc_B581
0xb553  ldarg.0
0xb554  ldfld    valuetype Microsoft.ReportingServices.Modeling.ModelingSerializationOptions Microsoft.ReportingServices.Modeling.ModelingXmlWriter::m_options
0xb559  ldc.i4.2
0xb55a  and
0xb55b  brfalse.s loc_B56E
0xb55d  ldarg.0
0xb55e  ldfld    class [System.Xml]System.Xml.XmlWriter Microsoft.ReportingServices.Modeling.ModelingXmlWriter::m_xw
0xb563  ldloc.0
0xb564  callvirt instance string Microsoft.ReportingServices.Modeling.ModelItem::get_Name()
0xb569  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteComment(string)
0xb56e  ldarg.0
0xb56f  ldarg.1
0xb570  ldloc.0
0xb571  callvirt instance valuetype Microsoft.ReportingServices.Modeling.QName Microsoft.ReportingServices.Modeling.ModelItem::get_ID()
0xb576  box      Microsoft.ReportingServices.Modeling.QName
0xb57b  call     instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteElement(string name, object value)
0xb580  ret
0xb581  ldloc.1
0xb582  brfalse.s loc_B5B0
0xb584  ldloc.1
0xb585  callvirt instance string Microsoft.ReportingServices.Modeling.Expression::get_Name()
0xb58a  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb58f  brtrue.s loc_B5A2
0xb591  ldloc.1
0xb592  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0xb597  call     string Microsoft.ReportingServices.Modeling.DevExceptionMessages::Xml_ReferenceToUnnamedObject(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0xb59c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xb5a1  throw
0xb5a2  ldarg.0
0xb5a3  ldarg.1
0xb5a4  ldloc.1
0xb5a5  callvirt instance string Microsoft.ReportingServices.Modeling.Expression::get_Name()
0xb5aa  call     instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteElement(string name, object value)
0xb5af  ret
0xb5b0  ldloc.2
0xb5b1  brfalse.s loc_B5DF
0xb5b3  ldloc.2
0xb5b4  callvirt instance string Microsoft.ReportingServices.Modeling.Grouping::get_Name()
0xb5b9  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb5be  brtrue.s loc_B5D1
0xb5c0  ldloc.2
0xb5c1  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0xb5c6  call     string Microsoft.ReportingServices.Modeling.DevExceptionMessages::Xml_ReferenceToUnnamedObject(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0xb5cb  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xb5d0  throw
0xb5d1  ldarg.0
0xb5d2  ldarg.1
0xb5d3  ldloc.2
0xb5d4  callvirt instance string Microsoft.ReportingServices.Modeling.Grouping::get_Name()
0xb5d9  call     instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteElement(string name, object value)
0xb5de  ret
0xb5df  ldloc.3
0xb5e0  brfalse.s loc_B60E
0xb5e2  ldloc.3
0xb5e3  callvirt instance string Microsoft.ReportingServices.Modeling.Parameter::get_Name()
0xb5e8  callvirt instance int32 [mscorlib]System.String::get_Length()
0xb5ed  brtrue.s loc_B600
0xb5ef  ldloc.3
0xb5f0  call     valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor Microsoft.ReportingServices.Modeling.SRObjectDescriptor::FromScope(class Microsoft.ReportingServices.Modeling.IValidationScope scope)
0xb5f5  call     string Microsoft.ReportingServices.Modeling.DevExceptionMessages::Xml_ReferenceToUnnamedObject(valuetype Microsoft.ReportingServices.Modeling.SRObjectDescriptor objectTypeAndName)
0xb5fa  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xb5ff  throw
0xb600  ldarg.0
0xb601  ldarg.1
0xb602  ldloc.3
0xb603  callvirt instance string Microsoft.ReportingServices.Modeling.Parameter::get_Name()
0xb608  call     instance void Microsoft.ReportingServices.Modeling.ModelingXmlWriter::WriteElement(string name, object value)
0xb60d  ret
0xb60e  ldstr    aUnknownItem// "Unknown item '"
0xb613  ldarg.2
0xb614  brtrue.s loc_B619
0xb616  ldnull
0xb617  br.s     loc_B61F
0xb619  ldarg.2
0xb61a  callvirt instance string [mscorlib]System.Object::ToString()
0xb61f  ldstr    asc_3E096// "'"
0xb624  call     string [mscorlib]System.String::Concat(string, string, string)
0xb629  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0xb62e  throw
```
