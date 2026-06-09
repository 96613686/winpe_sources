# System.Xml.Serialization.SoapReflectionImporter::SetArrayMappingType

- ea: `0x6f550`
- end: `0x6f6da`
- name: `System.Xml.Serialization.SoapReflectionImporter::SetArrayMappingType`
- size: `394`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, broker_com_uri`

## callers

- `0x6f420`

## callees

- `0x622f0`
- `0x65420`
- `0x68600`
- `0x68c10`
- `0x68c20`
- `0x68c30`
- `0x68c40`
- `0x68c50`
- `0x68dc0`
- `0x69850`
- `0x6b100`
- `0x6f550`
- `0x72b50`
- `0x72b90`
- `0x72be0`
- `0x72e50`
- `0xd6af0`

## string_xrefs

- `0x6f5a6`: `http://www.w3.org/2001/XMLSchema`
- `0x6f5d6`: `http://www.w3.org/2001/XMLSchema`
- `0x6f59f`: `http://microsoft.com/wsdl/types/`
- `0x6f60e`: `XmlInvalidSoapArray`

## pseudocode

```c

```

## disassembly

```asm
0x6f550  ldc.i4.0
0x6f551  stloc.0
0x6f552  ldarg.1
0x6f553  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.ArrayMapping::get_Elements()
0x6f558  ldlen
0x6f559  conv.i4
0x6f55a  ldc.i4.1
0x6f55b  bne.un.s loc_6F56D
0x6f55d  ldarg.1
0x6f55e  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.ArrayMapping::get_Elements()
0x6f563  ldc.i4.0
0x6f564  ldelem.ref
0x6f565  callvirt instance class System.Xml.Serialization.TypeMapping System.Xml.Serialization.Accessor::get_Mapping()
0x6f56a  stloc.3
0x6f56b  br.s     loc_6F56F
0x6f56d  ldnull
0x6f56e  stloc.3
0x6f56f  ldloc.3
0x6f570  isinst   System.Xml.Serialization.EnumMapping
0x6f575  brfalse.s loc_6F58A
0x6f577  ldloc.3
0x6f578  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x6f57d  stloc.2
0x6f57e  ldloc.3
0x6f57f  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x6f584  stloc.1
0x6f585  br       loc_6F632
0x6f58a  ldloc.3
0x6f58b  isinst   System.Xml.Serialization.PrimitiveMapping
0x6f590  brfalse.s loc_6F5C1
0x6f592  ldloc.3
0x6f593  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x6f598  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsXsdType()
0x6f59d  brtrue.s loc_6F5A6
0x6f59f  ldstr    aHttpMicrosoftC// "http://microsoft.com/wsdl/types/"
0x6f5a4  br.s     loc_6F5AB
0x6f5a6  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x6f5ab  stloc.2
0x6f5ac  ldloc.3
0x6f5ad  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x6f5b2  callvirt instance class System.Xml.Schema.XmlSchemaType System.Xml.Serialization.TypeDesc::get_DataType()
0x6f5b7  callvirt instance string System.Xml.Schema.XmlSchemaType::get_Name()
0x6f5bc  stloc.1
0x6f5bd  ldc.i4.1
0x6f5be  stloc.0
0x6f5bf  br.s     loc_6F632
0x6f5c1  ldloc.3
0x6f5c2  isinst   System.Xml.Serialization.StructMapping
0x6f5c7  brfalse.s loc_6F5F6
0x6f5c9  ldloc.3
0x6f5ca  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x6f5cf  callvirt instance bool System.Xml.Serialization.TypeDesc::get_IsRoot()
0x6f5d4  brfalse.s loc_6F5E6
0x6f5d6  ldstr    aHttpWwwW3Org20_0// "http://www.w3.org/2001/XMLSchema"
0x6f5db  stloc.2
0x6f5dc  ldstr    aAnytype// "anyType"
0x6f5e1  stloc.1
0x6f5e2  ldc.i4.1
0x6f5e3  stloc.0
0x6f5e4  br.s     loc_6F632
0x6f5e6  ldloc.3
0x6f5e7  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x6f5ec  stloc.2
0x6f5ed  ldloc.3
0x6f5ee  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x6f5f3  stloc.1
0x6f5f4  br.s     loc_6F632
0x6f5f6  ldloc.3
0x6f5f7  isinst   System.Xml.Serialization.ArrayMapping
0x6f5fc  brfalse.s loc_6F60E
0x6f5fe  ldloc.3
0x6f5ff  callvirt instance string System.Xml.Serialization.TypeMapping::get_Namespace()
0x6f604  stloc.2
0x6f605  ldloc.3
0x6f606  callvirt instance string System.Xml.Serialization.TypeMapping::get_TypeName()
0x6f60b  stloc.1
0x6f60c  br.s     loc_6F632
0x6f60e  ldstr    aXmlinvalidsoap// "XmlInvalidSoapArray"
0x6f613  ldc.i4.1
0x6f614  newarr   [mscorlib]System.Object
0x6f619  dup
0x6f61a  ldc.i4.0
0x6f61b  ldarg.1
0x6f61c  callvirt instance class System.Xml.Serialization.TypeDesc System.Xml.Serialization.TypeMapping::get_TypeDesc()
0x6f621  callvirt instance string System.Xml.Serialization.TypeDesc::get_FullName()
0x6f626  stelem.ref
0x6f627  call     string System.Xml.Res::GetString(string name, object[] args)
0x6f62c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x6f631  throw
0x6f632  ldloc.1
0x6f633  call     string System.Xml.Serialization.CodeIdentifier::MakePascal(string identifier)
0x6f638  stloc.1
0x6f639  ldstr    aArrayof// "ArrayOf"
0x6f63e  ldloc.1
0x6f63f  call     string [mscorlib]System.String::Concat(string, string)
0x6f644  stloc.s  4
0x6f646  ldloc.0
0x6f647  brtrue.s loc_6F64C
0x6f649  ldloc.2
0x6f64a  br.s     loc_6F652
0x6f64c  ldarg.0
0x6f64d  ldfld    string System.Xml.Serialization.SoapReflectionImporter::defaultNs
0x6f652  stloc.s  5
0x6f654  ldc.i4.1
0x6f655  stloc.s  6
0x6f657  ldarg.0
0x6f658  ldfld    class System.Xml.Serialization.NameTable System.Xml.Serialization.SoapReflectionImporter::types
0x6f65d  ldloc.s  4
0x6f65f  ldloc.s  5
0x6f661  callvirt instance object System.Xml.Serialization.NameTable::get_Item(string name, string ns)
0x6f666  castclass System.Xml.Serialization.TypeMapping
0x6f66b  stloc.s  7
0x6f66d  br.s     loc_6F6C5
0x6f66f  ldloc.s  7
0x6f671  isinst   System.Xml.Serialization.ArrayMapping
0x6f676  brfalse.s loc_6F695
0x6f678  ldloc.s  7
0x6f67a  castclass System.Xml.Serialization.ArrayMapping
0x6f67f  stloc.s  8
0x6f681  ldloc.s  8
0x6f683  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.ArrayMapping::get_Elements()
0x6f688  ldarg.1
0x6f689  callvirt instance class System.Xml.Serialization.ElementAccessor[] System.Xml.Serialization.ArrayMapping::get_Elements()
0x6f68e  call     bool System.Xml.Serialization.AccessorMapping::ElementsMatch(class System.Xml.Serialization.ElementAccessor[] a, class System.Xml.Serialization.ElementAccessor[] b)
0x6f693  brtrue.s loc_6F6C9
0x6f695  ldloc.1
0x6f696  ldloca.s 6
0x6f698  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x6f69d  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x6f6a2  call     string [mscorlib]System.String::Concat(string, string)
0x6f6a7  stloc.s  4
0x6f6a9  ldarg.0
0x6f6aa  ldfld    class System.Xml.Serialization.NameTable System.Xml.Serialization.SoapReflectionImporter::types
0x6f6af  ldloc.s  4
0x6f6b1  ldloc.s  5
0x6f6b3  callvirt instance object System.Xml.Serialization.NameTable::get_Item(string name, string ns)
0x6f6b8  castclass System.Xml.Serialization.TypeMapping
0x6f6bd  stloc.s  7
0x6f6bf  ldloc.s  6
0x6f6c1  ldc.i4.1
0x6f6c2  add
0x6f6c3  stloc.s  6
0x6f6c5  ldloc.s  7
0x6f6c7  brtrue.s loc_6F66F
0x6f6c9  ldarg.1
0x6f6ca  ldloc.s  5
0x6f6cc  callvirt instance void System.Xml.Serialization.TypeMapping::set_Namespace(string value)
0x6f6d1  ldarg.1
0x6f6d2  ldloc.s  4
0x6f6d4  callvirt instance void System.Xml.Serialization.TypeMapping::set_TypeName(string value)
0x6f6d9  ret
```
