# System.Windows.Markup.BamlReader::GetStaticExtensionValueString

- ea: `0x8e4b0`
- end: `0x8e60e`
- name: `System.Windows.Markup.BamlReader::GetStaticExtensionValueString`
- size: `350`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x8e670`
- `0x8e6c0`

## callees

- `0x29370`
- `0x38c40`
- `0x8a810`
- `0x8aa90`
- `0x8e4b0`
- `0x8e810`
- `0x8e9f0`
- `0x99580`
- `0x998d0`
- `0x99910`
- `0xb4030`
- `0xb47d0`
- `0xb4860`
- `0xb4910`

## string_xrefs

- `0x8e4c2`: `http://schemas.microsoft.com/winfx/2006/xaml`
- `0x8e549`: `BamlBadExtensionValue`
- `0x8e55f`: `http://schemas.microsoft.com/winfx/2006/xaml/presentation`

## pseudocode

```c

```

## disassembly

```asm
0x8e4b0  ldsfld   string [mscorlib]System.String::Empty
0x8e4b5  stloc.0
0x8e4b6  ldnull
0x8e4b7  stloc.1
0x8e4b8  ldnull
0x8e4b9  stloc.2
0x8e4ba  ldnull
0x8e4bb  stloc.3
0x8e4bc  ldarg.0
0x8e4bd  ldfld    class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.BamlReader::_prefixDictionary
0x8e4c2  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x8e4c7  callvirt instance string System.Windows.Markup.XmlnsDictionary::get_Item(string prefix)
0x8e4cc  stloc.s  4
0x8e4ce  ldloc.s  4
0x8e4d0  ldsfld   string [mscorlib]System.String::Empty
0x8e4d5  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x8e4da  brfalse.s loc_8E4F0
0x8e4dc  ldstr    asc_29CBA0// "{"
0x8e4e1  ldloc.s  4
0x8e4e3  ldstr    aStatic// ":Static "
0x8e4e8  call     string [mscorlib]System.String::Concat(string, string, string)
0x8e4ed  stloc.0
0x8e4ee  br.s     loc_8E4F6
0x8e4f0  ldstr    aStatic_0// "{Static "
0x8e4f5  stloc.0
0x8e4f6  ldarg.1
0x8e4f7  ldc.i4.0
0x8e4f8  bge      loc_8E580
0x8e4fd  ldarg.1
0x8e4fe  neg
0x8e4ff  conv.i2
0x8e500  starg.s  1
0x8e502  ldc.i4.1
0x8e503  stloc.s  5
0x8e505  ldarg.1
0x8e506  ldloca.s 5
0x8e508  call     int16 System.Windows.SystemResourceKey::GetSystemResourceKeyIdFromBamlId(int16 bamlId, [out] bool& isKey)
0x8e50d  starg.s  1
0x8e50f  ldtoken  System.Windows.SystemResourceKeyID
0x8e514  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x8e519  ldarg.1
0x8e51a  box      [mscorlib]System.Int32
0x8e51f  call     bool [mscorlib]System.Enum::IsDefined(class [mscorlib]System.Type, object)
0x8e524  brfalse.s loc_8E549
0x8e526  ldarg.1
0x8e527  stloc.s  7
0x8e529  ldloc.s  7
0x8e52b  call     string System.Windows.Markup.SystemKeyConverter::GetSystemClassName(valuetype System.Windows.SystemResourceKeyID id)
0x8e530  stloc.2
0x8e531  ldloc.s  5
0x8e533  brfalse.s loc_8E53F
0x8e535  ldloc.s  7
0x8e537  call     string System.Windows.Markup.SystemKeyConverter::GetSystemKeyName(valuetype System.Windows.SystemResourceKeyID id)
0x8e53c  stloc.3
0x8e53d  br.s     loc_8E559
0x8e53f  ldloc.s  7
0x8e541  call     string System.Windows.Markup.SystemKeyConverter::GetSystemPropertyName(valuetype System.Windows.SystemResourceKeyID id)
0x8e546  stloc.3
0x8e547  br.s     loc_8E559
0x8e549  ldstr    aBamlbadextensi// "BamlBadExtensionValue"
0x8e54e  call     string System.Windows.SR::Get(string id)
0x8e553  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8e558  throw
0x8e559  ldarg.0
0x8e55a  ldfld    class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.BamlReader::_prefixDictionary
0x8e55f  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/winfx/2006"...
0x8e564  callvirt instance string System.Windows.Markup.XmlnsDictionary::get_Item(string prefix)
0x8e569  stloc.s  6
0x8e56b  ldloc.s  6
0x8e56d  brfalse.s loc_8E578
0x8e56f  ldloc.s  6
0x8e571  castclass [mscorlib]System.String
0x8e576  br.s     loc_8E57D
0x8e578  ldsfld   string [mscorlib]System.String::Empty
0x8e57d  stloc.1
0x8e57e  br.s     loc_8E5D5
0x8e580  ldarg.0
0x8e581  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlReader::get_MapTable()
0x8e586  ldarg.1
0x8e587  callvirt instance class System.Windows.Markup.BamlAttributeInfoRecord System.Windows.Markup.BamlMapTable::GetAttributeInfoFromId(int16 id)
0x8e58c  stloc.s  8
0x8e58e  ldarg.0
0x8e58f  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlReader::get_MapTable()
0x8e594  ldloc.s  8
0x8e596  callvirt instance int16 System.Windows.Markup.BamlAttributeInfoRecord::get_OwnerTypeId()
0x8e59b  callvirt instance class System.Windows.Markup.BamlTypeInfoRecord System.Windows.Markup.BamlMapTable::GetTypeInfoFromId(int16 id)
0x8e5a0  stloc.s  9
0x8e5a2  ldarg.0
0x8e5a3  ldloc.s  9
0x8e5a5  ldloca.s 0xB
0x8e5a7  ldloca.s 1
0x8e5a9  ldloca.s 0xA
0x8e5ab  call     instance void System.Windows.Markup.BamlReader::GetAssemblyAndPrefixAndXmlns(class System.Windows.Markup.BamlTypeInfoRecord typeInfo, [out] string& assemblyFullName, [out] string& prefix, [out] string& xmlns)
0x8e5b0  ldloc.s  9
0x8e5b2  callvirt instance string System.Windows.Markup.BamlTypeInfoRecord::get_TypeFullName()
0x8e5b7  stloc.2
0x8e5b8  ldloc.2
0x8e5b9  ldloc.2
0x8e5ba  ldstr    asc_28A756// "."
0x8e5bf  ldc.i4.4
0x8e5c0  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x8e5c5  ldc.i4.1
0x8e5c6  add
0x8e5c7  callvirt instance string [mscorlib]System.String::Substring(int32)
0x8e5cc  stloc.2
0x8e5cd  ldloc.s  8
0x8e5cf  callvirt instance string System.Windows.Markup.BamlAttributeInfoRecord::get_Name()
0x8e5d4  stloc.3
0x8e5d5  ldloc.1
0x8e5d6  ldsfld   string [mscorlib]System.String::Empty
0x8e5db  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8e5e0  brfalse.s loc_8E5EC
0x8e5e2  ldloc.0
0x8e5e3  ldloc.2
0x8e5e4  call     string [mscorlib]System.String::Concat(string, string)
0x8e5e9  stloc.0
0x8e5ea  br.s     loc_8E5FA
0x8e5ec  ldloc.0
0x8e5ed  ldloc.1
0x8e5ee  ldstr    asc_291A4E// ":"
0x8e5f3  ldloc.2
0x8e5f4  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x8e5f9  stloc.0
0x8e5fa  ldloc.0
0x8e5fb  ldstr    asc_28A756// "."
0x8e600  ldloc.3
0x8e601  ldstr    asc_29CBC0// "}"
0x8e606  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x8e60b  stloc.0
0x8e60c  ldloc.0
0x8e60d  ret
```
