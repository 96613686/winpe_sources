# Microsoft.ReportingServices.Modeling.SemanticModel::LoadXmlElement

- ea: `0x16d90`
- end: `0x16e57`
- name: `Microsoft.ReportingServices.Modeling.SemanticModel::LoadXmlElement`
- size: `199`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xa730`
- `0xa760`
- `0xa7b0`
- `0xa7c0`
- `0xaa40`
- `0xaa90`
- `0xcd30`
- `0xcf10`
- `0x13f10`
- `0x16b00`
- `0x16b30`
- `0x16d90`

## string_xrefs

- `0x16e13`: `http://schemas.microsoft.com/analysisservices/2003/engine`

## pseudocode

```c

```

## disassembly

```asm
0x16d90  ldarg.1
0x16d91  callvirt instance bool Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_IsDefaultNamespace()
0x16d96  brfalse.s loc_16E0D
0x16d98  ldarg.1
0x16d99  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0x16d9e  stloc.0
0x16d9f  ldloc.0
0x16da0  ldstr    aVersion// "Version"
0x16da5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16daa  brtrue.s loc_16DD5
0x16dac  ldloc.0
0x16dad  ldstr    aCulture_0// "Culture"
0x16db2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16db7  brtrue.s loc_16DE3
0x16db9  ldloc.0
0x16dba  ldstr    aEntities// "Entities"
0x16dbf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16dc4  brtrue.s loc_16DF1
0x16dc6  ldloc.0
0x16dc7  ldstr    aPerspectives// "Perspectives"
0x16dcc  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16dd1  brtrue.s loc_16DFF
0x16dd3  br.s     loc_16E0D
0x16dd5  ldarg.0
0x16dd6  ldarg.1
0x16dd7  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsString()
0x16ddc  stfld    string Microsoft.ReportingServices.Modeling.SemanticModel::m_version
0x16de1  ldc.i4.1
0x16de2  ret
0x16de3  ldarg.0
0x16de4  ldarg.1
0x16de5  callvirt instance class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadValueAsCultureInfo()
0x16dea  stfld    class [mscorlib]System.Globalization.CultureInfo Microsoft.ReportingServices.Modeling.SemanticModel::m_culture
0x16def  ldc.i4.1
0x16df0  ret
0x16df1  ldarg.0
0x16df2  call     instance class Microsoft.ReportingServices.Modeling.ModelEntityFolderItemCollection Microsoft.ReportingServices.Modeling.SemanticModel::get_Entities()
0x16df7  ldarg.1
0x16df8  callvirt instance void class Microsoft.ReportingServices.Modeling.OwnedModelItemCollection`1<class Microsoft.ReportingServices.Modeling.ModelEntityFolderItem>::Load(class Microsoft.ReportingServices.Modeling.ModelingXmlReader)
0x16dfd  ldc.i4.1
0x16dfe  ret
0x16dff  ldarg.0
0x16e00  call     instance class Microsoft.ReportingServices.Modeling.PerspectiveCollection Microsoft.ReportingServices.Modeling.SemanticModel::get_Perspectives()
0x16e05  ldarg.1
0x16e06  callvirt instance void class Microsoft.ReportingServices.Modeling.OwnedModelItemCollection`1<class Microsoft.ReportingServices.Modeling.Perspective>::Load(class Microsoft.ReportingServices.Modeling.ModelingXmlReader)
0x16e0b  ldc.i4.1
0x16e0c  ret
0x16e0d  ldarg.1
0x16e0e  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_NamespaceURI()
0x16e13  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/analysisse"...
0x16e18  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16e1d  brfalse.s loc_16E4F
0x16e1f  ldarg.1
0x16e20  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0x16e25  ldstr    aDatasourceview// "DataSourceView"
0x16e2a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16e2f  brfalse.s loc_16E4F
0x16e31  ldarg.0
0x16e32  newobj   instance void Microsoft.ReportingServices.Modeling.DataSourceView::.ctor()
0x16e37  stfld    class Microsoft.ReportingServices.Modeling.DataSourceView Microsoft.ReportingServices.Modeling.SemanticModel::m_dsv
0x16e3c  ldarg.0
0x16e3d  ldfld    class Microsoft.ReportingServices.Modeling.DataSourceView Microsoft.ReportingServices.Modeling.SemanticModel::m_dsv
0x16e42  ldarg.1
0x16e43  callvirt instance class [System.Xml]System.Xml.XmlReader Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_Reader()
0x16e48  callvirt instance void Microsoft.ReportingServices.Modeling.DataSourceView::Load(class [System.Xml]System.Xml.XmlReader xr)
0x16e4d  ldc.i4.1
0x16e4e  ret
0x16e4f  ldarg.0
0x16e50  ldarg.1
0x16e51  call     instance bool Microsoft.ReportingServices.Modeling.ModelItem::LoadXmlElement(class Microsoft.ReportingServices.Modeling.ModelingXmlReader xr)
0x16e56  ret
```
