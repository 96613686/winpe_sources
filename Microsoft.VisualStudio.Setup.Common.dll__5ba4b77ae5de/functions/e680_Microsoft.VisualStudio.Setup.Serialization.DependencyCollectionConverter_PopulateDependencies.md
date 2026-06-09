# Microsoft.VisualStudio.Setup.Serialization.DependencyCollectionConverter::PopulateDependencies

- ea: `0xe680`
- end: `0xe755`
- name: `Microsoft.VisualStudio.Setup.Serialization.DependencyCollectionConverter::PopulateDependencies`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callers

- `0xe580`

## callees

- `0x4160`
- `0x4170`
- `0x43d0`
- `0xe680`
- `0xe760`

## string_xrefs

- `0xe6b5`: `Unexpected read failure while deserializing a dependency in DependencyCollection`
- `0xe70e`: `Unexpected token type {0} reached while reading dependencies in {1}`
- `0xe739`: `No {0} reached while reading {1}`

## pseudocode

```c

```

## disassembly

```asm
0xe680  br       loc_E72E
0xe685  ldarg.1
0xe686  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xe68b  ldc.i4.4
0xe68c  bne.un.s loc_E703
0xe68e  ldarg.1
0xe68f  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_Value()
0xe694  brtrue.s loc_E6A1
0xe696  ldstr    aPropertyNameIs// "Property name is null"
0xe69b  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonException::.ctor(string)
0xe6a0  throw
0xe6a1  ldarg.1
0xe6a2  callvirt instance object [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_Value()
0xe6a7  castclass [mscorlib]System.String
0xe6ac  stloc.0
0xe6ad  ldarg.1
0xe6ae  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xe6b3  brtrue.s loc_E6C0
0xe6b5  ldstr    aUnexpectedRead// "Unexpected read failure while deseriali"...
0xe6ba  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonException::.ctor(string)
0xe6bf  throw
0xe6c0  ldarg.2
0xe6c1  ldarg.1
0xe6c2  callvirt T0x2B00006C
0xe6c7  stloc.1
0xe6c8  ldloc.1
0xe6c9  brfalse.s loc_E72E
0xe6cb  ldloc.1
0xe6cc  callvirt instance string Microsoft.VisualStudio.Setup.Dependency::get_Id()
0xe6d1  brtrue.s loc_E6DA
0xe6d3  ldloc.1
0xe6d4  ldloc.0
0xe6d5  callvirt instance void Microsoft.VisualStudio.Setup.Dependency::set_Id(string value)
0xe6da  ldloc.1
0xe6db  callvirt instance string Microsoft.VisualStudio.Setup.Dependency::get_Id()
0xe6e0  ldsfld   string Microsoft.VisualStudio.Setup.Serialization.DependencyCollectionConverter::MinShellId
0xe6e5  ldc.i4.5
0xe6e6  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xe6eb  brfalse.s loc_E6FA
0xe6ed  ldarg.0
0xe6ee  ldloc.1
0xe6ef  ldarg.2
0xe6f0  callvirt instance valuetype [mscorlib]System.Runtime.Serialization.StreamingContext [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer::get_Context()
0xe6f5  call     instance void Microsoft.VisualStudio.Setup.Serialization.DependencyCollectionConverter::HandleMinShellVersioning(class Microsoft.VisualStudio.Setup.Dependency dependency, valuetype [mscorlib]System.Runtime.Serialization.StreamingContext context)
0xe6fa  ldarg.3
0xe6fb  ldloc.1
0xe6fc  callvirt instance void Microsoft.VisualStudio.Setup.DependencyCollection::Add(class Microsoft.VisualStudio.Setup.Dependency item)
0xe701  br.s     loc_E72E
0xe703  ldarg.1
0xe704  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xe709  ldc.i4.s 0xD
0xe70b  bne.un.s loc_E70E
0xe70d  ret
0xe70e  ldstr    aUnexpectedToke// "Unexpected token type {0} reached while"...
0xe713  ldarg.1
0xe714  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xe719  box      [Newtonsoft.Json]Newtonsoft.Json.JsonToken
0xe71e  ldstr    aDependencycoll// "DependencyCollection"
0xe723  call     string [mscorlib]System.String::Format(string, object, object)
0xe728  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonException::.ctor(string)
0xe72d  throw
0xe72e  ldarg.1
0xe72f  callvirt instance bool [Newtonsoft.Json]Newtonsoft.Json.JsonReader::Read()
0xe734  brtrue   loc_E685
0xe739  ldstr    aNo0ReachedWhil// "No {0} reached while reading {1}"
0xe73e  ldc.i4.s 0xD
0xe740  box      [Newtonsoft.Json]Newtonsoft.Json.JsonToken
0xe745  ldstr    aDependencycoll// "DependencyCollection"
0xe74a  call     string [mscorlib]System.String::Format(string, object, object)
0xe74f  newobj   instance void [Newtonsoft.Json]Newtonsoft.Json.JsonException::.ctor(string)
0xe754  throw
```
