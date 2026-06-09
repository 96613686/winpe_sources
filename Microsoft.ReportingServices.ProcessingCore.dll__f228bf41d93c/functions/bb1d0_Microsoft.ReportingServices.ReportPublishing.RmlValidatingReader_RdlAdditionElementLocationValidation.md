# Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::RdlAdditionElementLocationValidation

- ea: `0xbb1d0`
- end: `0xbb443`
- name: `Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::RdlAdditionElementLocationValidation`
- size: `627`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0xba8b0`

## callees

- `0xbb1b0`
- `0xbb1d0`
- `0xbb450`
- `0xbb7f0`
- `0xbbbd0`
- `0xbbbf0`
- `0x18a470`

## string_xrefs

- `0xbb2e2`: `http://schemas.microsoft.com/sqlserver/reporting/2010/01/reportdefinition`
- `0xbb2f4`: `http://schemas.microsoft.com/sqlserver/reporting/2016/01/reportdefinition`
- `0xbb301`: `(this.NamespaceURI == Constants.RDL2010NamespaceURI) || (this.NamespaceURI == Constants.RDL2016NamespaceURI)`

## pseudocode

```c

```

## disassembly

```asm
0xbb1d0  ldloca.s 0
0xbb1d2  initobj  valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>>
0xbb1d8  ldnull
0xbb1d9  stloc.1
0xbb1da  ldc.i4.0
0xbb1db  stloc.2
0xbb1dc  ldarg.1
0xbb1dd  ldnull
0xbb1de  stind.ref
0xbb1df  ldarg.0
0xbb1e0  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb1e5  ldarg.0
0xbb1e6  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::m_validationNamespaceList
0xbb1eb  call     bool Microsoft.ReportingServices.ReportProcessing.ListUtils::ContainsWithOrdinalComparer(string item, class [mscorlib]System.Collections.Generic.List`1<string> list)
0xbb1f0  brfalse  loc_BB441
0xbb1f5  ldarg.0
0xbb1f6  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xbb1fb  stloc.s  4
0xbb1fd  ldloc.s  4
0xbb1ff  ldc.i4.1
0xbb200  beq.s    loc_BB210
0xbb202  ldloc.s  4
0xbb204  ldc.i4.s 0xF
0xbb206  beq      loc_BB435
0xbb20b  br       loc_BB441
0xbb210  ldarg.0
0xbb211  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xbb216  ldarg.0
0xbb217  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb21c  call     string Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::GetExpandedName(string localName, string namespaceURI)
0xbb221  stloc.1
0xbb222  ldarg.0
0xbb223  call     instance bool Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::IsPowerViewMicroVersionedNamespace()
0xbb228  stloc.3
0xbb229  ldarg.0
0xbb22a  ldloc.1
0xbb22b  call     instance bool Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::ShouldPerformMicroversionCheck(string currentRdlElement)
0xbb230  brfalse.s loc_BB248
0xbb232  ldarg.0
0xbb233  ldfld    valuetype ItemType Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_itemType
0xbb238  brfalse.s loc_BB245
0xbb23a  ldarg.0
0xbb23b  ldfld    valuetype ItemType Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_itemType
0xbb240  ldc.i4.2
0xbb241  ceq
0xbb243  br.s     loc_BB249
0xbb245  ldc.i4.1
0xbb246  br.s     loc_BB249
0xbb248  ldc.i4.0
0xbb249  ldloc.3
0xbb24a  and
0xbb24b  brfalse.s loc_BB28F
0xbb24d  ldarg.1
0xbb24e  ldloc.1
0xbb24f  ldarg.0
0xbb250  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb255  ldarg.0
0xbb256  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LineNumber()
0xbb25b  stloc.s  5
0xbb25d  ldloca.s 5
0xbb25f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb264  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb269  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb26e  ldarg.0
0xbb26f  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LinePosition()
0xbb274  stloc.s  5
0xbb276  ldloca.s 5
0xbb278  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb27d  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb282  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb287  call     string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.RDLValidatingReaderStringsWrapper::rdlValidationInvalidNamespaceElement(string, string, string, string)
0xbb28c  stind.ref
0xbb28d  ldc.i4.0
0xbb28e  ret
0xbb28f  ldarg.0
0xbb290  ldfld    class [System]System.Collections.Generic.Stack`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>> Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_rdlElementHierarchy
0xbb295  callvirt instance int32 class [System]System.Collections.Generic.Stack`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>>::get_Count()
0xbb29a  ldc.i4.0
0xbb29b  ble.s    loc_BB2AF
0xbb29d  ldloca.s 0
0xbb29f  ldarg.0
0xbb2a0  ldfld    class [System]System.Collections.Generic.Stack`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>> Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_rdlElementHierarchy
0xbb2a5  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>>::Peek()
0xbb2aa  call     instance void valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>>::.ctor(var<u1>)
0xbb2af  ldloca.s 0
0xbb2b1  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>>::get_HasValue()
0xbb2b6  brtrue.s loc_BB30B
0xbb2b8  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0xbb2bd  ldarg.0
0xbb2be  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xbb2c3  ldstr    aReport// "Report"
0xbb2c8  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbb2cd  ldstr    aThisLocalnameC// "(this.LocalName == Constants.Report)"
0xbb2d2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0xbb2d7  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0xbb2dc  ldarg.0
0xbb2dd  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb2e2  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/sqlserver/"...
0xbb2e7  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbb2ec  brtrue.s loc_BB300
0xbb2ee  ldarg.0
0xbb2ef  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb2f4  ldstr    aHttpSchemasMic_7// "http://schemas.microsoft.com/sqlserver/"...
0xbb2f9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbb2fe  br.s     loc_BB301
0xbb300  ldc.i4.1
0xbb301  ldstr    aThisNamespaceu// "(this.NamespaceURI == Constants.RDL2010"...
0xbb306  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0xbb30b  ldarg.0
0xbb30c  callvirt instance bool [System.Xml]System.Xml.XmlReader::get_IsEmptyElement()
0xbb311  brtrue.s loc_BB32A
0xbb313  ldarg.0
0xbb314  ldfld    class [System]System.Collections.Generic.Stack`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>> Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_rdlElementHierarchy
0xbb319  ldloc.1
0xbb31a  ldarg.0
0xbb31b  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb320  newobj   instance void valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>::.ctor(var<u1>, !!T0)
0xbb325  callvirt instance void class [System]System.Collections.Generic.Stack`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>>::Push(var<u1>)
0xbb32a  ldloc.3
0xbb32b  brfalse  loc_BB441
0xbb330  ldarg.0
0xbb331  ldfld    class [System]System.Collections.Specialized.NameValueCollection Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_microversioningValidationStructureElements
0xbb336  ldloc.1
0xbb337  callvirt instance string[] [System]System.Collections.Specialized.NameValueCollection::GetValues(string)
0xbb33c  stloc.s  6
0xbb33e  ldloc.s  6
0xbb340  brfalse  loc_BB3CE
0xbb345  ldc.i4.0
0xbb346  stloc.s  7
0xbb348  br.s     loc_BB36D
0xbb34a  ldloca.s 0
0xbb34c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>>::get_Value()
0xbb351  ldfld    var<u1> valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>::First
0xbb356  ldloc.s  6
0xbb358  ldloc.s  7
0xbb35a  ldelem.ref
0xbb35b  ldc.i4.4
0xbb35c  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xbb361  brfalse.s loc_BB367
0xbb363  ldc.i4.1
0xbb364  stloc.2
0xbb365  br.s     loc_BB375
0xbb367  ldloc.s  7
0xbb369  ldc.i4.1
0xbb36a  add
0xbb36b  stloc.s  7
0xbb36d  ldloc.s  7
0xbb36f  ldloc.s  6
0xbb371  ldlen
0xbb372  conv.i4
0xbb373  blt.s    loc_BB34A
0xbb375  ldloc.2
0xbb376  brtrue   loc_BB441
0xbb37b  ldarg.1
0xbb37c  ldarg.0
0xbb37d  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xbb382  ldarg.0
0xbb383  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb388  ldloca.s 0
0xbb38a  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>>::get_Value()
0xbb38f  ldfld    var<u1> valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>::First
0xbb394  ldarg.0
0xbb395  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LineNumber()
0xbb39a  stloc.s  5
0xbb39c  ldloca.s 5
0xbb39e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb3a3  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb3a8  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb3ad  ldarg.0
0xbb3ae  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LinePosition()
0xbb3b3  stloc.s  5
0xbb3b5  ldloca.s 5
0xbb3b7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb3bc  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb3c1  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb3c6  call     string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.RDLValidatingReaderStringsWrapper::rdlValidationInvalidParent(string, string, string, string, string)
0xbb3cb  stind.ref
0xbb3cc  ldc.i4.0
0xbb3cd  ret
0xbb3ce  ldloca.s 0
0xbb3d0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>>::get_Value()
0xbb3d5  ldfld    var<u1> valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>::Second
0xbb3da  ldarg.0
0xbb3db  callvirt instance string [System.Xml]System.Xml.XmlReader::get_NamespaceURI()
0xbb3e0  ldc.i4.4
0xbb3e1  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xbb3e6  brtrue.s loc_BB441
0xbb3e8  ldarg.1
0xbb3e9  ldarg.0
0xbb3ea  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0xbb3ef  ldloca.s 0
0xbb3f1  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>>::get_Value()
0xbb3f6  ldfld    var<u1> valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>::First
0xbb3fb  ldarg.0
0xbb3fc  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LineNumber()
0xbb401  stloc.s  5
0xbb403  ldloca.s 5
0xbb405  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb40a  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb40f  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb414  ldarg.0
0xbb415  call     instance int32 Microsoft.ReportingServices.ReportPublishing.RDLValidatingReader::get_LinePosition()
0xbb41a  stloc.s  5
0xbb41c  ldloca.s 5
0xbb41e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xbb423  callvirt instance class [mscorlib]System.Globalization.NumberFormatInfo [mscorlib]System.Globalization.CultureInfo::get_NumberFormat()
0xbb428  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0xbb42d  call     string [microsoft.reportingservices.rdlobjectmodel]Microsoft.ReportingServices.RdlObjectModel.RDLValidatingReaderStringsWrapper::rdlValidationInvalidMicroVersionedElement(string, string, string, string)
0xbb432  stind.ref
0xbb433  ldc.i4.0
0xbb434  ret
0xbb435  ldarg.0
0xbb436  ldfld    class [System]System.Collections.Generic.Stack`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>> Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader::m_rdlElementHierarchy
0xbb43b  callvirt instance var<u1> class [System]System.Collections.Generic.Stack`1<valuetype Microsoft.ReportingServices.ReportIntermediateFormat.Pair`2<string, string>>::Pop()
0xbb440  pop
0xbb441  ldc.i4.1
0xbb442  ret
```
