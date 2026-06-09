# RoleFragmentLoader::LoadXmlElement

- ea: `0x39420`
- end: `0x394b9`
- name: `RoleFragmentLoader::LoadXmlElement`
- size: `153`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa7b0`
- `0xa7c0`
- `0xae90`
- `0x26b20`
- `0x26b40`
- `0x26b60`
- `0x26b80`
- `0x39420`

## string_xrefs

- `0x39426`: `http://schemas.microsoft.com/sqlserver/2004/10/semanticmodeling`

## pseudocode

```c

```

## disassembly

```asm
0x39420  ldarg.1
0x39421  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_NamespaceURI()
0x39426  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sqlserver/"...
0x3942b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x39430  brfalse.s loc_394B1
0x39432  ldarg.1
0x39433  callvirt instance string Microsoft.ReportingServices.Modeling.ModelingXmlReader::get_LocalName()
0x39438  stloc.0
0x39439  ldloc.0
0x3943a  ldstr    aRole// "Role"
0x3943f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x39444  brtrue.s loc_39455
0x39446  ldloc.0
0x39447  ldstr    aFieldfolder// "FieldFolder"
0x3944c  call     bool [mscorlib]System.String::op_Equality(string, string)
0x39451  brtrue.s loc_39483
0x39453  br.s     loc_394B1
0x39455  ldarg.0
0x39456  ldfld    valuetype Microsoft.ReportingServices.Modeling.RelationEnd RoleFragmentLoader::m_end
0x3945b  brtrue.s loc_39470
0x3945d  ldarg.0
0x3945e  call     instance var<u1> class Microsoft.ReportingServices.Modeling.ModelingXmlLoaderBase`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule>::get_Item()
0x39463  ldarg.1
0x39464  callvirt instance class [System.Xml]System.Xml.XPath.XPathDocument Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadFragment()
0x39469  callvirt instance void Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule::set_SourceRoleFragment(class [System.Xml]System.Xml.XPath.IXPathNavigable value)
0x3946e  br.s     loc_39481
0x39470  ldarg.0
0x39471  call     instance var<u1> class Microsoft.ReportingServices.Modeling.ModelingXmlLoaderBase`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule>::get_Item()
0x39476  ldarg.1
0x39477  callvirt instance class [System.Xml]System.Xml.XPath.XPathDocument Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadFragment()
0x3947c  callvirt instance void Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule::set_TargetRoleFragment(class [System.Xml]System.Xml.XPath.IXPathNavigable value)
0x39481  ldc.i4.1
0x39482  ret
0x39483  ldarg.0
0x39484  ldfld    valuetype Microsoft.ReportingServices.Modeling.RelationEnd RoleFragmentLoader::m_end
0x39489  brtrue.s loc_3949E
0x3948b  ldarg.0
0x3948c  call     instance var<u1> class Microsoft.ReportingServices.Modeling.ModelingXmlLoaderBase`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule>::get_Item()
0x39491  ldarg.1
0x39492  callvirt instance class [System.Xml]System.Xml.XPath.XPathDocument Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadFragment()
0x39497  callvirt instance void Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule::set_SourceFolderFragment(class [System.Xml]System.Xml.XPath.IXPathNavigable value)
0x3949c  br.s     loc_394AF
0x3949e  ldarg.0
0x3949f  call     instance var<u1> class Microsoft.ReportingServices.Modeling.ModelingXmlLoaderBase`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule>::get_Item()
0x394a4  ldarg.1
0x394a5  callvirt instance class [System.Xml]System.Xml.XPath.XPathDocument Microsoft.ReportingServices.Modeling.ModelingXmlReader::ReadFragment()
0x394aa  callvirt instance void Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule::set_TargetFolderFragment(class [System.Xml]System.Xml.XPath.IXPathNavigable value)
0x394af  ldc.i4.1
0x394b0  ret
0x394b1  ldarg.0
0x394b2  ldarg.1
0x394b3  call     instance bool class Microsoft.ReportingServices.Modeling.ModelingXmlLoaderBase`1<class Microsoft.ReportingServices.Modeling.ModelGeneration.CreateRoleRule>::LoadXmlElement(class Microsoft.ReportingServices.Modeling.ModelingXmlReader)
0x394b8  ret
```
