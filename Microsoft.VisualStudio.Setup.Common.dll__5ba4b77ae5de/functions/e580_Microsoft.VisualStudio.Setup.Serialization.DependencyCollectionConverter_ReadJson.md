# Microsoft.VisualStudio.Setup.Serialization.DependencyCollectionConverter::ReadJson

- ea: `0xe580`
- end: `0xe5ce`
- name: `Microsoft.VisualStudio.Setup.Serialization.DependencyCollectionConverter::ReadJson`
- size: `78`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x4640`
- `0xc1a0`
- `0xe580`
- `0xe680`

## string_xrefs

- `0xe581`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0xe580  ldarg.1
0xe581  ldstr    aReader// "reader"
0xe586  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xe58b  ldarg.s  4
0xe58d  ldstr    aSerializer// "serializer"
0xe592  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0xe597  ldarg.1
0xe598  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xe59d  ldc.i4.s 0xB
0xe59f  bne.un.s loc_E5A3
0xe5a1  ldnull
0xe5a2  ret
0xe5a3  ldarg.1
0xe5a4  callvirt instance valuetype [Newtonsoft.Json]Newtonsoft.Json.JsonToken [Newtonsoft.Json]Newtonsoft.Json.JsonReader::get_TokenType()
0xe5a9  ldc.i4.1
0xe5aa  bne.un.s loc_E5C8
0xe5ac  ldarg.3
0xe5ad  isinst   Microsoft.VisualStudio.Setup.DependencyCollection
0xe5b2  dup
0xe5b3  brtrue.s loc_E5BB
0xe5b5  pop
0xe5b6  newobj   instance void Microsoft.VisualStudio.Setup.DependencyCollection::.ctor()
0xe5bb  stloc.0
0xe5bc  ldarg.0
0xe5bd  ldarg.1
0xe5be  ldarg.s  4
0xe5c0  ldloc.0
0xe5c1  call     instance void Microsoft.VisualStudio.Setup.Serialization.DependencyCollectionConverter::PopulateDependencies(class [Newtonsoft.Json]Newtonsoft.Json.JsonReader reader, class [Newtonsoft.Json]Newtonsoft.Json.JsonSerializer serializer, class Microsoft.VisualStudio.Setup.DependencyCollection collection)
0xe5c6  ldloc.0
0xe5c7  ret
0xe5c8  newobj   instance void [mscorlib]System.NotSupportedException::.ctor()
0xe5cd  throw
```
