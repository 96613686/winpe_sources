# System.Windows.Markup.BamlReader::GetTemplateBindingExtensionValueString

- ea: `0x8e3a0`
- end: `0x8e4aa`
- name: `System.Windows.Markup.BamlReader::GetTemplateBindingExtensionValueString`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x8e6c0`

## callees

- `0x38c40`
- `0x8a810`
- `0x8aa90`
- `0x8e3a0`
- `0x8e810`
- `0x8e9f0`
- `0x99580`
- `0x998d0`
- `0x99910`
- `0x9e500`
- `0xb4030`

## string_xrefs

- `0x8e3d0`: `BamlBadExtensionValue`
- `0x8e3fb`: `http://schemas.microsoft.com/winfx/2006/xaml/presentation`

## pseudocode

```c

```

## disassembly

```asm
0x8e3a0  ldsfld   string [mscorlib]System.String::Empty
0x8e3a5  stloc.0
0x8e3a6  ldnull
0x8e3a7  stloc.1
0x8e3a8  ldnull
0x8e3a9  stloc.2
0x8e3aa  ldnull
0x8e3ab  stloc.3
0x8e3ac  ldarg.1
0x8e3ad  ldc.i4.0
0x8e3ae  bge.s    loc_8E41C
0x8e3b0  ldarg.1
0x8e3b1  neg
0x8e3b2  conv.i2
0x8e3b3  starg.s  1
0x8e3b5  ldnull
0x8e3b6  stloc.s  4
0x8e3b8  ldarg.1
0x8e3b9  ldc.i4   0x89
0x8e3be  bge.s    loc_8E3CC
0x8e3c0  ldarg.1
0x8e3c1  stloc.s  6
0x8e3c3  ldloc.s  6
0x8e3c5  call     class [WindowsBase]System.Windows.DependencyProperty System.Windows.Markup.KnownTypes::GetKnownDependencyPropertyFromId(valuetype System.Windows.Markup.KnownProperties knownProperty)
0x8e3ca  stloc.s  4
0x8e3cc  ldloc.s  4
0x8e3ce  brtrue.s loc_8E3E0
0x8e3d0  ldstr    aBamlbadextensi// "BamlBadExtensionValue"
0x8e3d5  call     string System.Windows.SR::Get(string id)
0x8e3da  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x8e3df  throw
0x8e3e0  ldloc.s  4
0x8e3e2  callvirt instance class [mscorlib]System.Type [WindowsBase]System.Windows.DependencyProperty::get_OwnerType()
0x8e3e7  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x8e3ec  stloc.2
0x8e3ed  ldloc.s  4
0x8e3ef  callvirt instance string [WindowsBase]System.Windows.DependencyProperty::get_Name()
0x8e3f4  stloc.3
0x8e3f5  ldarg.0
0x8e3f6  ldfld    class System.Windows.Markup.XmlnsDictionary System.Windows.Markup.BamlReader::_prefixDictionary
0x8e3fb  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/winfx/2006"...
0x8e400  callvirt instance string System.Windows.Markup.XmlnsDictionary::get_Item(string prefix)
0x8e405  stloc.s  5
0x8e407  ldloc.s  5
0x8e409  brfalse.s loc_8E414
0x8e40b  ldloc.s  5
0x8e40d  castclass [mscorlib]System.String
0x8e412  br.s     loc_8E419
0x8e414  ldsfld   string [mscorlib]System.String::Empty
0x8e419  stloc.1
0x8e41a  br.s     loc_8E471
0x8e41c  ldarg.0
0x8e41d  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlReader::get_MapTable()
0x8e422  ldarg.1
0x8e423  callvirt instance class System.Windows.Markup.BamlAttributeInfoRecord System.Windows.Markup.BamlMapTable::GetAttributeInfoFromId(int16 id)
0x8e428  stloc.s  7
0x8e42a  ldarg.0
0x8e42b  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlReader::get_MapTable()
0x8e430  ldloc.s  7
0x8e432  callvirt instance int16 System.Windows.Markup.BamlAttributeInfoRecord::get_OwnerTypeId()
0x8e437  callvirt instance class System.Windows.Markup.BamlTypeInfoRecord System.Windows.Markup.BamlMapTable::GetTypeInfoFromId(int16 id)
0x8e43c  stloc.s  8
0x8e43e  ldarg.0
0x8e43f  ldloc.s  8
0x8e441  ldloca.s 0xA
0x8e443  ldloca.s 1
0x8e445  ldloca.s 9
0x8e447  call     instance void System.Windows.Markup.BamlReader::GetAssemblyAndPrefixAndXmlns(class System.Windows.Markup.BamlTypeInfoRecord typeInfo, [out] string& assemblyFullName, [out] string& prefix, [out] string& xmlns)
0x8e44c  ldloc.s  8
0x8e44e  callvirt instance string System.Windows.Markup.BamlTypeInfoRecord::get_TypeFullName()
0x8e453  stloc.2
0x8e454  ldloc.2
0x8e455  ldloc.2
0x8e456  ldstr    asc_28A756// "."
0x8e45b  ldc.i4.4
0x8e45c  callvirt instance int32 [mscorlib]System.String::LastIndexOf(string, valuetype [mscorlib]System.StringComparison)
0x8e461  ldc.i4.1
0x8e462  add
0x8e463  callvirt instance string [mscorlib]System.String::Substring(int32)
0x8e468  stloc.2
0x8e469  ldloc.s  7
0x8e46b  callvirt instance string System.Windows.Markup.BamlAttributeInfoRecord::get_Name()
0x8e470  stloc.3
0x8e471  ldloc.1
0x8e472  ldsfld   string [mscorlib]System.String::Empty
0x8e477  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8e47c  brfalse.s loc_8E488
0x8e47e  ldloc.0
0x8e47f  ldloc.2
0x8e480  call     string [mscorlib]System.String::Concat(string, string)
0x8e485  stloc.0
0x8e486  br.s     loc_8E496
0x8e488  ldloc.0
0x8e489  ldloc.1
0x8e48a  ldstr    asc_291A4E// ":"
0x8e48f  ldloc.2
0x8e490  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x8e495  stloc.0
0x8e496  ldloc.0
0x8e497  ldstr    asc_28A756// "."
0x8e49c  ldloc.3
0x8e49d  ldstr    asc_29CBC0// "}"
0x8e4a2  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x8e4a7  stloc.0
0x8e4a8  ldloc.0
0x8e4a9  ret
```
