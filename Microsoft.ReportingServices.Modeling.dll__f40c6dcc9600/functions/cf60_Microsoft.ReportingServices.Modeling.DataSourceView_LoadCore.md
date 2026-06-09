# Microsoft.ReportingServices.Modeling.DataSourceView::LoadCore

- ea: `0xcf60`
- end: `0xcff9`
- name: `Microsoft.ReportingServices.Modeling.DataSourceView::LoadCore`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x2fdc0`

## callees

- `0x97d0`
- `0xbaa0`
- `0xbb10`
- `0xcd70`
- `0xcf60`
- `0x2ed90`
- `0x2f880`

## string_xrefs

- `0xcf66`: `http://schemas.microsoft.com/analysisservices/2003/engine`
- `0xcfe2`: `http://schemas.microsoft.com/analysisservices/2003/engine`

## pseudocode

```c

```

## disassembly

```asm
0xcf60  ldarg.1
0xcf61  ldstr    aDatasourceview// "DataSourceView"
0xcf66  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/analysisse"...
0xcf6b  call     void Microsoft.ReportingServices.Modeling.XmlUtil::CheckElement(class [System.Xml]System.Xml.XmlReader xr, string localName, string namespaceUri)
0xcf70  ldarg.1
0xcf71  callvirt instance class [System.Xml]System.Xml.Schema.IXmlSchemaInfo [System.Xml]System.Xml.XmlReader::get_SchemaInfo()
0xcf76  brfalse.s loc_CFD1
0xcf78  ldarg.1
0xcf79  callvirt instance class [System.Xml]System.Xml.Schema.IXmlSchemaInfo [System.Xml]System.Xml.XmlReader::get_SchemaInfo()
0xcf7e  callvirt instance class [System.Xml]System.Xml.Schema.XmlSchemaType [System.Xml]System.Xml.Schema.IXmlSchemaInfo::get_SchemaType()
0xcf83  callvirt instance class [System.Xml]System.Xml.XmlQualifiedName [System.Xml]System.Xml.Schema.XmlSchemaType::get_QualifiedName()
0xcf88  stloc.0
0xcf89  ldloc.0
0xcf8a  ldsfld   class [System.Xml]System.Xml.XmlQualifiedName Microsoft.ReportingServices.Modeling.DataSourceView::DataSourceViewType
0xcf8f  call     bool [System.Xml]System.Xml.XmlQualifiedName::op_Inequality(class [System.Xml]System.Xml.XmlQualifiedName, class [System.Xml]System.Xml.XmlQualifiedName)
0xcf94  brfalse.s loc_CFD1
0xcf96  ldc.i4.5
0xcf97  newarr   [mscorlib]System.String
0xcf9c  dup
0xcf9d  ldc.i4.0
0xcf9e  ldstr    aUnexpectedData_0// "Unexpected DataSourceView type '"
0xcfa3  stelem.ref
0xcfa4  dup
0xcfa5  ldc.i4.1
0xcfa6  ldloc.0
0xcfa7  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Name()
0xcfac  stelem.ref
0xcfad  dup
0xcfae  ldc.i4.2
0xcfaf  ldstr    aInNamespace// "' in namespace '"
0xcfb4  stelem.ref
0xcfb5  dup
0xcfb6  ldc.i4.3
0xcfb7  ldloc.0
0xcfb8  callvirt instance string [System.Xml]System.Xml.XmlQualifiedName::get_Namespace()
0xcfbd  stelem.ref
0xcfbe  dup
0xcfbf  ldc.i4.4
0xcfc0  ldstr    asc_3E096// "'"
0xcfc5  stelem.ref
0xcfc6  call     string [mscorlib]System.String::Concat(string[])
0xcfcb  newobj   instance void Microsoft.ReportingServices.Modeling.InternalModelingException::.ctor(string traceMessage)
0xcfd0  throw
0xcfd1  ldarg.0
0xcfd2  newobj   instance void DsvInfoDS::.ctor()
0xcfd7  call     instance void Microsoft.ReportingServices.Modeling.DataSourceView::Reset(class IDsvInfo dsvInfo)
0xcfdc  ldarg.1
0xcfdd  ldstr    aDatasourceview// "DataSourceView"
0xcfe2  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/analysisse"...
0xcfe7  ldarg.0
0xcfe8  ldftn    instance bool Microsoft.ReportingServices.Modeling.DataSourceView::LoadXmlElement(class [System.Xml]System.Xml.XmlReader xr)
0xcfee  newobj   instance void LoadXmlElementLDC::.ctor(object object, native int method)
0xcff3  call     void Microsoft.ReportingServices.Modeling.XmlUtil::LoadDirectChildren(class [System.Xml]System.Xml.XmlReader xr, string parentElementName, string parentElementNamespaceURI, class LoadXmlElementLDC loadXmlElement)
0xcff8  ret
```
