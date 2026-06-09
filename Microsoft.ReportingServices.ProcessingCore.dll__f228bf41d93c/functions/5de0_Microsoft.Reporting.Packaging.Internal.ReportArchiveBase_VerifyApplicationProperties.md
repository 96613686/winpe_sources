# Microsoft.Reporting.Packaging.Internal.ReportArchiveBase::VerifyApplicationProperties

- ea: `0x5de0`
- end: `0x5f4c`
- name: `Microsoft.Reporting.Packaging.Internal.ReportArchiveBase::VerifyApplicationProperties`
- size: `364`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0xbc380`

## callees

- `0x5dc0`
- `0x5dd0`
- `0x5de0`
- `0x5f50`

## string_xrefs

- `0x5e20`: `http://schemas.microsoft.com/sqlserver/reporting/2012/01/extendedproperties`
- `0x5e38`: `http://schemas.openxmlformats.org/markup-compatibility/2006`

## pseudocode

```c

```

## disassembly

```asm
0x5de0  ldarg.0
0x5de1  callvirt instance class [mscorlib]System.IO.Stream Microsoft.Reporting.Packaging.Internal.ReportArchiveBase::GetApplicationPropertiesStream()
0x5de6  stloc.0
0x5de7  ldloc.0
0x5de8  brfalse  loc_5F3F
0x5ded  ldloc.0
0x5dee  newobj   instance void [mscorlib]System.IO.StreamReader::.ctor(class [mscorlib]System.IO.Stream)
0x5df3  call     class [System.Xml.Linq]System.Xml.Linq.XDocument [System.Xml.Linq]System.Xml.Linq.XDocument::Load(class [mscorlib]System.IO.TextReader)
0x5df8  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XDocument::get_Root()
0x5dfd  stloc.1
0x5dfe  ldloc.1
0x5dff  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XElement::get_Name()
0x5e04  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XName::get_LocalName()
0x5e09  ldstr    aProperties// "Properties"
0x5e0e  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5e13  brtrue.s loc_5E2C
0x5e15  ldloc.1
0x5e16  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XNamespace [System.Xml.Linq]System.Xml.Linq.XElement::GetDefaultNamespace()
0x5e1b  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNamespace::get_NamespaceName()
0x5e20  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sqlserver/"...
0x5e25  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5e2a  brfalse.s loc_5E38
0x5e2c  ldarg.0
0x5e2d  ldc.i4.0
0x5e2e  call     T0x2B000001
0x5e33  callvirt instance void Microsoft.Reporting.Packaging.Internal.ReportArchiveBase::HandleApplicationPropertiesError(valuetype ApplicationPropertiesError error, string[] items)
0x5e38  ldstr    aHttpSchemasOpe// "http://schemas.openxmlformats.org/marku"...
0x5e3d  call     class [System.Xml.Linq]System.Xml.Linq.XNamespace [System.Xml.Linq]System.Xml.Linq.XNamespace::op_Implicit(string)
0x5e42  stloc.2
0x5e43  ldloc.1
0x5e44  ldloc.2
0x5e45  ldstr    aMustunderstand// "MustUnderstand"
0x5e4a  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XNamespace::op_Addition(class [System.Xml.Linq]System.Xml.Linq.XNamespace, string)
0x5e4f  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x5e54  stloc.3
0x5e55  ldloc.3
0x5e56  brfalse  loc_5F3F
0x5e5b  ldloc.3
0x5e5c  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x5e61  ldsfld   string [mscorlib]System.String::Empty
0x5e66  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5e6b  brfalse  loc_5F3F
0x5e70  ldloc.3
0x5e71  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x5e76  ldc.i4.1
0x5e77  newarr   [mscorlib]System.Char
0x5e7c  dup
0x5e7d  ldc.i4.0
0x5e7e  ldc.i4.s 0x20
0x5e80  stelem.i2
0x5e81  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x5e86  stloc.s  4
0x5e88  ldloc.s  4
0x5e8a  ldlen
0x5e8b  brfalse  loc_5F3F
0x5e90  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5e95  stloc.s  5
0x5e97  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x5e9c  stloc.s  6
0x5e9e  ldloc.s  4
0x5ea0  stloc.s  7
0x5ea2  ldc.i4.0
0x5ea3  stloc.s  8
0x5ea5  br.s     loc_5EF5
0x5ea7  ldloc.s  7
0x5ea9  ldloc.s  8
0x5eab  ldelem.ref
0x5eac  stloc.s  9
0x5eae  ldloc.1
0x5eaf  ldloc.s  9
0x5eb1  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XNamespace [System.Xml.Linq]System.Xml.Linq.XElement::GetNamespaceOfPrefix(string)
0x5eb6  stloc.s  0xA
0x5eb8  ldloc.s  0xA
0x5eba  ldnull
0x5ebb  call     bool [System.Xml.Linq]System.Xml.Linq.XNamespace::op_Equality(class [System.Xml.Linq]System.Xml.Linq.XNamespace, class [System.Xml.Linq]System.Xml.Linq.XNamespace)
0x5ec0  brfalse.s loc_5ECD
0x5ec2  ldloc.s  5
0x5ec4  ldloc.s  9
0x5ec6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5ecb  br.s     loc_5EEF
0x5ecd  ldarg.0
0x5ece  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Reporting.Packaging.Internal.ReportArchiveBase::m_mustUnderstandNamespaces
0x5ed3  ldloc.s  0xA
0x5ed5  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNamespace::get_NamespaceName()
0x5eda  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::ContainsKey(var<u1>)
0x5edf  brtrue.s loc_5EEF
0x5ee1  ldloc.s  6
0x5ee3  ldloc.s  0xA
0x5ee5  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XNamespace::get_NamespaceName()
0x5eea  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x5eef  ldloc.s  8
0x5ef1  ldc.i4.1
0x5ef2  add
0x5ef3  stloc.s  8
0x5ef5  ldloc.s  8
0x5ef7  ldloc.s  7
0x5ef9  ldlen
0x5efa  conv.i4
0x5efb  blt.s    loc_5EA7
0x5efd  ldloc.s  5
0x5eff  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x5f04  ldc.i4.0
0x5f05  ble.s    loc_5F1E
0x5f07  ldarg.0
0x5f08  ldc.i4.1
0x5f09  ldc.i4.1
0x5f0a  newarr   [mscorlib]System.String
0x5f0f  dup
0x5f10  ldc.i4.0
0x5f11  ldloc.s  5
0x5f13  call     string Microsoft.Reporting.Packaging.Internal.ReportArchiveBase::ConvertToString(class [mscorlib]System.Collections.Generic.List`1<string> items)
0x5f18  stelem.ref
0x5f19  callvirt instance void Microsoft.Reporting.Packaging.Internal.ReportArchiveBase::HandleApplicationPropertiesError(valuetype ApplicationPropertiesError error, string[] items)
0x5f1e  ldloc.s  6
0x5f20  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x5f25  ldc.i4.0
0x5f26  ble.s    loc_5F3F
0x5f28  ldarg.0
0x5f29  ldc.i4.2
0x5f2a  ldc.i4.1
0x5f2b  newarr   [mscorlib]System.String
0x5f30  dup
0x5f31  ldc.i4.0
0x5f32  ldloc.s  6
0x5f34  call     string Microsoft.Reporting.Packaging.Internal.ReportArchiveBase::ConvertToString(class [mscorlib]System.Collections.Generic.List`1<string> items)
0x5f39  stelem.ref
0x5f3a  callvirt instance void Microsoft.Reporting.Packaging.Internal.ReportArchiveBase::HandleApplicationPropertiesError(valuetype ApplicationPropertiesError error, string[] items)
0x5f3f  leave.s  loc_5F4B
0x5f41  ldloc.0
0x5f42  brfalse.s loc_5F4A
0x5f44  ldloc.0
0x5f45  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5f4a  endfinally
0x5f4b  ret
```
