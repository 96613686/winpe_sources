# System.Windows.Markup.XamlTypeMapper::SetAssemblyPath

- ea: `0xa8d00`
- end: `0xa8dbe`
- name: `System.Windows.Markup.XamlTypeMapper::SetAssemblyPath`
- size: `190`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0xa8d00`
- `0xab250`

## string_xrefs

- `0xa8d11`: `assemblyPath`
- `0xa8d31`: `ParserBadAssemblyPath`

## pseudocode

```c

```

## disassembly

```asm
0xa8d00  ldarg.1
0xa8d01  brtrue.s loc_A8D0E
0xa8d03  ldstr    aAssemblyname// "assemblyName"
0xa8d08  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa8d0d  throw
0xa8d0e  ldarg.2
0xa8d0f  brtrue.s loc_A8D1C
0xa8d11  ldstr    aAssemblypath// "assemblyPath"
0xa8d16  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xa8d1b  throw
0xa8d1c  ldarg.2
0xa8d1d  ldsfld   string [mscorlib]System.String::Empty
0xa8d22  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa8d27  brfalse.s loc_A8D3B
0xa8d29  ldarg.0
0xa8d2a  ldc.i4.0
0xa8d2b  stfld    int32 System.Windows.Markup.XamlTypeMapper::_lineNumber
0xa8d30  ldarg.0
0xa8d31  ldstr    aParserbadassem// "ParserBadAssemblyPath"
0xa8d36  call     instance void System.Windows.Markup.XamlTypeMapper::ThrowException(string id)
0xa8d3b  ldarg.1
0xa8d3c  ldsfld   string [mscorlib]System.String::Empty
0xa8d41  call     bool [mscorlib]System.String::op_Equality(string, string)
0xa8d46  brfalse.s loc_A8D5A
0xa8d48  ldarg.0
0xa8d49  ldc.i4.0
0xa8d4a  stfld    int32 System.Windows.Markup.XamlTypeMapper::_lineNumber
0xa8d4f  ldarg.0
0xa8d50  ldstr    aParserbadassem_0// "ParserBadAssemblyName"
0xa8d55  call     instance void System.Windows.Markup.XamlTypeMapper::ThrowException(string id)
0xa8d5a  ldarg.1
0xa8d5b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa8d60  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0xa8d65  stloc.0
0xa8d66  ldarg.0
0xa8d67  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Windows.Markup.XamlTypeMapper::_assemblyPathTable
0xa8d6c  stloc.2
0xa8d6d  ldc.i4.0
0xa8d6e  stloc.3
0xa8d6f  ldloc.2
0xa8d70  ldloca.s 3
0xa8d72  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xa8d77  ldarg.0
0xa8d78  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Windows.Markup.XamlTypeMapper::_assemblyPathTable
0xa8d7d  ldloc.0
0xa8d7e  ldarg.2
0xa8d7f  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::set_Item(object, object)
0xa8d84  leave.s  loc_A8D90
0xa8d86  ldloc.3
0xa8d87  brfalse.s loc_A8D8F
0xa8d89  ldloc.2
0xa8d8a  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xa8d8f  endfinally
0xa8d90  ldloc.0
0xa8d91  call     class [mscorlib]System.Reflection.Assembly [WindowsBase]System.Windows.Markup.ReflectionHelper::GetAlreadyLoadedAssembly(string)
0xa8d96  stloc.1
0xa8d97  ldloc.1
0xa8d98  ldnull
0xa8d99  call     bool [mscorlib]System.Reflection.Assembly::op_Inequality(class [mscorlib]System.Reflection.Assembly, class [mscorlib]System.Reflection.Assembly)
0xa8d9e  brfalse.s loc_A8DBD
0xa8da0  ldloc.1
0xa8da1  callvirt instance bool [mscorlib]System.Reflection.Assembly::get_GlobalAssemblyCache()
0xa8da6  brtrue.s loc_A8DBD
0xa8da8  ldloc.0
0xa8da9  call     void [WindowsBase]System.Windows.Markup.ReflectionHelper::ResetCacheForAssembly(string)
0xa8dae  ldarg.0
0xa8daf  ldfld    class XamlTypeMapperSchemaContext System.Windows.Markup.XamlTypeMapper::_schemaContext
0xa8db4  brfalse.s loc_A8DBD
0xa8db6  ldarg.0
0xa8db7  ldnull
0xa8db8  stfld    class XamlTypeMapperSchemaContext System.Windows.Markup.XamlTypeMapper::_schemaContext
0xa8dbd  ret
```
