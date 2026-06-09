# System.Windows.Markup.BamlReader::GetAssemblyAndPrefixAndXmlns

- ea: `0x8e810`
- end: `0x8e8db`
- name: `System.Windows.Markup.BamlReader::GetAssemblyAndPrefixAndXmlns`
- size: `203`
- prototype: ``
- caller_count: `7`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8cc90`
- `0x8d020`
- `0x8db80`
- `0x8e310`
- `0x8e3a0`
- `0x8e4b0`
- `0x8e760`

## callees

- `0x8afd0`
- `0x8e810`
- `0x8e930`
- `0x8e960`
- `0x8e9b0`
- `0x8e9f0`
- `0x99350`
- `0x99540`
- `0x995b0`
- `0x995d0`
- `0xaaf80`
- `0xad1b0`

## string_xrefs

- `0x8e889`: `http://schemas.microsoft.com/winfx/2006/xaml`

## pseudocode

```c

```

## disassembly

```asm
0x8e810  ldarg.1
0x8e811  callvirt instance int16 System.Windows.Markup.BamlTypeInfoRecord::get_AssemblyId()
0x8e816  ldc.i4.0
0x8e817  bge.s    loc_8E827
0x8e819  ldarg.1
0x8e81a  callvirt instance class [mscorlib]System.Type System.Windows.Markup.BamlTypeInfoRecord::get_Type()
0x8e81f  ldnull
0x8e820  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x8e825  brfalse.s loc_8E843
0x8e827  ldarg.0
0x8e828  call     instance class System.Windows.Markup.BamlMapTable System.Windows.Markup.BamlReader::get_MapTable()
0x8e82d  ldarg.1
0x8e82e  callvirt instance int16 System.Windows.Markup.BamlTypeInfoRecord::get_AssemblyId()
0x8e833  callvirt instance class System.Windows.Markup.BamlAssemblyInfoRecord System.Windows.Markup.BamlMapTable::GetAssemblyInfoFromId(int16 id)
0x8e838  stloc.0
0x8e839  ldarg.2
0x8e83a  ldloc.0
0x8e83b  callvirt instance string System.Windows.Markup.BamlAssemblyInfoRecord::get_AssemblyFullName()
0x8e840  stind.ref
0x8e841  br.s     loc_8E857
0x8e843  ldarg.1
0x8e844  callvirt instance class [mscorlib]System.Type System.Windows.Markup.BamlTypeInfoRecord::get_Type()
0x8e849  callvirt instance class [mscorlib]System.Reflection.Assembly [mscorlib]System.Type::get_Assembly()
0x8e84e  stloc.1
0x8e84f  ldarg.2
0x8e850  ldloc.1
0x8e851  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0x8e856  stind.ref
0x8e857  ldarg.1
0x8e858  callvirt instance string System.Windows.Markup.BamlTypeInfoRecord::get_ClrNamespace()
0x8e85d  ldstr    aSystemWindowsM// "System.Windows.Markup"
0x8e862  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8e867  brfalse.s loc_8E891
0x8e869  ldarg.2
0x8e86a  ldind.ref
0x8e86b  ldstr    aPresentationfr// "PresentationFramework"
0x8e870  ldc.i4.4
0x8e871  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x8e876  brtrue.s loc_8E887
0x8e878  ldarg.2
0x8e879  ldind.ref
0x8e87a  ldstr    aSystemXaml// "System.Xaml"
0x8e87f  ldc.i4.4
0x8e880  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x8e885  brfalse.s loc_8E891
0x8e887  ldarg.s  4
0x8e889  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x8e88e  stind.ref
0x8e88f  br.s     loc_8E8CF
0x8e891  ldarg.s  4
0x8e893  ldarg.0
0x8e894  ldfld    class System.Windows.Markup.ParserContext System.Windows.Markup.BamlReader::_parserContext
0x8e899  callvirt instance class System.Windows.Markup.XamlTypeMapper System.Windows.Markup.ParserContext::get_XamlTypeMapper()
0x8e89e  ldarg.1
0x8e89f  callvirt instance string System.Windows.Markup.BamlTypeInfoRecord::get_ClrNamespace()
0x8e8a4  ldarg.2
0x8e8a5  ldind.ref
0x8e8a6  callvirt instance string System.Windows.Markup.XamlTypeMapper::GetXmlNamespace(string clrNamespaceFullName, string assemblyFullName)
0x8e8ab  stind.ref
0x8e8ac  ldarg.s  4
0x8e8ae  ldind.ref
0x8e8af  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8e8b4  brfalse.s loc_8E8CF
0x8e8b6  ldarg.0
0x8e8b7  ldarg.1
0x8e8b8  callvirt instance string System.Windows.Markup.BamlTypeInfoRecord::get_ClrNamespace()
0x8e8bd  ldarg.2
0x8e8be  ldind.ref
0x8e8bf  call     instance class [mscorlib]System.Collections.Generic.List`1<string> System.Windows.Markup.BamlReader::GetXmlNamespaceList(string clrNamespace, string assemblyFullName)
0x8e8c4  stloc.2
0x8e8c5  ldarg.3
0x8e8c6  ldarg.0
0x8e8c7  ldloc.2
0x8e8c8  call     instance string System.Windows.Markup.BamlReader::GetXmlnsPrefix(class [mscorlib]System.Collections.Generic.List`1<string> xmlnsList)
0x8e8cd  stind.ref
0x8e8ce  ret
0x8e8cf  ldarg.3
0x8e8d0  ldarg.0
0x8e8d1  ldarg.s  4
0x8e8d3  ldind.ref
0x8e8d4  call     instance string System.Windows.Markup.BamlReader::GetXmlnsPrefix(string xmlns)
0x8e8d9  stind.ref
0x8e8da  ret
```
