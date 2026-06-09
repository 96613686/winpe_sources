# System.Xml.Serialization.CodeExporter::.ctor

- ea: `0x624a0`
- end: `0x62529`
- name: `System.Xml.Serialization.CodeExporter::.ctor`
- size: `137`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `registry_config, loader_planting`

## callers

- `0x6df80`
- `0x6df90`
- `0x6dfa0`
- `0x6dfb0`
- `0x6dfc0`
- `0x75d60`
- `0x75d70`
- `0x75d80`
- `0x75d90`
- `0x75da0`

## callees

- `0x624a0`
- `0x63030`

## string_xrefs

- `0x624ca`: `System.dll`
- `0x624dc`: `System.dll`
- `0x624ed`: `System.Xml.dll`
- `0x624ff`: `System.Xml.dll`

## pseudocode

```c

```

## disassembly

```asm
0x624a0  ldarg.0
0x624a1  newobj   instance void [System]System.CodeDom.CodeAttributeDeclarationCollection::.ctor()
0x624a6  stfld    class [System]System.CodeDom.CodeAttributeDeclarationCollection System.Xml.Serialization.CodeExporter::includeMetadata
0x624ab  ldarg.0
0x624ac  call     instance void [mscorlib]System.Object::.ctor()
0x624b1  ldarg.1
0x624b2  brfalse.s loc_624BA
0x624b4  ldarg.1
0x624b5  call     void System.Xml.Serialization.CodeGenerator::ValidateIdentifiers(class [System]System.CodeDom.CodeObject e)
0x624ba  ldarg.0
0x624bb  ldarg.1
0x624bc  stfld    class [System]System.CodeDom.CodeNamespace System.Xml.Serialization.CodeExporter::codeNamespace
0x624c1  ldarg.2
0x624c2  brfalse.s loc_6250A
0x624c4  ldarg.2
0x624c5  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.CodeCompileUnit::get_ReferencedAssemblies()
0x624ca  ldstr    aSystemDll// "System.dll"
0x624cf  callvirt instance bool [System]System.Collections.Specialized.StringCollection::Contains(string)
0x624d4  brtrue.s loc_624E7
0x624d6  ldarg.2
0x624d7  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.CodeCompileUnit::get_ReferencedAssemblies()
0x624dc  ldstr    aSystemDll// "System.dll"
0x624e1  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x624e6  pop
0x624e7  ldarg.2
0x624e8  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.CodeCompileUnit::get_ReferencedAssemblies()
0x624ed  ldstr    aSystemXmlDll// "System.Xml.dll"
0x624f2  callvirt instance bool [System]System.Collections.Specialized.StringCollection::Contains(string)
0x624f7  brtrue.s loc_6250A
0x624f9  ldarg.2
0x624fa  callvirt instance class [System]System.Collections.Specialized.StringCollection [System]System.CodeDom.CodeCompileUnit::get_ReferencedAssemblies()
0x624ff  ldstr    aSystemXmlDll// "System.Xml.dll"
0x62504  callvirt instance int32 [System]System.Collections.Specialized.StringCollection::Add(string)
0x62509  pop
0x6250a  ldarg.0
0x6250b  ldarg.2
0x6250c  stfld    class [System]System.CodeDom.CodeCompileUnit System.Xml.Serialization.CodeExporter::codeCompileUnit
0x62511  ldarg.0
0x62512  ldarg.s  4
0x62514  stfld    valuetype System.Xml.Serialization.CodeGenerationOptions System.Xml.Serialization.CodeExporter::options
0x62519  ldarg.0
0x6251a  ldarg.s  5
0x6251c  stfld    class [mscorlib]System.Collections.Hashtable System.Xml.Serialization.CodeExporter::exportedMappings
0x62521  ldarg.0
0x62522  ldarg.3
0x62523  stfld    class [System]System.CodeDom.Compiler.CodeDomProvider System.Xml.Serialization.CodeExporter::codeProvider
0x62528  ret
```
